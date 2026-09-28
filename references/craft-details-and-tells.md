# Craft Floor: Surface Modes, Browser Details & Default Tells

Apple's **Craft** principle says nothing is random: every spacing, color, and timing value should be a choice you can defend. This file applies that to three places where generated and template UIs most often fall short:
- the wrong level of expression for the page;
- details the browser draws when nobody styles them;
- decoration added by reflex.

Use it while building and as the polish phase of an audit.

---

## 1. Know the Surface

Apple's own work spans registers: product pages that persuade, apps people operate, documentation people read. The principles are the same; the amount of expression isn't. Name the surface before choosing type, color, and motion.

| Surface | The visitor wants to… | Expression | Defaults |
| :--- | :--- | :--- | :--- |
| **Operate** — app UI, dashboards, settings, editors, admin | finish a task | Restrained. Brand lives in precise details, the one action tint, and the content | System font, calm density, standard components, motion only as feedback |
| **Persuade** — landing, pricing, product, and campaign pages | understand, believe, act | One authored moment per page; larger type contrast; the product itself as the image | A brand display face for headlines is fine; one primary call to action per view; real product visuals over decoration |
| **Read** — docs, articles, help, changelogs | understand something | Typography carries it | 45–75 character measure, clear heading levels, wayfinding (contents, breadcrumbs), motion only as feedback |
| **Showcase** — galleries, portfolios, media | look at the work | Deference: the work leads, the UI recedes | Neutral chrome, generous space, controls that appear on demand |

Choose by the **page, not the company**: a developer tool's pricing page is Persuade, and a marketing site's help center is Read.

**Existing style wins.** If the project already has a coherent visual system, extend it. That system might live in tokens in code, a `DESIGN.md`, a brand guide, or simply consistent screens. Apply Pineapple's principles inside it and don't re-skin it with Apple's values (see [Project Memory](./project-memory.md)). Redesign only when asked. Anything the brief pins down beats every default here, whether a font, a palette, or an era.

---

## 2. The Details Nobody Draws

Browsers ship defaults for text selection, the caret, native controls, scrollbars, focus, and link underlines. Unstyled, they're the cheapest sign that a page was assembled rather than designed. Apple's platforms draw the insertion point and text selection in the accent color, and a web app should do the same with its action tint.

```css
:root {
  color-scheme: light dark;               /* only when you ship both themes: native controls, form fields, and scrollbars follow */
  accent-color: var(--action-tint);       /* checkboxes, radios, range sliders, progress bars */
  caret-color: var(--action-tint);
  -webkit-text-size-adjust: 100%;         /* no automatic text inflation in landscape; pinch-zoom still works */
  text-size-adjust: 100%;
  -webkit-tap-highlight-color: transparent; /* only if every control has a designed :active state */
  scroll-padding-top: var(--sticky-header-height, 0px); /* anchor jumps and focused fields land below sticky headers */
}
::selection { background: color-mix(in srgb, var(--action-tint) 25%, transparent); }
:focus-visible { outline: 3px solid var(--action-tint); outline-offset: 2px; }
::placeholder { color: var(--label-secondary-text); opacity: 1; } /* Firefox dims placeholders by default */

h1, h2, h3 { text-wrap: balance; }        /* even heading lines */
p, li, figcaption { text-wrap: pretty; }  /* no one-word last lines (progressive enhancement) */
.prose { max-width: 65ch; }
a { text-underline-offset: 0.2em; text-decoration-thickness: from-font; }
.numeric, td.num, .kpi-value { font-variant-numeric: tabular-nums; }
img, video { max-width: 100%; height: auto; }  /* also set width/height or aspect-ratio so loading never shifts layout */

/* Scrolling panels inside the app (sidebars, tables, sheets). Leave the page scrollbar to the OS. */
.scroll-panel {
  overflow: auto;
  scrollbar-width: thin;
  scrollbar-color: var(--fill-primary) transparent;
  scrollbar-gutter: stable;          /* no layout jump when content starts to scroll */
  overscroll-behavior: contain;      /* scrolling a sheet doesn't scroll the page behind it */
}

/* Hover effects only where hover exists; otherwise a tap leaves a "stuck" hover */
@media (hover: hover) and (pointer: fine) {
  .row:hover { background: var(--fill-quaternary); }
}
```

```html
<html lang="en">  <!-- pronunciation, hyphenation, spellcheck, translation -->
<meta name="viewport" content="width=device-width, initial-scale=1">  <!-- never maximum-scale=1 or user-scalable=no -->
<meta name="theme-color" content="#ffffff" media="(prefers-color-scheme: light)">  <!-- tints browser UI where supported -->
<meta name="theme-color" content="#000000" media="(prefers-color-scheme: dark)">
<title>Invoices – Acme</title>  <!-- descriptive per page and state: the tab title is wayfinding -->
```

Rules:
- **Theme everything from tokens** so light, dark, and increased contrast follow automatically.
- **Never hide the scrollbar of content that scrolls** unless another visible control shows there's more, such as arrows or page dots.
- **Don't block text selection on content.** Use `user-select: none` only on controls where selecting by accident is noise: buttons, tab labels, drag handles.
- **Never disable zoom.** Prevent the mobile input-focus zoom with 16 px+ input text instead.
- **One icon system:** real icons in one weight matched to the text, never emoji or Unicode glyphs (see [Iconography](./iconography-and-symbols.md)).

---

## 3. Default Tells, and What to Do Instead

These are the category defaults that make generated and template interfaces look interchangeable. Each fails an Apple principle. Each also has a legitimate use, listed so the rule doesn't become a superstition. If you keep one, say why.

| Tell | Why it fails | Do instead | Legitimate when |
| :--- | :--- | :--- | :--- |
| **Decorative gradients** (purple→blue or indigo accents, gradient text, a gradient border on the "featured" card) | Color stops meaning anything (Simplicity); gradient text fails contrast at its lightest stop | One action tint on controls; emphasis from weight and size; mark the featured plan with a label and a tint border | One deliberate brand moment in a Persuade hero, with contrast checked at the lightest stop. Never in app UI, body text, buttons, or data |
| **Glow halos** (colored zero-offset shadows, radial "spotlight" meshes behind the hero) | Light doesn't behave that way (Craft), and the glow competes with the content (Deference) | A neutral, physically plausible shadow: small downward offset, soft blur, black at low opacity. Add depth only where layers really stack | Imagery or a product render that actually emits light |
| **Card-ception** (bordered cards inside bordered cards; the "ghost card": 1 px border plus a wide soft shadow) | Hierarchy should come from layout, spacing, and grouping, not stacked boxes | One container level. Separate groups with spacing, a grouped background, or a hairline: one cue, not three. If nesting is unavoidable, make the radii concentric | Genuinely separate objects: a card on a board you can drag, a floating sheet |
| **Icon tiles** (a colored rounded square with a glyph above every heading, feature card, or KPI) | Decoration posing as information: an icon with no job | Let the heading carry the section. Put an icon inline only where it identifies something or signals status | Long lists of peer destinations, where colored tiles speed up scanning (a Settings-style list) |
| **Emoji or Unicode as icons** | Weight, color, and rendering vary by platform | One icon library, one stroke weight, sized to the text | User-generated content and reactions |
| **An eyebrow on every section** (the small uppercase label above each heading) | Repetition that adds no information | Delete it; the heading stands alone | It carries information the heading doesn't: a product name above a tagline, "New", "Step 2 of 3". Once per region |
| **Identical feature grid** (3 or 6 same-size cards of icon, title, and two lines) | Treats unequal things as equal, so nothing leads | A list, a comparison, or a varied grid where size follows importance and each tile shows the actual product | Truly parallel items of equal weight: plan tiers, team members |
| **The same entrance everywhere** (every section fades up on scroll; everything staggers) | Motion without meaning that delays reading (Purpose) | Content visible by default; at most one authored moment per page; motion for feedback and continuity | A deliberate sequence that explains how the product works |
| **Side-stripe borders** (a thick colored `border-left` on cards, alerts, or list items) | Decoration standing in for a real status system | Show status as icon + label + tinted background, and selection as a fill or checkmark | Block quotes and code-diff gutters, where it's convention |
| **Gray text on color** (`#666` or `#888` on tinted or colored surfaces) | Muddy and low-contrast; ignores the surface | Derive secondary text from the surface's own foreground at reduced opacity, then check contrast. If it fails, darken the fill or drop the secondary text | — |
| **Invented proof** ("Trusted by 10,000+ teams", made-up logos, testimonials, metrics, ratings) | Fabricated claims mislead (Responsibility) | Real data, or clearly marked placeholders such as `[customer quote]`, plus a list of what needs real content | Sample data in a prototype, labeled as sample |
| **Dark by default because it looks "techy"** | Appearance is the person's choice | Follow `prefers-color-scheme` and ship both themes | Media, games, and pro tools where dark serves the content; still offer light if people read there |
| **Pills everywhere / over-rounding** (fully rounded cards; inputs and buttons with unrelated radii) | Radius no longer encodes structure | Capsules for touch controls, concentric radii for nested shapes, and card radii from one scale | — |
| **Decorative data** (sparklines, rings, and "hero metrics" with nothing behind them) | A chart that answers no question is noise; a fake number misleads | Show a chart only when it answers a question, and label the baseline | — |
| **`transition: all`, and bounce on everything** | Animates things that shouldn't move; bounce implies momentum that wasn't there | Name the properties; critically damped by default (see [Fluid Motion › Restraint](./fluid-motion-and-physics.md#12-restraint-when-not-to-animate)) | Bounce after a flick or throw |
| **A modal by reflex** | Interrupts without protecting anything (Agency) | Inline editing, a popover or sheet anchored to its source, or a new page | Focused subtasks that must be finished or abandoned |

---

## 4. Floors for Depth, Color, Type & Spacing

- **Shadows:** neutral, with a small downward offset and a soft blur, black at roughly 4–12% opacity. Larger surfaces sit higher, so they cast larger, softer shadows. Use one separation cue per edge: fill contrast, a hairline, *or* a shadow.
- **Grays:** Apple's grays carry a faint cool tint (`#F2F2F7`, and labels built from `rgb(60 60 67)`). Pure neutral `#888` looks dead beside them. The dark-mode base can be true black `#000` (Apple's primary dark background, good on OLED), with elevated surfaces lifting to `#1C1C1E` and `#2C2C2E`. Don't scatter extra near-blacks.
- **Headings:** more space above a heading than below it. The heading belongs to what follows (proximity). Keep groups tight inside and generous between.
- **Measure:** 45–75 characters for reading text (`max-width: 65ch`). Longer lines need more line height.
- **Display type:** tighten tracking as size grows (about −1% to −2.5% of the em; never tighter than −4%). Scale marketing display sizes with `clamp()` and cap them around 6 rem.
- **Secondary text:** Apple's light-mode secondary label (60% opacity) measures 3.4:1 on white and 3.3:1 on `#F2F2F7`. That's below Apple's own 4.5:1 minimum for text up to 17 pt, and below WCAG AA. For small text that carries information, use 75% (`--label-secondary-text`: 5.2:1 on white, 4.8:1 on `#F2F2F7`). Tertiary (30%, about 1.7:1) is only for disabled or decorative text. Dark-mode secondary already passes (5.3–6.4:1).
- **White on tinted fills:** white on system blue `#0088FF` is 3.5:1.
  - **Apple's rule** accepts 3:1 for bold text at any size.
  - **WCAG AA**, the legal bar for most websites, needs 4.5:1 unless text is at least 24 px, or at least 18.66 px bold.
  - **On the web,** fill buttons with small labels using the high-contrast blue `#1E6EF4` (4.6:1).
  - **Failing fills:** white fails every small-text threshold on the default green, orange, yellow, mint, teal, and cyan.

---

## 5. Before You Call It Done

Run these in one batched pass (see [Hardening & Review › Bounded passes](./hardening-and-review.md#3-verify-in-bounded-passes)):
- [ ] `color-scheme`, `accent-color`, caret, `::selection`, focus ring, and panel scrollbars are themed from tokens.
- [ ] No tell from §3 remains without a stated reason.
- [ ] Every text/background pair is ≥ 4.5:1 (3:1 for large text and UI parts). That includes secondary text, placeholders that carry information, and text on tinted fills.
- [ ] Content is real everywhere, and every placeholder is labeled and listed.
- [ ] Headings are balanced, body measure is ≤ 75 characters, and changing numbers use tabular figures.
- [ ] `lang` is set, zoom is allowed, and titles are descriptive.
