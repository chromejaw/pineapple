# Quick Rules Digest

The full curated rule summary this skill originally carried in SKILL.md — kept here so nothing is lost while SKILL.md stays lean. Wording is the original skill's where possible. Read when you want the complete, compact rule set in one place; each section links to the deep reference.

---

## 1. Design Fundamentals

### Core Design Principles

The principles here form the foundation for great interface design. There's no one right way to apply these principles; they are tools to help you weigh competing priorities and make key decisions on the path to a great design.

#### Purpose — *Make something meaningful.*
The best designs reflect a constant orientation toward what makes a product genuinely useful. At every stage of development, ask what your product is for and whether the design serves that purpose.
- **Prioritize your app's most important features** by aligning with how people want to use it, and focus on making those features truly great. A product with a clear use is more effective at helping people meet their goals.
- **Investigate existing solutions, and avoid re-creating them.** Define what sets your product apart, and ask how your design can reflect that.

#### Agency — *Let people do things their own way.*
People use your product to get things done. Often the best way to help them do this is to get them directly to the task or content at hand. The best designs are unobtrusive and present when people need them.
- **Let them move through your interface and access features without being locked into specific flows or modes.** When a guided flow is necessary, make it easy to skip or escape so people can get to the main experience quickly.
- **When people know they can reverse an action or return to a previous state, they feel free to explore**, and that freedom makes your interface more inviting. Build forgiveness into your design, and make it easy. Recovering from the unexpected shouldn't cost people their time or work.

#### Responsibility — *Act in people’s best interest.*
You have an opportunity to build a relationship with someone from their very first interaction. Make sure your app's intentions are clear from the start.
- **Provide a clear rationale when asking for permission**, and when gathering data, be clear about what you collect and how you use it.
- **People trust you to maintain the integrity of their data.** Only collect what your product needs to function, and handle it with care. Anticipate ways it could be misused or cause harm, and put protections in place to prevent abuse and unintended consequences.

#### Familiarity — *Build on what people know.*
People bring knowledge of the real world and other software to every new experience. Draw on both to make your interface feel familiar and intuitive.
- **Consistency helps people learn more quickly**, and gives them confidence that new interactions will work the way they expect. Once you establish a behavior or appearance for an element, apply it throughout your design.
- **Give people clear signals about what's happening as they use your app.** Show when controls are available, indicate when content changes, and use system patterns to display alerts and offer choices. Consistent feedback helps keep people informed and in control.

#### Flexibility — *Adapt to diverse contexts and needs.*
People are empowered by products designed with them in mind. Think about the diversity of people who may encounter your design, and take the range of their experiences, perspectives, and needs into account.
- **Treat accessibility as a priority from the start.** Design inclusively to reach the broadest possible audience and create a better experience for all.
- **Help people feel at home as your design adapts across platforms and configurations.** Keep content and controls in consistent, predictable positions, and use natural animations to ease transitions.
- **People interact with their devices in different ways.** Designing for as many inputs as possible — including voice, touch, keyboard, and more — means more people can use your product the way that works best for them.
- **Your software should feel polished and at home wherever it runs.** Give each platform you support the same level of care.

#### Simplicity — *Be clear and direct.*
Simplicity isn't minimalism. Aim for a focused, useful experience that keeps the important things close by and lets the others fall away.
- **When you find the simplest way to say something, it's often the most universal, and the most helpful.** Choose exactly the words you need to convey a concept or label a control.
- **When form and function are readily apparent, people know how to reach a desired outcome.** Prioritize recognizable controls and a consistent structure that helps people understand where they are and what comes next.

#### Craft — *Care about every detail.*
Every element of your design shows people how much you care. Be deliberate with each decision, and strive for stunning visuals, smooth animations, precise wording, and thoughtful audio.
- **Prototype early, try new approaches, and be willing to discard what doesn't work.** Set a high bar for every feature, refine it, and try again. Test your product in real-world settings to make sure it's durable, reliable, and high-performing.
- **Shipping isn't the finish line.** Keep your interface current with the latest platform capabilities and design patterns, and keep the quality bar high. Design is an ongoing commitment.

#### Delight — *Make it human.*
Not all software feels the same to use. A fitness app might energize; a meditation app might calm; a game might thrill. Know the feeling you want to evoke, and let it shape your design.
- **Every interaction is a chance to show what your software stands for.** From a simple button press to an error message, consider whether each moment is an opportunity to add a touch of character that reflects the spirit of your design.
- **Don't let pursuit of delight for its own sake get in the way of your product's core purpose.** Think about your overall aesthetic: Some designs benefit from a carefully considered practical touch, while others might prefer some whimsy. Experiment to find the right balance.
- **Delight emerges as the sum of the consideration that you put into your product.** It's the culmination of everything a person experiences as they use it: the freedom to act, the safety to explore, the comfort of familiar metaphors, and the flexibility to transition from one context to another.

#### Principles in Practice
- **Every feature spends people's time, attention, and trust** — choosing what to build is mostly deciding what not to include.
- **Simple ≠ minimal.** Hiding everything in one menu looks minimal but isn't simple; sometimes simpler means *adding* context (a play button that also shows time remaining).
- **Metaphors: neither too literal nor too abstract** — and never redefine a known one (trash = delete).
- **AI features:** assume the model will sometimes be wrong; add previews, confirmations, disclaimers — or drop the feature if the safety risk outweighs its value.
- **When no single layout suits everyone, let people rearrange or hide controls.**

*(Full text: [Design Fundamentals Reference](./design-fundamentals.md) · worked examples: [Design Process §6–7](./design-process-and-rubric.md))*

---

---

## 2. Foundations of Design

### Accessibility
An accessible interface empowers everyone to have a great experience regardless of capabilities or device usage.
1. **Consistent**: Uses familiar and predictable interactions making tasks straightforward to perform.
2. **Perceivable**: Content is perceivable through multiple sensory channels:
   - **Scalable text**: Text dynamically scales with system font size preferences without clipping or overlapping.
   - **Screen readers**: All interactive elements provide meaningful labels, values, traits, and hints.
   - **Color & Contrast**: Never convey critical information using color alone. Provide text or glyph alternatives. Maintain minimum contrast ratios of **4.5:1** for standard text and **3:1** for large text / graphical controls.
3. **Operable**: Supports diverse input methods (voice control, switch access, full keyboard navigation).
4. **Understandable**: Clear labels, unambiguous error feedback, and straightforward terminology.
5. **Reduced Motion**: Respect user motion preferences by replacing zooming/sliding view transitions with subtle cross-fades.
6. **Increased Contrast & Reduced Transparency**: Ship a high-contrast variant of every custom color (the reference palette's sit at ~4.5:1) and an opaque fallback for every translucent material.
7. **Screen-reader structure**: Headings for hierarchy, logical grouping/order (a card reads as one element), announcements when content changes, decorative images hidden. *(See [Commerce, Accounts & Accessibility › Screen Readers](./commerce-accounts-and-accessibility.md))*

### Layout & Adaptivity
A consistent layout that adapts across display sizes, orientations, and multitasking configurations helps people understand and enjoy your product.
- **Safe Areas**: Position all interactive elements and text inside safe regions: `max(16px, env(safe-area-inset-top/bottom/left/right))`. Backgrounds and visual media extend edge-to-edge.
- **Layout Margins**: Minimum **16pt** screen edge margins on compact/phone screens, **20pt** on regular/desktop screens.
- **Minimum Target Sizes**: Interactive elements must measure at least **44 × 44 pt** on touch (24 × 24 pt on pointer). If visual icons are smaller (e.g., 24px), expand tap boundaries invisibly using `::after` hit padding.
- **Continuous Curvature (Squircles)**: Use smooth corner radii without abrupt tangent breaks (`--radius-sm: 8px`, `--radius-md: 10px`, `--radius-lg: 14px`, `--radius-xl: 18px`, `--radius-full: 9999px`).
- **Concentricity**: Nested shapes share a center. Three shape types — *fixed* (constant radius), *capsule* (radius = ½ height; default for touch controls and bars), *concentric* (radius = parent radius − padding). Pinched or flared inner corners mean a radius was guessed instead of derived.
- **Width classes, not devices**: Lay out against *compact* vs. *regular* available width using margins and safe areas; never fixed widths or device-specific breakpoints. *(See [Adaptive Layout](./adaptive-layout-and-foldables.md).)*
- **Extend content under the chrome**: Full-bleed backgrounds and scroll views run beneath toolbars, tab bars, and sidebars; use a scroll edge effect — not a solid bar background — to separate controls from content.

### Color & Dark Mode
Judicious use of color enhances communication, provides visual continuity, communicates status, and establishes hierarchy.
- **Semantic Color Tokens**: Never use hardcoded hex literals for interface chrome. Use semantic tokens that adapt automatically:
  - *Backgrounds*: Primary (`#fff` / `#000`), Secondary (`#f2f2f7` / `#1c1c1e`), Tertiary (`#fff` / `#2c2c2e`).
  - *Labels*: Primary (100% opacity), Secondary (60%), Tertiary (30%), Quaternary (16-18%).
  - *Separators*: Subtle semi-transparent borders (`rgba(60,60,67,0.29)` / `rgba(84,84,88,0.65)`).
- **Single Action Tint**: Reserve one distinct accent color (e.g. blue `#0088ff` light / `#0091ff` dark) strictly for actionable elements. Keep non-interactive content neutral.
- **Default tints are for glyphs and fills, not small text**: Most bright light-mode tints are below 4.5:1 on white (blue 3.5, green 2.2, orange 2.3). For links and small tinted text use a high-contrast variant (blue `#1e6ef4`, 4.6:1).
- **Brand color lives in the content layer**: Minimize accent color on controls; put brand color in content that scrolls beneath the glass so the chrome picks it up dynamically. Always define light, dark, and increased-contrast variants — even for a single-appearance app.

### Typography & Optical Sizing
Typographic choices convey information hierarchy, legibility, and brand personality.
- **The Core Type Scale** (phone/tablet default size; all Regular except Headline — the *emphasized* variant is Bold for titles, Semibold otherwise):
  - *Large Title*: 34pt / 41pt leading / +0.40pt tracking (regular; emphasized bold)
  - *Title 1*: 28pt / 34pt leading / +0.38pt tracking (regular; emphasized bold)
  - *Title 2*: 22pt / 28pt leading / -0.26pt tracking (regular; emphasized bold)
  - *Title 3*: 20pt / 25pt leading / -0.45pt tracking (regular; emphasized semibold)
  - *Headline*: 17pt / 22pt leading / -0.43pt tracking (semibold)
  - *Body*: 17pt / 22pt leading / -0.43pt tracking (regular)
  - *Callout*: 16pt / 21pt leading / -0.31pt tracking
  - *Subhead*: 15pt / 20pt leading / -0.23pt tracking
  - *Footnote*: 13pt / 18pt leading / -0.08pt tracking
  - *Caption 1*: 12pt / 16pt leading / 0.00pt tracking
  - *Caption 2*: 11pt / 13pt leading / +0.06pt tracking
- **Optical Tracking Rule**: Tracking follows *optical size*, never one fixed letter-spacing across all sizes. Text below 12pt requires *positive* tracking for legibility; text sizes (13–22pt) run *negative*; optical-size fonts (e.g. SF Pro, Inter Display) switch to a tightly drawn display cut around 20pt, so tracking climbs back through zero by ~24pt, stays positive through display sizes, and fades to 0 by 80pt. With a font that lacks optical sizes, tighten display sizes (≈ −1% to −2.5% em) and loosen tiny ones instead.
- **Scalable Type**: Layouts must scale proportionally across user font size settings without clipping or breaking containers. At accessibility sizes body grows ~3× (17 → 53pt) while titles grow < 2× — hierarchy compresses, so *reflow* (stack side-by-side items, wrap labels) rather than scale.
- **Density by device**: Body is 17pt on phones but **13pt on desktop**. Minimum legible text: 11pt phone · 10pt desktop. Titles in alerts and onboarding are bold and left-aligned.

*(Full token and style specs: [Design Tokens Reference](./design-tokens-and-styles.md))*

### Materials & Glass
Materials create depth and separate foreground from background while letting content show through. Every interface has **two layers**: the content layer, and a floating functional layer (navigation and controls) above it.
- **Glass is for the functional layer only** — tab bars, toolbars, sidebars, floating buttons, menus, sheets. Content surfaces (lists, cards, backgrounds) stay opaque or use *standard* blur materials. Exception: a slider thumb or toggle may lift into glass while touched.
- **Never glass on glass.** Elements on top of glass use fills, transparency, and vibrancy.
- **Regular vs. clear variant (never mix):** *regular* adapts (blur, luminosity, light/dark flipping) and works anywhere, including text-heavy components; *clear* is highly translucent, non-adaptive, only over media-rich backgrounds, with bold bright glyphs and a **~35% dark dimming layer** over bright content.
- **Tint sparingly** — only the primary action or a status; tint the background, not the glyph. If everything is tinted, nothing stands out.
- **Scroll edge effects** replace hard dividers where content scrolls under floating controls: *soft* (default) or *hard* (pinned headers, desktop). One per view; functional, never decorative.
- **Hierarchy through layout and grouping, not decoration** — remove legacy bar backgrounds, borders, and hairlines.
- **Behavior:** glass materializes (modulates refraction) rather than fading, illuminates from within on touch, morphs between states on one floating plane, and recedes (more opaque) when focus moves deeper or a window goes inactive. Large glass (menus, sidebars) adapts but doesn't flip light/dark.
- **Accessibility:** Reduce Transparency → frostier/opaque; Increase Contrast → black/white with a contrasting border; Reduce Motion → no elastic effects.

*(Full rules + CSS recipe: [Materials & Glass](./materials-and-glass.md))*

### Icons & Symbol Systems
- **Treat icons as type:** match icon weight to adjacent text weight, size relative to cap height (small/medium/large scales), baseline-align, scale with text size.
- **Variants carry state:** outline (default, toolbars), fill (selection, tab bars, swipe actions), slash (unavailable), enclosed (small sizes). Let the container pick the variant.
- **Rendering modes:** monochrome, hierarchical (one color, layered opacity — for depth), palette, multicolor (color carries meaning). *Variable color* shows change (signal, volume, progress), never depth.
- **Animate with meaning:** bounce = something happened; pulse/breathe = ongoing; replace = state change; wiggle = overlooked call to action; rotate = working; draw on/off = progress or direction. Sparingly, and off under Reduce Motion.
- **Same symbol for the same action everywhere; use text when no symbol is unambiguous** (Edit, Select). Never emoji as interface icons; never a custom take on a universal metaphor (trash, magnifying glass); provide accessibility labels for custom icons.

*(Full spec: [Iconography & Symbols](./iconography-and-symbols.md))*

### App Icons
An app icon expresses your product's identity and personality, helping people recognize it at a glance.
- **Simplicity**: Focus on a single central concept or unique graphic emblem. Avoid cluttered photographic details or small text.
- **Layered design**: Design with separate foreground and background layers to support dynamic system effects (parallax, lighting, depth).
- **Corner radius**: Do not apply rounding manually. Supply full-bleed square assets; the system or container applies corner masking.

### Branding
Express brand identity subtly:
- Do not plaster logos onto every screen or navigation bar.
- Let brand voice emerge naturally through typography, curated color accents, precise layout, and high-quality imagery.
- **Apply the brand/accent color judiciously**: use it for primary actions and status (unread badges, the selected tab), not every control. To express the brand through color, put it in the content layer where it scrolls beneath translucent chrome.
- **Keep standard patterns standard**: a distinctive look shouldn't change how common controls behave or where they live.
- **Third-party marks** (payment, sign-in, platform badges): use the official artwork unaltered (height is the only change), keep clear space ≥ 1/10 of the mark's height and the minimum size, give competing providers equal prominence, use exact trademarked names — and emphasize your product over the technology. *(See [Commerce, Accounts & Accessibility](./commerce-accounts-and-accessibility.md))*

### Motion
Use animation to communicate relationships, provide feedback, and orient people within your interface.
- Motion should be **purposeful** — it helps people understand what changed and why.
- Transitions should be **interruptible** — users should never wait for an animation to finish before acting.
- Respect **reduced-motion preferences** — provide a parallel experience that uses opacity fades instead of spatial movement.
- **Spatial continuity** — surfaces spring from their source (a menu pops out of its button, an action sheet from the tapped control) and shared controls morph between states instead of cross-fading.

### Haptics
- Use each standard pattern only for its established meaning — *notification* (success/warning/error), *impact* (light → heavy, soft, rigid), *selection* (value changing).
- Keep cause → effect consistent; match haptic sharpness and intensity to the animation; prefer short haptics for discrete events.
- Don't overuse (the best haptics are missed only when turned off), always make them optional, and avoid vibrating during camera/mic/gyro use.

*(Full vocabulary + web fallback: [Patterns Extended › Haptics](./patterns-extended.md))*

### Privacy
Design with privacy as a core value:
- Only request permissions when the feature that needs them is being used — never on first launch.
- Explain clearly why you need access before prompting.
- Give people granular control over what they share.

*(Full chapters: [Foundations](./foundations.md))*

---

---

## 3. Patterns

### Modality
Modality restricts people to a focused task until they complete or dismiss it. Use sparingly — only when focused attention is truly necessary.
- Prefer non-modal, inline interactions whenever possible.
- Always provide a clear, visible way to dismiss a modal.
- Keep modal tasks self-contained and concise.

### Navigation & Structure
- **Flat navigation**: Each top-level category is accessible from a tab bar or equivalent.
- **Hierarchical navigation**: Drill-down from general to specific with a clear back path.
- **Content-driven navigation**: Content itself provides the navigation path (e.g., linked pages, cards).

### Feedback
Provide visible, audible, or haptic responses to every user action. Silence breeds uncertainty.
- Confirm destructive actions with clear, unambiguous prompts.
- Use inline validation rather than post-submission error lists.
- Display progress for operations that take more than ~1 second.

### Loading
- Show content as soon as it's available — don't wait for the full dataset.
- Use skeleton screens or subtle activity indicators rather than blank screens.
- If loading fails, explain why and offer a retry path.

### Onboarding
Get people into your product as fast as possible:
- Demonstrate value immediately rather than showing tutorial carousels.
- Defer sign-up until the user has experienced enough value to justify creating an account.
- Use progressive disclosure — teach features in context, when they're first needed.

### Searching
- Place search controls where people expect them (prominently, top of screen/page).
- Show recent and suggested queries.
- Display results instantly as the user types (live filtering).
- Handle empty results gracefully with suggestions.
- **Placement is decided by two questions — how do people navigate, and what is the search scope?** Phone: bottom toolbar field preferred (rises above the keyboard); top toolbar when the bottom is occupied; a *search tab* for global search (standard tab with suggestions for exploratory apps, prominent/button tab that opens the keyboard instantly when people know what they want); inline under the title for one collection. Tablet/desktop: trailing toolbar field, top of sidebar (filters the sidebar), or a search tab/section.
- **Keep the anatomy** even when branded: magnifying glass, scoped placeholder ("Search Albums"), clear button, Cancel.
- **Start broad, then narrow**: scope bar for locations/accounts, contextual filters, tokens for combinable natural-language filters (pair with visible filters — tokens are less discoverable). Recents must be removable; predicted completion text is visually distinct; the no-results view echoes the query.

### Paywalls, Subscriptions & Checkout
- **Value before payment:** let people experience the product first; prompt at relevant moments (nearing a free limit), never on launch; market subscriptions only to non-subscribers.
- **Price clarity:** show the total billing price and period for every option; explain trials plainly (length, what happens after, how to cancel); clear, comparable tiers.
- **Easy exit:** subscription management and cancellation always easy to find; a retention offer is fine, obstruction is not.
- **Checkout:** collect choices (size, shipping, pickup) *before* the payment sheet; prefer wallet-provided details; **no forced account creation before purchase**; short line items for fees, discounts, and recurring charges; show the result, then a confirmation.
- **Sign-in:** ask only in exchange for value and as late as possible; never demand a password with federated sign-in; mark optional fields; welcome people and show signed-in state.

*(See [Commerce, Accounts & Accessibility › Screen Readers](./commerce-accounts-and-accessibility.md))*

### Settings
- Minimize the number of settings — make smart defaults.
- Group related settings logically.
- Provide immediate visual feedback when a setting changes.

### Entering Data
- Minimize manual input — use pickers, defaults, autofill, and smart suggestions.
- Use input-appropriate keyboards and controls (numeric pad for phone numbers, date pickers for dates).
- Validate inline and in real-time, not after submission.

### Drag and Drop
- Make draggable items visually obvious during a drag session.
- Provide a clear visual drop target.
- Support both touch and pointer-based drag interactions.

### Undo and Redo
- Make undo discoverable and available for all significant actions.
- Support multi-level undo rather than single-step.
- For destructive actions, prefer a grace period ("Undo" toast) over a confirmation dialog.

### Live Content & Active Sessions
- Live content one tap (or zero) from launch, visibly marked as live, with progress for in-progress programs; instant visual feedback on channel change.
- During an active session (workout, recording, navigation) show only session-relevant data and big pause/stop controls, a distinct "active" appearance, a closing summary, and auto-discard accidental seconds-long sessions.

*(Full patterns: [Patterns Reference](./patterns.md) · [Patterns Extended](./patterns-extended.md) — haptics, search placement, live content, active sessions)*

---

---

## 4. Components

### Menus & Actions
- **Buttons**: Provide clear, concise labels. Use hierarchy (primary/secondary/tertiary) to convey relative importance.
- **Menus**: Group related actions logically. Use separators between groups. Place destructive actions at the bottom, visually distinguished (red).
- **Context menus**: Reveal on right-click / long-press. Include the most relevant actions for the current context.
- **Toolbars**: Place frequently-used actions in a toolbar. Use icons with text labels, or icons alone with accessible names.
  - Group items **by function and frequency**; grouped items share one background. Don't group an icon button with a text button (reads as one control); text buttons get their own container.
  - A crowded bar is a cue to cut — move secondary actions into a More menu. The primary action (Done) sits apart and tinted.
  - A title (not a menu or logo) answers *where am I*; the bar's actions answer *what can I do here*.

### Navigation & Search
- **Tab bars**: Use for top-level flat navigation between 3–5 sections. Each tab should represent a distinct category.
  - Tabs navigate; they never perform actions (no "Add" tab). A dedicated **Search tab** is the global entry point in tabbed apps.
  - Accessories above the tab bar are for persistent features (a mini player) — never screen-specific actions like Checkout.
  - The bar may *minimize* while scrolling content; it must not disappear on drill-down. On larger widths it can morph into a sidebar.
- **Sidebars**: Use on larger displays for persistent navigation. Sidebars can collapse to reveal more content.
- **Search fields**: Always visible or one tap away. Support live filtering, scoped search, and suggestions.

### Layout & Organization
- **Lists and tables**: The primary way to display structured collections. Support swipe actions, selection, reordering, and section headers.
- **Collections**: Grid-based layouts for visual content. Support multiple column configurations.
- **Split views**: Side-by-side master-detail for wider displays. Collapse to stacked navigation on narrow displays.
- **Labels**: Concise descriptive text for controls and data. Support dynamic text sizing.

### Presentation
- **Alerts**: Modal interruptions for critical information or decisions. Use sparingly — two buttons maximum is ideal, three is the limit.
- **Action sheets**: Present a set of choices related to the current context. Actions should be concise verbs. They spring from the control that triggered them, not from a fixed screen edge.
- **Sheets**: Partial-screen overlays for self-contained subtasks. Dismissible by swipe or explicit button. Add a dimming layer only when the sheet *interrupts* the main flow; parallel tasks stay undimmed. Sheets become more opaque as they're dragged to full height.
- **Popovers**: Anchored floating panels for contextual tools or information. Dismiss on outside tap.
- **Scroll views**: Contain content larger than the visible area. Support pull-to-refresh, pagination, and momentum scrolling.
- **Windows**: Distinct, resizable content containers on desktop. Support standard resize, minimize, and close behaviors.

### Selection & Input
- **Text fields**: Single-line input with clear affordance. Provide placeholder text, clear buttons, and inline validation.
- **Pickers**: Scrolling wheels, date pickers, or dropdown selectors for constrained value sets.
- **Segmented controls**: Mutually exclusive options (2–5 segments). The entire set should be visible at once.
- **Sliders**: Continuous value selection within a range. Show current value. Use for imprecise adjustments (volume, brightness).
- **Steppers**: Increment/decrement a numeric value by a fixed amount. Show the current value alongside.
- **Toggles**: Binary on/off switches. The effect should be immediate — no "save" step required.

### Status
- **Progress indicators**: Determinate (bar with percentage) for known-length operations, indeterminate (spinner) for unknown. Always prefer determinate when possible.
- **Gauges**: Visual representation of a value within a defined range (battery, storage, scoring).

*(Full component specs: [Components Reference](./components.md))*

---

---

## 5. Inputs & Interactions

### Gestures
Gestures should feel natural and discoverable:
- **Tap**: Primary selection action. Show the pressed state on touch-down for immediacy, but commit on release so people can slide off to cancel .
- **Long press**: Reveal contextual actions (context menu, drag initiation). Provide haptic/visual feedback at activation threshold.
- **Swipe**: Navigate between pages, reveal actions on list items, dismiss sheets.
- **Pinch**: Zoom content in/out. Always allow returning to default scale.
- **Pan/Drag**: Direct manipulation of objects. Track 1:1 with the pointer — never lag behind.
- **Rotation**: Rotate objects using two fingers. Support in combination with pinch for compound gestures.

### Keyboards
- **Show the appropriate keyboard type** for each field (email, numeric, URL, search, default).
- **Support keyboard shortcuts** for power users on devices with hardware keyboards.
- **Don't obscure focused content** — scroll or resize the view so the active field remains visible above the keyboard.

### Pointing Devices
- **Hover states**: Provide visual feedback when a pointer hovers over interactive elements.
- **Right-click**: Surface context menus on secondary click.
- **Scroll**: Support smooth scroll, momentum, and scroll-to-top shortcuts.

### Focus & Selection
- **Keyboard focus**: Every interactive element must be reachable via Tab/arrow keys.
- **Focus indicator**: Clearly visible focus ring around the focused element. Never remove focus outlines without providing an alternative.
- **Selection**: Support single and multi-selection patterns. Provide select-all and clear-selection shortcuts.

### Game Controls
- Support standard gamepad layouts (d-pad, action buttons, triggers, thumbsticks).
- Allow full remapping of controls for accessibility.
- Provide on-screen equivalents for touch-only devices.

### Fluid Motion & Spring Physics (Designing Fluid Interfaces)
- **Response**: Highlight on pointer-down (eliminate the 300ms delay). Continuous 1:1 position updates throughout the gesture.
- **Direct Manipulation**: Respect user grab offset. Never snap an object's center to the touch point.
- **Interruptibility (Core Principle)**: Never lock user input during an animation. Animate from the live computed presentation value, not the target value. Blend velocities when reversing mid-flight.
- **Apple's 2-Parameter Spring Model**:
  - *Damping Ratio ($\zeta$)*: `1.0` = critically damped (zero bounce, default for standard UI); `0.8` = underdamped (slight bounce, reserved for momentum releases).
  - *Response ($T$)*: Speed in seconds (Move/reposition: `0.40s`, Sheet/drawer: `0.30s`, Button press: `0.15s`).
- **Momentum Projection**: Project resting position from release velocity using exponential decay: $\text{project}(v) = (v/1000) \cdot d / (1-d)$ with $d \approx 0.998$.
- **Rubber-Banding**: Resistance past boundaries: $f(x) = (x \cdot d \cdot c) / (d + c \cdot |x|)$ with $c \approx 0.55$.

*(Full input & motion specs: [Inputs Reference](./inputs.md) | [Fluid Motion Reference](./fluid-motion-and-physics.md))*

---

---

## 6. Evaluation, Process & Prototyping

### The Apple Design Awards 6-Pillar Rubric
Apple evaluates world-class software against six core categories:
1. **Delight and Fun**: Memorable, engaging, and satisfying interactions. Clever simplicity, personality, tactility, and Easter eggs that make the app a pleasure rather than a chore.
2. **Inclusivity**: A great experience for all reflecting diverse backgrounds, abilities, and languages. Scalable fonts, high contrast, differentiating without color, screen reader semantics, and low cognitive load.
3. **Innovation**: State-of-the-art experiences through novel workflows and fresh paradigms that set the product apart in its genre.
4. **Interaction**: Intuitive interfaces and effortless controls tailored to the medium. Direct manipulation, 1:1 fluid physics without lag, and ergonomic input structures.
5. **Social Impact**: Meaningful improvements to lives, digital well-being, respect for human time/attention, and ethical privacy by design.
6. **Visuals and Graphics**: Stunning imagery, skillful layout, distinctive typography, and purposeful animations that lend to a cohesive theme.

### The 10 Essential Design Principles
*From Apple Design Evangelism (serving human needs for safety, meaning, achievement, and joy):*
1. **Wayfinding**: Every screen must answer 5 spatial questions: *Where am I? Where can I go? What will I find when I get there? What's nearby? How do I get out?*
2. **Feedback**: 4 distinct types: *Status* (current state), *Completion* (reassurance action succeeded), *Warning* (alerting before damage), *Error & Intent Inferencing* (inline real-time guidance; auto-correcting benign typos rather than throwing modal errors).
3. **Visibility**: Surface primary controls and critical status directly in plain sight. Balance visibility against density to avoid cognitive overload.
4. **Consistency**:
   - *External*: Respect conventions users already know from the platform and real world. Inconsistencies on simple icons/buttons trip users up.
   - *Internal*: Cohesion across screens—consistent icon strokes, typographic scale, and identical control behaviors signal deep craftsmanship.
5. **Mental Models**: Systems are intuitive when reality matches user expectations, and unintuitive when they conflict. Changing ingrained mental models is high-risk—only deviate when the innovation is objectively superior.
6. **Proximity**: Distance implies connection. Place controls adjacent to the objects or views they manipulate.
7. **Grouping**: Visually cluster related controls using whitespace, containers, and dividers to provide structural clarity.
8. **Mapping**: Controls should mirror the physical shape and movement of what they affect (horizontal sliders for width, dials for rotation, direct manipulation over abstract buttons).
9. **Affordance**: Visual and physical cues (depth, rounded corners, pill shapes, hover states, subtle bounce animations) that make interaction possibilities obvious.
10. **Progressive Disclosure & 80/20 Rule**: 80% of users need only 20% of features. Keep the top 20% visible and accessible, tucking the remaining 80% behind secondary disclosure.

### The 4 Design Aspirations
1. **Simple**: Does not try to do more than it needs to do; does one thing exceptionally well; saves mental energy for real life.
2. **Stunning**: Visual, interactive, and motion polish where touch and animation align 1:1; active discovery over intrusive tooltips.
3. **Timeless**: Built for durability over trends; avoids visual fads to stay elegant and functional 5–10 years later.
4. **Positive Impact**: Software that creates a substantial positive effect on user well-being, productivity, or creativity.

### Field Rules from Design Evangelism
- **When design feels "off"**: Step away and articulate the problem out loud to someone else. Describing the dilemma in plain words almost always identifies the broken assumption.
- **The 3-Tier Clutter Triage**: Map all proposed features to user goals into 3 strict tiers:
  1. *Must be visible constantly* (orientation & core primary verbs).
  2. *Progressive disclosure* (accessible within 1–2 taps or detail views).
  3. *Eliminate completely* (superfluous noise).
- **Single Action Tint System**: Reserve one clear accent color exclusively for actionable controls. Non-interactive elements must never use the action tint.
- **Navigation Hygiene**: Never hide persistent tab bars or primary navigation on drill-down subpages (only temporary modal sheets may cover it). Always label tabs — icon-only tabs cause ambiguity without saving vertical space (Minimizing the bar while scrolling is fine; removing it is not.)
- **The Three Screen Questions**: every screen answers *Where am I? What can I do? Where can I go from here?* at first glance — a polished screen can still fail all three.
- **IA Loop**: list everything the app does → imagine when/where/why people use it → remove, rename, and group. Group large content sets by *time* (recent, seasonal), *progress* (drafts, continue watching), or *patterns* (related items).
- **Squint Test**: blur your eyes — the heaviest, most colorful element should be the most important one.
- **Keyboard Shortcut Ergonomics**:
  - Default to a single modifier key (`Cmd`/`Ctrl` as the primary thumb anchor).
  - Use the first letter of the verb for memorability.
  - Favor keys in the natural ergonomic finger cluster: `Q, W, E, A, S, D, O, P`.

### Prototyping Methodology
- **"Make things, show them to people, learn from their feedback!"**: Keep prototyping cycles fast, light, and continuous.
- **Question-Driven Prototypes**: Every prototype must exist to answer a single specific unknown. Never prototype just to add polish prematurely.
- **Speed over Fidelity ("Fake It Till You Make It")**: Make the least amount needed to learn something. Use low-tech interactive sketches, slide animations, or throwaway code spikes before investing in production code.
- **Parallel Directions with Toggles**: Instead of debating competing designs in meetings, keep both branches active with a runtime toggle or slider to let testers feel the difference side-by-side.
- **Objective Feedback**: Frame critique around user communication, not personal taste (e.g., *"Blue communicates the actionable state more clearly than red"* rather than *"I don't like red"*).
- **The "Two or Three Hearts" Rule**: When feature creep sets in, ruthlessly focus on the 2 or 3 interactions people loved most and cut the rest.

*(Full rubric, 10 principles & interview transcripts: [Design Process & Rubric Reference](./design-process-and-rubric.md))*

---
