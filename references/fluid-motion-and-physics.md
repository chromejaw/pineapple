# Fluid Motion & Spring Physics

This reference captures the mathematical models, spring physics parameters, gesture mechanics, and implementation code that define fluid interfaces at Apple.

*Source: Apple Design Team (Chan Karunamuni & team, WWDC18 Session 803: Designing Fluid Interfaces).*

> *"When we align the interface to the way we think and move, something magical happens — it stops feeling like a computer and starts feeling like a seamless extension of us."*

---

## 1. The Core Philosophy of Fluid Motion

An interface is fluid when it behaves like the physical world:
- Things respond immediately without perceptible latency.
- Objects move continuously and track 1:1 with fingers.
- Motions carry real momentum when released.
- Boundaries resist softly and elastically rather than hitting hard frozen stops.
- Animations can be grabbed, redirected, and interrupted mid-flight.

Fixed-duration timing curves (`ease-in-out`, cubic-béziers) feel artificial because real-world physics does not run on a stopwatch. Apple builds fluid interfaces using **physical springs** that react dynamically to user velocity and position.

---

## 2. Response: Kill All Latency

The instant latency enters an interface, the illusion of direct manipulation collapses.

- **Acknowledge on pointer-down, commit on release**: Highlight buttons and begin gesture tracking the moment the pointer or finger touches down — waiting for touch-up to show *any* response makes software feel dead. But perform the action on release (inside the target) so people can slide off to cancel.
- **Continuous feedback throughout the gesture**: For drags, sheets, or sliders, update coordinates 1:1 during the motion—never wait to animate until the finger is lifted.
- **Eliminate artificial delays**: Remove excessive debounces, entry delays, and animations that must finish before input is accepted. (The old 300ms mobile-browser tap delay is gone in modern browsers when the page sets `<meta name="viewport" content="width=device-width">`; keep that tag and add `touch-action: manipulation` on custom controls.)

```css
/* Immediate pointer-down feedback */
.button:active {
  transform: scale(0.97);
  transition: transform 100ms ease-out;
}
```

---

## 3. Direct Manipulation & Grab Offsets

> *"Touch and content must move together."*

When a user grabs an object, it must stay glued to their finger and **respect the offset from where they touched it**. Snapping an object's center to the touch point destroys the tactile illusion immediately.

```javascript
element.addEventListener('pointerdown', (e) => {
  element.setPointerCapture(e.pointerId);
  // Respect where the user grabbed the element
  const grabOffsetY = e.clientY - element.getBoundingClientRect().top;
  const grabOffsetX = e.clientX - element.getBoundingClientRect().left;

  // Track position history with timestamps for velocity calculation
  let lastY = e.clientY;
  let lastTime = performance.now();
  let velocityY = 0;

  function onPointerMove(moveEvent) {
    const now = performance.now();
    const dt = now - lastTime;
    if (dt > 0) {
      velocityY = (moveEvent.clientY - lastY) / (dt / 1000); // px per second
      lastY = moveEvent.clientY;
      lastTime = now;
    }
    // Update position 1:1
    element.style.transform = `translateY(${moveEvent.clientY - grabOffsetY}px)`;
  }
});
```

### Gesture Recognition Details

- **Hysteresis before committing:** wait for about 8–10 px of travel on touch (3–4 px with a mouse) before deciding it's a drag, and on which axis. Then track 1:1, including the distance already traveled, so nothing jumps.
- **Recognize in parallel:** from the first move, consider every plausible gesture (tap, horizontal swipe, vertical scroll). Commit to the winner once intent is clear and cancel the rest. Avoid APIs that only report a finished swipe, because they throw away the continuous tracking that feedback needs.
- **Double-tap has a cost:** it delays every single tap while the system waits for a second one. Enable it only where double-tap does something.
- **One pointer per drag:** store the `pointerId` when a drag starts and ignore extra touches, so switching fingers doesn't make the element jump.
- **Claim the gesture:** set `touch-action` on drag surfaces (`none` for free drags, `pan-y` for horizontal swipes inside a vertical scroller) so the browser doesn't take the gesture for scrolling.
- **Always clean up:** handle `pointercancel`, `lostpointercapture`, and window `blur`. Reset the drag state and let a spring settle the element. A drag that nothing clears leaves the UI stuck.
- **Per-frame writes:** set `transform` directly on the moving element. Updating a CSS variable on a parent restyles every child, and animating layout properties forces layout on every frame.

---

## 4. Interruptibility: The Single Most Important Principle

> *"The thought and the gesture happen in parallel."*

Every transition in a fluid interface must be interruptible. A user must be able to catch a flying card, reverse a dismissal swipe, or reopen a closing sheet at any millisecond without waiting for an animation to finish.

- **Never lock user input during an animation**: Never set `pointer-events: none` during transitions.
- **Always animate from the presentation (live) value, never the target value**: If a sheet is halfway down and interrupted, read the element's current computed matrix and begin the new spring from that exact location. Snapping to the intended resting point causes a jarring jump.
- **Additive velocity blending**: When reversing motion mid-flight, carry existing velocity through into the new spring rather than cutting it to zero (avoiding the "brick wall" collision effect).
- **Decompose 2D motion**: Drive X and Y with independent springs, each seeded with its own velocity component. A single spring on the 2D distance drifts off the finger's path when the two axes move at different speeds.

---

## 5. Apple’s 2-Parameter Spring Model

Apple replaced traditional physics equations (mass, stiffness, damping) with two human-friendly parameters:

1. **Damping Ratio ($\zeta$)**: Controls oscillation and overshoot.
   - `1.0` = **Critically Damped**: Smooth settle, zero bounce or overshoot. The default for standard interface transitions.
   - `< 1.0` = **Underdamped**: Bounces and oscillates around the target. Lower numbers = bouncier.
   - `> 1.0` = **Overdamped**: Sluggish approach without oscillation.
2. **Response ($T$)**: How quickly the spring reaches its target (in seconds). Lower values = snappier. Note that response is not a fixed duration; the settling time naturally emerges from response and velocity.

### Suggested Spring Values

| Interaction Type | Damping Ratio | Response ($T$) | Feel Description |
| :--- | :---: | :---: | :--- |
| **Default UI / Reposition** | `1.0` | `0.40s` | Critically damped, zero overshoot, stable and graceful. |
| **Card / Modal Sheet Dismissal** | `0.8` | `0.30s` | Slight energetic bounce, responsive to flick release. |
| **Rotation** | `0.8` | `0.40s` | Gentle rotational inertia. |
| **Interactive Button Press** | `1.0` | `0.15s` | Snappy immediate press response. |
| **Tab / Segment Selection Switch**| `1.0` | `0.25s` | Clean slide with immediate lock. |

> **Provenance:** Apple published the two-parameter model (damping ratio + response) and the principle *critically damped by default, a little bounce only when the gesture carried momentum*. The per-component numbers above are practical starting points, not Apple-published values. For reference, SwiftUI’s default spring is response ≈ 0.5 s with no bounce. Tune by feel on real devices.

### Web Implementation (Framer Motion / Motion API)

```javascript
import { animate } from 'motion';

// 1. Default UI Transition: Critically damped (no bounce)
animate(element, { y: 0 }, {
  type: 'spring',
  bounce: 0,       // Damping Ratio = 1.0
  duration: 0.40   // Response = 0.4s
});

// 2. Momentum-Driven Release: Underdamped (slight bounce on flick)
animate(element, { y: targetY }, {
  type: 'spring',
  bounce: 0.2,     // Damping Ratio ~ 0.8
  duration: 0.30,  // Response = 0.3s
  velocity: releaseVelocity // Hand off user's release speed
});
```

---

## 6. Velocity Handoff & Momentum Projection

When a user releases a dragging element, the transition must inherit the pointer's velocity so there is zero seam between the finger lifting and the animation continuing.

### Apple's Exact Momentum Projection Formula

Don't snap an element based solely on where the finger released. Project where the gesture **would have landed** under natural exponential deceleration:

$$\text{project}(v, d) = \frac{v}{1000} \cdot \frac{d}{1 - d}$$

- $v$ = release velocity in pixels per second.
- $d$ = deceleration rate ($\approx 0.998$ for normal feel, $0.990$ for snappy feel).

```javascript
function projectPosition(initialVelocity, decelerationRate = 0.998) {
  return (initialVelocity / 1000) * decelerationRate / (1 - decelerationRate);
}

// Example usage on sheet release:
const projectedY = currentY + projectPosition(releaseVelocityY);

// Determine snap target based on projected landing point, not release point
const targetY = projectedY > dismissThreshold ? screenHeight : 0;

animateSpring(element, { y: targetY }, { velocity: releaseVelocityY });
```

**Commit or return by projection, not position.** A short, fast flick should dismiss. A long, slow drag released while moving backward should return. Compare the *projected* endpoint to the threshold, and let the sign of the release velocity break ties. Requiring people to drag past a fixed distance makes a quick flick feel ignored.

---

## 7. Apple’s Rubber-Banding Resistance Formula

When a user drags an element past its boundary (overscrolling a list or dragging a sheet past its limit), the element must not freeze. It resists with increasing friction:

$$f(x) = \frac{x \cdot d \cdot c}{d + c \cdot |x|}$$

- $x$ = distance the finger has traveled past the boundary.
- $d$ = dimension of the container (screen height or width).
- $c$ = coefficient of resistance (Apple uses $c \approx 0.55$).

```javascript
function rubberband(overshoot, dimension, constant = 0.55) {
  return (overshoot * dimension * constant) / (dimension + constant * Math.abs(overshoot));
}

// As overshoot increases toward infinity, the displacement approaches dimension * constant.
```

---

## 8. Spatial Consistency & Directional Hinting

> *"If something disappears one way, we expect it to emerge from where it came."*

- **Symmetric Paths**: A panel that enters from the right must dismiss to the right. Mixing slide-in-from-right with slide-out-to-bottom disorients users.
- **Trigger-Anchored Origins**: Menus, popovers, and context cards must scale outwards from their triggering button, not the screen center. Set `transform-origin` to match the source coordinates.
- **Directional Hinting**: When a user begins dragging toward a destination, scale and tilt intermediate frames toward the outcome so the interface confirms their intent before completion.

---

## 9. Multimodal Feedback (Motion + Audio + Haptics)

*Source: Apple WWDC Session: Designing Audio-Haptic Experiences.*

1. **Causality**: The user must immediately perceive the cause. Trigger feedback on the physical event (the toggle flipping, the item snapping home).
2. **Harmony**: Visual animation, audio click, and tactile vibration must fire on the **exact same frame**. A 50ms desync shatters the physical illusion.
3. **Restraint**: Reserve haptic taps and clicks for meaningful state changes (commits, errors, snaps). Overuse desensitizes users.

Fire the haptic and the sound in the same event handler as the visual state change, not after a transition ends. On the web, vibration is unavailable in some browsers, including Safari, so never make it the only signal.

---

## 10. Accessible Reduced Motion Adaptations

When `prefers-reduced-motion: reduce` is active, follow Apple's list:
- **Tighten springs** to remove bounce, overshoot, and elastic oscillation.
- **Keep gesture tracking direct.** Content that follows the finger 1:1 is expected, not "motion".
- **Replace x-, y-, and z-axis movement with fades.** That covers slides, zooms, parallax, and depth changes: use short cross-fades (opacity 0 → 1 over 150–200 ms).
- **Don't animate into and out of blurs.**
- **Keep what explains state.** Opacity, color, and progress indicators still animate. A spinner that freezes looks like a hang.

```css
@media (prefers-reduced-motion: reduce) {
  .sheet, .menu, .popover, .toast, .page-transition {
    transform: none !important;             /* no travel or scale */
    transition: opacity 150ms ease-out;     /* cross-fade instead */
  }
  .parallax, .ambient-loop, [data-autoplay] { animation: none; }
  /* Spinners and progress bars keep running; if a spinner rotates large, swap it for a gentle opacity pulse. */
}
```

```javascript
const reduceMotion = matchMedia('(prefers-reduced-motion: reduce)');
const springFor = (base) => reduceMotion.matches ? { ...base, bounce: 0 } : base; // tighten, don't remove feedback
```

Avoid the global kill `* { animation-duration: 0.01ms !important; animation-iteration-count: 1 !important }`. It stops every infinite animation after one invisible cycle, which freezes spinners and progress indicators, and it deletes feedback that people with reduced motion still need.

---

## 11. Timing Budgets & Durations

### Response-time thresholds (Nielsen/Card, widely used; consistent with Apple's "respond instantly")

| Delay | What people perceive | What to do |
| :--- | :--- | :--- |
| **≤ 100 ms** | Instant — cause and effect feel connected | Direct feedback (press states, toggles, typing, drag tracking) must land here. Target one frame (16 ms at 60 Hz, 8 ms at 120 Hz) for tracking. |
| **100 ms – 1 s** | Noticeable but flow is kept | No spinner needed; show a pressed/working state. Optimistic UI works well here. |
| **1 – 10 s** | Attention drifts | Show progress (determinate when possible) and keep the rest of the UI usable. Skeletons for content loads. |
| **> 10 s** | People switch tasks | Run in the background, show % and time remaining, allow cancel, notify on completion. |

Other budgets: interaction to next paint (INP) ≤ 200 ms on the web; scroll and animation at the display's full frame rate; first meaningful content ≤ ~1 s on a warm start.

### Duration guide (when you can't use springs)

| Movement | Duration | Easing |
| :--- | :--- | :--- |
| Press/hover state, color/opacity change | 100–150 ms | ease-out |
| Small component (toggle knob, checkbox, chip) | 150–200 ms | ease-out |
| Menu, popover, tooltip appear | 150–250 ms (exit ~30% faster) | ease-out both ways |
| Sheet, drawer, panel, page transition | 250–400 ms | decelerate (`cubic-bezier(0.2, 0.8, 0.2, 1)`) |
| Large/full-screen or long-distance movement | 350–500 ms | decelerate; scale duration with distance |
| Reduced motion alternative | 150–200 ms cross-fade | linear/ease |

Rules:
- **Scale with distance and size** — farther and bigger moves take longer; tiny ones should be almost instant.
- **Exits are faster than entrances** — people already decided; get out of the way.
- **Never block input** during an animation, and never chain animations so a task waits > 500 ms on motion alone.
- **One focal motion at a time** — stagger lists by 20–40 ms per item, capped at ~150 ms total.

---

## 12. Restraint: When Not to Animate

Apple's guidance: *"In apps, generally avoid adding motion to UI interactions that occur frequently,"* and *"Let people cancel motion."* Motion is a budget. Spend it where it explains something, and never where it taxes something people do all day.

### Budget by frequency

| How often | Motion | Examples |
| :--- | :--- | :--- |
| **Constantly**, especially from the keyboard | **None.** Respond in the same frame | ⌘/Ctrl-K palette open and close, arrow-key list navigation, switching tabs by shortcut, typing, focus moves, toggling a sidebar by shortcut |
| **Often** | **Minimal:** ≤ 100–150 ms, opacity or color, no travel | Hover, press, selection, segmented controls, checkboxes |
| **Occasionally** | **Standard:** a spring, or 200–400 ms, that shows where things went | Sheets, menus opened by click, navigation push and pop, toasts |
| **Rarely** | **Room for one authored moment** | First run, finishing a big task, an empty state filling up |

Held keys auto-repeat around 30 times a second, so any per-step animation turns into lag. The *result* of a keyboard action, such as opening a document, can use the same transition as the click path, kept short.

### Entrances & origins

- **Never scale from 0.** Nothing physical appears out of a point. Start at 0.9–0.97 scale with opacity 0; menus and popovers look right around 0.95.
- **Grow from the source.** Put `transform-origin` at the trigger for menus, popovers, tooltips, and context menus. Headless UI libraries expose it; for example Radix sets `--radix-popover-content-transform-origin` and Floating UI reports the placement. Centered modals keep `transform-origin: center`. Sheets and drawers travel from their edge.
- **Leave the way you came, faster.** Use a symmetric path, with the exit about 30% quicker.

### Tooltips

- **Warm-up once:** show the first tooltip after roughly 400–700 ms of rest, so passing pointers don't flash tooltips. While one is open, and for about 300 ms after it closes, neighboring tooltips appear instantly with no animation.
- **Follow WCAG 1.4.13 (content on hover or focus):**
  - show tooltips on keyboard focus as well as hover;
  - Esc dismisses them;
  - the pointer can move onto the tooltip without closing it;
  - the tooltip stays until it's dismissed or unhovered.
- **Never the only home for essential information.** Touch has no hover.

### Choosing the tool (web)

| Motion | Use | Why |
| :--- | :--- | :--- |
| Gesture-driven, or velocity matters (drags, flicks, sheets) | A JS spring (Motion, react-spring, or §5–§7 by hand) | Starts from the live value and carries velocity through interruptions |
| State changes that can re-trigger quickly (toggles, hover, toasts, expanding rows) | CSS transitions | Retarget from the current value when interrupted (velocity resets to zero) |
| Newly inserted elements | Transitions plus `@starting-style` | An entry animation with no JavaScript mount tricks |
| One-shot or looping sequences (spinner, skeleton shimmer) | `@keyframes` or the Web Animations API | They restart from zero when re-triggered: fine for loops, wrong for toggles |
| Page or shared-element continuity | View Transitions API | Morphs between states instead of cross-fading two views |

### Easing when springs aren't available

```css
:root {
  --ease-out: cubic-bezier(0.23, 1, 0.32, 1);      /* responses: enter, exit, press (fast start, like a spring) */
  --ease-in-out: cubic-bezier(0.77, 0, 0.175, 1);  /* on-screen moves from A to B */
  --ease-sheet: cubic-bezier(0.32, 0.72, 0, 1);    /* sheets and drawers */

  /* Apple's spring model as pure CSS (response 0.4 s), sampled into linear() */
  --spring-smooth: linear(0, 0.089, 0.261, 0.438, 0.59, 0.709, 0.797, 0.861, 0.906, 0.937, 0.958,
                          0.972, 0.982, 0.988, 0.992, 0.995, 0.997, 0.998, 0.999, 1);   /* damping 1.0 — use 600ms */
  --spring-bouncy: linear(0, 0.058, 0.188, 0.345, 0.499, 0.636, 0.75, 0.838, 0.904, 0.95, 0.98, 0.999,
                          1.009, 1.014, 1.015, 1.014, 1.012, 1.01, 1.007, 1.005, 1.004, 1.002, 1.001, 1); /* damping 0.8 — 550ms, only after a flick */
}
.sheet { transition: transform 600ms var(--spring-smooth); }
```

- **Ease-out for anything responding to input.** It's a spring's natural shape: fast start, soft settle. Ease-in spends its first frames barely moving, exactly when people are watching, so avoid it for UI.
- **Linear** only for constant motion (progress bars, marquees) and for `linear()` spring curves.
- **Provenance:** the curves are practical approximations. The `linear()` values are sampled from the damping-ratio/response model in §5, with settle times of about 1.4–1.5 × response. CSS transitions still drop velocity when interrupted, so gesture-driven motion needs a JS spring.

### Hygiene

- **Name the properties:** `transition: transform 200ms var(--ease-out), opacity 200ms var(--ease-out)`. Never `transition: all`, which animates things that should snap, such as color-scheme changes and layout.
- **Stick to cheap properties:** animate `transform` and `opacity`, plus bounded `filter`. Animate size and position changes with FLIP, not `width`, `height`, `top`, or `left`.
- **`will-change` only around an animation:** set it just before the animation runs and remove it afterward.
- **Gate hover motion** with `@media (hover: hover) and (pointer: fine)`.
- **Slow where the person decides, fast where the system responds:** a hold-to-confirm fills slowly, and the release snaps back in about 200 ms.
- **Stagger only a list's first appearance,** never every re-render or every scrolled section. Never block input while a stagger plays.
- **Crossfades that show double images:** a brief 2–4 px blur during the swap bridges them. Glass surfaces materialize (blur and scale together) rather than simply fading.
