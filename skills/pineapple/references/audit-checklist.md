# Full Design Audit Checklist

Work **top-down**: a structural failure makes the polish below it moot. Use every phase for a full review; for a quick review, do Phases 1, 4, and 6. Report findings in the format from [Hardening & Review › Reporting an Audit](./hardening-and-review.md#4-reporting-an-audit): a severity-ranked table, what's working, and systemic patterns.

### Phase 1 — Purpose, Structure & Wayfinding
- [ ] **Three Screen Questions**: Does every screen answer *where am I, what can I do, where can I go* at first glance?
- [ ] **Surface Fit**: Does the level of expression match the surface? Operate (app UI) is restrained, Persuade (marketing) has one authored moment, Read (docs) lets typography lead ([Craft Floor](./craft-details-and-tells.md#1-know-the-surface)).
- [ ] **Navigation Persistence**: Is primary navigation (e.g., tab bar) preserved without being hidden on sub-pages?
- [ ] **Modal Restraint**: Are modals reserved for focused subtasks, not routine navigation?
- [ ] **Visual Hierarchy**: Are critical actions positioned prominently, with secondary actions in menus or sheets?
- [ ] **Clutter & Triage**: Has the screen been stripped of superfluous elements through progressive disclosure?
- [ ] **Decision Load**: At each decision point, are there at most 4–5 visible options, with one primary action, one or two secondary, and the rest in a menu?
- [ ] **Search**: Is search placed by navigation model and scope, with removable recents, scoped placeholder, filters, and a no-results view that echoes the query?
- [ ] **Menus Stay Put**: Are unavailable menu items dimmed rather than hidden?

### Phase 2 — Layout, Ergonomics & Adaptivity
- [ ] **Touch Targets**: Are all interactive elements large enough to tap reliably? That means at least 44×44pt on touch (expand small icons with `::after` padding when the visual is smaller) and at least 28×28pt on pointer (never below 24×24).
- [ ] **Safe Area**: Is interactive content clear of hardware obstructions using `max(16px, env(safe-area-inset-*))` while backgrounds bleed edge-to-edge?
- [ ] **Resize, Don't Redesign**: Does the layout adapt by width class with margins/safe areas, keep the same features and state at every size or pose, and keep controls off folds and camera regions?
- [ ] **Overflow Priorities**: When bars compress, do frequent and badged actions survive longest, with every item carrying both a title and an icon?
- [ ] **Concentric Shapes**: Are nested radii derived (parent − padding) and touch controls capsules, with no pinched or flared corners?
- [ ] **Spacing Rhythm & Measure**: Does spacing follow a 4/8 scale, with more space above headings than below them? Is reading text kept to 45–75 characters per line?

### Phase 3 — Type, Color & Materials
- [ ] **Scalable Text & Optical Tracking**: Does text scale smoothly with user size preferences (including accessibility sizes, reflowing rather than truncating), with size-specific tracking — positive for small captions, following the font's optical-size curve above that?
- [ ] **Typography Hierarchy**: Do text styles (headline, body, caption, etc.) establish clear visual hierarchy?
- [ ] **Color Contrast**: Do all text and meaningful graphical elements achieve at least 4.5:1 contrast (3:1 for large text)? Include secondary text (Apple's light 60% label is only 3.4:1), placeholders that carry information, and white labels on tinted fills.
- [ ] **Dark Mode & Tokens**: Does the interface use semantic color tokens rather than hardcoded hex values, adapting between light and dark appearances?
- [ ] **Increased Contrast & Reduced Transparency**: Do custom colors have high-contrast variants, small tinted text meet 4.5:1, and every translucent surface have an opaque fallback?
- [ ] **Action Tint Consistency**: Is interactive color used strictly for actions, with neutral colors for content?
- [ ] **Inclusivity & Differentiate Without Color**: Is all critical status communicated via shape, label, or glyph in addition to color?
- [ ] **Two Layers**: Is glass/translucency used only for the floating functional layer — no glass content cards, no glass on glass?
- [ ] **Variant & Tint Discipline**: Regular glass by default; clear only over media with a dimming layer; tint reserved for the one primary action or status?
- [ ] **Scroll Edge, Not Borders**: Do controls separate from scrolling content with an edge effect instead of opaque bar backgrounds and hairlines?
- [ ] **Icons**: Do icons match text weight, use variants for state, stay consistent per action, and fall back to text when ambiguous?

### Phase 4 — Components, States & Forms
- [ ] **State Matrix**: Does every control have a designed default, hover (hover-capable pointers only), pressed, focus-visible (≥ 3:1 ring), selected, disabled, loading, error, and empty state? Do states avoid shifting layout and avoid relying on color alone ([States](./component-states-and-forms.md))?
- [ ] **Forms**: Visible labels (placeholders are only examples), correct input types and `autocomplete`, paste allowed everywhere, submit not disabled by default, inline errors that say how to fix, input preserved on error?
- [ ] **Error Recovery**: Can the user undo actions, and are errors explained with a clear path forward?
- [ ] **Keyboard Navigation**: Can every interactive element be reached and operated via keyboard alone?
- [ ] **Screen Reader Structure**: Headings, grouped elements in a logical order, labels on icon-only controls, announced changes, decorative images hidden?
- [ ] **Shortcut Ergonomics**: Do desktop shortcuts avoid awkward multi-modifier finger gymnastics?

### Phase 5 — Motion, Feedback & Haptics
- [ ] **Direct Manipulation & 1:1 Tracking**: Do gestures track 1:1 with user input, preserving grab offset without snapping to center?
- [ ] **Interruptible Spring Motion**: Are transitions powered by velocity-aware springs (damping 1.0 for UI, 0.8 for momentum releases) that can be interrupted and redirected mid-flight without locking input?
- [ ] **Rubber-Banding**: Do boundaries resist softly and elastically rather than hitting a hard frozen stop?
- [ ] **Frequency Restraint**: Do keyboard-driven and high-frequency actions respond instantly with no animation? That includes ⌘/Ctrl-K palettes, arrow-key navigation, and tab switching by shortcut.
- [ ] **Physical Entrances**: Does nothing enter from `scale(0)`? Do menus, popovers, and tooltips grow from their trigger while centered modals stay centered? Does each exit mirror its entrance, faster?
- [ ] **Motion Hygiene**: No `transition: all`; ease-out (or a spring) for responses to input; no bounce without momentum; hover motion gated to hover-capable pointers; tooltips warm up once, then appear instantly?
- [ ] **Reduced Motion**: Are intense zoom/slide transitions replaced with fades when `prefers-reduced-motion` is active? Are springs tightened, blur transitions dropped, and spinners and feedback still working (no global 0.01 ms kill)?
- [ ] **Haptics**: Is each haptic used for its established meaning, consistent, synced with visuals, sparing, and optional?

### Phase 6 — Craft Floor
- [ ] **Browser Details**: Are `color-scheme`, `accent-color`, the caret, `::selection`, focus rings, panel scrollbars, link underline offset, and tabular numbers themed from tokens? Is `lang` set and zoom allowed ([Craft Floor](./craft-details-and-tells.md#2-the-details-nobody-draws))?
- [ ] **Default Tells**: Is the UI free of decorative gradients and gradient text, glow halos, cards nested in cards, icon tiles above headings, emoji icons, an eyebrow on every section, identical feature grids, the same scroll-reveal everywhere, side-stripe borders, and gray text on color? Any exception needs a stated reason.
- [ ] **Depth & Grays**: Are shadows neutral, with offset and blur? Is there one separation cue per edge? Are grays consistent, and are elevated dark surfaces from one ramp?
- [ ] **Delight & Personality**: Does the interface feature thoughtful micro-interactions or tactile touches that spark genuine joy?

### Phase 7 — Hardening ([details](./hardening-and-review.md#1-stress-test-before-calling-it-done))
- [ ] **Content Extremes**: Are 0, 1, many, and too many items handled? Does the layout survive text 3× longer, translated strings (+30%, short labels 2–3×), RTL, and odd input (emoji, single names, pasted cells)?
- [ ] **Network & Time**: Skeletons in the final layout's shape; offline and failure states with retry; double submit prevented (plus idempotent endpoints); state survives back, refresh, and a second tab; toasts pause on hover, focus, and hidden tabs?
- [ ] **Zoom & Settings**: Does the layout reflow at 200% zoom and at 320 px wide without horizontal scrolling? Do maximum text size, dark mode, increased contrast, reduced transparency, and reduced motion all render correctly?
- [ ] **Persona Walkthrough**: Has the primary task been walked as 2–3 relevant personas (power user, first-timer, assistive-tech user, stress tester, one-handed mobile user), with red flags reported per persona?

### Phase 8 — Responsibility & Commerce
- [ ] **Paywall & Sign-in Ethics**: Value before payment, total price visible, trials explained, cancellation easy, no account wall before purchase, sign-in as late as possible?
- [ ] **Honest Content & Consent**: Is the UI free of invented metrics, logos, testimonials, or ratings? Are placeholders labeled, and do consent choices carry equal visual weight?
- [ ] **Dark Patterns**: No confirmshaming, pre-checked add-ons, hidden costs, fake urgency, or hard-to-cancel flows ([Ethics](./dark-patterns-and-ethics.md))?

---
