# Component States & Forms

Apple's guidance repeatedly asks for *clear signals about what's happening*: show when controls are available, when they're working, and when something changed. This file turns that into a complete state spec for any component, then applies it to forms, where most state bugs live.

---

## 1. The State Matrix

Every interactive component needs a designed appearance for each state it can reach. Missing states are the most common craft failure.

| State | When | Visual treatment (Apple-style default) | Must also |
| :--- | :--- | :--- | :--- |
| **Default / rest** | Available, not interacted with | Tint for actionable, neutral for content | Look interactive at rest (affordance), not only on hover |
| **Hover** (pointer only) | Pointer over target | Subtle fill or highlight (≈ 4–8% label color overlay), cursor change | Never be the only way to discover something; touch has no hover |
| **Pressed / active** | Finger or button down | Darken/dim ~15–20% or scale to ~0.97; appears on touch-down | Commit on release; sliding off cancels |
| **Focused** (keyboard) | Keyboard/switch focus | Visible ring: 2–3 px, accent color, ≥ 3:1 against adjacent colors, offset 2 px | Use `:focus-visible` so mouse clicks don't show rings; never remove without replacement |
| **Selected / on** | Chosen item, active tab, toggle on | Fill variant of icon, tinted background, or checkmark | Differ from focus and hover; don't rely on color alone |
| **Disabled / unavailable** | Action can't be performed now | ~30–40% opacity or tertiary label color; no hover/press response | Explain why nearby when it isn't obvious; prefer enabling + validating over disabling submit buttons |
| **Loading / in progress** | Action running | Inline spinner in the control, label changes ("Saving…"), control keeps its size | Prevent double-submit; allow cancel for long work |
| **Success** | Action completed | Brief confirmation (checkmark, toast, inline message) | Only when the result isn't already visible |
| **Error / invalid** | Input or action failed | Red/destructive color **plus** icon and text | Say what happened and how to fix it; keep the user's input |
| **Empty** | No content yet | Illustration or symbol + title + one action | Explain what will appear and how to create it |
| **Read-only** | Visible but not editable | Plain text styling, no field chrome | Don't style as disabled — people can still select and copy |
| **Dragging / drop target** | During drag and drop | Lifted item (scale + shadow); target highlights only when it can accept | Show "not allowed" when it can't |

Rules:
- **Every state needs a non-color cue** (shape, icon, text, weight) — the "differentiate without color" rule.
- **States must not shift layout.** Borders, spinners, and error text reserve their space or overlay; the page shouldn't jump.
- **Combine states predictably** (selected + focused, error + focused). Define the combinations, not just the singles.
- **Mirror platform conventions.** On the web use real `button`, `a`, `input`, `select`; set `aria-pressed`, `aria-expanded`, `aria-selected`, `aria-invalid`, `aria-busy`, `disabled` vs `aria-disabled` deliberately.
- **Hover only where hover exists.** Wrap hover styles in `@media (hover: hover) and (pointer: fine)`; otherwise a tap leaves a "stuck" hover on touch screens.
- **Tooltips supplement, never inform alone.** Show them on hover *and* keyboard focus, dismiss with Esc, and keep them open while the pointer moves onto them (WCAG 1.4.13). Use a warm-up delay once, then show neighbors instantly ([Fluid Motion › Restraint](./fluid-motion-and-physics.md#12-restraint-when-not-to-animate)).

```css
.btn { background: var(--action-fill); color: #fff;   /* --action-fill: white label ≥ 4.5:1 */
       transition: background-color 120ms ease-out, transform 120ms ease-out; }
@media (hover: hover) and (pointer: fine) {
  .btn:hover { background: color-mix(in oklab, var(--action-fill) 90%, black); }
}
.btn:active { background: color-mix(in oklab, var(--action-fill) 80%, black); transform: scale(0.97); }
.btn:focus-visible { outline: 3px solid var(--action-tint); outline-offset: 2px; }
.btn[aria-busy="true"] { pointer-events: none; }
.btn:disabled, .btn[aria-disabled="true"] { opacity: 0.4; cursor: not-allowed; }
@media (prefers-reduced-motion: reduce) {
  .btn { transition: background-color 120ms ease-out; }  /* keep the color feedback */
  .btn:active { transform: none; }                     /* drop only the scale */
}
```

---

## 2. Forms

Apple's data-entry principles: **minimize manual input, use the right control, validate inline, make it effortless to fix mistakes.**

### Structure
- **Ask only for what you need, when you need it.** Every field costs completion. Defer optional data until after the first success.
- **One column.** Multi-column forms cause missed fields and wrong reading order; exceptions: tightly related short pairs (city/postcode, first/last name where culturally appropriate).
- **Group related fields** with a short heading; long forms become steps with a visible progress indicator and the ability to go back without losing data.
- **Order fields the way people think** (name → email → password), and match the order of any paper or ID they're copying from.

### Labels, hints, placeholders
- **Always a visible label** above (or beside, on desktop) the field. Placeholders are examples, not labels — they disappear on typing and are low-contrast.
- **Put format hints below the label** before people type ("Use 8 or more characters"), not after they fail.
- **Mark the minority**: if most fields are required, mark optional ones "(optional)"; otherwise mark required ones. Be consistent.
- **Write labels as nouns** ("Email address"), buttons as specific verbs ("Create account", "Pay $24.00") — never "Submit" or "OK".

### Input help
- **Right keyboard and autofill:** `type="email|tel|url|number"`, `inputmode="numeric|decimal"`, `autocomplete="email|name|street-address|one-time-code|new-password|current-password|cc-number"`, `autocapitalize`, `spellcheck="false"` for codes and usernames.
- **Pickers for constrained values** (date, country, time); free text for names and addresses — never force people's names into a pattern.
- **Smart defaults** (country from locale, today's date, last-used option) and **accept flexible formats** (spaces/dashes in card and phone numbers) — normalize them yourself.
- **Show/hide password** toggle; allow paste everywhere (including password and code fields).
- **Mobile web:** input font ≥ 16 px to prevent zoom on focus; keep the focused field visible above the keyboard.

### Validation & errors
- **Validate on blur, re-validate on input once an error is shown** — don't yell while someone is still typing their first attempt.
- **Inline errors next to the field**, in text + icon + color, saying what's wrong and how to fix it ("Enter a date after today"), not "Invalid input."
- **On submit with errors:** keep everything people typed, focus the first invalid field, and show an error summary at the top that links to each field (screen readers announce it via `role="alert"` or a live region).
- **Don't disable the submit button** as the only signal of invalid input — people can't discover why. Let them submit, then explain.
- **Server errors** get the same treatment: specific, near the cause, input preserved, retry available.

### Submission
- The primary button shows a loading state and prevents double submission; slow operations show progress. Guard the server side too: payment and create requests carry an idempotency key, so a retry or double tap can't charge or create twice ([Hardening](./hardening-and-review.md#1-stress-test-before-calling-it-done)).
- **Confirm success** with the result itself (the created item, a receipt) rather than a generic toast when possible.
- **Destructive or irreversible submits** (delete account, send payment) get a confirmation that restates the consequence; everything else prefers undo.
- **Never lose work:** autosave drafts of long forms; warn before navigating away with unsaved changes.

### Accessibility checklist for forms
- Every input has a programmatic label (`<label for>` or `aria-labelledby`); groups use `fieldset`/`legend` (radio sets, date parts).
- Error text is linked with `aria-describedby` and `aria-invalid="true"`.
- Target size ≥ 44 pt (touch) for checkboxes/radios — make the label clickable.
- Logical tab order matches visual order; no keyboard traps in custom pickers.
- Timeouts are warned about and extendable.
