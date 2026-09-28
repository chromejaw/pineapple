# Extended Patterns: Haptics, Search Placement, Live Content, Active Sessions

Distilled from Apple's guidance on haptics, search (2026), live media, and activity-tracking apps, generalized for web and app products. Complements [Patterns](./patterns.md).

---

## 1. Haptics

Touch is a feedback channel with its own grammar. Standard controls (switches, sliders, pickers) typically already play haptics — custom haptics must stay consistent with them.

**Rules**
- **Use each standard pattern only for its established meaning.** If a pattern's meaning doesn't fit, use a generic one or design your own — never repurpose "success" as "tap."
- **Consistent cause → effect.** The same haptic always follows the same kind of event; a "failure" buzz must never also celebrate a win.
- **Complement, don't replace,** visual and audio feedback; match haptic sharpness/intensity to the animation's sharpness/intensity, and sync with sound.
- **Don't overuse.** The best haptics go unnoticed until they're turned off. Test frequency with real people.
- **Prefer short haptics for discrete events** in apps; long continuous haptics dilute meaning (and are unpleasant in a controller held for long).
- **Make haptics optional** — the experience must be complete without them.
- **Don't disturb sensors:** vibration can blur the camera, disturb motion sensors, or bleed into the microphone.

**Standard vocabulary**

| Category | Variants | Meaning |
| :--- | :--- | :--- |
| Notification | success · warning · error | Outcome of a task |
| Impact | light · medium · heavy · soft · rigid | Physical metaphor: snap into place, collision |
| Selection | (single tick) | A value is changing (picker detents, scrubbing) |

**Trackpads with force feedback:** alignment (snapped to a guide / reached min-max), level change (pressure steps), generic.

**Custom haptics** are built from *transient* events (taps, impulses) and *continuous* events (sustained vibration), each with **intensity** (strength) and **sharpness** (soft/organic ↔ crisp/mechanical). Games vary them dynamically (a jump from a tree hits harder than a hop in place).

**Web:** `navigator.vibrate()` exists on some browsers (Android Chrome) but not all, and has no sharpness control — treat web haptics as progressive enhancement, keep "tap"-class patterns ≤ 50 ms, never rely on them, and gate behind a user setting.

```js
const haptic = {
  selection: () => navigator.vibrate?.(8),
  success:   () => navigator.vibrate?.([12, 60, 18]),
  error:     () => navigator.vibrate?.([30, 50, 30, 50, 30]),
};
if (settings.haptics && !matchMedia('(prefers-reduced-motion: reduce)').matches) haptic.success();
```

## 2. Search Placement

Where search lives changes what people think they're searching and where the field animates when active. **Two questions decide placement: how do people navigate the app, and what is the scope of the search?**

**Phone**
| Placement | When | Behavior |
| :--- | :--- | :--- |
| **Bottom toolbar field** (preferred) | Navigation happens through a list with contextual toolbars (an email client) | Rises above the keyboard — best reach; width adapts to neighboring buttons |
| Toolbar **button → field** | The bottom toolbar needs > 2 other items | Expands into a field when tapped |
| **Top toolbar** | The bottom is occupied (e.g. by a persistent sheet) | Also lifts above the keyboard |
| **Search tab** (standard) | Tabbed app with rich, browsable content; exploratory mindset | Landing page with suggestions/categories before typing (a streaming app) |
| **Search tab** (prominent/button style) | People know what they want; speed matters | Tap = keyboard immediately (a contacts/calls app) |
| **Inline under the title** | Search scoped to one screen/collection | Stays at top when active; placeholder names the scope ("Search Albums") |

**Tablet/desktop** (keep them aligned)
- **Trailing toolbar field** — multi-column apps searching across columns, or when results appear in the detail view; collapses to a button when space is tight and expands on activation, pushing overflow into a menu.
- **Top of sidebar** — filters the sidebar's own list (settings), or when a rich detail view must stay visually separate.
- **Dedicated search tab/section** — one global entry point for multi-section apps; a bigger canvas for results.

**Behavior**
- Keep the core anatomy even when branded: leading magnifying glass, descriptive placeholder, clear button, Cancel (phone) that exits search and dismisses the keyboard.
- **Recents** on focus (inline on phone; a menu under toolbar/sidebar fields on larger screens); be selective (e.g. only results people actually opened); allow swipe-to-delete and "Clear".
- **Predictive suggestions** that complete the typed text, with the predicted part visually distinct; keep them few so results stay front and center.
- **Start broad, then narrow:** scope bar for 2–4 locations/accounts (All vs. Current folder); contextual filters that change with the query (a maps app); **tokens** for combinable natural-language filters ("Joshua Tree" + "2021") — powerful but less discoverable, so pair them with visible filter UI.
- **No results:** never a blank view — show a search icon, a title, a subtitle, and echo the query so typos are obvious.

## 3. Live Content (live streams, events, sports)

- **Live content first and one tap (or zero) to play.** A "Watch Now" button disappears into full-screen playback.
- **Live must look live:** play it, badge it, label rows ("On Now"); show progress for in-progress programs so people know where they'll land.
- Playback is always the primary action; secondary actions (Start Over, Record, Download) appear in the **same order everywhere**.
- Browse without leaving playback (content footer, picture-in-picture); show **instant visual feedback on channel change** (also buys loading time).
- Audio follows context: keep playing while browsing within the live context; stop when leaving it.

## 4. Active Sessions (workouts, recordings, navigation, timers, calls)

- During an active session show only session-relevant data and controls; hide the rest of the app.
- **Distinct visual state** for "active" (live-updating values, a unique appearance) recognizable at a glance.
- Pause/resume/stop are big and easy to hit; clear feedback on start and stop.
- If a sensor can't read (e.g. heart rate underwater), explain what is still recorded.
- End with a **summary** that confirms completion.
- **Discard accidental micro-sessions** (a few seconds) automatically or ask.
- Text for people in motion: large sizes, high contrast, most important value first.
