# Materials, Glass & the Two-Layer Interface

Distilled from Apple's materials and glass design-system guidance, generalized for any stack (web, Android, desktop, games).

The core idea: **an interface has two layers — content, and a floating functional layer (navigation + controls) above it.** Materials exist to keep those layers visually distinct while letting content stay visible.

---

## 1. The Two Layers

| Layer | What lives there | Material |
| :--- | :--- | :--- |
| **Functional (navigation) layer** | Tab bars, toolbars, sidebars, floating buttons, menus, popovers, sheets, alerts | Glass (translucent, refractive/blurred, floating) |
| **Content layer** | Lists, cards, text, media, app backgrounds | Opaque surfaces or *standard* materials (ultra-thin → thick blurs) |

Rules:
- **Glass belongs to the functional layer only.** A table view or card made of glass competes with the controls above it and muddies hierarchy. Keep content surfaces solid or use standard materials.
  - *Exception:* transient controls inside content (a slider thumb, a toggle knob) may *lift into* glass while being touched, then settle back — the resting state stays quiet, the active state comes alive.
- **Never stack glass on glass.** Anything placed on a glass surface uses fills, transparency, and vibrancy — it should read as a thin overlay that is part of the material, not a second pane.
- **Use glass sparingly on custom controls.** System components get it for free; each additional custom glass element dilutes attention away from content. Reserve it for the most important functional elements.
- **Remove old bar decoration.** Extra backgrounds, borders, and hairlines under bar buttons were valid in older designs; on glass they fight the material. Express hierarchy with **layout and grouping**, not decoration.
- **Extend content under the chrome.** Full-bleed backgrounds, hero images, and scroll views should run beneath toolbars, tab bars, and sidebars (a *background extension effect*). Keep text and controls in the content layer clear of those regions so they aren't distorted.
- **In steady states (e.g. first launch), avoid content intersecting glass.** Reposition or scale content so the initial composition has clean separation; overlap is for scrolling.

## 2. Variants: Regular vs. Clear

Never mix the two in one component set.

| | Regular (default) | Clear |
| :--- | :--- | :--- |
| Behavior | Fully adaptive: blurs, shifts luminosity, flips light/dark, deepens shadow over busy content | Permanently highly translucent; **not adaptive** |
| Use for | Everything, especially text-heavy components (alerts, sidebars, popovers, menus) | Controls floating over **media-rich** backgrounds (photos, video, maps, games) |
| Legibility aid | Built in | Requires a **dimming layer** under the glass |

Use *clear* only when all three hold:
1. The element sits over visually rich media.
2. The content can tolerate a dimming layer.
3. The foreground symbols/labels are bold and bright.

**Dimming guidance:** over bright content add a dark dim of about **35% opacity**; over already-dark content (or media players that ship their own scrim) no dim is needed. Small glass elements can use *localized* dimming so the rest of the media keeps its vibrancy.

## 3. How Good Glass Behaves

- **Lensing, not just scattering.** A plain blur frosts light; good glass bends and concentrates it. The edges refract what's behind, which defines the shape without an outline.
- **Adapts to what's behind it.** Shadow opacity rises over text and falls over flat light backgrounds; tint and dynamic range shift continuously to keep glyphs legible.
- **Size changes thickness.** Small elements (bars, buttons) flip between light and dark to match underlying content; large elements (menus, sidebars) adapt but do **not** flip — too much surface would flash. Larger glass reads as thicker: deeper shadow, stronger refraction, softer scatter.
- **Glyphs follow the glass.** Symbols and text on regular glass flip light/dark with it (monochrome by default) to maximize contrast.
- **Materializes, doesn't fade.** Glass appears/disappears by modulating its lensing, preserving the optical sense of an object.
- **Responds to touch by illuminating from within**, the glow spreading from the finger to nearby glass; it flexes like a gel during interaction.
- **Morphs between states.** Controls shape-shift from one context to the next as if on a single floating plane; a menu "pops open" from the button that summoned it, keeping the spatial link.
- **Recedes when focus leaves.** Inactive windows get subdued glass; a sheet dragged to full height becomes more opaque to signal deeper engagement.

## 4. Color on Glass

- Glass is colorless by default; it borrows color from what's behind it.
- **Tint sparingly** — only for elements with a distinct functional purpose: the primary action (e.g. *Done*, *Checkout*), status indicators. When everything is tinted, nothing stands out.
- **Tint the background, not the glyph**, to emphasize a primary action. Prominent buttons get the accent color as a colored-glass fill.
- Good tinting is not a flat fill: a chosen hue generates a *range of tones* mapped to the brightness underneath, like stained glass. A solid opaque fill "breaks" the material.
- **Want brand color? Put it in the content layer**, where it scrolls beneath the glass and gets picked up dynamically — not painted on every control.
- Supply light and dark variants of every custom color even if you ship one appearance; glass adapts between them.

## 5. Scroll Edge Effects

Where scrolling content meets floating controls, replace hard dividers with an edge effect that dissolves content into the background (or subtly dims it when the glass has gone dark).

- **Functional, not decorative.** Only use it where floating UI actually overlaps content. It clarifies the boundary; it doesn't block or darken like an overlay.
- **Soft** (default, touch UIs): gradual fade — good behind glass buttons and inputs.
- **Hard** (dense desktop UIs): a uniform, more opaque band — for interactive text, controls without their own backgrounds, or **pinned accessory views** like column headers.
- One edge effect per view; don't mix or stack soft and hard. In split views each pane may have its own — keep their heights aligned.

## 6. Shape: Concentricity

Device corners, windows, and controls share centers; UI radii are derived, not guessed.

Three shape types:
1. **Fixed** — constant radius.
2. **Capsule** — radius = ½ height. Naturally concentric; the default for touch controls, sliders, switches, bars, grouped rows.
3. **Concentric** — radius = parent radius − padding (inset). Use for anything nested inside a rounded container.

Practical rules:
- If a nested corner looks **pinched** (inner radius too large) or **flared** (too small), it isn't concentric — derive it from the parent.
- Components used both nested and standalone: *concentric with a fallback radius*.
- Near device edges on phones: a capsule with extra margin. In windows: a concentric shape aligned to the window corner.
- Dense desktop UIs keep rounded rectangles for small/medium controls; reserve capsules for standout or large controls.
- Optical centering: mathematically center when it works; offset subtly when the optical center differs (e.g. play triangles, asymmetric glyphs).

```css
/* Concentric radii: inner = outer − inset */
.card { --r: 28px; --pad: 12px; border-radius: var(--r); padding: var(--pad); }
.card > .media { border-radius: max(calc(var(--r) - var(--pad)), 6px); } /* fallback floor */
.pill { border-radius: 9999px; } /* capsule */
```

## 7. Standard Materials (content layer)

- Four thicknesses: **ultra-thin, thin, regular (default), thick.** Thicker = more opaque = better for fine text; thinner = more context shows through.
- Choose by **purpose**, never by the color it happens to produce (user settings change the look).
- Always put **vibrant/semantic** label, fill, and separator colors on materials. Avoid the faintest (quaternary) label level on thin materials — contrast is too low.
- Full-screen light overlays → ultra-thin; partial overlays → thin/regular; overlays needing a dark scheme → thick.
- Desktop windows can blend with what's *behind the window* (the desktop) or *within the window* (content beneath a sidebar) — pick deliberately.
- Full-screen modals on small screens keep a material background — it orients people.

## 8. Accessibility Modifiers (must support)

| Setting | What glass should do |
| :--- | :--- |
| Reduce Transparency | Become frostier/more opaque, obscuring more of the background |
| Increase Contrast | Controls go predominantly black or white with a contrasting border |
| Reduce Motion | Tone down effects; disable elastic/gel behaviors |

## 9. When Not to Use Glass

Glass is a signature of Apple's current visual language, not a requirement of good design. Skip it (use solid or standard-material surfaces) when:

- **Legibility is at risk.** Text-heavy UI, busy or high-contrast backgrounds, small text, or audiences with low vision. Translucency reduces effective contrast; if you can't guarantee 4.5:1 for text over every possible background, go opaque.
- **Performance matters.** `backdrop-filter` is expensive — many blurred layers, large blur radii, or blur over scrolling video/canvas can drop frames, drain battery, and jank low-end Android devices. Budget one or two blurred layers per screen; test on a low-end device.
- **The product already follows another system.** Material, Fluent, or a brand system with flat surfaces — layering glass on top reads as inconsistent.
- **Dense, data-first interfaces.** Dashboards, tables, spreadsheets, admin tools: people scan values, and see-through chrome adds noise. Use solid bars with a hairline or hard scroll edge.
- **Print, e-ink, or reduced-transparency contexts.** Always have a solid fallback anyway.
- **Content cards and list rows.** Never — glass belongs only to the floating control layer.

A good default for most web and app products: solid content surfaces, one translucent top/bottom bar with a soft scroll edge, and a tinted primary button. Add more glass only when it clearly helps content stay visible.

## 10. CSS Implementation

True lensing needs a displacement shader; a faithful approximation keeps the *behavior rules* even if the optics are simpler.

```css
:root {
  --glass-bg: rgb(255 255 255 / 0.55);
  --glass-edge: rgb(255 255 255 / 0.6);
  --glass-shadow: 0 8px 24px rgb(0 0 0 / 0.12);
}
@media (prefers-color-scheme: dark) {
  :root { --glass-bg: rgb(30 30 32 / 0.5); --glass-edge: rgb(255 255 255 / 0.14); --glass-shadow: 0 8px 28px rgb(0 0 0 / 0.45); }
}

/* Functional layer only: bars, floating buttons, menus */
.glass {
  background: var(--glass-bg);
  backdrop-filter: blur(16px) saturate(180%) brightness(1.05);
  -webkit-backdrop-filter: blur(16px) saturate(180%) brightness(1.05);
  border-radius: 9999px;                     /* capsule by default */
  box-shadow: inset 0 1px 0 var(--glass-edge), /* specular rim */
              inset 0 0 0 0.5px var(--glass-edge),
              var(--glass-shadow);
}
.glass--prominent { background: color-mix(in oklab, var(--action-tint) 78%, transparent); color: white; }

/* Clear variant over media: needs a dim behind it */
.media-controls { background: rgb(0 0 0 / 0.35); } /* ≈35% dim on bright media */
.glass--clear { background: rgb(255 255 255 / 0.12); backdrop-filter: blur(6px) saturate(160%); }

/* Soft scroll edge effect under a floating top bar */
.scroller { mask-image: linear-gradient(to bottom, transparent 0, black 56px); }
/* Hard edge (pinned headers, desktop) */
.pinned-header { background: var(--system-background-primary); }

@media (prefers-reduced-transparency: reduce) {
  .glass, .glass--clear { background: var(--system-background-secondary); backdrop-filter: none; -webkit-backdrop-filter: none; }
}
@media (prefers-contrast: more) {
  .glass { background: var(--system-background-primary); box-shadow: 0 0 0 1.5px var(--label-primary); }
}
```

Motion: scale ~1.03–1.08 and brighten on press (the "illuminate" response), spring back on release; morph shared elements between states instead of cross-fading two separate bars; under `prefers-reduced-motion` drop the elastic overshoot.
