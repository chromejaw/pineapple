# Inputs & Interactions

Universal interaction models: touch gestures, keyboards, pointers, focus navigation, and game controllers.

---

## Gestures

A gesture is a physical motion that a person uses to directly affect an object in an app or game on their device.

Depending on the device they’re using, people can make gestures on a touchscreen, in the air, or on a range of input devices such as a trackpad, mouse, or game controller that includes a touch surface.

Every platform supports basic gestures like tap, swipe, and drag. Although the precise movements that make up basic gestures can vary per platform and input device, people are familiar with the underlying functionality of these gestures and expect to use them everywhere. For a list of these gestures, see Standard gestures.


### Best practices

**Give people more than one way to interact with your app.** People commonly prefer or need to use other inputs — such as their voice, keyboard, or Switch Control — to interact with their devices. Don’t assume that people can use a specific gesture to perform a given task. For guidance, see Accessibility.

**In general, respond to gestures in ways that are consistent with people’s expectations.** People expect most gestures to work the same regardless of their current context. For example, people expect tap to activate or select an object. Avoid using a familiar gesture like tap or swipe to perform an action that’s unique to your app; similarly, avoid creating a unique gesture to perform a standard action like activating a button or scrolling a long view.

**Handle gestures as responsively as possible.** Useful gestures enhance the experience of direct manipulation and provide immediate feedback. As people perform a gesture in your app, provide feedback that helps them predict its results and, if necessary, communicates the extent and type of movement required to complete the action.

**Indicate when a gesture isn’t available.** If you don’t clearly communicate why a gesture doesn’t work, people might think your app has frozen or they aren’t performing the gesture correctly, leading to frustration. For example, if someone tries to drag a locked object, the UI may not indicate that the object’s position has been locked; or if they try to activate an unavailable button, the button’s unavailable state may not be clearly distinct from its available state.


### Custom gestures

**Add custom gestures only when necessary.** Custom gestures work best when you design them for specialized tasks that people perform frequently and that aren’t covered by existing gestures, like in a game or drawing app. If you decide to implement a custom gesture, make sure it’s:

- Discoverable

- Straightforward to perform

- Distinct from other gestures

- Not the only way to perform an important action in your app or game

**Make custom gestures easy to learn.** Offer moments in your app to help people quickly learn and perform custom gestures, and make sure to test your interactions in real use scenarios. If you’re finding it difficult to use simple language and graphics to describe a gesture, it may mean people will find the gesture difficult to learn and perform.

**Use shortcut gestures to supplement standard gestures, not replace them.** While you may supply a custom gesture to quickly access parts of your app, people also need simple, familiar ways to navigate and perform actions, even if it means an extra tap or two. For example, in an app that supports navigation through a hierarchy of views, people expect to find a Back button in a top toolbar that lets them return to the previous view with a single tap. To help accelerate this action, many apps also offer a shortcut gesture — such as swiping from the side of a window or touchscreen — while continuing to provide the Back button.


### Device-specific considerations


#### Phone & tablet
In addition to the standard gestures supported in all platforms, phones and tablets support a few other gestures that people expect.

| Gesture | Common action |
| --- | --- |
| Three-finger swipe | Initiate undo (left swipe); initiate redo (right swipe). |
| Three-finger pinch | Copy selected text (pinch in); paste copied text (pinch out). |
| Four-finger swipe (tablets only) | Switch between apps. |
| Shake | Initiate undo; initiate redo. |

**Consider allowing simultaneous recognition of multiple gestures if it enhances the experience.** Although simultaneous gestures are unlikely to be useful in nongame apps, a game might include multiple onscreen controls — such as a joystick and firing buttons — that people can operate at the same time.


#### Desktop
People primarily interact with desktop using a keyboard and mouse. In addition, they can make standard gestures on a trackpad, mouse, or a game controller that includes a touch surface.


### Specifications


#### Standard gestures


| Gesture | Supported in | Common action |
| --- | --- | --- |
| Tap | phones, tablets and desktop | Activate a control; select an item. |
| Swipe | phones, tablets and desktop | Reveal actions and controls; dismiss views; scroll. |
| Drag | phones, tablets and desktop | Move a UI element. |
| Touch (or pinch) and hold | phones and tablets | Reveal additional controls or functionality. |
| Double tap | phones, tablets and desktop | Zoom in; zoom out if already zoomed in. |
| Zoom | phones, tablets and desktop | Zoom a view; magnify content. |
| Rotate | phones, tablets and desktop | Rotate a selected item. |

For guidance on supporting additional gestures and button presses on specific input devices, see Pointing devices, Remotes, and Game controls.


---

## Keyboards

A physical keyboard can be an essential input device for entering text, playing games, controlling apps, and more.

Desktop users tend to use a physical keyboard all the time and tablet users often do. Many games work well with a physical keyboard, and people can prefer using one instead of a virtual keyboard when entering a lot of text.

Keyboard users often appreciate using keyboard shortcuts to speed up their interactions with apps and games. A *keyboard shortcut* is a combination of a primary key and one or more modifier keys (Control, Option/Alt, Shift, and Command/Windows/Super) that map to a specific command. A keyboard shortcut in a game — called a *key binding* — often consists of a single key.

Every desktop platform defines standard keyboard shortcuts that work consistently across the system and most apps, helping people transfer their knowledge to new experiences. Some apps define custom keyboard shortcuts for the app-specific commands people use most; most games define custom key bindings that make it quick and efficient to use the keyboard to control the game. For guidance, see Game controls.


### Best practices

**Support full keyboard access.** Most platforms (and the web) let people navigate and activate windows, menus, controls, and system features using only the keyboard. Test your app with keyboard-only navigation turned on, and make sure every control is reachable and visibly focused.

> **Important**: On touch-first platforms, keep keyboard navigation for text fields, text views, lists, and sidebars predictable, and rely on the system’s full-keyboard-access mode to reach other controls and perform gesture-based interactions like drag and drop, rather than inventing custom focus behavior.

**Respect standard keyboard shortcuts.** While using most apps, people generally expect to rely on the standard keyboard shortcuts that work in other apps and throughout the system. If your app offers a unique action that people perform frequently, prefer creating a custom shortcut for it instead of repurposing a standard one that people associate with a different action. While playing a game, people may expect to use certain standard keyboard shortcuts — such as Cmd-Q / Alt-F4 to quit the game — but they also expect to be able to modify each game’s key bindings to fit their personal play style. For guidance, see Game controls.


### Standard keyboard shortcuts

**In general, don’t repurpose standard keyboard shortcuts for custom actions.** People can get confused when the shortcuts they know work differently in your app or game. Only consider redefining a standard shortcut if its action doesn’t make sense in your app.

People expect these cross-platform shortcuts to perform the listed action. Apple platforms use **Cmd**; Windows, Linux, and ChromeOS use **Ctrl** (the web should honor the platform convention).

| Action | Mac | Windows / Linux |
| --- | --- | --- |
| New document / item | Cmd-N | Ctrl-N |
| Open | Cmd-O | Ctrl-O |
| Save | Cmd-S | Ctrl-S |
| Save As / Duplicate | Shift-Cmd-S | Ctrl-Shift-S |
| Print | Cmd-P | Ctrl-P |
| Close window / tab | Cmd-W | Ctrl-W |
| Quit app | Cmd-Q | Alt-F4 |
| Undo | Cmd-Z | Ctrl-Z |
| Redo | Shift-Cmd-Z | Ctrl-Y or Ctrl-Shift-Z |
| Cut / Copy / Paste | Cmd-X / C / V | Ctrl-X / C / V |
| Paste and match style | Option-Shift-Cmd-V | Ctrl-Shift-V |
| Select all | Cmd-A | Ctrl-A |
| Find | Cmd-F | Ctrl-F |
| Find next / previous | Cmd-G / Shift-Cmd-G | F3 / Shift-F3 (or Ctrl-G) |
| Use selection for Find | Cmd-E | — |
| Bold / Italic / Underline | Cmd-B / I / U | Ctrl-B / I / U |
| Settings / Preferences | Cmd-Comma | Ctrl-Comma (common in cross-platform apps) |
| Help | Cmd-Shift-? | F1 |
| Cancel operation | Cmd-Period or Esc | Esc |
| New tab | Cmd-T | Ctrl-T |
| Next / previous window of the app | Cmd-` / Shift-Cmd-` | Alt-Tab (system) |
| Minimize window | Cmd-M | Win-Down |
| Enter full screen | Ctrl-Cmd-F | F11 |
| Zoom in / out | Cmd-= / Cmd-- | Ctrl-= / Ctrl-- |
| Show / hide toolbar | Option-Cmd-T | — |
| Show / hide sidebar | Ctrl-Cmd-S | — |
| Inspector / Info | Option-Cmd-I / Cmd-I | — |
| Line start / end | Cmd-Left / Cmd-Right | Home / End |
| Document start / end | Cmd-Up / Cmd-Down | Ctrl-Home / Ctrl-End |
| Word left / right | Option-Left / Option-Right | Ctrl-Left / Ctrl-Right |
| Extend selection | add Shift to any movement shortcut | add Shift to any movement shortcut |
| Move focus between cells/values in a table | Ctrl-Arrow | Arrow keys / Tab |

**Never override system-reserved shortcuts** — app switching (Cmd-Tab / Alt-Tab), system search (Cmd-Space / Win), screenshots, force quit, input-source switching (Ctrl-Space), screen-reader and zoom toggles, and lock/log out.

### Custom keyboard shortcuts

**Define custom keyboard shortcuts for only the most frequently used app-specific commands.** People appreciate using keyboard shortcuts for actions they perform frequently, but defining too many new shortcuts can make your app seem difficult to learn.

**Use modifier keys in ways that people expect.** For example, pressing Command while dragging moves items as a group, and pressing Shift while drag-resizing constrains resizing to the item’s aspect ratio. In addition, holding an arrow key moves the selected item by the smallest app-defined unit of distance until people release the key.

Here are the modifier keys and the symbols that represent them.

| Modifier key | Symbol | Recommended usage |
| --- | --- | --- |
| Command (Mac) / Ctrl (Windows, Linux) | ⌘ / Ctrl | Prefer it as the main modifier key in a custom keyboard shortcut. |
| Shift | ⇧ | Prefer the Shift key as a secondary modifier that complements a related shortcut. |
| Option (Mac) / Alt | ⌥ / Alt | Use this modifier sparingly for less-common commands or power features. |
| Control (Mac) / Windows-Super key | ⌃ / ⊞ | Avoid as a modifier in custom shortcuts. Systems use these keys for many systemwide features, like moving focus or capturing screenshots. |

> **Tip**: Some languages require modifier keys to generate certain characters. For example, on a French keyboard, Option-5 generates the “{“ character. It’s usually safe to use Command/Ctrl as a modifier, but avoid using an additional modifier with characters that aren’t available on all keyboards. If you must use a modifier other than Command, prefer using it only with the alphabetic characters.

**List modifier keys in the correct order.** If you use more than one modifier key in a custom shortcut, always list them in the platform order — Mac: Control, Option, Shift, Command; Windows/Linux: Ctrl, Alt, Shift.

**Avoid adding Shift to a shortcut that uses the upper character of a two-character key.** People already understand that they must hold the Shift key to type the upper character of a two-character key, so it’s clearer to simply list the upper character in the shortcut. For example, the keyboard shortcut for Hide Status Bar is Command-Slash, whereas the keyboard shortcut for Help is Command-Question mark, not Shift-Command-Slash.

**Let the system localize and mirror your keyboard shortcuts as needed.** The system automatically localizes a shortcut’s primary and modifier keys to support the currently connected keyboard; if your app or game switches to a right-to-left layout, the system automatically mirrors the shortcut. For guidance, see Right to left.

**Avoid creating a new shortcut by adding a modifier to an existing shortcut for an unrelated command.** For example, because people are accustomed to using Cmd/Ctrl-Z for undoing an action, it would be confusing to use Shift-Cmd/Ctrl-Z as the shortcut for a command that’s unrelated to undo and redo.


### Device-specific considerations

## Pointing devices

People can use a pointing device like a trackpad or mouse to navigate the interface and initiate actions.

People appreciate the precision and flexibility that pointing devices offer. On a computer, people typically expect to combine a pointing device with a keyboard as they navigate apps and the system.


### Best practices

**Be consistent when responding to mouse and trackpad gestures.** People expect most gestures to work the same throughout the system, regardless of the app or game they’re using. On a computer, for example, people rely on the “Swipe between pages” gesture to behave the same way whether they’re browsing individual document pages, webpages, or images.

**Avoid redefining systemwide trackpad gestures.** Even in a game that uses app-specific gestures in a custom way, people expect systemwide gestures to be available; for example, people expect to make familiar gestures to reveal the dock/taskbar or the window overview on desktop. Remember that desktop users can customize the gestures for performing systemwide actions.

**Provide a consistent experience in your app, whether people are using gestures, eyes, a pointing device, or a keyboard.** People expect to move fluidly between multiple types of input, and they don’t want to learn different interactions for each mode or for each app they use.

**Let people use the pointer to reveal and hide controls that automatically minimize or fade out.** On tablets, for example, people can reveal the minimized browser toolbar by holding the pointer over it (the toolbar minimizes again when the pointer moves away). People can also move the pointer to reveal or hide playback controls while they watch a full-screen video.

**Provide a consistent experience when people press and hold a modifier key while interacting with objects in your app.** For example, if people can duplicate an object by pressing and holding the Option key while they drag that object, ensure the result is the same whether they drag using touch or the pointer.


### Device-specific considerations

#### Tablet
Tablets build on the traditional pointer experience, automatically adapting the pointer to the current context and providing rich visual feedback at a level of precision that enhances productivity and simplifies common tasks on a touchscreen device. A tablet pointing system gives people an additional way to interact with apps and content — it doesn’t replace touch.

**Allow multiple selection in custom views when necessary.** On tablets, people can click and drag the pointer over multiple items to select them. As people use the pointer in this way, it expands into a visible rectangle that selects the items it encompasses. Standard nonlist collection views support this interaction by default; if you want to support multiple selection in custom views, you need to implement it yourself.

**Distinguish between pointer and finger input only if it provides value.** For example, a scrubber can give people an additional way to target a location in a video when they’re using the pointer. In this scenario, people can drag the playhead using either the pointer or touch, but they can use the pointer to click a precise seek destination.


##### Pointer shape and content effects

Tablets integrate the appearance and behavior of both the pointer and the element it moves over, bringing focus to the item the pointer is targeting. You can support the system-provided pointer effects or modify them to suit your experience.

By default, the pointer’s shape is a circle, but it can display a system-defined or custom shape when people move it over specific elements or regions. For example, the pointer automatically uses the familiar I-beam shape when people move it over a text-entry area.

With a *content effect*, the UI element or region beneath the pointer can also change its appearance when people hold the pointer over it. Depending on the type of content effect, the pointer can retain its current shape or transform into a shape that integrates with the element’s new appearance.

Tablets define three content effects that bring focus to different types of interactive elements in your app: highlight, lift, and hover.

The *highlight* effect transforms the pointer into a translucent, rounded rectangle that acts as a background for a control and includes a gentle parallax. The subtle highlighting and movement bring focus to the control without distracting people from their task. By default, tablets apply the highlight effect to bar buttons, tab bars, segmented controls, and edit menus.

The *lift* effect combines a subtle parallax with the appearance of elevation to make an element seem like it’s floating above the screen. As the pointer fades out beneath the element, tablets create the illusion of lift by scaling the element up while adding a shadow below it and a soft specular highlight on top of it. By default, tablets apply the lift effect to app icons and to buttons in the control panel.

*Hover* is a generic effect that lets you apply custom scale, tint, or shadow values to an element as the pointer moves over it. The hover effect combines your custom values to bring focus to an item, but it doesn’t transform the default pointer shape.


##### Pointer accessories

Pointer accessories are visual indicators that help people understand how they can use the pointer to interact with the current UI element. For example, a pointer approaching a resizable element might display small arrows to indicate that the element allows resizing along a certain axis.

Unlike pointer shapes and content effects, accessories are secondary items that can combine with any pointer to communicate additional information.

**Use clear, simple images to create custom accessories.** A pointer accessory is small, so it’s essential to create an image that communicates the pointer interaction without using too many details.

**Consider using the accessory transition to signal a change in an element’s state or behavior.** In addition to animating the appearance and disappearance of pointer accessories, the system also animates the transitions among accessory shapes and positions that can accompany content effects. For example, you could communicate that an add action has become unavailable by transitioning the pointer accessory from the plus symbol to the circle.slash symbol.


##### Pointer magnetism

Tablets help people use the pointer to target an element by making the element appear to attract the pointer. People can experience this magnetic effect when they move the pointer close to an element and when they flick the pointer toward an element.

When people move the pointer close to an element, the system starts transforming the pointer’s shape as soon as it reaches the element’s hit region. Because an element’s hit region typically extends beyond its visible boundaries, the pointer begins to transform before it appears to touch the element itself, creating the illusion that the element is pulling the pointer toward it.

When people flick the pointer toward an element, the system examines the pointer’s trajectory to discover the element that’s the most likely target. When there’s an element in the pointer’s path, the system uses magnetism to pull the pointer toward the element’s center.

By default, tablets apply magnetism to elements that use the lift effect (like app icons) and the highlight effect (like bar buttons), but not to elements that use hover. Because an element that supports hover doesn’t transform the default pointer shape, adding magnetism could be jarring and might make people feel that they’ve lost control of the pointer.

The system also applies magnetism to text-entry areas, where it can help people avoid skipping to another line if they make unintended vertical movements while they’re selecting text.


##### Standard pointers and effects

**When possible, support the system-provided content effects.** People quickly become accustomed to the content effects they see throughout the system and generally expect their experience to apply to every app they use. To provide a consistent user experience, align your interactions with the design intent of each effect. Specifically:

- Use highlight for a small element that has a transparent background.

- Use lift for a small element that has an opaque background.

- Use hover for large elements and customize the scale, tint, and shadow attributes as needed (for guidance, see Customizing pointers).

**Prefer the system-provided pointer appearances for standard buttons and text-entry areas.** You can help people feel more comfortable with your app when the pointer behaves in ways they expect.

**Add padding around interactive elements to create comfortable hit regions.** You might need to experiment to determine the right size for an element’s hit region. If the hit region is too small, it can make people feel that they have to be extra precise when interacting with the element. On the other hand, when an element’s hit region is too large, people can feel that it takes a lot of effort to pull the pointer away from the element. In general, it works well to add about 12 points of padding around elements that include a bezel; for elements without a bezel, it works well to add about 24 points of padding around the element’s visible edges.

**Create contiguous hit regions for custom bar buttons.** If there’s space between the hit regions of adjacent buttons in a bar, people may experience a distracting motion when the pointer reverts briefly to its default shape as it moves between buttons.

**Specify the corner radius of a nonstandard element that receives the lift effect.** With the system-provided lift effect, the pointer transforms to match the element’s shape as it fades out. By default, the pointer uses the system-defined corner radius to transform into a rounded rectangle. If your element is a different shape — if it’s a circle, for example — you need to provide the radius so the pointer can animate seamlessly into the shape of the element.


##### Customizing pointers

**Prefer system-provided pointer effects for custom elements that behave like standard elements.** When a custom element behaves like a standard one, people generally expect to interact with it using familiar pointer interactions. For example, if buttons in a custom toolbar don’t use the standard highlight effect, people might think they’re broken.

**Use pointer effects in consistent ways throughout your app.** For example, if your app helps people draw, provide a similar pointer experience for every drawing area in your app so that people can apply the knowledge they gain in one area to the others.

**Avoid creating gratuitous pointer and content effects.** People notice when the appearance of the pointer or the UI element beneath it changes, and they expect the changes to be useful. Creating a purely decorative pointer effect can distract and even irritate people without providing any practical value.

**Keep custom pointer shapes simple.** Ideally, the pointer’s shape signals the action people can take in the current context without drawing too much attention to itself. If people don’t instantly understand your custom pointer shape, they’re likely to waste time trying to discover what the shape means.

**Consider enhancing the pointer experience by displaying custom annotations that provide useful information.** For example, you could display X and Y values when people hold the pointer over a graphing area in your app. A presentation app uses annotations to display the current width and height of a resizable image.

**Avoid displaying instructional text with a pointer.** A pointer that displays instructional text can make an app seem complicated and difficult to use. Instead of providing instructions, prioritize clarity and simplicity in your interface, so that people can quickly grasp how to use your app whether they’re using the pointer or touching the screen.

**Consider the interplay of shadow, scale, and element spacing when defining custom hover effects.** In general, reserve scaling for elements that can increase in size without crowding nearby elements. For example, scaling doesn’t work well for a table row because a row can’t expand without overlapping adjacent rows. For an element that has little space around it, consider using a hover effect that includes tint, but not scale and shadow. Note that it doesn’t work well to use shadow without including scale, because an unscaled element doesn’t appear to get closer to the viewer even when its shadow implies that it’s elevated above the screen.


#### Desktop
Desktop supports a wide range of standard mouse and trackpad interactions that people can customize. For example, when a click or gesture isn’t a primary way to interact with content, people can often turn it on or off based on their current workflow. People can also choose specific regions of a mouse or trackpad to invoke secondary clicks, and select specific finger combinations and movements for certain gestures.

| Click or gesture | Expected behavior | Mouse | Trackpad |
| --- | --- | --- | --- |
| Primary click | Select or activate an item, such as a file or button. | ● | ● |
| Secondary click | Reveal contextual menus. | ● | ● |
| Scrolling | Move content up, down, left, or right within a view. | ● | ● |
| Smart zoom | Zoom in or out on content, such as a web page or PDF. | ● | ● |
| Swipe between pages | Navigate forward or backward between individually displayed pages. | ● | ● |
| Swipe between full-screen apps | Navigate forward or backward between full-screen apps and spaces. | ● | ● |
| Window overview (e.g. swipe up with three or four fingers) | Show all open windows. | ● | ● |
| Lookup and data detectors (force click with one finger or tap with three fingers) | Display a lookup window above selected content. | | ● |
| Tap to click | Perform the primary click action using a tap rather than a click. | | ● |
| Force click | Click then press firmly to display a preview or lookup window above selected content. Apply a variable amount of pressure to affect pressure-sensitive controls, such as variable speed media controls. | | ● |
| Zoom in or out (pinch with two fingers) | Zoom in or out. | | ● |
| Rotate (move two fingers in a circular motion) | Rotate content, such as an image. | | ● |
| App windows (swipe down with three or four fingers) | Show the current app’s windows. | | ● |
| Show Desktop (spread with thumb and three fingers) | Slide all windows out of the way to reveal the desktop. | | ● |


##### Pointers

Desktop offers a variety of standard pointer styles, which your app can use to communicate the interactive state of an interface element or the result of a drag operation.

| Name | Meaning | CSS `cursor` |
| --- | --- | --- |
| Arrow | Standard pointer for selecting and interacting with content and interface elements. | `default` |
| Closed hand | Dragging to reposition the display of content within a view—for example, dragging a map around in a maps app. | `grabbing` |
| Contextual menu | A contextual menu is available for the content below the pointer. This pointer is generally shown only when the Control key is pressed. | `context-menu` |
| Crosshair | Precise rectangular selection is possible, such as when viewing an image in an image viewer. | `crosshair` |
| Disappearing item | A dragged item will disappear when dropped. If the item references an original item, the original is unaffected. For example, when dragging a mailbox out of the favorites bar in a mail app, the original mailbox isn’t removed. | `—` |
| Drag copy | Duplicates a dragged—not moved—item when dropped into the destination. Appears when pressing the Option key during a drag operation. | `copy` |
| Drag link | During a drag and drop operation, creates an alias of the selected file when dropped. The alias points to the original file, which remains unmoved. Appears when pressing the Option and Command keys during a drag operation. | `alias` |
| Horizontal I beam | Selection and insertion of text is possible in a horizontal layout, such as a text document. | `text` |
| Open hand | Dragging to reposition content within a view is possible. | `grab` |
| Operation not allowed | A dragged item can’t be dropped in the current location. | `not-allowed` |
| Pointing hand | The content beneath the pointer is a URL link to a webpage, document, or other item. | `pointer` |
| Resize down | Resize or move a window, view, or element downward. | `s-resize` |
| Resize left | Resize or move a window, view, or element to the left. | `w-resize` |
| Resize left/right | Resize or move a window, view, or element to the left or right. | `ew-resize` |
| Resize right | Resize or move a window, view, or element to the right. | `e-resize` |
| Resize up | Resize or move a window, view, or element upward. | `n-resize` |
| Resize up/down | Resize or move a window, view, or element upward or downward. | `ns-resize` |
| Vertical I beam | Selection and insertion of text is possible in a vertical layout. | `vertical-text` |


## Focus and selection

Focus helps people visually confirm the object that their interaction targets.

Focus supports simplified, component-based navigation.

In many cases, focusing an item also selects it. The exception is when automatic selection might cause a distracting context shift, like opening a new view.

Different platforms communicate focus in different ways. The combination of focus effects and interactions is sometimes called a *focus system* or *focus model*.


### Best practices

**Rely on system-provided focus effects.** System-defined focus effects are precisely tuned to complement interactions with devices, providing experiences that feel responsive, fluid, and lifelike. Incorporating system-provided focus behaviors gives your app consistency and predictability, helping people understand it quickly. Consider creating custom focus effects only if it’s absolutely necessary.

**Avoid changing focus without people’s interaction.** People rely on the focus system to help them know where they are in your app. If you change focus without their interaction, people have to spend time finding the newly focused item, delaying their current task. The exception is when people are moving focus using an input device that lets them make discrete, directional movements — like a keyboard, remote, or game controller — and a previously focused item disappears. In this scenario, there are only a small number of items within one discrete step of the previously focused item, so moving focus to one of these remaining items ensures that the focus indicator is in a location people can easily find. When people aren’t moving focus by using such an input device, you can’t predict the item they’ll target next, so it’s generally best to simply hide the focus indicator when the focused object disappears.

**Be consistent with the platform as you help people bring focus to items in your app.** For example, on tablets and desktop, a full keyboard access mode helps people use the keyboard to reach every control, so you only need to support focus for content elements like list items, text fields, and search fields, and not for controls like buttons, sliders, and toggles.

**Indicate focus using visual appearances that are consistent with the platform.** For example, consider a window that contains a list of items. On tablets and desktop, the system draws focused list items using white text and a background highlight that matches the app’s accent color, drawing unfocused items using the standard text color and a gray background highlight.

**In general, use a focus ring for a text or search field, but use a highlight in a list or collection.** Although you can use a focus ring to draw attention to an item that fills a cell, like a photo, it’s usually easier for people to view lists and collections when an entire row is highlighted.


### Device-specific considerations

#### Tablet
Tablets define a focus system that supports keyboard interactions for navigating text fields, text views, and sidebars, in addition to various types of collection views and other custom views in your app.

The tablets focus systems are similar. Although the underlying system is the same, the user experiences are a little different. In contrast, tablets define *focus groups*, which represent specific areas within an app, like a sidebar, grid, or list. Using focus groups, tablets can support two different keyboard interactions.

- Pressing the Tab key moves focus among focus groups, letting people navigate to sidebars, grids, and other app areas.

- For example, people can use an arrow key to move through the items in a list or a sidebar.

Onscreen components can indicate focus by using the halo effect or the highlighted appearance.

The *halo* focus effect — also known as the *focus ring* — displays a customizable outline around the component. You can apply the halo effect to custom views and to fully opaque content within a collection or list cell, such as an image.

**Customize the halo focus effect when necessary.** By default, the system uses an item’s shape to infer the shape of its halo. If the system-provided halo doesn’t give you the appearance you want, you can refine it to match contours like rounded corners or shapes defined by Bézier paths. You can also adjust a halo’s position if another component occludes or clips it. For example, you might need to ensure that a badge appears above the halo or that a parent view doesn’t clip it.

The *highlighted* appearance — in which the component’s text uses the app’s accent color — also indicates focus, but it’s not a focus effect. The highlight appearance occurs automatically when people select a collection view cell on which you’ve set content configurations.

**Ensure that focus moves through your custom views in ways that make sense.** As people continue pressing the Tab key, focus moves through focus groups in reading order: leading to trailing, and top to bottom. Although focus moves through system-provided views in ways that people expect, you might need to adjust the order in which the focus system visits your custom views. For example, if you want focus to move down through a vertical stack of custom views before it moves in the trailing direction to the next view, you need to identify the stack container as a single focus group.

**Adjust the priority of an item to reflect its importance within a focus group.** When a group receives focus, its *primary item* automatically receives focus too, making it easy for people to select the item they’re most likely to want. You can make an item primary by increasing its priority.


## Game controls

Precise, intuitive game controls enhance gameplay and can increase a player’s immersion in the game.

Players might prefer to use physical game controllers, but there are two important reasons to also support a platform’s default interaction methods:


- Players appreciate games that let them use the platform interaction method they’re most familiar with.

To reach the widest audience and provide the best experience for each platform, keep these factors in mind when choosing the input methods to support.


### Touch controls

For phone and tablet games, supporting touch interaction means that you can provide virtual controls on top of game content while also letting players interact with game elements by touching them directly. Use your platform’s or engine’s virtual-controller support to add these controls. Keep the following guidelines in mind to create an enjoyable touch control experience.

**Determine whether it makes sense to display virtual controls on top of game content.** In general, virtual game controls benefit games that offer a large number of actions or require players to control movement. However, sometimes gameplay is more immersive and effective when players can interact directly with in-game objects. Look for opportunities to reduce the amount of virtual controls that overlap your game content by associating actions with in-game gestures instead. For example, consider letting players tap objects to select them instead of adding a virtual selection button.

**Place virtual buttons where they’re easy to access.** Take into account the device’s boundaries and safe areas as well as comfortable locations for controls. Place frequently used buttons near a player’s thumb, avoiding the circular regions where players expect movement and camera input to happen. Place secondary controls, like menus, at the top of the screen.

**Make sure controls are large enough.** Make sure frequently used controls are a minimum size of 44x44 pt, and less important controls, such as menus, are a minimum size of 28x28 pt to accommodate people’s fingers.

**Always include visible and tactile press states.** A virtual control feels unresponsive without a visual and physical press state. Help players understand when they successfully interact with a button by adding a visual press state effect, such as a glow, that they can see even when their finger is covering the control. Combine this press state with sound and haptics to enhance the feeling of feedback. For guidance, see Playing haptics.

**Use symbols that communicate the actions they perform.** Choose artwork that visually represents the action each button performs, such as a graphic of a weapon to represent an attack. Avoid using abstract shapes or controller-based naming like A, X, or R1 as artwork, which makes it harder for players to understand and remember what specific controls do.

**Show and hide virtual controls to reflect gameplay.** Take advantage of the dynamic nature of touch controls and adapt what controls players see onscreen depending on their context. You can hide controls when an action isn’t available or relevant, letting you reduce clutter and help players concentrate on what’s important. For example, consider hiding movement controls until a player touches the screen to reduce the amount of UI overlapping your game content.

**Combine functionality into a single control.** Consider redesigning game mechanics that require players to press multiple buttons at the same time or in a sequence. Leverage gestures such as double tap and touch and hold to provide different variations of the same action, such as touch and hold to use a special powered up version of an attack. For multiple actions, such as walking or sprinting, consider combining the actions into a single control.

**Map movement and camera controls to predictable behavior.** Typically, players expect to control movement using the left side of their screen, and control camera direction using the right side of their screen. Maximize the amount of space that players can control both movement and the camera direction by using as large of an input area as possible. For movement control, opt to show a virtual thumbstick wherever the player lands their thumb instead of a static thumbstick position. For camera control, opt to use direct touch to pan the camera instead of a virtual thumbstick.


### Physical controllers


**Automatically detect whether a controller is paired.** Instead of having players manually set up a physical game controller, you can automatically detect whether a controller is paired and get its profile.

**Customize onscreen content to match the connected game controller.** To simplify your game’s code, controller APIs typically assign standard names to controller elements based on their placement, but the colors and symbols on an actual game controller may differ. Be sure to use the connected controller’s labeling scheme when referring to controls or displaying related content in your interface.

**Map controller buttons to expected UI behavior.** Outside of gameplay, players expect to navigate your game’s UI in a way that matches the familiar behavior of the platform they’re playing on. When not controlling gameplay, follow these conventions across platforms:

| Button | Expected behavior for UI |
| --- | --- |
| A | Activates a control |
| B | Cancels an action or returns to previous screen |
| X | — |
| Y | — |
| Left shoulder | Navigates left to a different screen or section |
| Right shoulder | Navigates right to a different screen or section |
| Left trigger | — |
| Right trigger | — |
| Left/right thumbstick | Moves selection |
| Directional pad | Moves selection |
| Home/logo | Reserved for system controls |
| Menu | Opens game settings or pauses gameplay |

**Support multiple connected controllers.** If there are multiple controllers connected, use labels and glyphs that match the one that the player is actively using. If your game supports multiplayer, use the appropriate labels and symbols when referring to a specific player’s controller. If you need to refer to buttons on multiple controllers, consider listing them together.

**Prefer using symbols, not text, to refer to game controller elements.** Use glyph sets that match each controller brand’s buttons (most controller APIs and engines provide them). Using symbols instead of text descriptions can be especially helpful for players who aren’t experienced with controllers because it doesn’t require them to hunt for a specific button label during gameplay.


### Keyboards

Keyboard players appreciate using keyboard bindings to speed up their interactions with apps and games.

**Prioritize single-key commands.** Single-key commands are generally easier and faster for players to perform, especially while they’re simultaneously using a mouse or trackpad. For example, you might use the first letter of a menu item as a shortcut, such as I for Inventory or M for Map; you might also map the game’s main action to the Space bar, taking advantage of the key’s relatively large size.

**Test key-binding comfort on different keyboard layouts.** A binding that uses Control on a PC keyboard might be better mapped to Command on a Mac keyboard, where Command sits next to the Space bar and is easy to reach while using W, A, S, and D. Also test non-QWERTY layouts (AZERTY, QWERTZ) and let players rebind.

**Take the proximity of keys into account.** For example, if players navigate using the W, A, S, and D keys, consider using nearby keys to define other high-value commands. Similarly, if there’s a group of closely related actions, it can work well to map their bindings to keys that are physically close together, such as using the number keys for inventory categories.

**Let players customize key bindings.** Although players tend to expect a reasonable set of defaults, many people need to customize a game’s key bindings for personal comfort and play style.


### Device-specific considerations
