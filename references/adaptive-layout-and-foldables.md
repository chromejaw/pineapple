# Adaptive Layout, Foldables & Resizable Windows

Distilled from Apple's guidance on folding/dual-display phones, resizable tablet windows, and cross-device continuity — generalized for web, Android foldables, desktop, and split-screen multitasking.

---

## 1. Core Stance: Resize, Don't Re-Design

- **Design for width classes, not devices.** Target *compact width* (phones, folded screens, narrow windows) and *regular width* (tablets, unfolded screens, wide windows). Avoid fixed widths, device-specific breakpoints, or metrics tied to one screen.
- **Build from layout margins + safe-area insets.** A layout that respects them adapts to new shapes with little work.
- **Don't design a layout per posture.** Let the existing layout expand into available space. If you add an optional posture-specific layout (e.g. tabletop: media on top, controls on the stable bottom half), it must keep the same controls and hierarchy — never tie functionality to one posture.
- **Continuity across screen sizes.** Same features, same state, same information hierarchy. On a larger screen, *optionally* reveal one extra level of hierarchy (email: list *or* message when narrow; list *and* message side-by-side when wide).
- **Changes must be non-destructive.** Resizing or folding shouldn't permanently alter layout or lose scroll position/selection; revert to the prior state when space returns.
- **Avoid extreme rearrangement.** Move only what's needed to stay visible and tappable. Controls that jump or vanish are hard to re-find — prefer small adjustments.

## 2. Postures

People hold and set a foldable many ways: closed in hand, open flat, half-open like a book, on a table like a tiny laptop (tabletop), or standing on an edge. Split-screen and pinned picture-in-picture resize the app continuously.

- Every posture exposes the same functionality.
- Keep controls in the same *relative* positions across postures so people don't relearn where actions live.
- Games: fill the screen in every posture. You may lock orientation, but change aspect ratio rather than letterboxing; if bars are unavoidable, put artwork in them. Keep text and control sizes stable across resizes.

## 3. Reserved Regions (dynamic safe areas)

A *reserved region* is display area content must avoid, or that components adapt around.

| Region | When present | Behavior |
| :--- | :--- | :--- |
| Camera cutout / notch | Always | Controls align around it |
| Under-display or pop-up camera | Only while the camera is active | UI shifts aside to reveal the camera's presence |
| **Fold / hinge** | Only when partially folded (or always, on hinged dual screens) | Splits the display into usable regions; content moves off the crease |

Rules:
- **Keep interactive elements out of the fold.** Buttons in the crease are hard to hit. Dialogs, menus, sheets, context menus, and toolbar buttons should nudge themselves aside.
- **Scrollable content may pass through the fold**; static text and controls should not rest there.
- **Let the fold become a natural divider.** Split panes match the crease; in grids, prefer an **even number of columns** so content divides cleanly.
- In a half-folded portrait posture, interactive elements move to the bottom half (stable on the table, reachable).

## 4. Arrangement Views (a portable two-pane primitive)

A container holding a **primary** and **secondary** view, arranged by size, orientation, and reserved regions:

- **Split arrangement:** side-by-side when wider than tall, stacked when taller than wide. You can restrict the axes.
- **Overlay arrangement:** stacks primary over secondary; when half-folded, the two move to either side of the fold. The secondary can collapse when not wanted.

Use one when your layout already *is* two things side-by-side/stacked (row/column → split; layered → overlay). **Keep navigation outside** the arrangement — it lays out content, it doesn't navigate.

## 5. Vertical Controls (bars on the side)

On wide-and-short screens — and in most foldable postures — toolbars, tab bars, and navigation controls move to a **vertical strip on one edge** to give content maximum height and keep controls under the thumb. Tall screens keep horizontal bars.

- **Order on the vertical axis:** navigation (Back/Close) at the top, then the prominent action (Done), then remaining groups in their original grouping; top-bar items go to the top, bottom-bar items to the bottom, tabs bottom-aligned. Let the layout system space the groups — **don't hand-place fixed spacers**.
- **Items too wide for the strip stay horizontal** (text buttons, segmented controls). So: **prefer icons** over text buttons, and give *every* item both a title and an icon — the layout picks the representation, and the title is used in overflow menus and for accessibility.
- **Overflow is prioritized.** Items overflow bottom-to-top by default; assign visibility priorities (group first, then item). Keep frequent actions (Compose, New) and items carrying status (badges) visible longest.
- **Compression strategy depends on the view's job:**
  - *Navigation-focused* → keep the tab bar, move toolbar items to overflow.
  - *Task-focused* → minimize the tab bar, keep the task's toolbar actions.
- **One overflow menu.** Reserve the ellipsis icon for overflow; give other menus distinct icons.
- **Asymmetry is real.** Offset content from the control strip via safe-area insets — including a strip on the *opposite* edge when two apps share the screen (each app puts controls on its outer edge). Hardware-aligned controls stay on the same side even in RTL languages.
- **Full-width is allowed** for immersive, non-scrolling UIs (a calculator) if nothing collides with camera/status areas; or mix: full-width background/header, inset scrollable foreground with every interactive element inside the inset area.
- **Proximity beats uniformity:** controls that belong to a specific pane (list filters above the list column) stay with that pane instead of moving to the side strip.

## 6. Using a Big Screen Well

Don't ship a stretched phone layout. Options, in rough order of preference:
1. **Split view** — show two (or three) levels of hierarchy at once; collapses to one pane when narrow.
2. **Reflow** — a vertical stack that becomes two columns when width allows.
3. **Tab bar ⇄ sidebar** — tabs become a sidebar when wide, for information-dense apps. If unsure which navigation to pick, start with a tab bar; it can become a sidebar as the app grows.

Sheets on a foldable slide off the fold when half-open.

## 7. Windows & Multitasking

- **Resizable windows are the norm.** Any width can occur; adaptive navigation (tab bar ⇄ sidebar, collapsing columns) must reflow gracefully.
- **Wrap the toolbar around window controls** (close/minimize/maximize) rather than reserving a whole band above it — reclaim that space for content.
- **One window per document.** Opening a second document shouldn't replace the first; windows persist until closed.
- **Give every window a descriptive, unique title** (document name) so window lists and switchers are useful.
- **Pointer:** precise, 1:1 tracking; hover shows a highlight on the target — no magnetic snapping that fights the user.
- **Menu bar / command menus:** every related command in each menu, ordered by frequency (not alphabetically), grouped into sections, secondary items in submenus, icons matching the in-app icons, shortcuts for the most common. Put tab switching (with shortcuts) and the sidebar toggle in **View**. **Never hide menus or items based on context — dim them.** Stable menus preserve spatial memory and aid discovery.

## 8. Continuity Across Devices

- **Design the app's anatomy once**, then express it per device: phone = zoomed-in, narrow and vertical; tablet = the bridge; desktop = the expansive canvas.
- Content that's grouped stays grouped as the layout adapts.
- Use **the same icons across devices**; when no icon is unambiguous (Select, Edit), use a text label.
- Shared component anatomy (selection indicator, icon, label, accessory) and **the same core interactions** everywhere — a tab bar, segmented control, and sidebar all signal selection, navigation, and state with the same cues.

## 9. Implementation Mapping

| Concept | Web | Android |
| :--- | :--- | :--- |
| Width classes | Container queries / `@media (width >= 600px)` on *available* width, never device detection | `WindowSizeClass` (compact/medium/expanded) |
| Fold region | Viewport Segments: `@media (horizontal-viewport-segments: 2)`, `env(viewport-segment-left 1 0)`, `env(viewport-segment-right 0 0)` | Jetpack WindowManager `FoldingFeature` bounds |
| Posture | Device Posture API: `@media (device-posture: folded)` | `FoldingFeature.state == HALF_OPENED`, orientation |
| Camera cutouts | `env(safe-area-inset-*)` + `viewport-fit=cover` | `WindowInsets.displayCutout` |
| Side-strip controls | A `nav` that becomes a vertical rail via container query when the box is wide and short | `NavigationRail` |

```css
/* Keep interactive elements off the fold */
@media (horizontal-viewport-segments: 2) {
  .layout {
    display: grid;
    grid-template-columns: env(viewport-segment-width 0 0) calc(env(viewport-segment-left 1 0) - env(viewport-segment-right 0 0)) 1fr;
  }
  .layout > .primary { grid-column: 1; }
  .layout > .secondary { grid-column: 3; }
}
/* Wide-and-short → controls move to a side rail (root needs container: app / size) */
@container app (min-aspect-ratio: 13/10) and (max-height: 520px) {
  .bar { position: fixed; inset-block: 0; inset-inline-end: 0; flex-direction: column; }
  .content { padding-inline-end: var(--rail-width); }
}
```
