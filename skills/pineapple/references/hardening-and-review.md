# Hardening, Review & Verification

Apple's **Flexibility** and **Craft** principles in practice: a design has to hold up under real data, real people, and real networks, not just the ideal mock. This file covers:
- stress tests;
- persona walkthroughs;
- a bounded way to verify your own work;
- a report format for audits.

---

## 1. Stress-Test Before Calling It Done

**Content extremes**
- **0, 1, a few, many, too many.**
  - Empty: an empty state with a glyph, a title, and one action.
  - One item: no grid holes or awkward plurals.
  - 10,000 rows: virtualize or paginate.
- **Text 3× longer than the mock** (names, titles, button labels, notifications). Decide per element:
  - wrap (the default for content);
  - truncate with the full text on hover, focus, or tap (single-line UI such as tabs and table cells);
  - shrink, but never below the minimum sizes.
- **Localization:** sentences grow about 30%, and short labels can double or triple (German, Finnish). CJK is shorter but may need more line height. Arabic and Hebrew mirror the layout. Logical CSS properties (`margin-inline-start`, `inset-inline-end`, `text-align: start`) make RTL nearly free.
- **Unexpected input:** emoji, accented and non-Latin names, very short or single names, pasted spreadsheet cells, leading or trailing spaces.
- **Numbers, dates, money:**
  - edge values: 0, negatives, huge values (1,234,567,890);
  - locale formats: `Intl.NumberFormat`, `Intl.DateTimeFormat`, `Intl.PluralRules`;
  - time zones, labeled wherever time matters.
- **Media:** missing, slow, broken, or oddly shaped. Reserve the space, show a neutral placeholder, and never show a broken-image icon.

**Network & time**
- **Slow network:** skeletons in the final layout's shape; nothing jumps when data arrives.
- **Failure:** a specific message near the cause, a retry, and the person's input kept. **Offline:** say so, and queue or disable what needs the network.
- **Optimistic UI:** apply the change immediately; if the server refuses, roll back visibly and say why.
- **Double submit:** show the in-flight state on the control (`aria-busy`) and ignore repeats. Make payment and create endpoints idempotent (an idempotency key) so a retry can't charge twice.
- **Back, refresh, or a second tab mid-flow:** state survives (in the URL or an autosaved draft), or people are warned before losing work.
- **Session expiry:** re-authenticate in place without discarding the form.
- **Timers:** auto-dismissing toasts pause on hover, on focus, and while the tab is hidden. Anything people must read or act on never auto-dismisses. Apple's guidance is to prefer an explicit dismiss.

**People & settings**
- **Keyboard only:** every action reachable, visible focus, logical order, no traps, Esc closes overlays and returns focus to the trigger.
- **Screen reader:** names on icon buttons, headings and landmarks, and announced changes (`role="status"` or `aria-live`).
- **Zoom:** 200% zoom, reflow at 320 px wide with no horizontal scrolling (WCAG 1.4.10), and the OS text size at maximum.
- **Display settings:** dark mode, increased contrast, reduced transparency, and reduced motion each render correctly.
- **Touch:** targets ≥ 44 pt, every gesture has a visible alternative, and drags recover from `pointercancel`.
- **Permissions denied:** the feature explains what's missing and how to enable it, and everything else keeps working.

---

## 2. Persona Walkthroughs

Walk the primary task as 2–3 of these people. Report what broke for each one, not a generic description of them.

| Persona | Probe | Red flags |
| :--- | :--- | :--- |
| **Power user**: expert, keyboard-first, impatient | Shortcuts, command palette, bulk actions, speed | No shortcuts; animations that can't be skipped; one-at-a-time work where batching is natural; confirmations on low-risk actions |
| **First-timer**: careful, literal, easily lost | Is the first action obvious within 5 seconds? Plain words? A way back? | Icon-only navigation; jargon; no confirmation that something worked; dead ends |
| **Assistive-tech user**: screen reader, keyboard, zoom, switch control | Labels, order, announcements, focus, contrast | Click-only interactions; invisible focus; meaning by color alone; unannounced errors; time limits |
| **Stress tester**: breaks things on purpose | Empty and huge data, long text, refresh mid-flow, bad input | Silent failures; lost data; broken layouts; raw error codes |
| **One-handed mobile user**: interrupted, on a slow network | Thumb reach, resuming after an interruption, typing avoided | Primary actions at the top edge; progress lost on app switch; tiny adjacent targets; heavy pages |

Pairings: dashboards and admin → power user + assistive tech. Checkout and long forms → one-handed + stress tester + first-timer. Onboarding and marketing → first-timer + one-handed.

**Decision load:** at every decision point, count the visible options.
- **≤ 4:** easy.
- **5–7:** group them or disclose progressively.
- **8 or more:** people skip, misclick, or leave.

Aim for one primary action, one or two secondary actions, and the rest in a menu.

---

## 3. Verify in Bounded Passes

Open-ended self-review loops, the kind that tweak 2 px and take another screenshot, burn time and rarely improve the result. Use a fixed budget:

1. **Build completely:** every state, real content, both themes.
2. **Inspect once, batched.** In one round, check:
   - phone width (~390 px) and desktop (~1440 px);
   - light and dark;
   - one keyboard-only pass;
   - one reduced-motion check.
3. **Fix everything found**, in one batch.
4. **Confirm with at most one more round, then stop.** Report anything left as a known issue.

**Reading budget:** open only the one or two reference files the task needs; SKILL.md covers most decisions.

**Motion review:** watch key transitions once at 10–25% speed (the browser's animation inspector). Check:
- the transform origin;
- that animated properties stay in sync;
- that nothing blocks input;
- that the reduced-motion path still communicates the change.

---

## 4. Reporting an Audit

Lead with the verdict and the counts per severity, then the table. Write one row per issue, and fold repeated issues into one systemic row.

| Severity | Where | Issue (now) | Fix (after) | Principle · Ref |
| :--- | :--- | :--- | :--- | :--- |
| 🔴 Blocks | `login.html` password field | `onpaste="return false"` blocks password managers | Remove the handler | Agency · [Forms](./component-states-and-forms.md) |
| 🟠 Misleads | Consent checkbox | Marketing opt-in is pre-checked | Unchecked by default, neutral label | Responsibility · [Ethics](./dark-patterns-and-ethics.md) |
| 🟡 Friction | Command palette | 250 ms scale-in on every ⌘K | Open instantly | Restraint · [Motion](./fluid-motion-and-physics.md#12-restraint-when-not-to-animate) |
| ⚪ Polish | Text selection | Browser-default selection color | `::selection` from the action tint | Craft · [Craft Floor](./craft-details-and-tells.md#2-the-details-nobody-draws) |

Severity:
- **🔴 Blocks** — someone can't finish the task. Examples: broken or unreachable controls, blocked paste, keyboard traps, unreadable text, data loss.
- **🟠 Misleads or excludes** — dark patterns, missing labels, unannounced errors, color-only meaning, WCAG AA failures.
- **🟡 Friction** — slow or excessive motion, missing states, weak hierarchy, extra steps.
- **⚪ Polish** — unthemed browser details, radius mismatches, tracking, alignment.

After the table:
- **What's working:** 2–3 specifics worth keeping, so fixes don't regress them.
- **Systemic patterns:** "hard-coded colors in 14 components → introduce tokens" beats 14 separate rows.
- **Next steps:** the top three, in order.

Check each finding in the rendered page or the source before reporting it. Don't pad the report with low-value polish.

**Optional scorecard** (for full audits; re-score after fixes to show progress). Score each dimension from 0 to 4, where 0 = broken, 1 = major gaps, 2 = partial, 3 = good, 4 = excellent:
- Structure & wayfinding
- Clarity & hierarchy
- Interaction & feedback
- Accessibility & inclusion
- Craft & consistency
- Responsibility & honesty

Report the total out of 24.
