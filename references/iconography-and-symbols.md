# Iconography & Symbol Systems

Distilled from Apple's symbol-library and icon guidance, written as a spec for **any** interface icon system (Lucide, Material Symbols, Phosphor, or a custom set).

---

## 1. Icons Behave Like Text

- **Weights match the typeface.** A good symbol set offers a weight per font weight (ultralight → black); pair icon weight with adjacent text weight.
- **Three scales** (small, medium default, large) defined relative to the font's cap height — change emphasis without breaking weight matching.
- Icons align to the text baseline and scale with the user's text size.

```css
.icon { width: 1.15em; height: 1.15em; vertical-align: -0.2em; stroke-width: var(--icon-stroke, 1.75); }
.text-semibold .icon { --icon-stroke: 2.1; }  /* match weight to adjacent text */
.icon--sm { width: 0.95em; height: 0.95em; } .icon--lg { width: 1.4em; height: 1.4em; }
```

## 2. Rendering Modes (color is layered, not flat)

Build icons from ordered layers (primary / secondary / tertiary).

| Mode | Behavior | Use |
| :--- | :--- | :--- |
| Monochrome | One color on all layers | Default; toolbars, text-like contexts |
| Hierarchical | One color, decreasing opacity by layer | Depth and emphasis from a single accent |
| Palette | One explicit color per layer | Coordinated multi-color schemes |
| Multicolor | Intrinsic real-world colors (green leaf, red "delete") | Where color carries meaning |

- Check each mode's legibility at the actual size and background.
- Use semantic colors so icons adapt to dark mode, contrast settings, and materials.
- Gradients (single-source linear) read best at larger sizes.

## 3. Variable Color vs. Hierarchy

- **Variable color** fills layers as a value crosses thresholds (0–100%): signal strength, volume, capacity, progress. Layers that don't change (a speaker body) opt out.
- **Use variable color to show change, never depth.** For depth, use hierarchical rendering.

## 4. Design Variants Communicate State

| Variant | Meaning / placement |
| :--- | :--- |
| Outline | Default; toolbars, lists, next to text |
| Fill | More emphasis; tab bars, swipe actions, selected state with accent |
| Slash | Unavailable / disabled / muted |
| Enclosed (circle, square, rectangle) | Better legibility at small sizes; badges |
| Localized | Script-specific glyphs (Arabic, Hebrew, Devanagari, CJK, Thai, Cyrillic…) that switch with the UI language |

Often the **container decides**: a tab bar asks for fill, a toolbar for outline — so the component should pick the variant, not each call site.

## 5. Icon Animation Vocabulary

Each animation has a *meaning*; pick by intent, not by looks.

| Animation | Meaning |
| :--- | :--- |
| Appear / Disappear | Element enters/leaves |
| Bounce | "Something happened / do this" — one-shot feedback |
| Scale | Persistent emphasis (selected) until reset |
| Pulse | Ongoing activity (opacity only) |
| Breathe | Ongoing activity with presence (opacity + size), e.g. recording |
| Variable color (cumulative / iterative) | Progress, connecting, broadcasting; closed-loop shapes cycle seamlessly |
| Replace — down-up / up-up / off-up | State change / forward progression / emphasize next action |
| Morph replace | Smart transition between related icons (a slash draws on/off, a badge appears) |
| Wiggle | Nudge toward an overlooked call to action or direction |
| Rotate | Working/in progress, or mimic a physical part (fan blades only) |
| Draw on / Draw off | Draws along the path — progress (download), directional meaning |

Rules: animate judiciously (too many overwhelm), each animation serves a clear communicative purpose, match the product's tone, respect reduced motion.

## 6. Custom Icons

- Start from the closest existing icon; match **detail level, optical weight, alignment, position, perspective**.
- Aim for: **simple, recognizable, inclusive, directly related** to the action or content.
- Use **negative side margins** when a badge widens a glyph so stacks still align optically.
- Draw **whole shapes** and use erase layers instead of cut-outs so layer animations work.
- Build enclosed/badged variants from a component library instead of drawing each.
- Always provide an **accessibility label**.
- Don't replicate other companies' products or trademarked marks in icons; don't use a UI icon library's glyphs as your logo.

## 7. Choosing Glyphs

- **Don't reinvent common metaphors.** A trash can means delete; a magnifying glass means search; a custom take on either costs instant recognition. Customized icons must closely resemble what they replace.
- **Metaphors must be neither too literal nor too abstract** — they should let people predict the result.
- **Same icon for the same action everywhere**, across screens and devices.
- **When no icon is unambiguous, use text.** A pencil could mean edit *or* annotate; a checkmark could mean select *or* confirm.
- **Menus:** icons aid recognition, but for a group of closely related actions (several "Copy …" commands), show the icon once on the first item and let text differentiate.
- **Don't group an icon button with a text button** in one bar group — it reads as one control.
- **No emoji as interface icons.**
- Common action glyphs: share (box + up arrow), add (+), delete (trash), edit (pencil), more (ellipsis), close (×), search (magnifying glass), filter (funnel / descending lines), sort (up-down arrows) — see [Foundations › Icons](./foundations.md).
