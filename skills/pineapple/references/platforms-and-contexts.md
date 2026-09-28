# Device Contexts for Web & App Design

Distilled from Apple's per-platform guidance and its "UI Design Dos and Don'ts", reduced to the contexts web and app products actually ship to: phones, foldables, tablets, desktops (native and browser), and games on those devices.

Characterize every target with five lenses before choosing layout, density, or inputs:

**Display · Viewing distance & posture · Inputs · Session length · Where it runs (native app, browser, installed PWA)**

---

## 1. Context Matrix

| Context | Display | Viewing distance | Primary input | Session shape | Design emphasis |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Phone** (native or mobile web) | Small–medium, high-res | ≤ 1–2 ft, handheld, one or two hands | Touch, on-screen keyboard | Seconds-long check-ins to hour-long sessions; frequent app switching | Few onscreen controls, reachable bottom/middle zone, swipe-back, adapt to orientation, dark mode, and text size |
| **Foldable / split screen** | Narrow cover screen + large inner screen, or half a screen | Handheld, book, tabletop | Touch | Opens, closes, and resizes mid-task | Resize, don't redesign; keep controls off the fold; same features at every size |
| **Tablet** | Large, high-res | ≤ ~3 ft; held, propped, or on a stand | Touch + keyboard + trackpad, often combined | Quick actions to multi-hour creation | Elevate content, minimize modality, resizable windows, multi-input interactions |
| **Desktop app / desktop web** | Large, often multiple displays | ~1–3 ft, stationary | Keyboard + pointer | Minutes to hours of deep work, many apps or tabs at once | More content with less nesting, full command menus, shortcuts, precise selection, customization |
| **Game** (on any of the above) | Many aspect ratios | Varies | Device default + controller | Hours | Instant play, great defaults, teach through play, personalization |

## 2. Minimum Sizes by Context

| Context | Default body text | Minimum text | Default hit target | Minimum hit target |
| :--- | :---: | :---: | :---: | :---: |
| Phone, tablet (touch) | 17 pt | 11 pt | 44×44 pt | 28×28 pt |
| Desktop (pointer) | 13 pt | 10 pt | 28×28 pt | 20×20 pt |

Web translation: treat 1 pt ≈ 1 CSS px at default zoom. Touch web: 44 px default target, 16 px minimum input font (prevents mobile zoom-on-focus). Pointer-only desktop web: 24 px is the WCAG 2.2 AA floor, 28 px a comfortable default. Material-based products use 48 dp targets — see [Design Tokens §6](./design-tokens-and-styles.md).

## 3. Best-Practice Digest

**Phone**
- Keep primary tasks and content in focus; make secondary details discoverable with minimal interaction.
- Adapt to orientation, appearance, and text size — let people choose.
- Put frequent controls where thumbs reach (middle/bottom); support swipe-back and row swipe actions.
- With permission, use device capabilities (payments, biometrics, location, camera) instead of asking people to type.

**Tablet**
- Use the space to elevate content; avoid needless modal and full-screen transitions.
- Let viewing distance and input mode set size and density.
- Support touch, keyboard, and trackpad — and interactions that combine them.
- Adapt to multitasking sizes and translate cleanly to desktop.

**Desktop (native and web)**
- Present more content in fewer levels; keep density comfortable.
- Let people resize, hide, and move windows and panes; support full screen for focus.
- Expose every command in a menu or command palette; support keyboard shortcuts and keyboard-only work.
- Support precise selection and editing; allow toolbar, layout, color, and font customization.
- On the web: respect browser conventions (Back button, middle-click to open in new tab, text selection, find-in-page, zoom) — never hijack them.

**Games**
- Let people play as soon as install or load completes; stream the rest.
- Choose smart defaults from device capabilities, paired controllers, and accessibility settings.
- Teach through play; keep written tutorials as optional reference.
- Defer permission and rating requests to the moment they're relevant.
- Keep text legible and buttons large on every display; adapt in-game menus to 16:10, 19.5:9, 4:3 and both orientations without covering content.
- Support each device's default input and physical controllers — but always offer an alternative.
- Let players personalize type size, control mapping, motion intensity, and audio balance; support self-representation; avoid stereotypes.
- Sync progress across devices; use haptics where available.

## 4. UI Dos and Don'ts (fastest sanity check)

| Topic | Rule |
| :--- | :--- |
| Formatting content | Primary content fits the screen with no zoom or horizontal scroll |
| Touch controls | Use controls designed for touch gestures |
| Hit targets | ≥ 44×44 pt |
| Text size | ≥ 11 pt at typical viewing distance |
| Contrast | Ample contrast between text and background |
| Spacing | Text never overlaps; increase leading/tracking for legibility |
| High resolution | Provide @2x/@3x (or vector) assets — no blurry images |
| Distortion | Keep images at their intended aspect ratio |
| Organization | Put controls close to the content they modify |
| Alignment | Align text, images, and buttons to show relationships |
