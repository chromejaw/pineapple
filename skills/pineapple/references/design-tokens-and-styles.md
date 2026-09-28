# Design Tokens, Typography Scale & Visual Styles

This reference defines the concrete implementation specifications, exact typography scales, dynamic color tokens, corner radii, and hit target metrics used in Apple design systems.

> Values reflect Apple's current (2025+) published specifications. Treat them as a proven reference system: adopt them directly, or keep the ratios and relationships while substituting your own brand values.

---

## 1. The Apple Typography Scale

Apple's typography system is built around optical hierarchy, size-specific tracking (letter spacing), and proportional leading (line height). When applying typography on the web or in applications, apply these exact values:

### Default Typography Specifications (phone/tablet, Large = default size)

All styles use the **Regular** weight except Headline (Semibold). The *emphasized* variant (bold trait) uses the weight in the "Emphasized" column. Tracking is the system font's (SF Pro) size-specific tracking at that point size.

| Text Style | Weight | Emphasized | Size | Leading | Tracking | CSS Implementation |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Large Title** | Regular | Bold | 34pt | 41pt | +0.40pt (+12/1000 em) | `font: 400 34px/41px var(--font-ui); letter-spacing: 0.40px;` |
| **Title 1** | Regular | Bold | 28pt | 34pt | +0.38pt (+14/1000 em) | `font: 400 28px/34px var(--font-ui); letter-spacing: 0.38px;` |
| **Title 2** | Regular | Bold | 22pt | 28pt | −0.26pt (−12/1000 em) | `font: 400 22px/28px var(--font-ui); letter-spacing: -0.26px;` |
| **Title 3** | Regular | Semibold | 20pt | 25pt | −0.45pt (−23/1000 em) | `font: 400 20px/25px var(--font-ui); letter-spacing: -0.45px;` |
| **Headline** | Semibold | Semibold | 17pt | 22pt | −0.43pt (−26/1000 em) | `font: 600 17px/22px var(--font-ui); letter-spacing: -0.43px;` |
| **Body** | Regular | Semibold | 17pt | 22pt | −0.43pt (−26/1000 em) | `font: 400 17px/22px var(--font-ui); letter-spacing: -0.43px;` |
| **Callout** | Regular | Semibold | 16pt | 21pt | −0.31pt (−20/1000 em) | `font: 400 16px/21px var(--font-ui); letter-spacing: -0.31px;` |
| **Subhead** | Regular | Semibold | 15pt | 20pt | −0.23pt (−16/1000 em) | `font: 400 15px/20px var(--font-ui); letter-spacing: -0.23px;` |
| **Footnote** | Regular | Semibold | 13pt | 18pt | −0.08pt (−6/1000 em) | `font: 400 13px/18px var(--font-ui); letter-spacing: -0.08px;` |
| **Caption 1** | Regular | Semibold | 12pt | 16pt | 0 | `font: 400 12px/16px var(--font-ui); letter-spacing: 0;` |
| **Caption 2** | Regular | Semibold | 11pt | 13pt | +0.06pt (+6/1000 em) | `font: 400 11px/13px var(--font-ui); letter-spacing: 0.06px;` |

```css
:root { --font-ui: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro", system-ui, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; }
```

Bold, left-aligned titles: titles in key moments (alerts, onboarding) read best **bolder and left-aligned**. Use the emphasized weight for screen titles and headers.

### The Golden Rule of Optical Tracking
Tracking is a function of **optical size**, not a single "bigger = tighter" line. SF Pro's published curve (points of tracking) is a good model for any optical-size font:

| Size (pt) | 6 | 8 | 10 | 11 | 12 | 13 | 15 | 17 | 20 | 22 | 24 | 28 | 34 | 48 | 64 | 80+ |
| :--- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| Tracking | +0.24 | +0.21 | +0.12 | +0.06 | 0 | −0.08 | −0.23 | −0.43 | −0.45 | −0.26 | +0.07 | +0.38 | +0.40 | +0.35 | +0.22 | 0 |

- **Small text (< 12pt) gets positive tracking** — letters would otherwise run together.
- **Text sizes (13–22pt) get negative tracking** — the text optical cut is loosely spaced by design.
- **At 20pt SF switches from its Text to its tightly drawn Display optical cut**, so tracking climbs back through zero by ~24pt, stays *positive* through display sizes, and decays to 0 by 80pt.
- **Never use a single fixed letter-spacing across all sizes**: Tracking is strictly size-dependent.
- **Using a custom or non-optical-size font?** The underlying principle still holds, but the numbers don't transfer: display sizes usually need *tightening* (≈ −1% to −2.5% em at 32–64px), small sizes *loosening* (≈ +1% to +3% em at ≤ 12px). Tune by eye per size.
- Some platforms apply size-specific tracking to their system font automatically; otherwise (web, custom fonts, mockups) set it explicitly per size.

### Dynamic Type Scale (Font Size / Leading by User Setting)

Users choose their preferred reading size. Layouts must scale proportionally:

| Style | xSmall | Small | Medium | **Large (default)** | xLarge | xxLarge | xxxLarge |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Large Title** | 31/38 | 32/39 | 33/40 | **34/41** | 36/43 | 38/46 | 40/48 |
| **Title 1** | 25/31 | 26/32 | 27/33 | **28/34** | 30/37 | 32/39 | 34/41 |
| **Title 2** | 19/24 | 20/25 | 21/26 | **22/28** | 24/30 | 26/32 | 28/34 |
| **Title 3** | 17/22 | 18/23 | 19/24 | **20/25** | 22/28 | 24/30 | 26/32 |
| **Headline / Body** | 14/19 | 15/20 | 16/21 | **17/22** | 19/24 | 21/26 | 23/29 |
| **Callout** | 13/18 | 14/19 | 15/20 | **16/21** | 18/23 | 20/25 | 22/28 |
| **Subhead** | 12/16 | 13/18 | 14/19 | **15/20** | 17/22 | 19/24 | 21/28 |
| **Footnote** | 12/16 | 12/16 | 12/16 | **13/18** | 15/20 | 17/22 | 19/24 |
| **Caption 1** | 11/13 | 11/13 | 11/13 | **12/16** | 14/19 | 16/21 | 18/23 |
| **Caption 2** | 11/13 | 11/13 | 11/13 | **11/13** | 13/18 | 15/20 | 17/22 |

### Accessibility Sizes (AX1–AX5)

| Style | AX1 | AX2 | AX3 | AX4 | AX5 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Large Title** | 44/52 | 48/57 | 52/61 | 56/66 | 60/70 |
| **Title 1** | 38/46 | 43/51 | 48/57 | 53/62 | 58/68 |
| **Title 2** | 34/41 | 39/47 | 44/52 | 50/59 | 56/66 |
| **Title 3** | 31/38 | 37/44 | 43/51 | 49/58 | 55/65 |
| **Headline / Body** | 28/34 | 33/40 | 40/48 | 47/56 | 53/62 |
| **Callout** | 26/32 | 32/39 | 38/46 | 44/52 | 51/60 |
| **Subhead** | 25/31 | 30/37 | 36/43 | 42/50 | 49/58 |
| **Footnote** | 23/29 | 27/33 | 33/40 | 38/46 | 44/52 |
| **Caption 1** | 22/28 | 26/32 | 32/39 | 37/44 | 43/51 |
| **Caption 2** | 20/25 | 24/30 | 29/35 | 34/41 | 40/48 |

Note how **body grows ~3× (17 → 53pt) while titles grow < 2× (34 → 60pt)**: hierarchy compresses at large sizes. Layouts must reflow (stack horizontally arranged items vertically, allow multi-line labels, drop decorative imagery) rather than scale.

Web: base everything on `rem` so the user's browser font size drives it, and emulate the steps with `font-size: clamp()` or a `:root` multiplier; test at 200% and 310% zoom.

### Desktop Text Styles (default size)

| Style | Desktop |
| :--- | :--- |
| Large Title | 26/32 Regular |
| Title 1 | 22/26 Regular |
| Title 2 | 17/22 Regular |
| Title 3 | 15/20 Regular |
| Headline | 13/16 **Bold** |
| Body | 13/16 Regular |
| Callout | 12/15 Regular |
| Subheadline | 11/14 Regular |
| Footnote | 10/13 Regular |
| Caption 1 / 2 | 10/13 Regular · 10/13 Medium |

Desktop density is real: **desktop body is 13pt, not 17pt.** A web app aimed at desktop productivity should use a 13–14px body, not a phone-sized one.

---

## 2. Semantic Color System (Light & Dark Mode Tokens)

Never use raw hex color literals for interface structure. Use semantic tokens that automatically adapt to light and dark appearances:

```css
:root {
  /* System Backgrounds */
  --system-background-primary: #ffffff;
  --system-background-secondary: #f2f2f7;
  --system-background-tertiary: #ffffff;

  /* Grouped Backgrounds (for table rows, inset cards) */
  --grouped-background-primary: #f2f2f7;
  --grouped-background-secondary: #ffffff;
  --grouped-background-tertiary: #f2f2f7;

  /* Labels (Text hierarchy) */
  --label-primary: #000000;
  --label-secondary: rgba(60, 60, 67, 0.60);
  --label-tertiary: rgba(60, 60, 67, 0.30);
  --label-quaternary: rgba(60, 60, 67, 0.18);
  /* Text-safe secondary label: Apple's 60% is 3.4:1 on white; 75% is 5.2:1 (4.8:1 on #f2f2f7) */
  --label-secondary-text: rgba(60, 60, 67, 0.75);

  /* Separators */
  --separator: rgba(60, 60, 67, 0.29);
  --separator-opaque: #c6c6c8;

  /* Fills (for search bars, progress tracks, chips) */
  --fill-primary: rgba(120, 120, 128, 0.20);
  --fill-secondary: rgba(120, 120, 128, 0.16);
  --fill-tertiary: rgba(118, 118, 128, 0.12);
  --fill-quaternary: rgba(116, 116, 128, 0.08);

  /* System Accent Tints (Light Mode) — current Apple palette */
  --tint-red: #ff383c;
  --tint-orange: #ff8d28;
  --tint-yellow: #ffcc00;
  --tint-green: #34c759;
  --tint-mint: #00c8b3;
  --tint-teal: #00c3d0;
  --tint-cyan: #00c0e8;
  --tint-blue: #0088ff;
  --tint-indigo: #6155f5;
  --tint-purple: #cb30e0;
  --tint-pink: #ff2d55;
  --tint-brown: #ac7f5e;

  /* Gray ramp */
  --gray: #8e8e93; --gray-2: #aeaeb2; --gray-3: #c7c7cc; --gray-4: #d1d1d6; --gray-5: #e5e5ea; --gray-6: #f2f2f7;

  /* Active Interactive Tint */
  --action-tint: var(--tint-blue);
  /* Text-safe tint (≥ 4.5:1 on white) for links and small tinted text */
  --action-tint-text: #1e6ef4;
  /* Fill for buttons with white labels: white on #0088ff is 3.5:1, on #1e6ef4 4.6:1 */
  --action-fill: #1e6ef4;
}

@media (prefers-color-scheme: dark) {
  :root {
    /* System Backgrounds */
    --system-background-primary: #000000;
    --system-background-secondary: #1c1c1e;
    --system-background-tertiary: #2c2c2e;

    /* Grouped Backgrounds */
    --grouped-background-primary: #000000;
    --grouped-background-secondary: #1c1c1e;
    --grouped-background-tertiary: #2c2c2e;

    /* Labels (Dark Mode) */
    --label-primary: #ffffff;
    --label-secondary: rgba(235, 235, 245, 0.60);
    --label-tertiary: rgba(235, 235, 245, 0.30);
    --label-quaternary: rgba(235, 235, 245, 0.16);
    --label-secondary-text: rgba(235, 235, 245, 0.60); /* already 5.3–6.4:1 on dark backgrounds */

    /* Separators */
    --separator: rgba(84, 84, 88, 0.65);
    --separator-opaque: #38383a;

    /* Fills */
    --fill-primary: rgba(120, 120, 128, 0.36);
    --fill-secondary: rgba(120, 120, 128, 0.32);
    --fill-tertiary: rgba(118, 118, 128, 0.24);
    --fill-quaternary: rgba(116, 116, 128, 0.18);

    /* System Accent Tints (Dark Mode) */
    --tint-red: #ff4245;
    --tint-orange: #ff9230;
    --tint-yellow: #ffd600;
    --tint-green: #30d158;
    --tint-mint: #00dac3;
    --tint-teal: #00d2e0;
    --tint-cyan: #3cd3fe;
    --tint-blue: #0091ff;
    --tint-indigo: #6d7cff;
    --tint-purple: #db34f2;
    --tint-pink: #ff375f;
    --tint-brown: #b78a66;

    --gray: #8e8e93; --gray-2: #636366; --gray-3: #48484a; --gray-4: #3a3a3c; --gray-5: #2c2c2e; --gray-6: #1c1c1e;
    --action-tint-text: #5cb8ff;
  }
}

/* Increased Contrast (prefers-contrast: more) — high-contrast variants */
@media (prefers-contrast: more) {
  :root {
    --tint-red: #e9152d; --tint-orange: #c55300; --tint-yellow: #a16a00; --tint-green: #008932;
    --tint-mint: #008575; --tint-teal: #008198; --tint-cyan: #007eae; --tint-blue: #1e6ef4;
    --tint-indigo: #564ade; --tint-purple: #b02fc2; --tint-pink: #e7124d; --tint-brown: #956d51;
    --gray: #6c6c70; --gray-2: #8e8e93; --gray-3: #aeaeb2; --gray-4: #bcbcc0; --gray-5: #d8d8dc; --gray-6: #ebebf0;
  }
}
@media (prefers-contrast: more) and (prefers-color-scheme: dark) {
  :root {
    --tint-red: #ff6165; --tint-orange: #ffa056; --tint-yellow: #fedf43; --tint-green: #4ad968;
    --tint-mint: #54dfcb; --tint-teal: #3bddec; --tint-cyan: #6dd9ff; --tint-blue: #5cb8ff;
    --tint-indigo: #a7aaff; --tint-purple: #ea8dff; --tint-pink: #ff8ac4; --tint-brown: #dba679;
    --gray: #aeaeb2; --gray-2: #7c7c80; --gray-3: #545456; --gray-4: #444446; --gray-5: #363638; --gray-6: #242426;
  }
}
```

### System Color Reference with Contrast

| Color | Light | Dark | IC Light | IC Dark | Light on white | IC Light on white | Dark on black |
| :--- | :--- | :--- | :--- | :--- | :-: | :-: | :-: |
| Red | `#FF383C` | `#FF4245` | `#E9152D` | `#FF6165` | 3.6 | 4.6 | 6.1 |
| Orange | `#FF8D28` | `#FF9230` | `#C55300` | `#FFA056` | 2.3 | 4.6 | 9.4 |
| Yellow | `#FFCC00` | `#FFD600` | `#A16A00` | `#FEDF43` | 1.5 | 4.6 | 14.9 |
| Green | `#34C759` | `#30D158` | `#008932` | `#4AD968` | 2.2 | 4.5 | 10.4 |
| Mint | `#00C8B3` | `#00DAC3` | `#008575` | `#54DFCB` | 2.1 | 4.6 | 11.8 |
| Teal | `#00C3D0` | `#00D2E0` | `#008198` | `#3BDDEC` | 2.2 | 4.6 | 11.3 |
| Cyan | `#00C0E8` | `#3CD3FE` | `#007EAE` | `#6DD9FF` | 2.2 | 4.6 | 11.9 |
| Blue | `#0088FF` | `#0091FF` | `#1E6EF4` | `#5CB8FF` | 3.5 | 4.6 | 6.5 |
| Indigo | `#6155F5` | `#6D7CFF` | `#564ADE` | `#A7AAFF` | 5.1 | 6.1 | 6.0 |
| Purple | `#CB30E0` | `#DB34F2` | `#B02FC2` | `#EA8DFF` | 4.2 | 5.2 | 5.8 |
| Pink | `#FF2D55` | `#FF375F` | `#E7124D` | `#FF8AC4` | 3.6 | 4.6 | 6.0 |
| Brown | `#AC7F5E` | `#B78A66` | `#956D51` | `#DBA679` | 3.5 | 4.6 | 6.8 |

**Takeaway:** the default light tints are tuned for glyphs, fills, and large/bold text — most fall **below 4.5:1 on white**. The Increased Contrast light variants sit almost exactly at 4.5:1. Use them (or `--action-tint-text`) for small tinted text and links; use the defaults for icons, controls with white glyphs at large size, and fills.

**Three more traps on the web:**
- **Secondary text:** Apple's light-mode secondary label (`rgba(60,60,67,0.6)`) is **3.4:1 on white and 3.3:1 on `#F2F2F7`**. That's below Apple's own 4.5:1 minimum for text up to 17 pt, and below WCAG AA. Use `--label-secondary-text` (75%: 5.2:1 / 4.8:1) for small text that carries information. Keep tertiary (30%, ~1.7:1) for disabled or decorative text. Dark-mode secondary passes as-is (5.3–6.4:1).
- **White labels on tinted fills:** contrast is symmetric, so white on `#0088FF` is also 3.5:1.
  - **Apple's table** accepts 3:1 for bold text at any size, so bold white labels on system blue pass Apple's rule.
  - **WCAG AA**, the bar most websites are held to, needs 4.5:1 below 24 px regular or 18.66 px bold.
  - **Fix:** fill buttons that have small white labels with `--action-fill` (`#1E6EF4`, 4.6:1). It also works in dark mode (3.7:1 against `#1C1C1E`).
  - **Failing fills:** white fails small text on the default green, orange, yellow, mint, teal, and cyan.
- **Tinted text on gray:** `#1E6EF4` is 4.6:1 on white but only 4.1:1 on the grouped gray `#F2F2F7`. For small tinted text on gray surfaces, use `#1A66E0` (4.7:1 on gray, 5.2:1 on white).

The older palette (`#007AFF` blue, `#FF3B30` red, `#FF9500` orange…) is superseded but still valid if you prefer it.

---

## 3. Touch Targets, Margins & Safe Areas

### Minimum Hit Targets (44×44pt Rule)
Touch targets must measure at least **44×44pt** (pointer targets at least **24×24pt**). When visual button elements are smaller than 44px (e.g. 24px icon buttons), expand the hit boundary invisibly using pseudo-elements:

```css
/* Expand small icon button tap targets without changing visual size */
.icon-button {
  position: relative;
  width: 24px;
  height: 24px;
}

.icon-button::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  min-width: 44px;
  min-height: 44px;
  width: 100%;
  height: 100%;
}
```

Defaults/minimums by context: touch (phone/tablet, touch web) 44 / 28pt · pointer (desktop app, desktop web) 28 / 20pt, never below the WCAG 2.2 floor of 24×24 CSS px. See [Device Contexts](./platforms-and-contexts.md).

### Layout Margins & Insets
- **Compact Width (Phones)**: Minimum **16pt** screen edge margins.
- **Regular Width (Tablets, Desktops)**: Minimum **20pt** screen edge margins.
- **Cards and compact modules**: 16pt standard inner padding; 11–12pt for tight internal groupings.
- **Safe Area Insets**:
  ```css
  padding-top: max(16px, env(safe-area-inset-top));
  padding-bottom: max(16px, env(safe-area-inset-bottom));
  padding-left: max(16px, env(safe-area-inset-left));
  padding-right: max(16px, env(safe-area-inset-right));
  ```
- **Reserved regions** (camera cutouts, folds/hinges) extend safe areas dynamically — see [Adaptive Layout & Foldables](./adaptive-layout-and-foldables.md).

---

## 4. Corner Radius & Continuous Curvature (Squircles)

Apple uses continuous curvature (squircle) rounding rather than simple geometric circular arcs. This eliminates the abrupt tangent change between straight edge and curve.

```css
:root {
  --radius-xs: 6px;    /* Badges, tags */
  --radius-sm: 8px;    /* Stepper, segmented segments */
  --radius-md: 10px;   /* Text fields, standard buttons (dense/desktop) */
  --radius-lg: 14px;   /* Modals, popovers */
  --radius-xl: 18px;   /* Cards, sheets */
  --radius-2xl: 24px;  /* Floating panels */
  --radius-full: 9999px; /* Capsule pills, circular action buttons, touch controls */
}
/* Progressive enhancement for true continuous corners where supported */
@supports (corner-shape: squircle) { .squircle { corner-shape: squircle; } }
```

### Concentricity
Radii are **derived**, not picked per component. Three shape types:
- **Fixed** — constant radius (the scale above).
- **Capsule** — radius = ½ height; the default for touch controls, bars, sliders, switches.
- **Concentric** — radius = parent radius − inset padding, so nested shapes share a center.

```css
.container { --outer: 26px; --inset: 10px; border-radius: var(--outer); padding: var(--inset); }
.container > * { border-radius: max(var(--outer) - var(--inset), var(--radius-xs)); } /* concentric + fallback */
```

Pinched (too round) or flared (too square) inner corners signal a non-concentric shape. Dense desktop UIs keep rounded rectangles for small/medium controls; capsules for large/standout ones. Full rules: [Materials & Glass › Shape](./materials-and-glass.md).

---

## 5. Translucent Materials & Depth

Two families: **glass** for the floating functional layer (bars, controls, menus) and **standard materials** (ultra-thin / thin / regular / thick blurs) for structure within the content layer. Never put glass in the content layer or glass on glass. Full rules and a glass recipe: [Materials & Glass](./materials-and-glass.md).

Translucent materials layer depth into an interface, indicating hierarchy while keeping the user connected to underlying context:

```css
/* Standard material — content-layer structure (e.g. a pinned section header) */
.material-regular {
  background: rgba(255, 255, 255, 0.72);
  backdrop-filter: blur(20px) saturate(180%);
  -webkit-backdrop-filter: blur(20px) saturate(180%);
}

@media (prefers-color-scheme: dark) {
  .material-regular {
    background: rgba(28, 28, 30, 0.72);
  }
}

/* Floating functional layer: prefer a scroll edge effect over a hard border */
.chrome-floating { border-bottom: none; }
.scroll-under-chrome { mask-image: linear-gradient(to bottom, transparent 0, #000 48px); }

/* Material Support for Accessibility (prefers-reduced-transparency) */
@media (prefers-reduced-transparency: reduce) {
  .material-regular, .chrome-floating {
    background: var(--system-background-primary) !important;
    backdrop-filter: none !important;
    -webkit-backdrop-filter: none !important;
  }
}
```

Always put **vibrant** (semantic label/fill) colors on materials; avoid the quaternary label on thin materials.

---

## 6. Apple Values vs. Material Values (pick one system, don't mix)

This skill teaches Apple's *philosophy*. Its numbers are Apple's defaults. When a product already follows Material Design (Android-first, Google ecosystem) or another system, keep that system's numbers and apply the philosophy on top.

| Concern | Apple (this skill's defaults) | Material 3 | Notes |
| :--- | :--- | :--- | :--- |
| Minimum touch target | 44×44 pt | 48×48 dp | Both exceed WCAG 2.2 AA (24×24 CSS px). |
| Phone body text | 17 pt, leading 22 | 16 sp (Body Large), line height 24 | Web: 16–17px. |
| Desktop body text | 13 pt | 14 sp | Dense productivity UIs. |
| Spacing base | 4/8 pt rhythm (16/20 margins) | 4 dp grid, 8 dp rhythm (16/24 margins) | Both effectively 8-based. |
| Corner radii | Concentric; capsules for touch controls | Scale 0/4/8/12/16/28/full | Both round more at larger sizes. |
| Depth | Translucent materials + glass for the control layer | Tonal elevation + shadows | Don't combine glass and heavy tonal elevation. |
| Accent | One action tint, neutral content | Dynamic color from a seed (primary/secondary/tertiary roles) | Both reserve the strongest color for primary actions. |
| Motion | Interruptible springs (critically damped by default) | Duration + easing tokens (emphasized, standard) | Springs map to durations ≈ 1.2–1.5 × response. |
| Interaction states | Highlight on press, dim when disabled | State layers: hover 8%, focus 10%, pressed 10%, dragged 16%; disabled 38% content / 12% container | See [Component States](./component-states-and-forms.md). |
| Primary navigation | Tab bar (≤5), sidebar on wide screens | Navigation bar (3–5), rail, drawer | Same idea: flat, labeled, persistent. |
| Primary action | Prominent tinted button in the toolbar or content | FAB or filled button | Only one primary action per view in either system. |

## 7. Exporting the Tokens

### JSON (design-token format)
```json
{
  "font": {
    "family": { "ui": "-apple-system, BlinkMacSystemFont, 'SF Pro Text', system-ui, 'Segoe UI', Roboto, sans-serif" },
    "style": {
      "largeTitle": { "size": 34, "lineHeight": 41, "weight": 400, "tracking": 0.40 },
      "title1":     { "size": 28, "lineHeight": 34, "weight": 400, "tracking": 0.38 },
      "title2":     { "size": 22, "lineHeight": 28, "weight": 400, "tracking": -0.26 },
      "title3":     { "size": 20, "lineHeight": 25, "weight": 400, "tracking": -0.45 },
      "headline":   { "size": 17, "lineHeight": 22, "weight": 600, "tracking": -0.43 },
      "body":       { "size": 17, "lineHeight": 22, "weight": 400, "tracking": -0.43 },
      "callout":    { "size": 16, "lineHeight": 21, "weight": 400, "tracking": -0.31 },
      "subhead":    { "size": 15, "lineHeight": 20, "weight": 400, "tracking": -0.23 },
      "footnote":   { "size": 13, "lineHeight": 18, "weight": 400, "tracking": -0.08 },
      "caption1":   { "size": 12, "lineHeight": 16, "weight": 400, "tracking": 0 },
      "caption2":   { "size": 11, "lineHeight": 13, "weight": 400, "tracking": 0.06 }
    }
  },
  "color": {
    "light": { "bg": "#FFFFFF", "bg2": "#F2F2F7", "label": "#000000", "label2": "rgba(60,60,67,0.6)", "label2Text": "rgba(60,60,67,0.75)", "separator": "rgba(60,60,67,0.29)", "tint": "#0088FF", "tintText": "#1E6EF4", "fill": "#1E6EF4", "red": "#FF383C", "green": "#34C759", "orange": "#FF8D28" },
    "dark":  { "bg": "#000000", "bg2": "#1C1C1E", "label": "#FFFFFF", "label2": "rgba(235,235,245,0.6)", "label2Text": "rgba(235,235,245,0.6)", "separator": "rgba(84,84,88,0.65)", "tint": "#0091FF", "tintText": "#5CB8FF", "fill": "#1E6EF4", "red": "#FF4245", "green": "#30D158", "orange": "#FF9230" }
  },
  "space": { "1": 4, "2": 8, "3": 12, "4": 16, "5": 20, "6": 24, "8": 32, "10": 40, "12": 48 },
  "radius": { "xs": 6, "sm": 8, "md": 10, "lg": 14, "xl": 18, "2xl": 24, "full": 9999 },
  "target": { "touch": 44, "pointer": 28, "min": 24 },
  "motion": {
    "spring": { "default": { "dampingRatio": 1.0, "response": 0.4 }, "bouncy": { "dampingRatio": 0.8, "response": 0.4 }, "snappy": { "dampingRatio": 1.0, "response": 0.2 } },
    "duration": { "instant": 100, "fast": 200, "base": 300, "slow": 450 },
    "easing": { "out": "cubic-bezier(0.23, 1, 0.32, 1)", "inOut": "cubic-bezier(0.77, 0, 0.175, 1)", "sheet": "cubic-bezier(0.32, 0.72, 0, 1)" },
    "never": ["keyboard shortcuts", "command palette open/close", "arrow-key list navigation"]
  }
}
```

### Tailwind (v3 `theme.extend`; v4: put the same values in `@theme`)
```js
// tailwind.config.js
module.exports = {
  darkMode: 'media',
  theme: {
    extend: {
      fontFamily: { ui: ['-apple-system', 'BlinkMacSystemFont', '"SF Pro Text"', 'system-ui', '"Segoe UI"', 'Roboto', 'sans-serif'] },
      fontSize: {
        'large-title': ['34px', { lineHeight: '41px', letterSpacing: '0.40px' }],
        'title-1': ['28px', { lineHeight: '34px', letterSpacing: '0.38px' }],
        'title-2': ['22px', { lineHeight: '28px', letterSpacing: '-0.26px' }],
        'title-3': ['20px', { lineHeight: '25px', letterSpacing: '-0.45px' }],
        headline: ['17px', { lineHeight: '22px', letterSpacing: '-0.43px', fontWeight: '600' }],
        body: ['17px', { lineHeight: '22px', letterSpacing: '-0.43px' }],
        callout: ['16px', { lineHeight: '21px', letterSpacing: '-0.31px' }],
        subhead: ['15px', { lineHeight: '20px', letterSpacing: '-0.23px' }],
        footnote: ['13px', { lineHeight: '18px', letterSpacing: '-0.08px' }],
        'caption-1': ['12px', { lineHeight: '16px' }],
        'caption-2': ['11px', { lineHeight: '13px', letterSpacing: '0.06px' }],
      },
      colors: {                      // wire to the CSS variables in §2 so dark mode and contrast modes work
        bg: 'var(--system-background-primary)', 'bg-2': 'var(--system-background-secondary)',
        label: 'var(--label-primary)', 'label-2': 'var(--label-secondary)', 'label-2-text': 'var(--label-secondary-text)', 'label-3': 'var(--label-tertiary)',
        separator: 'var(--separator)', tint: 'var(--action-tint)', 'tint-text': 'var(--action-tint-text)', 'tint-fill': 'var(--action-fill)',
      },
      borderRadius: { xs: '6px', sm: '8px', md: '10px', lg: '14px', xl: '18px', '2xl': '24px' },
      minHeight: { touch: '44px' }, minWidth: { touch: '44px' },
      transitionTimingFunction: { spring: 'cubic-bezier(0.2, 0.8, 0.2, 1)', out: 'cubic-bezier(0.23, 1, 0.32, 1)', 'in-out': 'cubic-bezier(0.77, 0, 0.175, 1)', sheet: 'cubic-bezier(0.32, 0.72, 0, 1)' },
      transitionDuration: { fast: '200ms', base: '300ms', slow: '450ms' },
    },
  },
};
```
Durations and easing curves are practical approximations of the springs in [Fluid Motion](./fluid-motion-and-physics.md), not Apple-published values. For pure-CSS springs sampled from Apple's model, see the `linear()` tokens in [Fluid Motion › Restraint](./fluid-motion-and-physics.md#12-restraint-when-not-to-animate). The browser details that should use these tokens (`accent-color`, caret, `::selection`, scrollbars) are covered in [Craft Floor](./craft-details-and-tells.md#2-the-details-nobody-draws).
