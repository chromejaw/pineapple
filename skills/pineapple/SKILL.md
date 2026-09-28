---
name: pineapple
description: Apple's design philosophy applied to web and app design on any stack (React/HTML/CSS, iOS, Android, desktop, Electron, Flutter). Use when designing, building, reviewing, or auditing a website, web app, mobile app, desktop app, or game UI — layout and responsive/foldable adaptivity, typography, color and dark mode, glass/blur materials, motion and spring physics, haptics, icons, components and interaction states, forms, navigation and search, onboarding, paywalls, checkout, sign-in, dashboards and data tables, accessibility, and ethical (non-manipulative) design. Also for polish and craft details, removing the generic "AI look" (gradients, glows, nested cards, icon tiles), edge-case hardening, design reviews with severity-ranked fixes, and DESIGN.md design-system docs. Distilled from Apple's Human Interface Guidelines and Apple design sessions, made platform-neutral.
---

# Pineapple — Apple's Design Philosophy for Web & Apps

How Apple designs, made usable by anyone: principles, concrete values, and patterns for websites and apps on phones, tablets, foldables, and desktops — on any stack.

- **Numbers are Apple's defaults** (17 pt body, 44 pt targets, the system palette, springs). Use them directly, or keep their *ratios and relationships* with your own brand values.
- **If a product already follows another system** (e.g. Material), keep that system's numbers and apply the philosophy — see [Apple vs. Material](./references/design-tokens-and-styles.md#6-apple-values-vs-material-values-pick-one-system-dont-mix).
- Values labeled *suggested* are practical starting points, not Apple-published numbers.

## Working Method

**Before starting:**
- **Read what exists.** Check the project's `DESIGN.md`, its tokens, and a few screens. An established style beats these defaults: apply the principles inside it and don't re-skin it with Apple's values ([Project Memory](./references/project-memory.md)).
- **Name the surface.** *Operate* (app UI, dashboards), *persuade* (landing, pricing), or *read* (docs). It sets how much expression is right ([Surface modes](./references/craft-details-and-tells.md#1-know-the-surface)).

**Designing:** (1) purpose & information architecture (§1–2) → (2) target contexts and width classes (§3) → (3) navigation, search, and what floats vs. what's content (§2, §5) → (4) tokens: type, color, radii (§4–5) → (5) standard components with every state designed (§7) → (6) motion and feedback (§6) → (7) craft floor and stress tests (§10) → (8) audit (§11).

**Budget:**
- **Read sparingly.** Open only the 1–2 references the task needs.
- **Verify in bounded passes.** Build fully, then run one batched check: ~390 px and ~1440 px wide, light and dark, a keyboard pass, and reduced motion. Fix everything in one batch, confirm with at most one more round, then stop ([Bounded passes](./references/hardening-and-review.md#3-verify-in-bounded-passes)).

**Auditing:**
- **Work top-down.** Walk §11, structure before polish; use the [phased checklist](./references/audit-checklist.md) for thorough reviews.
- **Report as a table:** Severity · Where · Issue · Fix · Principle/ref, one row per issue.
- **Rank by severity:** 🔴 blocks a task › 🟠 misleads or excludes › 🟡 friction › ⚪ polish.
- **Add context:** what's working and any systemic patterns. Don't write files during an audit unless asked ([Report format](./references/hardening-and-review.md#4-reporting-an-audit)).

**Finishing:** if you created or changed the design system, record it in `DESIGN.md`. *Offer* to add a pointer in the project's agent instructions (CLAUDE.md/AGENTS.md); never add one silently.

**Reference map**

| Need | Read |
| :--- | :--- |
| Exact type scale, tracking, colors, radii, token JSON/Tailwind, Apple vs. Material | [Design Tokens](./references/design-tokens-and-styles.md) |
| Component states, forms, validation | [Component States & Forms](./references/component-states-and-forms.md) |
| Full component specs (buttons, menus, sheets, lists, tab bars…) | [Components](./references/components.md) |
| Glass/blur, scroll edges, concentric shapes, when not to use glass | [Materials & Glass](./references/materials-and-glass.md) |
| Responsive, foldable, split-screen, windows, command menus | [Adaptive Layout](./references/adaptive-layout-and-foldables.md) · [Device Contexts](./references/platforms-and-contexts.md) |
| Springs, gestures, momentum, timing budgets, durations | [Fluid Motion](./references/fluid-motion-and-physics.md) |
| Accessibility, color, typography, layout, icons, images, writing, privacy | [Foundations](./references/foundations.md) · [Iconography](./references/iconography-and-symbols.md) |
| Onboarding, loading, feedback, modality, search, settings, undo, charts, files | [Patterns](./references/patterns.md) · [Patterns Extended](./references/patterns-extended.md) |
| Paywalls, checkout, sign-in, third-party logos, screen readers, collaboration | [Commerce, Accounts & Accessibility](./references/commerce-accounts-and-accessibility.md) |
| Dashboards, data tables, admin tools | [Data-Dense UI](./references/data-dense-ui.md) |
| Manipulative patterns and honest alternatives | [Dark Patterns & Ethics](./references/dark-patterns-and-ethics.md) |
| Surface modes, browser details (selection, caret, scrollbars…), "AI look" tells and what to do instead | [Craft Floor](./references/craft-details-and-tells.md) |
| Stress tests, persona walkthroughs, bounded verification, audit report format | [Hardening & Review](./references/hardening-and-review.md) |
| DESIGN.md template, agent-instructions pointer | [Project Memory](./references/project-memory.md) |
| Gestures, keyboard shortcuts (Mac/Windows), pointer, focus, game controls | [Inputs](./references/inputs.md) |
| Generative AI, machine learning, AR, maps | [Technologies](./references/technologies.md) |
| Design Awards rubric, 10 principles, prototyping, idea→interface method | [Design Process](./references/design-process-and-rubric.md) · [Fundamentals](./references/design-fundamentals.md) |
| All rules in one compact place (original curated summary) · the full phased audit checklist | [Quick Rules Digest](./references/quick-rules.md) · [Full Audit Checklist](./references/audit-checklist.md) |

---

## 1. Principles

No formula combines these; they are tools for weighing trade-offs.

- **Purpose — *Make something meaningful.*** Know what the product is for; make the few most important things great. Every feature spends people's time, attention, and trust — deciding what *not* to build is most of design.
- **Agency — *Let people do things their own way.*** Get people straight to their task; no forced flows; everything reversible. Interrupt only right before a big mistake.
- **Responsibility — *Act in people's best interest.*** Ask for data only when needed and say why; anticipate misuse and harm. AI features need previews, confirmations, and disclaimers — or removal if the risk outweighs the value.
- **Familiarity — *Build on what people know.*** Use established metaphors (neither too literal nor too abstract; never redefine one). Same look → same behavior → same place.
- **Flexibility — *Adapt to diverse contexts and needs.*** Accessibility from the start; every input (touch, keyboard, pointer, voice); every size; let people rearrange or hide controls when no single layout fits everyone.
- **Simplicity — *Be clear and direct.*** Simple ≠ minimal: hiding everything in a menu isn't simple. Concise words, strong hierarchy, and sometimes *more* context (a play button that shows time remaining).
- **Craft — *Care about every detail.*** Laggy taps, jittery scrolling, and misaligned icons read as cheap. Prototype, test in real conditions, keep improving after launch.
- **Delight — *Make it human.*** Pick the emotion (calm, confident, energized) and reinforce it everywhere. Delight is the sum of the other principles, not confetti at the end.

## 2. Structure & Navigation

- **Every screen answers three questions at a glance:** *Where am I? What can I do? Where can I go from here?* A title (not a logo or menu) answers the first; the screen's actions the second; navigation the third.
- **IA loop:** list everything the product does → imagine when, where, and why people use it → remove, rename, group. Group large content sets by *time* (recent), *progress* (drafts, continue), or *patterns* (related items).
- **Tab bar / bottom nav:** 3–5 labeled, distinct top-level destinations; tabs navigate, never act (no "Add" tab); persistent on drill-down (may minimize on scroll); becomes a sidebar on wide screens.
- **Toolbars:** title + screen-specific actions; group items by function and frequency; the primary action (Done, Save) sits apart and tinted; a crowded bar means cut or move items into a More menu; don't group an icon button with a text button.
- **Search placement** follows two questions — how people navigate, and what the search covers. Phone: bottom field (reachable, rises above keyboard) or a search tab; inline under the title for one collection. Desktop: trailing toolbar field or top of sidebar. Keep recents removable, scope visible, and make the no-results view echo the query.
- **Modality:** only for focused, self-contained tasks; always an obvious way out; confirm before discarding work. Dim the background only when the task interrupts.
- **Progressive disclosure:** show a few items + "See all"; the expanded view keeps the same arrangement.
- **Menus:** order by frequency, group with separators, destructive last in red; in menu bars, **dim unavailable items — never hide them**. Context menus hold only relevant actions, all also reachable elsewhere.

## 3. Layout & Adaptivity

- **Margins:** ≥ 16 pt on compact (phone) widths, ≥ 20 pt on regular (tablet/desktop). Spacing on a 4/8 pt rhythm.
- **Safe areas:** controls and text inside `max(16px, env(safe-area-inset-*))`; backgrounds and media bleed edge to edge.
- **Targets:** ≥ 44×44 pt touch, ≥ 28 pt pointer (never below 24 px). Expand small icons' hit area invisibly.
- **Width classes, not devices:** lay out for compact vs. regular *available* width with container queries; no fixed widths or device breakpoints.
- **Resize, don't redesign** (foldables, split screen, resizable windows): same features, state, and hierarchy at every size; a wide screen may add *one* level (list → list + detail); move only what must move; keep controls off folds and camera cutouts; even column counts split cleanly at a fold.
- **Big screen ≠ stretched phone:** split view, reflow into columns, or tab bar → sidebar.
- **Shapes are derived:** *capsule* (radius = ½ height) for touch controls; *concentric* (radius = parent − padding) for nested shapes; continuous-curve corners. Pinched or flared inner corners mean a guessed radius.
- **Desktop and web apps:** one window/tab per document, descriptive titles, command menu or palette with every command, standard shortcuts (Cmd on Mac, Ctrl on Windows/Linux), and never hijack browser behaviors (Back, middle-click, find, zoom, text selection).

## 4. Typography

| Style | Size / leading (pt) | Weight | Tracking (pt) |
| :--- | :--- | :--- | :--- |
| Large Title | 34 / 41 | Regular (emphasized Bold) | +0.40 |
| Title 1 · 2 · 3 | 28/34 · 22/28 · 20/25 | Regular (emph. Bold, Bold, Semibold) | +0.38 · −0.26 · −0.45 |
| Headline · Body | 17 / 22 | Semibold · Regular | −0.43 |
| Callout · Subhead | 16/21 · 15/20 | Regular | −0.31 · −0.23 |
| Footnote · Caption 1 · Caption 2 | 13/18 · 12/16 · 11/13 | Regular | −0.08 · 0 · +0.06 |

- **Tracking follows optical size**, never one letter-spacing for all sizes: positive below 12 pt, negative through text sizes, and — for fonts without optical sizes — slightly tighter (≈ −1% to −2.5% em) at display sizes.
- **Scalable type:** honor the user's text size (rem units on the web; test 200%). At the largest sizes body grows ~3× and titles < 2× — reflow (stack side-by-side items, wrap labels) instead of truncating.
- **Density by context:** desktop body is **13 pt** (web: 13–14 px for productivity apps), phone 17 pt; minimum legible 11 pt (10 pt desktop).
- System font first (`-apple-system, system-ui, "Segoe UI", Roboto`); custom fonts for headlines and brand, with bold-text and scaling support. Titles in alerts and onboarding: bold, left-aligned.

## 5. Color & Materials

- **Semantic tokens only** — background (primary/secondary/tertiary, plain and grouped), label (100/60/30/18%), separator, fill — each with light, dark, and increased-contrast values.
- **One action tint** (blue `#0088FF` light / `#0091FF` dark) reserved for interactive elements; content stays neutral.
- **Default tints fail small text:** most sit below 4.5:1 on white (blue 3.5). Use the high-contrast variant for links and small tinted text (blue `#1E6EF4`, 4.6:1). Text ≥ 4.5:1, large text and UI parts ≥ 3:1.
- **Two more traps:**
  - **Secondary text:** Apple's light-mode secondary label (60%) is only 3.4:1 on white; use 75% for small informative text.
  - **Filled buttons:** white on system blue is 3.5:1, so fill buttons that have small labels with `#1E6EF4`. WCAG AA needs this; Apple's rule accepts 3:1 for bold. Tokens: `--label-secondary-text`, `--action-fill`.
- **Brand color:** use it sparingly on controls (primary action, selected tab, badges); express brand through typography, imagery, and color in the *content* layer. No logos on every screen.
- **Never color alone** — pair every status color with an icon, shape, or text.
- **Two layers:** content (opaque or standard blur materials) and a floating control layer (bars, menus, sheets, floating buttons). Glass/translucency belongs only to the control layer; never glass on glass; hierarchy comes from layout and grouping, not borders and backgrounds.
- **Glass variants:** *regular* (adaptive, works anywhere) or *clear* (only over rich media, with a ~35% dim behind bright content). Tint glass only for the primary action or status.
- **Scroll edge effect** (soft fade; hard for pinned headers and dense desktop UIs) instead of hairlines under floating bars.
- **When not to use glass:** text-heavy or low-contrast contexts, performance-sensitive or low-end devices, data-dense UIs, products on another design system. A solid content surface + one translucent bar + a tinted primary button is a strong default.
- Support `prefers-reduced-transparency` (go opaque) and `prefers-contrast: more` (solid surfaces, visible borders).

## 6. Motion & Feedback

- **Acknowledge on touch-down, commit on release** (slide off to cancel). Track drags 1:1 and keep the grab offset.
- **Interruptible always:** never block input during animation; animate from the current on-screen value; carry release velocity into the next motion.
- **Springs, not fixed curves:** damping ratio 1.0 (no bounce) by default; ~0.8 only when a gesture carried momentum. *Suggested* response: 0.4 s move, 0.3 s sheets, 0.15–0.25 s small controls.
- **Momentum:** projected distance = (v/1000) · d / (1 − d), d ≈ 0.998. **Rubber-band** past bounds: f(x) = x·d·c / (d + c·|x|), c ≈ 0.55.
- **Timing budgets:** ≤ 100 ms feels instant (all direct feedback); 0.1–1 s keep a working state; 1–10 s show progress; > 10 s run in the background with cancel. Without springs: 100–150 ms state changes, 150–250 ms menus, 250–400 ms sheets and pages; exits faster than entrances.
- **Spatial continuity:** things appear from and return to their source (menus from their button); morph shared elements instead of cross-fading.
- **Restraint by frequency** (Apple: avoid motion on frequent interactions):
  - **Constant, keyboard-driven actions** (⌘/Ctrl-K palettes, arrow-key navigation, shortcut tab switches) respond instantly, with no animation.
  - **Frequent actions** (hover, press, selection) get ≤ 150 ms of opacity or color change.
  - **Occasional changes** get the real motion.
- **Physical entrances:**
  - Never scale from 0; start at 0.9–0.97 with opacity.
  - Popovers and menus grow from their trigger (`transform-origin`); centered modals stay centered.
  - Tooltips wait ~500 ms once, then show neighbors instantly.
- **Web hygiene:**
  - Ease-out (a spring's shape) for responses to input; never ease-in for UI.
  - Name the properties; never `transition: all`.
  - Gate hover effects with `@media (hover: hover)`.
  - Details: [Restraint](./references/fluid-motion-and-physics.md#12-restraint-when-not-to-animate).
- **Reduced motion:** replace movement and bounce with short cross-fades; tighten springs; keep spinners and state feedback working (no global 0.01 ms kill).
- **Feedback types:** status, completion, warning (before damage), and error (inline, specific, recoverable). Confirm only what isn't already visible; progress for anything > 1 s.
- **Haptics** (apps): notification (success/warning/error), impact (light→heavy), selection (value changing) — each only for its meaning, in sync with visuals, sparing, and optional.

## 7. Components & States

- **Design every state:** default, hover (pointer only), pressed, focus-visible (≥ 3:1 ring), selected, disabled (explain why), loading (inside the control, no double submit), success, error, empty, read-only, drop target. States never shift layout and never rely on color alone.
- **Buttons:** specific verb labels ("Pay $24", not "Submit"); one primary per view; destructive styled as destructive; icon-only buttons get accessible names and tooltips.
- **Alerts:** rare; title states the issue, ≤ 3 buttons, the safe choice is the default, destructive in red. Prefer **undo** over "Are you sure?" for recoverable actions.
- **Sheets & popovers** for self-contained subtasks; **action sheets** spring from their source; **toasts** for undo and background completion.
- **Lists & tables:** the default for structured content; section headers, swipe/context actions, selection, reorder; grids/collections for visual items.
- **Selection controls:** toggles act immediately (no Save); segmented controls for 2–5 peer views; sliders for imprecise values; steppers for small increments; pickers for constrained sets.
- **Progress:** determinate when you can estimate; skeletons for content; indeterminate only for short, unknown waits.
- **Icons:** match icon weight to adjacent text, size relative to cap height; outline by default, fill for selected; slash for unavailable; one icon per action everywhere; text when no icon is unambiguous; never emoji.
- **Forms:** one column; visible labels (placeholders are examples); right keyboard and `autocomplete`; accept flexible formats; validate on blur; inline errors with text + icon that say how to fix; keep input on error; don't disable submit as the only signal. Details: [Component States & Forms](./references/component-states-and-forms.md).

## 8. Patterns

- **Onboarding:** value first; no tutorial carousels; teach in context; defer sign-up and permissions until they're needed.
- **Loading:** show content as soon as it's available; skeletons over blank screens; explain failures with a retry.
- **Undo & recovery:** multi-level undo; grace-period undo toasts for destructive actions; autosave; warn before leaving with unsaved changes.
- **Settings:** few, with smart defaults; changes apply immediately; don't duplicate system-wide settings.
- **Data entry:** minimize typing — defaults, pickers, autofill, suggestions.
- **Paywalls & subscriptions:** value before payment; total price and period on every option; trials explained (length, price after, how to cancel); cancellation as easy as sign-up.
- **Checkout:** collect choices before payment; wallet payments first when available; guest checkout — accounts offered after purchase; itemized fees; clear result and confirmation.
- **Sign-in:** only for real value, as late as possible; passkeys and federated sign-in over passwords; show signed-in state; account deletion in-app. Third-party buttons and logos: official artwork unaltered, clear space ≥ ⅒ of height, equal prominence.
- **Dashboards & tables:** summarize → trend → detail; right-aligned tabular numbers; sticky headers; sort, filter, bulk select; solid chrome. Details: [Data-Dense UI](./references/data-dense-ui.md).
- **Ethics:** no confirmshaming, hidden costs, pre-checked add-ons, fake urgency, hard-to-cancel flows, or fake permission prompts; equal-weight Accept/Reject. See [Dark Patterns & Ethics](./references/dark-patterns-and-ethics.md).

## 9. Accessibility & Inclusion

- Scalable text; screen-reader labels, headings, grouping, and change announcements; decorative images hidden.
- Contrast 4.5:1 text / 3:1 large text and UI; never color alone; support increased contrast, reduced transparency, reduced motion, and bold text.
- Full keyboard access with visible focus and logical order; targets ≥ 44 pt touch; no gesture-only actions — always a visible alternative.
- Captions and transcripts for media; plain language; no gendered or culture-bound assumptions; RTL layouts mirror direction, not numbers or media controls.

## 10. Craft Floor & Hardening

- **Theme what the browser draws:**
  - `color-scheme: light dark`, with `accent-color` and `caret-color` from the action tint;
  - `::selection`, a `:focus-visible` ring, and thin themed scrollbars on app panels;
  - `text-wrap: balance` on headings and `tabular-nums` for changing numbers;
  - `lang` set, zoom never disabled.
  - Full baseline: [Craft Floor](./references/craft-details-and-tells.md#2-the-details-nobody-draws).
- **Refuse the default "AI look"** unless the brief earns it:
  - decorative purple-blue gradients and gradient text; glow halos and spotlight meshes;
  - cards nested in cards; icon tiles above headings; emoji as icons;
  - an eyebrow over every section; identical feature-card grids; the same fade-up on every section;
  - colored side stripes; gray text on color; invented metrics or testimonials.
  - Each has an honest alternative in [Default Tells](./references/craft-details-and-tells.md#3-default-tells-and-what-to-do-instead).
- **Depth is physical:** neutral shadows with offset and blur, and one separation cue per edge (fill, hairline, *or* shadow). Put more space above a heading than below it. Keep the reading measure at 45–75 characters.
- **Stress-test before calling it done:**
  - 0, 1, and many items; text 3× longer; translations and RTL;
  - slow, failed, and offline network; double submit;
  - back or refresh mid-flow; 200% zoom.
  - Walk the main task as 2–3 personas ([Hardening](./references/hardening-and-review.md)).

## 11. Evaluation & Audit

**Apple Design Awards rubric:** Delight & Fun · Inclusivity · Innovation · Interaction · Social Impact · Visuals & Graphics.

**Ten evangelism principles:** wayfinding · feedback · visibility · consistency (external and internal) · mental models · proximity · grouping · mapping · affordance · progressive disclosure (80/20).

**Process heuristics:** prototype to answer one question at a time; build parallel options behind a toggle and let people feel the difference; critique in terms of communication, not taste; when features creep, keep the two or three interactions people loved; say the problem out loud when a design feels "off"; squint test — the heaviest element should be the most important.

**Checklist**
- [ ] Every screen answers where am I / what can I do / where can I go.
- [ ] Targets ≥ 44 pt touch (≥ 28 pt pointer); content inside safe areas; margins 16/20 pt.
- [ ] Type uses named styles, scales with user settings, reflows at large sizes, size-specific tracking.
- [ ] Semantic color tokens with dark and high-contrast variants; text ≥ 4.5:1; nothing conveyed by color alone.
- [ ] One action tint, used only for interactive elements; one primary action per view.
- [ ] Glass only on the control layer, never glass on glass, solid fallback for reduced transparency — or no glass where it hurts legibility or performance.
- [ ] Nested radii concentric; touch controls capsules.
- [ ] Every component state designed (hover, pressed, focus-visible, disabled, loading, error, empty) without layout shift.
- [ ] Direct feedback ≤ 100 ms; progress for > 1 s; animations interruptible and never blocking input; reduced-motion alternative.
- [ ] Works at every width: no horizontal page scroll, adapts by width class, same features at every size.
- [ ] Full keyboard operation with visible focus; standard shortcuts; browser behaviors intact.
- [ ] Forms: visible labels, correct input types and autofill, inline actionable errors, input preserved.
- [ ] Destructive actions undoable or confirmed with the consequence stated.
- [ ] Paywall, checkout, sign-in, and consent flows are honest and easy to exit.
- [ ] Screen reader reads a logical, labeled structure; changes are announced.
- [ ] Keyboard-driven and high-frequency actions have no animation; nothing enters from `scale(0)`; popovers grow from their trigger.
- [ ] Browser details themed (selection, caret, `accent-color`, focus, scrollbars); no default "AI look" tells left without a reason.
- [ ] Stress-tested: long and translated text, 0/1/many items, slow or failed network, double submit, 200% zoom.
