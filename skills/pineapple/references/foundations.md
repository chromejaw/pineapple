# Foundations of Design

Universal design elements covering accessibility, color, typography, layout, motion, privacy, and visual expression.

---

## Accessibility

Accessible user interfaces empower everyone to have a great experience with your app or game.

When you design for accessibility, you reach a larger audience and create a more inclusive experience. An accessible interface allows people to experience your app or game regardless of their capabilities or how they use their devices. Accessibility makes information and interactions available to everyone. An accessible interface is:

- **Intuitive.** Your interface uses familiar and consistent interactions that make tasks straightforward to perform.

- **Perceivable.** Your interface doesn’t rely on any single method to convey information. People can access and interact with your content, whether they use sight, hearing, speech, or touch.

- **Adaptable.** Your interface adapts to how people want to use their device, whether by supporting system accessibility features or letting people personalize settings.

As you design your app, audit the accessibility of your interface. Use your platform’s accessibility inspector (or an automated checker such as axe or Lighthouse on the web) to highlight issues and understand how your app represents itself to assistive technologies. Consider publishing an accessibility statement so people know which features your app supports.


### Vision

The people who use your interface may be blind, color blind, or have low vision or light sensitivity. They may also be in situations where lighting conditions and screen brightness affect their ability to interact with your interface.

**Support larger text sizes.** Make sure people can adjust the size of your text or icons to make them more legible, visible, and comfortable to read. Your interface can support font size enlargement either through custom UI, or by adopting dynamic text sizing. Dynamic text sizing is a systemwide setting that lets people adjust the size of text for comfort and legibility. For more guidance, see Supporting dynamic text sizing.

**Use recommended defaults for custom type sizes.** Each platform has different default and minimum sizes for system-defined type styles to promote readability. If you’re using custom type styles, follow the recommended defaults.

| Platform | Default size | Minimum size |
| --- | --- | --- |
| phones and tablets | 17 pt | 11 pt |
| desktop | 13 pt | 10 pt |

**Bear in mind that font weight can also impact how easy text is to read.** If you’re using a custom font with a thin weight, aim for larger than the recommended sizes to increase legibility. For more guidance, see Typography.

**Strive to meet color contrast minimum standards.** To ensure all information in your app is legible, it’s important that there’s enough contrast between foreground text and icons and background colors. Two popular standards of measure for color contrast are the Web Content Accessibility Guidelines (WCAG) and the Accessible Perceptual Contrast Algorithm (APCA). Use standard contrast calculators to ensure your UI meets acceptable levels. Accessibility Inspector uses the following values from WCAG Level AA as guidance in determining whether your app’s colors have an acceptable contrast.

| Text size | Text weight | Minimum contrast ratio |
| --- | --- | --- |
| Up to 17 pts | All | 4.5:1 |
| 18 pts | All | 3:1 |
| All | Bold | 3:1 |

If your app doesn’t provide this minimum contrast by default, ensure it at least provides a higher contrast color scheme when the system setting Increase Contrast is turned on. If your app supports Dark Mode, make sure to check the minimum contrast in both light and dark appearances.

**Prefer system-defined colors.** These colors have their own accessible variants that automatically adapt when people adjust their color preferences, such as enabling Increase Contrast or toggling between the light and dark appearances. For guidance, see Color.

**Convey information with more than color alone.** Some people have trouble differentiating between certain colors and shades. For example, people who are color blind may have particular difficulty with pairings such as red-green and blue-orange. Offer visual indicators, like distinct shapes or icons, in addition to color to help people perceive differences in function and changes in state. Consider allowing people to customize color schemes such as chart colors or game characters so they can personalize your interface in a way that’s comfortable for them.

**Describe your app’s interface and content for the screen reader.** A screen reader lets people experience your app’s interface without needing to see the screen. For more guidance, see [Commerce, Accounts & Accessibility › Screen Readers](./commerce-accounts-and-accessibility.md).


### Hearing

The people who use your interface may be deaf or hard of hearing. They may also be in noisy or public environments.

**Support text-based ways to enjoy audio and video.** It’s important that dialogue and crucial information about your app or game isn’t communicated through audio alone. Depending on the context, give people different text-based ways to experience their media, and allow people to customize the visual presentation of that text:

- **Captions** give people the textual equivalent of audible information in video or audio-only content. Captions are great for scenarios like game cutscenes and video clips where text synchronizes live with the media.

- **Subtitles** allow people to read live onscreen dialogue in their preferred language. Subtitles are great for TV shows and movies.

- **Audio descriptions** are interspersed between natural pauses in the main audio of a video and supply spoken narration of important information that’s presented only visually.

- **Transcripts** provide a complete textual description of a video, covering both audible and visual information. Transcripts are great for longer-form media like podcasts and audiobooks where people may want to review content as a whole or highlight the transcript as media is playing.


**Use haptics in addition to audio cues.** If your interface conveys information through audio cues — such as a success chime, error sound, or game feedback — consider pairing that sound with matching haptics for people who can’t perceive the audio or have their audio turned off. On phones and tablets, you can also use haptic music playback and audio graphs (where the platform supports them) to let people experience music and infographics through vibration and texture. For guidance, see Playing haptics.

**Augment audio cues with visual cues.** This is especially important for games and spatial apps where important content might be taking place off screen. When using audio to guide people towards a specific action, also add in visual indicators that point to where you want people to interact.


### Mobility

Ensure your interface offers a comfortable experience for people with limited dexterity or mobility.

**Offer sufficiently sized controls.** Controls that are too small are hard for many people to interact with and select. Strive to meet the recommended minimum control size for each platform to ensure controls and menus are comfortable for all when tapping and clicking.

| Platform | Default control size | Minimum control size |
| --- | --- | --- |
| phones and tablets | 44x44 pt | 28x28 pt |
| desktop | 28x28 pt | 20x20 pt |

**Consider spacing between controls as important as size.** Include enough padding between elements to reduce the chance that someone taps the wrong control. In general, it works well to add about 12 points of padding around elements that include a bezel. For elements without a bezel, about 24 points of padding works well around the element’s visible edges.

**Support simple gestures for common interactions.** For many people, with or without disabilities, complex gestures can be challenging. For interactions people do frequently in your app or game, use the simplest gesture possible — avoid custom multifinger and multihand gestures — so repetitive actions are both comfortable and easy to remember.

**Offer alternatives to gestures.** Make sure your UI’s core functionality is accessible through more than one type of physical interaction. Gestures can be less comfortable for people who have limited dexterity, so offer onscreen ways to achieve the same outcome. For example, if you use a swipe gesture to dismiss a view, also make a button available so people can tap or use an assistive device.

**Let people use Voice Control to give guidance and enter information verbally.** With Voice Control, people can interact with their devices entirely by speaking commands. They can perform gestures, interact with screen elements, dictate and edit text, and more. To ensure a smooth experience, label interface elements appropriately.


**Support mobility-related assistive technologies.** Features like screen readers, on-screen assistive touch menus, full keyboard access, head and hand pointer control, and switch control offer alternative ways for people with low mobility to interact with their devices. Conduct testing and verify that your app or game supports these technologies, and that your interface elements are appropriately labeled to ensure a great experience.


### Speech

The platform’s accessibility features help people with speech disabilities and people who prefer text-based interactions to communicate effectively using their devices.

**Let people use the keyboard alone to navigate and interact with your app.** People can turn on Full Keyboard Access to navigate apps using their physical keyboard. The system also defines accessibility keyboard shortcuts and a wide range of other keyboard shortcuts that many people use all the time. Avoid overriding system-defined keyboard shortcuts and evaluate your app to ensure it works well with Full Keyboard Access. For additional guidance, see Keyboards.

**Support Switch Control.** Switch Control is an assistive technology that lets people control their devices through separate hardware, game controllers, or sounds such as a click or a pop. People can perform actions like selecting, tapping, typing, and drawing when your app or game supports the ability to navigate using Switch Control.


### Cognitive

When you minimize complexity in your app or game, all people benefit.

**Keep actions simple and intuitive.** Ensure that people can navigate your interface using easy-to-remember and consistent interactions. Prefer system gestures and behaviors people are already familiar with over creating custom gestures people must learn and retain.

**Minimize use of time-boxed interface elements.** Views and controls that auto-dismiss on a timer can be problematic for people who need longer to process information, and for people who use assistive technologies that require more time to traverse the interface. Prefer dismissing views with an explicit action.

**Consider offering difficulty accommodations in games.** Everyone has their own way of playing and enjoying games. To support a variety of cognitive abilities, consider adding the ability to customize the difficulty level of your game, such as offering options for people to reduce the criteria for successfully completing a level, adjust reaction time, or enable control assistance.

**Let people control audio and video playback.** Avoid autoplaying audio and video content without also providing controls to start and stop it. Make sure these controls are discoverable and easy to act upon, and consider global settings that let people opt out of auto-playing all audio and video.

**Allow people to opt out of flashing lights in video playback.** People might want to avoid bright, frequent flashes of light in the media they consume. A Dim Flashing Lights setting allows the system to calculate, mitigate, and inform people about flashing lights in a piece of media. If your app supports video playback, ensure that it responds appropriately to the Dim Flashing Lights setting.

**Be cautious with fast-moving and blinking animations.** When you use these effects in excess, it can be distracting, cause dizziness, and in some cases even result in epileptic episodes. People who are prone to these effects can turn on the Reduce Motion accessibility setting. When this setting is active, ensure your app or game responds by reducing automatic and repetitive animations, including zooming, scaling, and peripheral motion. Other best practices for reducing motion include:

- Tightening animation springs to reduce bounce effects

- Tracking animations directly with people’s gestures


- Replacing transitions in x-, y-, and z-axes with fades to avoid motion

- Avoiding animating into and out of blurs

**Optimize your app’s UI for simplified accessibility modes.** Some platforms offer a simplified mode that lets people with cognitive disabilities use a streamlined version of your app, with a default layout and control presentation that reduces cognitive load (large buttons, fewer choices, clear labels).

To optimize your app for this mode, use the following guidelines when a simplified mode is on (or when designing a simple mode of your own):

- Identify the core functionality of your app and consider removing noncritical workflows and UI elements.

- Break up multistep workflows so people can focus on a single interaction per screen.

- Always ask for confirmation twice whenever people perform an action that’s difficult to recover from, such a deleting a file.


### Device-specific considerations

## App icons

A unique, memorable icon expresses your app’s or game’s purpose and personality and helps people recognize it at a glance.

Your app icon is a crucial aspect of your app’s or game’s branding and user experience. It appears on the home screen and in key locations throughout the system, including search results, notifications, system settings, and share sheets. A well-designed app icon conveys your app’s or game’s identity clearly and consistently across all platforms.


### Layer design

Although you can provide a flattened image for your icon, layers give you the most control over how your icon design is represented. A layered app icon comes together to produce a sense of depth and vitality. On each platform, the system applies visual effects that respond to the environment and people’s interactions.

Modern app icons are often built from a background layer and one or more foreground layers so the system can add dimensional effects — specular highlights, refraction, translucency, parallax — that adapt with icon size and system version. Even where a platform flattens icons, designing in layers keeps your icon adaptable.


The system enhances the icon’s visual dimensionality by adding shadows that convey a sense of depth between layers and by using the alpha channel of the upper layers to create an embossed appearance.

You use your favorite design tool to craft the individual foreground layers of your app icon.


**Prefer clearly defined edges in foreground layers.** To ensure system-drawn highlights and shadows look best, avoid soft and feathered edges on foreground layer shapes.

**Vary opacity in foreground layers to increase the sense of depth and liveliness.** For example, a photo app’s icon might separate its centerpiece into multiple layers that contain translucent pieces, bringing greater dynamism to the design.

**Design a background that both stands out and emphasizes foreground content.** If you choose a gradient for your background layer, ensure that it responds well to system lighting effects. If you do import a background layer, make sure it’s full-bleed and opaque.

Outline artwork and convert text to outline in your design. For mesh gradients and raster artwork, prefer PNG format because it’s a lossless image format.


### Icon shape

An app icon’s shape varies based on a platform’s visual language. On phones, tablets and desktop, icons are square, and the system applies masking to produce rounded corners that precisely match the curvature of other rounded interface elements throughout the system and the bezel of the physical device itself.

**Produce appropriately shaped, unmasked layers.** The system masks all layer edges to produce an icon’s final shape. For phones, tablets and desktop icons, provide square layers so the system can apply rounded corners. Providing layers with pre-defined masking negatively impacts specular highlight effects and makes edges look jagged.


### Design

Embrace simplicity in your icon design. Simple icons tend to be easiest for people to understand and recognize. An icon with fine visual features might look busy when rendered with system-provided shadows and highlights, and details may be hard to discern at smaller sizes. Find a concept or element that captures the essence of your app or game, make it the core idea of your icon, and express it in a simple, unique way with a minimal number of shapes. Prefer a simple background, such as a solid color or gradient, that puts the emphasis on your primary design — you don’t need to fill the entire icon canvas with content.

**Provide a visually consistent icon design across all the platforms your app supports.** A consistent design helps people quickly find your app wherever it appears and prevents people from mistaking your app for multiple apps.

**Consider basing your icon design around filled, overlapping shapes.** Overlapping solid shapes in the foreground, particularly when paired with transparency and blurring, can give an icon a sense of depth.

**Include text only when it’s essential to your experience or brand.** Text in icons doesn’t support accessibility or localization, is often too small to read easily, and can make an icon appear cluttered. In some contexts, your app name already appears nearby, making it redundant to display the name within the icon itself.

**Prefer illustrations to photos and avoid replicating UI components.** Photos are full of details that don’t work well when displayed in different appearances, viewed at small sizes, or split into layers. Instead of using photos, create a graphic representation of the content that emphasizes the features you want people to notice. Make sure to avoid extremely thin line weights and sharp corners, because they tend to lose detail and crispness in smaller icon sizes at lower resolutions. If your app has an interface that people recognize, don’t just replicate standard UI components or use app screenshots in your icon.

**Don’t use replicas of other companies’ hardware products.** Product designs are protected and can’t be reproduced in your app icons.


### Visual effects

**Let the system handle blurring and other visual effects.** The system dynamically applies visual effects to your app icon layers, so there’s no need to include specular highlights, drop shadows between layers, beveled edges, blurs, glows, and other effects. In addition to interfering with system-provided effects, custom effects are static, whereas the system supplies dynamic ones.

**Create layer groupings to apply effects to multiple layers at once.** System effects typically occur on individual layers.


### Appearances

On platforms that support icon appearances, people can choose whether their home screen app icons are default, dark, clear, or tinted. For example, someone may want to personalize their app icon appearance to complement their wallpaper. You can design app icon variants for every appearance variant, and the system automatically generates variants you don’t provide.

**Keep your icon’s features consistent across appearances.** To create a seamless experience, keep your icon’s core visual features the same in the default, dark, clear, and tinted appearances. Avoid creating custom icon variants that swap elements in and out with each variant, which may make it harder for people to find your app when they switch appearances.

**Design dark and tinted icons that feel at home beside system app icons.** You can preserve the color palette of your default icon, but be mindful that dark icons are more subdued, and clear and tinted icons are even more so. A great app icon is visible, legible, and recognizable, regardless of its appearance variant.

**Use your light app icon as the basis for your dark icon.** Choose complementary colors that reflect the default design, and avoid excessively bright images. Color backgrounds generally offer the greatest contrast in dark icons. For guidance, see Dark Mode.

**Consider offering alternate app icons.** On platforms that support it, you can let people visit your app’s settings to choose an alternate version of your app icon. For example, a sports app might offer icons for different teams, letting someone choose their favorite. If you offer this capability, make sure each icon you design remains closely related to your content and experience. Avoid creating one someone might mistake for another app.

> **Note**: Alternate app icons need their own dark, clear, and tinted variants wherever the platform offers those appearances.


### Device-specific considerations

### Specifications

The layout, size, style, and appearances of app icons vary by platform.

| Platform | Layout shape | Icon shape after system masking | Layout size | Style | Appearances |
| --- | --- | --- | --- | --- | --- |
| phones, tablets and desktop | Square | Rounded rectangle (square) | 1024x1024 px | Layered | Default, dark, clear light, clear dark, tinted light, tinted dark |

The system automatically scales your icon to produce smaller variants that appear in certain locations, such as Settings and notifications.

App icons support the following color spaces:

- sRGB (color)

- Gray Gamma 2.2 (grayscale)

- Display P3 (wide-gamut color on phones, tablets and desktop only)


---

## Branding

Apps and games express their unique brand identity in ways that make them instantly recognizable while feeling at home on the platform and giving people a consistent experience.

In addition to expressing your brand in your app icon and throughout your experience, highlight it on your app-store product pages and marketing materials, following each store’s marketing guidelines.


### Best practices

**Use your brand’s unique voice and tone in all the written communication you display.** For example, your brand might convey feelings of encouragement and optimism by using plain words, occasional exclamation marks and emoji, and simple sentence structures.

**Apply your app’s accent color judiciously.** Using your brand color too broadly can overwhelm your interface and dilute its impact. Minimize its use on controls and instead use it intentionally for primary actions or status indicators, like badges for unread content or an icon for the selected tab in a tab bar. To express your brand through color, consider moving it into the content layer, where it scrolls beneath glass controls and gets picked up dynamically. For guidance, see Color.

**Consider using a custom font.** If your brand is strongly associated with a specific font, be sure that it’s legible at all sizes and supports accessibility features like bold text and dynamic text sizing. It can work well to use a custom font for headlines and subheadings while using system fonts for body copy and captions, because the system fonts are designed for optimal legibility at small sizes. For guidance, see Typography.

**Express your brand with familiar components.** When you use components that people already know, the experience feels immediately reliable and familiar, and people can focus on the unique content and features that make your app stand apart. If you need to customize a component’s appearance to reflect your brand, ensure that details like sizing, placement, and behavior continue to preserve a familiar experience that’s appropriate for the platform.

**Ensure branding always defers to content.** Using screen space for an element that does nothing but display a brand asset can mean there’s less room for the content people care about. Aim to incorporate branding in refined, unobtrusive ways that don’t distract people from your experience.

**Help people feel comfortable by using standard patterns consistently.** Even a highly stylized interface can be approachable if it maintains familiar behaviors and patterns. Place UI in expected locations, use standard symbols to represent common actions, and rely on established conventions for navigation and modality.

**Resist the temptation to display your logo throughout your app or game unless it’s essential for providing context.** People seldom need to be reminded which app they’re using, and it’s usually better to use the space to give people valuable information and controls.

**Avoid using a launch screen as a branding opportunity.** Some platforms use a launch screen to minimize the startup experience, while simultaneously giving the app or game a little time to load resources (for guidance, see Launch screens). A launch screen disappears too quickly to convey any information, but you might consider displaying a welcome or onboarding screen that incorporates your branding content at the beginning of your experience. For guidance, see Onboarding.

**Follow trademark guidelines.** Other companies’ trademarks — including platform owners’ — must not appear in your app name or images without permission.


---

## Color

Judicious use of color can enhance communication, evoke your brand, provide visual continuity, communicate status and feedback, and help people understand information.

The system defines colors that look good on various backgrounds and appearance modes, and can automatically adapt to vibrancy and accessibility settings. Using system colors is a convenient way to make your experience feel at home on the device.

You may also want to use custom colors to enhance the visual experience of your app or game and express its unique personality. The following guidelines can help you use color in ways that people appreciate, regardless of whether you use system-defined or custom colors.


### Best practices

**Avoid using the same color to mean different things.** Use color consistently throughout your interface, especially when you use it to help communicate information like status or interactivity. For example, if you use your brand color to indicate that a borderless button is interactive, using the same or similar color to stylize noninteractive text is confusing.

**Make sure all your app’s colors work well in light, dark, and increased contrast contexts.** Most platforms offer both light and dark appearance settings. System colors vary subtly depending on the system appearance, adjusting to ensure proper color differentiation and contrast for text, symbols, and other elements. With the Increase Contrast setting turned on, the color differences become far more apparent. When possible, use system colors, which already define variants for all these contexts. If you define a custom color, make sure to supply light and dark variants, and an increased contrast option for each variant that provides a significantly higher amount of visual differentiation. Even if your app ships in a single appearance mode, provide both light and dark colors to support glass adaptivity in these contexts.

**Test your app’s color scheme under a variety of lighting conditions.** Colors can look different when you view your app outside on a sunny day or in dim light. In bright surroundings, colors look darker and more muted. In dark environments, colors appear bright and saturated. Adjust app colors to provide an optimal viewing experience in the majority of use cases.

**Test your app on different devices.** For example, adaptive white-point displays use ambient light sensors to automatically adjust the white point of the display to adapt to the lighting conditions of the current environment. Apps that primarily support reading, photos, video, and gaming can strengthen or weaken this effect by specifying a white point adaptivity style. You can also test the appearance of your app using different color profiles on a computer — such as P3 and Standard RGB (sRGB) — by switching the display’s color profile in system settings. For guidance, see Color management.

**Consider how artwork and translucency affect nearby colors.** Variations in artwork sometimes warrant changes to nearby colors to maintain visual continuity and prevent interface elements from becoming overpowering or underwhelming. A maps app, for example, displays a light color scheme when in map mode but switches to a dark color scheme when in satellite mode. Colors can also appear different when placed behind or applied to a translucent element like a toolbar.

**If your app lets people choose colors, prefer system-provided color controls where available.** Using built-in color pickers provides a consistent user experience, in addition to letting people save a set of colors they can access from any app.


### Inclusive color

**Avoid relying solely on color to differentiate between objects, indicate interactivity, or communicate essential information.** When you use color to convey information, be sure to provide the same information in alternative ways so people with color blindness or other visual disabilities can understand it. For example, you can use text labels or glyph shapes to identify objects or states.

**Avoid using colors that make it hard to perceive content in your app.** For example, insufficient contrast can cause icons and text to blend with the background and make content hard to read, and people who are color blind might not be able to distinguish some color combinations. For guidance, see Accessibility.

**Consider how the colors you use might be perceived in other countries and cultures.** For example, red communicates danger in some cultures, but has positive connotations in other cultures. Make sure the colors in your app send the message you intend.


### System colors

**Avoid hard-coding system color values in your app.** Documented color values are for your reference during the app design process. The actual color values may fluctuate from release to release, based on a variety of environmental variables. Use APIs like Color to apply system colors.

Phones, tablets and desktop also define sets of *dynamic system colors* that match the color schemes of standard UI components and automatically adapt to both light and dark contexts. Each dynamic color is semantically defined by its purpose, rather than its appearance or color values. For example, some colors represent view backgrounds at different levels of hierarchy and other colors represent foreground content, such as labels, links, and separators.

**Avoid redefining the semantic meanings of dynamic system colors.** To ensure a consistent experience and ensure your interface looks great when the appearance of the platform changes, use dynamic system colors as intended. For example, don’t use the separator color as a text color, or secondary text label color as a background color.


### Glass color

By default, glass has no inherent color, and instead takes on colors from the content directly behind it. You can apply color to some glass elements, giving them the appearance of colored or stained glass. This is useful for drawing emphasis to a specific control, like a primary call to action, and is the approach the system uses for prominent button styling. Symbols or text labels on glass controls can also have color.

For smaller elements like toolbars and tab bars, the system can adapt glass between a light and dark appearance in response to the underlying content. By default, symbols and text on these elements follow a monochromatic color scheme, becoming darker when the underlying content is light, and lighter when it’s dark. Glass appears more opaque in larger elements like sidebars to preserve legibility over complex backgrounds and accommodate richer content on the material’s surface.

**Apply color sparingly to the glass material, and to symbols or text on the material.** If you apply color, reserve it for elements that truly benefit from emphasis, such as status indicators or primary actions. To emphasize primary actions, apply color to the background rather than to symbols or text. For example, the system applies the app accent color to the background in prominent buttons — such as the Done button — to draw attention and elevate their visual prominence. Refrain from adding color to the background of multiple controls.

**Avoid using similar colors in control labels if your app has a colorful background.** While color can make apps more visually appealing, playful, or reflective of your brand, too much color can be overwhelming and make control labels more difficult to read. If your app features colorful backgrounds or visually rich content, prefer a monochromatic appearance for toolbars and tab bars, or choose an accent color with sufficient visual differentiation. By contrast, in apps with primarily monochromatic content or backgrounds, choosing your brand color as the app accent color can be an effective way to tailor your app experience and reflect your company’s identity.

**Be aware of the placement of color in the content layer.** Make sure your interface maintains sufficient contrast by avoiding overlap of similar colors in the content layer and controls when possible. Although colorful content might intermittently scroll underneath controls, make sure its default or resting state — like the top of a screen of scrollable content — maintains clear legibility.


### Color management

A *color space* represents the colors in a *color model* like RGB or CMYK. Common color spaces — sometimes called *gamuts* — are sRGB and Display P3.

A *color profile* describes the colors in a color space using, for example, mathematical formulas or tables of data that map colors to numerical representations. An image embeds its color profile so that a device can interpret the image’s colors correctly and reproduce them on a display.

**Apply color profiles to your images.** Color profiles help ensure that your app’s colors appear as intended on different displays. The sRGB color space produces accurate colors on most displays.

**Use wide color to enhance the visual experience on compatible displays.** Wide color displays support a P3 color space, which can produce richer, more saturated colors than sRGB. As a result, photos and videos that use wide color are more lifelike, and visual data and status indicators that use wide color can be more meaningful. When appropriate, use the Display P3 color profile at 16 bits per pixel (per channel) and export images in PNG format. Note that you need to use a wide color display to design wide color images and select P3 colors.

**Provide color space–specific image and color variations if necessary.** In general, P3 colors and images appear fine on sRGB displays. Occasionally, it may be hard to distinguish two very similar P3 colors when viewing them on an sRGB display. Gradients that use P3 colors can also sometimes appear clipped on sRGB displays.


### Device-specific considerations


#### Phone & tablet
Define two sets of dynamic background colors — *system* and *grouped* — each with primary, secondary, and tertiary variants that help you convey a hierarchy of information. In general, use the grouped background colors when you have a grouped list or table; otherwise, use the system set.

With both sets of background colors, you generally use the variants to indicate hierarchy in the following ways:

- Primary for the overall view

- Secondary for grouping content or elements within the overall view

- Tertiary for grouping content or elements within secondary elements

For foreground content, define dynamic colors like these:

| Color | Use for… | Token |
| --- | --- | --- |
| Label | A text label that contains primary content. | label |
| Secondary label | A text label that contains secondary content. | secondaryLabel |
| Tertiary label | A text label that contains tertiary content. | tertiaryLabel |
| Quaternary label | A text label that contains quaternary content. | quaternaryLabel |
| Placeholder text | Placeholder text in controls or text views. | placeholderText |
| Separator | A separator that allows some underlying content to be visible. | separator |
| Opaque separator | A separator that doesn’t allow any underlying content to be visible. | opaqueSeparator |
| Link | Text that functions as a link. | link |


#### Desktop
Desktop UIs need a richer set of dynamic colors, such as:

| Color | Use for… | Token |
| --- | --- | --- |
| Alternate selected control text color | The text on a selected surface in a list or table. | alternateSelectedControlTextColor |
| Alternating content background colors | The backgrounds of alternating rows or columns in a list, table, or collection view. | alternatingContentBackgroundColors |
| Control accent | The accent color people select in System Settings. | controlAccentColor |
| Control background color | The background of a large interface element, such as a browser or table. | controlBackgroundColor |
| Control color | The surface of a control. | controlColor |
| Control text color | The text of a control that is available. | controlTextColor |
| Current control tint | The system-defined control tint. | currentControlTint |
| Unavailable control text color | The text of a control that’s unavailable. | disabledControlTextColor |
| Find highlight color | The color of a find indicator. | findHighlightColor |
| Grid color | The gridlines of an interface element, such as a table. | gridColor |
| Header text color | The text of a header cell in a table. | headerTextColor |
| Highlight color | The virtual light source onscreen. | highlightColor |
| Keyboard focus indicator color | The ring that appears around the currently focused control when using the keyboard for interface navigation. | keyboardFocusIndicatorColor |
| Label color | The text of a label containing primary content. | labelColor |
| Link color | A link to other content. | linkColor |
| Placeholder text color | A placeholder string in a control or text view. | placeholderTextColor |
| Quaternary label color | The text of a label of lesser importance than a tertiary label, such as watermark text. | quaternaryLabelColor |
| Secondary label color | The text of a label of lesser importance than a primary label, such as a label used to represent a subheading or additional information. | secondaryLabelColor |
| Selected content background color | The background for selected content in a key window or view. | selectedContentBackgroundColor |
| Selected control color | The surface of a selected control. | selectedControlColor |
| Selected control text color | The text of a selected control. | selectedControlTextColor |
| Selected menu item text color | The text of a selected menu. | selectedMenuItemTextColor |
| Selected text background color | The background of selected text. | selectedTextBackgroundColor |
| Selected text color | The color for selected text. | selectedTextColor |
| Separator color | A separator between different sections of content. | separatorColor |
| Shadow color | The virtual shadow cast by a raised object onscreen. | shadowColor |
| Tertiary label color | The text of a label of lesser importance than a secondary label. | tertiaryLabelColor |
| Text background color | The background color behind text. | textBackgroundColor |
| Text color | The text in a document. | textColor |
| Under page background color | The background behind a document’s content. | underPageBackgroundColor |
| Unemphasized selected content background color | The selected content in a non-key window or view. | unemphasizedSelectedContentBackgroundColor |
| Unemphasized selected text background color | A background for selected text in a non-key window or view. | unemphasizedSelectedTextBackgroundColor |
| Unemphasized selected text color | Selected text in a non-key window or view. | unemphasizedSelectedTextColor |
| Window background color | The background of a window. | windowBackgroundColor |
| Window frame text color | The text in the window’s title bar area. | windowFrameTextColor |


##### App accent colors

Desktop platforms often let you specify an app *accent color* to customize your buttons, selection highlighting, and sidebar icons. It applies when people keep the system accent at its default/multicolor setting.

If people choose a specific system accent color, the system applies their chosen color to the relevant items throughout your app, replacing your accent color. The exception is a sidebar icon that uses a fixed color you specify. Because a fixed-color sidebar icon uses a specific color to provide meaning, the system doesn’t override its color when people change the value of accent color settings. For guidance, see Sidebars.


### Specifications


#### System colors

| Name | Token | Default (light) | Default (dark) | Increased contrast (light) | Increased contrast (dark) |
| --- | --- | --- | --- | --- | --- |
| Red | red | rgb(255, 56, 60) | rgb(255, 66, 69) | rgb(233, 21, 45) | rgb(255, 97, 101) |
| Orange | orange | rgb(255, 141, 40) | rgb(255, 146, 48) | rgb(197, 83, 0) | rgb(255, 160, 86) |
| Yellow | yellow | rgb(255, 204, 0) | rgb(255, 214, 0) | rgb(161, 106, 0) | rgb(254, 223, 67) |
| Green | green | rgb(52, 199, 89) | rgb(48, 209, 88) | rgb(0, 137, 50) | rgb(74, 217, 104) |
| Mint | mint | rgb(0, 200, 179) | rgb(0, 218, 195) | rgb(0, 133, 117) | rgb(84, 223, 203) |
| Teal | teal | rgb(0, 195, 208) | rgb(0, 210, 224) | rgb(0, 129, 152) | rgb(59, 221, 236) |
| Cyan | cyan | rgb(0, 192, 232) | rgb(60, 211, 254) | rgb(0, 126, 174) | rgb(109, 217, 255) |
| Blue | blue | rgb(0, 136, 255) | rgb(0, 145, 255) | rgb(30, 110, 244) | rgb(92, 184, 255) |
| Indigo | indigo | rgb(97, 85, 245) | rgb(109, 124, 255) | rgb(86, 74, 222) | rgb(167, 170, 255) |
| Purple | purple | rgb(203, 48, 224) | rgb(219, 52, 242) | rgb(176, 47, 194) | rgb(234, 141, 255) |
| Pink | pink | rgb(255, 45, 85) | rgb(255, 55, 95) | rgb(231, 18, 77) | rgb(255, 138, 196) |
| Brown | brown | rgb(172, 127, 94) | rgb(183, 138, 102) | rgb(149, 109, 81) | rgb(219, 166, 121) |


#### Gray ramp

| Name | Token | Default (light) | Default (dark) | Increased contrast (light) | Increased contrast (dark) |
| --- | --- | --- | --- | --- | --- |
| Gray | systemGray | rgb(142, 142, 147) | rgb(142, 142, 147) | rgb(108, 108, 112) | rgb(174, 174, 178) |
| Gray (2) | systemGray2 | rgb(174, 174, 178) | rgb(99, 99, 102) | rgb(142, 142, 147) | rgb(124, 124, 128) |
| Gray (3) | systemGray3 | rgb(199, 199, 204) | rgb(72, 72, 74) | rgb(174, 174, 178) | rgb(84, 84, 86) |
| Gray (4) | systemGray4 | rgb(209, 209, 214) | rgb(58, 58, 60) | rgb(188, 188, 192) | rgb(68, 68, 70) |
| Gray (5) | systemGray5 | rgb(229, 229, 234) | rgb(44, 44, 46) | rgb(216, 216, 220) | rgb(54, 54, 56) |
| Gray (6) | systemGray6 | rgb(242, 242, 247) | rgb(28, 28, 30) | rgb(235, 235, 240) | rgb(36, 36, 38) |


---

## Dark Mode

Dark Mode is a systemwide appearance setting that uses a dark color palette to provide a comfortable viewing experience tailored for low-light environments.

On phones, tablets and desktop, people often choose Dark Mode as their default interface style, and they generally expect all apps and games to respect their preference. In Dark Mode, the system uses a dark color palette for all screens, views, menus, and controls, and may also use greater perceptual contrast to make foreground content stand out against the darker backgrounds.


### Best practices

**Avoid offering an app-specific appearance setting.** An app-specific appearance mode option creates more work for people because they have to adjust more than one setting to get the appearance they want. Worse, they may think your app is broken because it doesn’t respond to their systemwide appearance choice.

**Ensure that your app looks good in both appearance modes.** In addition to using one mode or the other, people can choose the Auto appearance setting, which switches between the light and dark appearances as conditions change throughout the day, potentially while your app is running.

**Test your content to make sure that it remains comfortably legible in both appearance modes.** For example, in Dark Mode with Increase Contrast and Reduce Transparency turned on (both separately and together), you may find places where dark text is less legible when it’s on a dark background. You might also find that turning on Increase Contrast in Dark Mode can result in reduced visual contrast between dark text and a dark background. Although people with strong vision might still be able to read lower contrast text, such text could be illegible for many. For guidance, see Accessibility.

**In rare cases, consider using only a dark appearance in the interface.** For example, it can make sense for an app that supports immersive media viewing to use a permanently dark appearance that lets the UI recede and helps people focus on the media.


### Dark Mode colors

The color palette in Dark Mode includes dimmer background colors and brighter foreground colors. It’s important to realize that these colors aren’t necessarily inversions of their light counterparts: while many colors are inverted, some are not. For more information, see Specifications.

**Embrace colors that adapt to the current appearance.** Semantic colors (like label, control, and separator colors) automatically adapt to the current appearance. Avoid using hard-coded color values or colors that don’t adapt.

**Aim for sufficient color contrast in all appearances.** Using system-defined colors can help you achieve a good contrast ratio between your foreground and background content. At a minimum, make sure the contrast ratio between colors is no lower than 4.5:1. For custom foreground and background colors, strive for a contrast ratio of 7:1, especially in small text. This ratio ensures that your foreground content stands out from the background, and helps your content meet recommended accessibility guidelines.

**Soften the color of white backgrounds.** If you display a content image that includes a white background, consider slightly darkening the image to prevent the background from glowing in the surrounding Dark Mode context.


#### Icons and images

Use symbol icons (which automatically adapt to Dark Mode) and full-color images that are optimized for both the light and dark appearances.

**Use a symbol/icon library wherever possible.** Symbols work well in both appearance modes when you use dynamic colors to tint them or when you add vibrancy. For guidance, see Color.

**Design separate interface icons for the light and dark appearances if necessary.** For example, an icon that depicts a full moon might need a subtle dark outline to contrast well with a light background, but need no outline when it displays on a dark background. Similarly, an icon that represents a drop of oil might need a slight border to make the edge visible against a dark background.

**Make sure full-color images and icons look good in both appearances.** Use the same asset if it looks good in both the light and dark appearances. If an asset looks good in only one mode, modify the asset or create separate light and dark assets.


#### Text

The system uses vibrancy and increased contrast to maintain the legibility of text on darker backgrounds.

**Use the system-provided label colors for labels.** The primary, secondary, tertiary, and quaternary label colors adapt automatically to the light and dark appearances.

**Use system views to draw text fields and text views.** System views and controls make your app’s text look good on all backgrounds, adjusting automatically for the presence or absence of vibrancy. When possible, use a system-provided view to display text instead of drawing the text yourself.


### Device-specific considerations

#### Phone & tablet
In Dark Mode, the system uses two sets of background colors — called *base* and *elevated* — to enhance the perception of depth when one dark interface is layered above another. The base colors are dimmer, making background interfaces appear to recede, and the elevated colors are brighter, making foreground interfaces appear to advance.

**Prefer the system background colors.** Dark Mode is dynamic, which means that the background color automatically changes from base to elevated when an interface is in the foreground, such as a popover or modal sheet. The system also uses the elevated background color to provide visual separation between apps in a multitasking environment and between windows in a multiple-window context. Using a custom background color can make it harder for people to perceive these system-provided visual distinctions.


#### Desktop
Some desktop systems tint window backgrounds with color from the current wallpaper (*desktop tinting*), a subtle effect that helps windows blend with surrounding content. Make sure custom backgrounds tolerate it.

**Include some transparency in custom component backgrounds when appropriate.** Transparency lets your components pick up color from the window background when desktop tinting is active, creating a visual harmony that can persist even when the desktop picture changes. To help achieve this harmony, add transparency only to a custom component that has a visible background or bezel, and only when the component is in a neutral state, such as state that doesn’t use color. You don’t want to add transparency when the component is in a state that uses color, because doing so can cause the component’s color to fluctuate when the window background adjusts to a different location on the desktop or when the desktop picture changes.


---

## Icons

An effective icon is a graphic asset that expresses a single concept in ways people instantly understand.

Apps and games use a variety of simple icons to help people understand the items, actions, and modes they can choose. Unlike app icons, which can use rich visual details like shading, texturing, and highlighting to evoke the app’s personality, an *interface icon* typically uses streamlined shapes and touches of color to communicate a straightforward idea.

Both interface icons and symbols use black and clear colors to define their shapes; the system can apply other colors to the black areas in each image. For guidance, see [Iconography & Symbols](./iconography-and-symbols.md).


### Best practices

**Create a recognizable, highly simplified design.** Too many details can make an interface icon confusing or unreadable. Strive for a simple, universal design that most people will recognize quickly. In general, icons work best when they use familiar visual metaphors that are directly related to the actions they initiate or content they represent.

**Maintain visual consistency across all interface icons in your app.** Whether you use only custom icons or mix custom and system-provided ones, all interface icons in your app need to use a consistent size, level of detail, stroke thickness (or weight), and perspective. Depending on the visual weight of an icon, you may need to adjust its dimensions to ensure that it appears visually consistent with other icons.

**In general, match the weights of interface icons and adjacent text.** Unless you want to emphasize either the icons or the text, using the same weight for both gives your content a consistent appearance and level of emphasis.

**If necessary, add padding to a custom interface icon to achieve optical alignment.** Some icons — especially asymmetric ones — can look unbalanced when you center them geometrically instead of optically. For example, the download icon shown below has more visual weight on the bottom than on the top, which can make it look too low if it’s geometrically centered.

In such cases, you can slightly adjust the position of the icon until it’s optically centered. When you create an asset that includes your adjustments as padding around an interface icon (as shown below on the right), you can optically center the icon by geometrically centering the asset.

Adjustments for optical centering are typically very small, but they can have a big impact on your app’s appearance.

**Provide a selected-state version of an interface icon only if necessary.** You don’t need to provide selected and unselected appearances for an icon that’s used in standard system components such as toolbars, tab bars, and buttons. The system updates the visual appearance of the selected state automatically.

**Use inclusive images.** Consider how your icons can be understandable and welcoming to everyone. Prefer depicting gender-neutral human figures and avoid images that might be hard to recognize across different cultures or languages. For guidance, see Inclusion.

**Include text in your design only when it’s essential for conveying meaning.** For example, using a character in an interface icon that represents text formatting can be the most direct way to communicate the concept. If you need to display individual characters in your icon, be sure to localize them. If you need to suggest a passage of text, design an abstract representation of it, and include a flipped version of the icon to use when the context is right-to-left. For guidance, see Right to left.

**If you create a custom interface icon, use a vector format like PDF or SVG.** The system automatically scales a vector-based interface icon for high-resolution displays, so you don’t need to provide high-resolution versions of it. In contrast, PNG — used for app icons and other images that include effects like shading, textures, and highlighting — doesn’t support scaling, so you have to supply multiple versions for each PNG-based interface icon. Alternatively, create a custom symbol in your icon system and specify a scale that ensures the symbol’s emphasis matches adjacent text. For guidance, see [Iconography & Symbols](./iconography-and-symbols.md).

**Provide alternative text labels for custom interface icons.** Alternative text labels — or accessibility descriptions — aren’t visible, but they let the screen reader audibly describe what’s onscreen, simplifying navigation for people with visual disabilities. For guidance, see [Commerce, Accounts & Accessibility › Screen Readers](./commerce-accounts-and-accessibility.md).

**Avoid using replicas of hardware products.** Hardware designs tend to change frequently and can make your interface icons and other content appear dated.


### Standard icons

For icons to represent common actions in menus, toolbars, buttons, and other places in interfaces across most platforms, these are the conventional glyphs (names follow a widely used symbol library, useful as naming and drawing references):


#### Editing

| Action | Reference symbol |
| --- | --- |
| Cut | scissors |
| Copy | document.on.document |
| Paste | document.on.clipboard |
| Done | checkmark |
| Save | | |
| Cancel | xmark |
| Close | | |
| Delete | trash |
| Undo | arrow.uturn.backward |
| Redo | arrow.uturn.forward |
| Compose | square.and.pencil |
| Duplicate | plus.square.on.square |
| Rename | pencil |
| Move to | folder |
| Folder | | |
| Attach | paperclip |
| Add | plus |
| More | ellipsis |


#### Selection

| Action | Reference symbol |
| --- | --- |
| Select | checkmark.circle |
| Deselect | xmark |
| Close | | |
| Delete | trash |


#### Text formatting

| Action | Reference symbol |
| --- | --- |
| Superscript | textformat.superscript |
| Subscript | textformat.subscript |
| Bold | bold |
| Italic | italic |
| Underline | underline |
| ​​Align Left | text.alignleft |
| Center | text.aligncenter |
| Justified | text.justify |
| Align Right | text.alignright |


#### Search

| Action | Reference symbol |
| --- | --- |
| Search | magnifyingglass |
| Find | text.page.badge.magnifyingglass |
| Find and Replace | | |
| Find Next | | |
| Find Previous | | |
| Use Selection for Find | | |
| Filter | line.3.horizontal.decrease |


#### Sharing and exporting

| Action | Reference symbol |
| --- | --- |
| Share | square.and.arrow.up |
| Export | | |
| Print | printer |


#### Users and accounts

| Action | Reference symbol |
| --- | --- |
| Account | person.crop.circle |
| User | | |
| Profile | | |


#### Ratings

| Action | Reference symbol |
| --- | --- |
| Dislike | hand.thumbsdown |
| Like | hand.thumbsup |


#### Layer ordering

| Action | Reference symbol |
| --- | --- |
| Bring to Front | square.3.layers.3d.top.filled |
| Send to Back | square.3.layers.3d.bottom.filled |
| Bring Forward | square.2.layers.3d.top.filled |
| Send Backward | square.2.layers.3d.bottom.filled |


#### Other

| Action | Reference symbol |
| --- | --- |
| Alarm | alarm |
| Archive | archivebox |
| Calendar | calendar |


### Device-specific considerations

#### Desktop
##### Document icons

If your desktop app can use a custom document type, you can create a document icon to represent it. Traditionally, a document icon looks like a piece of paper with its top-right corner folded down. This distinctive appearance helps people distinguish documents from apps and other content, even when icon sizes are small.

If you don’t supply a document icon for a file type you support, desktop creates one for you by compositing your app icon and the file’s extension onto the canvas. For example, an image viewer might rely on a system-generated document icon for JPG files.

In some cases, it can make sense to create a set of document icons to represent a range of file types your app handles.

To create a custom document icon, you can supply any combination of background fill, center image, and text. The system layers, positions, and masks these elements as needed and composites them onto the familiar folded-corner icon shape.

**Design simple images that clearly communicate the document type.** Whether you use a background fill, a center image, or both, prefer uncomplicated shapes and a reduced palette of distinct colors. Your document icon can display as small as 16x16 px, so you want to create designs that remain recognizable at every size.


**Consider reducing complexity in the small versions of your document icon.** Icon details that are clear in large versions can look blurry and be hard to recognize in small versions. For example, to ensure that the grid lines in the custom heart document icon remain clear in intermediate sizes, you might use fewer lines and thicken them by aligning them to the reduced pixel grid. In the 16x16 px size, you might remove the lines altogether.

**Avoid placing important content in the top-right corner of your background fill.** The system automatically masks your image to fit the document icon shape and draws the white folded corner on top of the fill. Create a set of background images in the sizes listed below.

- 512x512 px @1x, 1024x1024 px @2x

- 256x256 px @1x, 512x512 px @2x

- 128x128 px @1x, 256x256 px @2x

- 32x32 px @1x, 64x64 px @2x

- 16x16 px @1x, 32x32 px @2x

**If a familiar object can convey a document’s type or its connection with your app, consider creating a center image that depicts it.** Design a simple, unambiguous image that’s clear and recognizable at every size. The center image measures half the size of the overall document icon canvas. For example, to create a center image for a 32x32 px document icon, use an image canvas that measures 16x16 px. You can provide center images in the following sizes:

- 256x256 px @1x, 512x512 px @2x

- 128x128 px @1x, 256x256 px @2x

- 32x32 px @1x, 64x64 px @2x

- 16x16 px @1x, 32x32 px @2x

**Define a margin that measures about 10% of the image canvas and keep most of the image within it.** Although parts of the image can extend into this margin for optical alignment, it’s best when the image occupies about 80% of the image canvas. For example, most of the center image in a 256x256 px canvas would fit in an area that measures 205x205 px.

**Specify a succinct term if it helps people understand your document type.** By default, the system displays a document’s extension at the bottom edge of the document icon, but if the extension is unfamiliar you can supply a more descriptive term. For example, the document icon for a SceneKit scene file uses the term *scene* instead of the file extension *scn*. The system automatically scales the extension text to fit in the document icon, so be sure to use a term that’s short enough to be legible at small sizes. By default, the system capitalizes every letter in the text.


---

## Images

To make sure your artwork looks great on all devices you support, learn how the system displays content and how to deliver art at the appropriate scale factors.


### Resolution

Different devices can display images at different resolutions. For example, a 2D device displays images according to the resolution of its screen.

A *point* is an abstract unit of measurement that helps visual content remain consistent regardless of how it’s displayed.

When creating bitmap images, you specify a *scale factor* which determines the resolution of an image. You can visualize scale factor by considering the density of pixels per point in 2D displays of various resolutions. For example, a scale factor of 1 (also called @1x) describes a 1:1 pixel density, where one pixel is equal to one point. High-resolution 2D displays have higher pixel densities, such as 2:1 or 3:1. A 2:1 density (called @2x) has a scale factor of 2, and a 3:1 density (called @3x) has a scale factor of 3. Because of higher pixel densities, high-resolution displays demand images with more pixels.

Use the following values for guidance; for additional scale factors, see Layout.

| Platform | Scale factors |
| --- | --- |
| tablets | @2x |
| phones | @2x and @3x |
| desktop | @1x and @2x |

**In general, design images at the lowest resolution and scale them up to create high-resolution assets.** When you use resizable vectorized shapes, you might want to position control points at whole values so that they’re cleanly aligned at 1x. This positioning allows the points to remain cleanly aligned to the raster grid at higher resolutions, because 2x and 3x are multiples of 1x.


### Formats

As you create different types of images, consider the following recommendations.

| Image type | Format |
| --- | --- |
| Bitmap or raster work | De-interlaced PNG files |
| PNG graphics that don’t require full 24-bit color | An 8-bit color palette |
| Photos | JPEG files, optimized as necessary, or HEIC files |
| Stereo or spatial photos | Stereo HEIC |
| Flat icons, interface icons, and other flat artwork that requires high-resolution scaling | PDF or SVG files |


### Best practices

**Include a color profile with each image.** Color profiles help ensure that your app’s colors appear as intended on different displays. For guidance, see Color management.

**Always test images on a range of actual devices.** An image that looks great at design time may appear pixelated, stretched, or compressed when viewed on various devices.


### Device-specific considerations

## Inclusion

Inclusive apps and games put people first by prioritizing respectful communication and presenting content and functionality in ways that everyone can access and understand.

To help you design an inclusive app or game, consider the following goals as you review the words and images you use and the experiences you offer.

As with all design, designing an inclusive app is an iterative process that takes time to get right. Throughout the process, be prepared to examine your assumptions about how other people think and feel and be open to evolving knowledge and understanding.


### Inclusive by design

Simple, intuitive experiences are at the core of well-designed apps and games. To design an intuitive experience, you start by investigating people’s goals and perspectives so you can present content that resonates with them.

Empathy is an important tool in this investigation because it helps you understand how people with different perspectives might respond to the content and experiences you create. For example, you might discover that from some perspectives a word or image is incomprehensible or has a meaning you don’t intend.

Although each person’s perspective comprises a unique intersection of human qualities that’s both distinct and dynamic, all perspectives arise from human characteristics and experiences that everyone shares, including:

- Age

- Gender and gender identity

- Race and ethnicity

- Sexuality

- Physical attributes

- Cognitive attributes

- Permanent, temporary, and situational disabilities

- Language and culture

- Religion

- Education

- Political or philosophical opinions

- Social and economic context

As you examine your app or game through different perspectives, avoid framing the work as merely a search for content that might give offense. Although no design should contain offensive material or experiences, an inoffensive app or game isn’t necessarily an inclusive one. Focusing on inclusion can help you avoid potentially offensive content while also helping you create a welcoming experience that everyone can enjoy.


### Welcoming language

Using plain, inclusive language welcomes everyone and helps them understand your app or game. Carefully review the writing in your experience to make sure that your tone and words don’t exclude people. Here are a few tips for writing text — also known as *copy* — that’s direct, easy to understand, and inclusive.

**Consider the tone of your copy from different perspectives.** The style of your writing communicates almost as much as the words you use. Although different apps use different communication styles, make sure the tone you use doesn’t send messages you don’t intend. For example, an academic tone can make an app or game seem like it welcomes only high levels of education. As you seek the style that’s right for your experience, be clear, direct, and respectful.

**Pay attention to how you refer to people.** It typically works well to use *you* and *your* to address people directly. Referring to people indirectly as *the user* or *the player* can make your experience feel distant and unwelcoming. Also, consider reserving words like *we* and *our* to represent your software or company; otherwise, these terms can suggest a personal relationship with people that might be interpreted as insulting or condescending.

**Avoid using specialized or technical terms without defining them.** Using specialized or technical terms can make your writing more succinct, but doing so excludes people who don’t know what the terms mean. If you must use such terms, be sure to define them first and make the definitions easy for people to look up. Even when people know the definition of a specialized or technical term in a sentence, the sentence is easier to read — and translate — when it uses plain language instead.

**Replace colloquial expressions with plain language.** Colloquial expressions are often culture-specific and can be difficult to translate. Worse, some colloquial phrases have exclusionary meanings you might not know. For example, the phrases *peanut gallery* and *grandfathered in* both arose from oppressive contexts and continue to exclude people. Even when a colloquial phrase doesn’t have an exclusionary meaning, it can still exclude everyone who doesn’t understand it.

**Consider carefully before including humor.** Humor is highly subjective and — similar to colloquial expressions — difficult to translate from one culture to another. Including humor in your experience risks confusing people who donʼt understand it, irritating people who tire of repeatedly encountering it, and insulting people who interpret it differently. For additional writing guidance, see Writing inclusively.


### Being approachable

An approachable app or game doesn’t require people to have particular skills or knowledge before they can use it, and it gives people a clear path toward deepening their understanding over time. Here are two ways to help make an experience approachable.

- Present a clear, straightforward interface. To help you design a simple interface that fits in with other experiences on each platform, see [Device Contexts](./platforms-and-contexts.md).

- Build in ways to learn how to use your app or game. Consider designing an onboarding flow that helps people who are new to your experience take a step-by-step approach while letting others skip straight to the content they want. For guidance, see Onboarding.


### Gender identity

Throughout history, cultures around the world have recognized a spectrum of self-identity and expression that expands beyond the binary variants of woman and man.

You can help everyone feel welcome in your app or game by avoiding unnecessary references to specific genders. For example, a recipe-sharing app that uses copy like “You can let a subscriber post his or her recipes to your shared folder” could avoid unnecessary gender references by using an alternative like “Subscribers can post recipes to your shared folder.” In addition to using the gender-neutral noun “subscribers,” the revised copy avoids the unnecessary singular pronouns “his” and “her,” helping the sentence remain inclusive when it’s localized for languages that use gendered pronouns.

In addition, you can often avoid referencing a specific gender in an avatar, emoji, glyph, or game character. To welcome everyone to your app or game, prefer giving people the tools they need to customize such items as they choose.

If you need to depict a generic person or people, use a nongendered human image to reinforce the message that *generic person* means *human*, not *man* or *woman*. Most icon libraries provide nongendered figure and person glyphs you can use.

Most apps and games don’t need to know a person’s gender, but if you require this information — such as for health or legal reasons — consider providing inclusive options, such as *nonbinary*, *self-identify*, and *decline to state*. In this situation, you could also let people specify the pronouns they use so you can address them properly when necessary.


### People and settings

Portraying human diversity is one of the most noticeable ways your app or game can welcome everyone. When people recognize others like themselves within an experience and its related materials, they’re less likely to feel excluded and can be more likely to think they’ll benefit from it.

As you create copy and images that represent people, portray a range of human characteristics and activities. For example, a fitness app could feature exercise moves demonstrated by people with different racial backgrounds, body types, ages, and physical capabilities. If you need to depict occupations or behaviors, avoid stereotypical representations, such as showing only male doctors, female nurses, or heroes and villains that may perpetuate real-world racial or gender stereotypes.

Also review the settings and objects you show. For example, showing high levels of affluence might make sense in some scenarios, but in other cases it can be unwelcoming and make an experience seem out of touch. When it makes sense in your app or game, prefer showing places, homes, activities, and items that are familiar and relatable to most people.


### Avoiding stereotypes

Everyone holds biases and stereotypes — often unconsciously — and it can be challenging to discover how they affect your thoughts. A goal of inclusive design is to become aware of your biases and generalizations so you can recognize where they might influence your design decisions.

For example, consider an app that helps people manage account access for various family members. If this app uses a stereotypical definition of *family* — such as a woman, a man, and their biological children — it’s likely to communicate this perspective in its copy and images. Because the app assumes that people’s families fit this narrow definition, it excludes everyone whose family is different.

Although the assumption made in the account-access app might seem like an obvious mistake, it’s important to realize that not all assumptions are so easy to spot. For example, consider an app or game that requires people to choose security questions they can answer for future identity confirmation, such as:

- What was your favorite subject in college?

- What was the make of your first car?

- How did you feel when you first saw a rainbow?

From some perspectives these questions refer to commonplace events, but all are based on experiences that not everyone has. Using a context-specific experience to communicate something is useless for everyone who doesn’t share that context and effectively excludes them. To create alternatives to the culture- and capability-specific questions above, you might reference more universal human experiences like:

- What’s your favorite activity?

- What was the name of your first friend?

- What quality describes you best?

Basing design decisions on stereotypes or assumptions inevitably leads to exclusion because generalizations can’t reflect the diversity of human perspectives. Avoiding assumptions and instead concentrating on inclusion can help you craft experiences that benefit everyone.


### Accessibility

An inclusive app or game is accessible to everyone. People rely on the platform’s accessibility features — such as screen readers, display accommodations (color filters, reduced white point), closed captions, switch control, and speak-screen — to customize their devices for their individual needs, so it’s essential to support these features.

It’s also essential to avoid assuming that any disability might prevent someone from wanting to enjoy the experience your software provides. Making an assumption like this can result in designs that limit the potential audience for your app or game. In contrast, when you make each experience accessible, you give everyone the opportunity to benefit from your app or game in ways that work for them.

To help you design an app or game that everyone can enjoy, remember that:

- Each disability is a spectrum. For example, visual disabilities range from low vision to complete blindness, and include things like color blindness, blurry vision, light sensitivity, and peripheral vision loss.

- Everyone can experience disabilities. In addition to disabilities that most people experience as they age, there are *temporary disabilities* — like short-term hearing loss due to an infection — and *situational disabilities* — like being unable to hear while on a noisy train — that can affect everyone at various times.

As you design content that welcomes people of all abilities, consider the following tips.

**Avoid images and language that exclude people with disabilities.** For example, include people with disabilities when you represent a variety of people, and avoid language that uses a disability to express a negative quality.

**Take a people-first approach when writing about people with disabilities.** For example, you could describe an individual’s accomplishments and goals before mentioning a disability they may have. If you’re writing about a specific person or community, find out how they self-identify; for more guidance, see Writing about disability.

**Prioritize simplicity and perceivability.** Prefer familiar, consistent interactions that make tasks simple to perform, and ensure that everyone can perceive your content, whether they use sight, hearing, or touch.

To learn more about making your app or game accessible, see Accessibility.


### Languages

People expect to customize their device by choosing a language for text and a region for formatting values like date, time, and money. To welcome a global audience, first prepare your software to handle languages and regions other than your own — a process called *internationalization* — and provide translated text and resources for specific locales. For an overview of internationalization, see Expanding your app to new markets; for developer guidance on localization, see Localization.

Creating an inclusive experience can also help you prepare for localization. For example, using plain language, avoiding unnecessary gender references, representing a variety of people, and avoiding stereotypes and culture-specific content, can put you in a good position to create versions of your software localized into more languages. Using a well-localized icon library for the glyphs in your app or game can also help streamline localization. Good libraries provide language-specific glyphs and include glyphs you can use in both left-to-right and right-to-left contexts; for guidance, see Right to left.

As you localize your app or game and related content, also be aware of the ways you use color. Colors often have strong culture-specific meanings, so it’s essential to discover how people respond to specific colors in each locale you support. In some places, for example, white is associated with death or grief, whereas in other places, it’s associated with purity or peace. If you use color as a way to communicate, make sure your color choices communicate the same thing in each version of your software.


---

## Layout

A consistent layout that adapts across display sizes, orientations, and multitasking configurations helps people understand and enjoy your app or game on all their devices.

Your layout provides the structure for people to understand your content from the moment they open your app. Familiar relationships between controls and content let people use and discover features right away, and make your design feel at home on every platform.


### Visual hierarchy

**Order content by relative importance.** People often start by viewing content in reading order — that is, from top to bottom and from the leading to trailing side — so place the most important items near the top and leading side of the window or display. To support right-to-left languages, prefer standard system components that can automatically adapt UI elements to better reflect each language’s natural reading order. For guidance, see Right to left.

**Align elements to make them easier to scan, and use indentation to convey hierarchy.** Alignment makes an app look neat and organized, and can help people track content while scrolling or moving their eyes. People assume that aligned items are related to each other, and conversely, they perceive indented items as subordinate to the item they follow. Because of this, using alignment and indentation deliberately can help people understand your information hierarchy.

**Group related items to clearly express related information or functions.** For example, you might use negative space, container shapes, or separator lines to show which elements are related and which are unrelated.

**Use progressive disclosure to make layouts cleaner and easier to interact with.** An interface with too much content and too many choices makes it harder to find information quickly, and harder to understand the choices that are available. Use disclosure triangles, menus, or nested views to reduce how much content to initially display; or use scrollable sections to showcase additional content, which is particularly useful for media-focused apps like those for video, music, or books.

**Differentiate controls from content.** Take advantage of the glass material on all platforms that support it to provide a distinct appearance for your controls. Instead of applying a solid or semi-opaque background color beneath controls, use a scroll edge effect to visually elevate controls above content. For guidance, see Scroll views. For full-screen background content, be sure to extend it underneath sidebars, toolbars, and tab bars to fit the entire screen or window.

If scaling a background image to the full window edge results in components like sidebars or inspectors covering important parts of the image, you can use a background extension effect to flip and blur the image, mirroring it beneath adjacent components and providing the appearance that the background image extends beneath them.


### Adaptability

Apps and games need to adapt to different display sizes, orientation changes, window sizes, and multitasking states. Most platforms define characteristics of the device environment that can affect the way your app or game looks.

Here are some of the most common device and system characteristics that apps need to handle:

- Hardware features like camera cutouts, notches, and rounded screen corners

- Regular and compact horizontal and vertical size classes

- Different device screen sizes

- Different device orientations and aspect ratios


- External displays, display zoom, and resizable windows

- Text-size changes

- Locale-based internationalization features like left-to-right/right-to-left layout direction, date/time/number formatting, font variation, and text length

**Design a layout that adapts gracefully and consistently.** People expect your experience to remain familiar when they rotate their device, resize a window, add another display, or switch to a different device. You can help ensure an adaptable interface by respecting system-defined safe areas, margins, and guides (where available) and specifying layout modifiers to fine-tune the placement of views in your interface.

Even if your app is locked to a certain orientation, such as a landscape-only game, it’s still important to ensure your interface resizes well to provide the best experience across devices and window sizes.

**Be prepared for text-size changes.** People use dynamic text sizing to increase text size to be more readable, which occurs at the system level. Apps that don’t respond to this setting can be difficult or impossible to use for people who rely on this feature. Support dynamic text sizing by adjusting your layout to accommodate text at larger sizes. For example, horizontally adjacent views may need to stack vertically to provide more space for text; table rows or other containers may need to grow in height so that text isn’t cropped or doesn’t overlap other content; and table rows with a single line of text by default might need to grow vertically to accommodate multiple lines of text.

Game engines should honor the platform text-size setting too, using the engine’s accessibility plug-ins where available. For guidance on displaying text in your app, see Typography.

**Preview your app on multiple devices, using different size classes, localizations, and text sizes.** You can streamline the testing process by first testing versions of your experience that use the largest and the smallest layouts. Use device simulators or browser device emulation to check for clipping and other layout issues at each size, including when your app is resized in a window.

**When necessary, scale background artwork in response to display changes.** Viewing your app or game in a different context — such as on a screen with a different aspect ratio — might make your artwork appear cropped, letterboxed, or pillarboxed. If this happens, don’t change the aspect ratio of the artwork; instead, scale it so that it fills the screen completely. Note that since windows can be very wide and short or tall and narrow, background artwork may often need to extend beyond what is typically visible in a more standard display aspect ratio.


#### Size classes

Size classes are an indication of how much horizontal and vertical space is available to an app’s interface.

Each dimension — horizontal and vertical — is represented by one of two size classes: *compact* or *regular*. The horizontal size class determines whether an app is narrow (compact) or wide (regular), while the vertical size class determines whether it is short (compact) or tall (regular).

The system sets size classes based on the device type, window configuration, and multitasking state; for example, whether an app is full screen, in slide-over, or mirrored to another device. Depending on their environment, apps can exist in every combination of size classes.


**Determine layout based on size classes, not device type or orientation.** Size classes describe the actual space available, regardless of whether an app is in portrait or landscape. Conversely, a device’s orientation and type (also called its *idiom*) aren’t useful for making layout decisions because they don’t provide your app with information about how much space is available.

Size classes also let your app’s interface adapt to a wide range of window sizes. For example, people can freely resize a window’s width and height on desktop, or resize an app when multitasking on a tablet.

**Consider all possible combinations of size classes.** Your app can appear in a variety of size classes in both portrait and landscape aspect ratios, and it’s important to consider all of them to provide a good experience. A layout solely designed for landscape on phone with regular width and compact height might not take advantage of the vertical space available on tablet in landscape when someone resizes the window to regular height. Conversely, designing exclusively for compact portrait could leave extra space when someone resizes the app window to a regular width on tablet.

**Keep functionality the same as size classes change, and keep layout changes recognizable and familiar to the platform.** Don’t change your app’s functionality based on the space it occupies. However, you can change the amount of functionality that’s visible onscreen as the amount of space changes. Consider taking advantage of larger spaces to switch from a tab bar to a sidebar or expose functionality that might otherwise be grouped into an overflow menu.

Similarly, while an app’s size classes might change when someone resizes it, its idiom — the device type it’s made for — remains the same: keep the layout recognizable and familiar to the platform even when resizing.


### Guides and safe areas

A *layout guide* defines a rectangular region that helps you position, align, and space your content on the screen. The system includes predefined layout guides that make it easy to apply standard margins around content and restrict the width of text for optimal readability. You can also define custom layout guides.

A *safe area* defines the area within a window that isn’t covered on the edge by a hardware feature or another view within the window, like a toolbar, tab bar, or status bar.


### Device-specific considerations

#### Desktop
**Avoid placing controls or critical information at the bottom of a window.** People often move windows so that the bottom edge is below the bottom of the screen.

**Avoid displaying content behind the camera housing at the top edge of the window.**


## Motion

Beautiful, fluid motions bring the interface to life, conveying status, providing feedback and instruction, and enriching the visual experience of your app or game.

Many system components automatically include motion, letting you offer familiar and consistent experiences throughout your app or game. System components might also adjust their motion in response to factors like accessibility settings or different input methods. For example, the movement of glass responds to direct touch interaction with greater emphasis to reinforce the feeling of a tactile experience, but produces a more subdued effect when a person interacts using a trackpad.

If you design custom motion, follow the guidelines below.


### Best practices

**Add motion purposefully, supporting the experience without overshadowing it.** Don’t add motion for the sake of adding motion. Gratuitous or excessive animation can distract people and may make them feel disconnected or physically uncomfortable.

**Make motion optional.** Not everyone can or wants to experience the motion in your app or game, so it’s essential to avoid using it as the only way to communicate important information. To help everyone enjoy your app or game, supplement visual feedback by also using alternatives like haptics and audio to communicate.


### Providing feedback

**Strive for realistic feedback motion that follows people’s gestures and expectations.** In nongame apps, accurate, realistic motion can help people understand how something works, but feedback motion that doesn’t make sense can make them feel disoriented. For example, if someone reveals a view by sliding it down from the top, they don’t expect to dismiss the view by sliding it to the side.

**Aim for brevity and precision in feedback animations.** When animated feedback is brief and precise, it tends to feel lightweight and unobtrusive, and it can often convey information more effectively than prominent animation. For example, when a game displays a succinct animation that’s precisely tied to a successful action, players can instantly get the message without being distracted from their gameplay.

**In apps, generally avoid adding motion to UI interactions that occur frequently.** The system already provides subtle animations for interactions with standard interface elements. For a custom element, you generally want to avoid making people spend extra time paying attention to unnecessary motion every time they interact with it.

**Let people cancel motion.** As much as possible, don’t make people wait for an animation to complete before they can do anything, especially if they have to experience the animation more than once.

**Consider using animated symbols where it makes sense.** Many symbol libraries support animation; animate symbols to communicate state and feedback. For guidance, see [Iconography & Symbols](./iconography-and-symbols.md).


### Leveraging platform capabilities

**Make sure your game’s motion looks great by default on each platform you support.** In most games, maintaining a consistent frame rate of 30 to 60 fps typically results in a smooth, visually appealing experience. For each platform you support, use the device’s graphics capabilities to enable default settings that let people enjoy your game without first having to change those settings.

**Let people customize the visual experience of your game to optimize performance or battery life.** For example, consider letting people switch between power modes when the system detects the presence of an external power source.


### Device-specific considerations

## Privacy

Privacy is paramount: it’s critical to be transparent about the privacy-related data and resources you require and essential to protect the data people allow you to access.

People use their devices in very personal ways and they expect apps to help them preserve their privacy.

When you distribute through an app store, you typically must declare your privacy practices and the data you collect so the store can show them on your product page. Keep that declaration accurate and current.


### Best practices

**Request access only to data that you actually need.** Asking for more data than a feature needs — or asking for data before a person shows interest in the feature — can make it hard for people to trust your app. Give people precise control over their data by making your permission requests as specific as possible.

**Be transparent about how your app collects and uses people’s data.** People are less likely to be comfortable sharing data with your app if they don’t understand exactly how you plan to use it. Always respect people’s choices to use privacy features like relay (hidden) email addresses and mail privacy protection, and understand your obligations regarding cross-app tracking.


**Adopt system-defined privacy protections and follow security best practices.** For example, rely on platform or well-audited services for end-to-end encryption and key management rather than inventing your own.


### Requesting permission

Here are several examples of the things you must request permission to access:

- Personal data, including location, health, financial, contact, and other personally identifying information

- User-generated content like emails, messages, calendar data, contacts, gameplay information, music listening activity, smart-home data, and audio, video, and photo content

- Protected resources like Bluetooth peripherals, home automation features, Wi-Fi connections, and local networks

- Device capabilities like camera and microphone


- The device’s advertising identifier, which supports app tracking

The system provides a standard alert that lets people view each request you make. You supply copy that describes why your app needs access, and the system displays your description in the alert. People can also view the description — and update their choice — in Settings > Privacy.

**Request permission only when your app clearly needs access to the data or resource.** It’s natural for people to be suspicious of a request for personal information or access to a device capability, especially if there’s no obvious need for it. Ideally, wait to request permission until people actually use an app feature that requires access. For example, you can use the location button to give people a way to share their location after they indicate interest in a feature that needs that information.

**Avoid requesting permission at launch unless the data or resource is required for your app to function.** People are less likely to be bothered by a launch-time request when it’s obvious why you’re making it. For example, people understand that a navigation app needs access to their location before they can benefit from it.

**Write copy that clearly describes how your app uses the ability, data, or resource you’re requesting.** The standard alert displays your copy (called a *purpose string* or *usage description string*) after your app name and before the buttons people use to grant or deny their permission. Aim for a brief, complete sentence that’s straightforward, specific, and easy to understand. Use sentence case, avoid passive voice, and include a period at the end.

| Example purpose string | Notes |
| --- | --- |
| The app records during the night to detect snoring sounds. | An active sentence that clearly describes how and why the app collects the data. |
| Microphone access is needed for a better experience. | A passive sentence that provides a vague, undefined justification. |
| Turn on microphone access. | An imperative sentence that doesn’t provide any justification. |

Here are several examples of the standard system alert:


#### Pre-alert screens, windows, or views

Ideally, the current context helps people understand why you’re requesting their permission. If it’s essential to provide additional details, you can display a custom screen or window before the system alert appears. The following guidelines apply to custom views that display before system alerts that request permission to access protected data and resources, including camera, microphone, location, contact, calendar, and tracking.

**Include only one button and make it clear that it opens the system alert.** People can feel manipulated when a custom screen or window also includes a button that doesn’t open the alert because the experience diverts them from making their choice. Another type of manipulation is using a term like “Allow” to title the custom screen’s button. If the custom button seems similar in meaning and visual weight to the allow button in the alert, people can be more likely to choose the alert’s allow button without meaning to. Use a term like “Continue” or “Next” to title the single button in your custom screen or window, clarifying that its action is to open the system alert.

**Don’t include additional actions in your custom screen or window, unless needed to obtain a legal consent.** For example, don’t provide a way for people to leave the screen or window without viewing the system alert — like offering an option to close or cancel.


#### Tracking requests

App tracking is a sensitive issue. In some cases, it might make sense to display a custom screen or window that describes the benefits of tracking. If you want to perform app tracking as soon as people launch your app, you must display the system-provided alert before you collect any tracking data.

**Never precede the system-provided alert with a custom screen or window that could confuse or mislead people.** People sometimes tap quickly to dismiss alerts without reading them. A custom messaging screen, window, or view that takes advantage of such behaviors to influence choices is deceptive, and major app stores reject it.

There are several prohibited custom-screen designs that will cause rejection. Some examples are offering incentives, displaying a screen or window that looks like a request, displaying an image of the alert, and annotating the screen behind the alert (as shown below). For the avoidance of confusion, a consent screen or window shown before or after an system tracking-permission alert to comply with local privacy laws is allowed.


### Location button

Some platforms provide a system **location button** that grants one-time location access at the moment a task needs it, without a broad permission prompt. The first tap shows a standard explanation; afterward each tap grants temporary access that expires when people stop using the app.

**Consider using a one-time location control for lightweight, task-specific sharing** — attaching a location to a message or post, finding a nearby store, identifying a plant or building. If people often grant only one-time access, this reduces friction for everyone.

**Customize it only within the allowed range** — title (“Current Location”, “Share My Current Location”), filled or outlined glyph, background and foreground colors, corner radius — and keep it legible (sufficient contrast, not too translucent, text that fits). People must be able to recognize and trust it; a control that doesn’t reliably share location erodes trust.

### Protecting data

Protecting people’s information is paramount. Give people confidence in your app’s security and help preserve their privacy by taking advantage of system-provided security technologies when you need to store information locally, authorize people for specific operations, and transport information across a network.

Here are some high-level guidelines.

**Avoid relying solely on passwords for authentication.** Where possible, use passkeys to replace passwords. If you need to continue using passwords for authentication, augment security by requiring two-factor authentication. To further protect access to apps that people keep logged in on their device, use biometric identification like face, iris, or fingerprint authentication.

**Store sensitive information in a keychain.** A keychain provides a secure, predictable user experience when handling someone’s private information.

**Never store passwords or other secure content in plain-text files.** Even if you restrict access using file permissions, sensitive information is much safer in an encrypted keychain.

**Avoid inventing custom authentication schemes.** If your app requires authentication, prefer system-provided features like passkeys, federated sign-in, or the platform’s password autofill. For related guidance, see Managing accounts.


### Device-specific considerations

#### Desktop
**Sign your app.** If you distribute outside an app store, code-sign (and notarize, where the platform supports it) so the OS can verify your app is safe to use.

**Protect people’s data with app sandboxing.** Sandboxing provides your app with access to system resources and user data while protecting it from malware. Many app stores require it.

**Avoid making assumptions about who is signed in.** Because of fast user switching, multiple people may be active on the same system.


## Right to left

Support right-to-left languages like Arabic and Hebrew by reversing your interface as needed to match the reading direction of the related scripts.

When people choose a language for their device — or just your app or game — they expect the interface to adapt in various ways (to learn more, see Localization).

System-provided UI frameworks support right-to-left (RTL) by default, allowing system-provided UI components to flip automatically in the RTL context. If you use system-provided elements and standard layouts, you might not need to make any changes to your app’s automatically reversed interface.

If you want to fine-tune your layout or enhance specific localizations to adapt to different currencies, numerals, or mathematical symbols that can occur in various locales in countries that use RTL languages, follow these guidelines.


### Text alignment

**Adjust text alignment to match the interface direction, if the system doesn’t do so automatically.** For example, if you left-align text with content in the left-to-right (LTR) context, right-align the text to match the content’s mirrored position in the RTL context.

**Align a paragraph based on its language, not on the current context.** When the alignment of a paragraph — defined as three or more lines of text — doesn’t match its language, it can be difficult to read. For example, right-aligning a paragraph that consists of LTR text can make the beginning of each line difficult to see. To improve readability, continue aligning one- and two-line text blocks to match the reading direction of the current context, but align a paragraph to match its language.

**Use a consistent alignment for all text items in a list.** To ensure a comfortable reading and scanning experience, reverse the alignment of all items in a list, including items that are displayed in a different script.


### Numbers and characters

Different RTL languages can use different number systems. For example, Hebrew text uses Western Arabic numerals, whereas Arabic text might use either Western or Eastern Arabic numerals. The use of Western and Eastern Arabic numerals varies among countries and regions and even among areas within the same country or region.

If your app covers mathematical concepts or other number-centric topics, it’s a good idea to identify the appropriate way to display such information in each locale you support. In contrast, apps that don’t address number-related topics can generally rely on system-provided number representations.

**Don’t reverse the order of numerals in a specific number.** Regardless of the current language or the surrounding content, the digits in a specific number — such as “541,” a phone number, or a credit card number — always appear in the same order.

**Reverse the order of numerals that show progress or a counting direction; never flip the numerals themselves.** Controls like progress bars, sliders, and rating controls often include numerals to clarify their meaning. If you use numerals in this way, be sure to reverse the order of the numerals to match the direction of the flipped control. Also reverse a sequence of numerals if you use the sequence to communicate a specific order.


### Controls

**Flip controls that show progress from one value to another.** Because people tend to view forward progress as moving in the same direction as the language they read, it makes sense to flip controls like sliders and progress indicators in the RTL context. When you do this, also be sure to reverse the positions of the accompanying glyphs or images that depict the beginning and ending values of the control.

**Flip controls that help people navigate or access items in a fixed order.** For example, in the RTL context, a back button must point to the right so the flow of screens matches the reading order of the RTL language. Similarly, next or previous buttons that let people access items in an ordered list need to flip in the RTL context to match the reading order.

**Preserve the direction of a control that refers to an actual direction or points to an onscreen area.** For example, if you provide a control that means “to the right,” it must always point right, regardless of the current context.

**Visually balance adjacent Latin and RTL scripts when necessary.** In buttons, labels, and titles, Arabic or Hebrew text can appear too small when next to uppercased Latin text, because Arabic and Hebrew don’t include uppercase letters. To visually balance Arabic or Hebrew text with Latin text that uses all capitals, it often works well to increase the RTL font size by about 2 points.


### Images

**Avoid flipping images like photographs, illustrations, and general artwork.** Flipping an image often changes the image’s meaning; flipping a copyrighted image could be a violation. If an image’s content is strongly connected to reading direction, consider creating a new version of the image instead of flipping the original.

**Reverse the positions of images when their order is meaningful.** For example, if you display multiple images in a specific order like chronological, alphabetical, or favorite, reverse their positions to preserve the order’s meaning in the RTL context.


### Interface icons

When your icon library supplies interface icons, use its variants for the RTL context and localized symbols for Arabic and Hebrew, among other languages. If you create custom symbols, you can specify their directionality.

**Flip interface icons that represent text or reading direction.** For example, if an interface icon uses left-aligned bars to represent text in the LTR context, right-align the bars in the RTL context.

**Consider creating a localized version of an interface icon that displays text.** Some interface icons include letters or words to help communicate a script-related concept, like font-size choice or a signature. If you have a custom interface icon that needs to display actual text, consider creating a localized version. For example, good symbol libraries offer different versions of the signature, rich-text, and I-beam pointer symbols for use with Latin, Hebrew, and Arabic text, among others.

If you have a custom interface icon that uses letters or words to communicate a concept unrelated to reading or writing, consider designing an alternative image that doesn’t use text.

**Flip an interface icon that shows forward or backward motion.** When something moves in the same direction that people read, they typically interpret that direction as forward; when something moves in the opposite direction, people tend to interpret the direction as backward. An interface icon that depicts an object moving forward or backward needs to flip in the RTL context to preserve the meaning of the motion. For example, an icon that represents a speaker typically shows sound waves emanating forward from the speaker. In the LTR context, the sound waves come from the left, so in the RTL context, the icon needs to flip to show the waves coming from the right.

**Don’t flip logos or universal signs and marks.** Displaying a flipped logo confuses people and can have legal repercussions. Always display a logo in its original form, even if it includes text. People expect universal symbols and marks like the checkmark to have a consistent appearance, so avoid flipping them.

**In general, avoid flipping interface icons that depict real-world objects.** Unless you use the object to indicate directionality, it’s best to avoid flipping an icon that represents a familiar item. For example, clocks work the same everywhere, so a traditional clock interface icon needs to look the same regardless of language direction. Some interface icons might seem to reference language or reading direction because they represent items that are slanted for right-handed use. However, most people are right-handed, so flipping an icon that shows a right-handed tool isn’t necessary and might be confusing.

**Before merely flipping a complex custom interface icon, consider its individual components and the overall visual balance.** In some cases, a component — like a badge, slash, or magnifying glass — needs to adhere to a visual design language regardless of localization. For example, a well-designed symbol library maintains visual consistency by using the same backslash to represent the prohibition or negation of a symbol’s meaning in both LTR and RTL versions.

In other cases, you might need to flip a component (or its position) to ensure the localized version of the icon still makes sense. For example, if a badge represents the actual UI that people see in your app, it needs to flip if your UI flips. Alternatively, if a badge modifies the meaning of an interface icon, consider whether flipping the badge preserves both the modified meaning and the overall visual balance of the icon. In the images shown below, the badge doesn’t depict an object in the UI, but keeping it in the top-right corner visually unbalances the cart.

If your custom interface icon includes a component that can imply handedness, like a tool, consider preserving the orientation of the tool while flipping the base image if necessary.


---

## Typography

Your typographic choices can help you display legible text, convey an information hierarchy, communicate important content, and express your brand or style.


### Ensuring legibility

**Use font sizes that most people can read easily.** People need to be able to read your content at various viewing distances and under a variety of conditions. Follow the recommended default and minimum text sizes for each platform — for both custom and system fonts — to ensure your text is legible on all devices. Keep in mind that font weight can also impact how easy text is to read. If you use a custom font with a thin weight, aim for larger than the recommended sizes to increase legibility.

| Platform | Default size | Minimum size |
| --- | --- | --- |
| phones and tablets | 17 pt | 11 pt |
| desktop | 13 pt | 10 pt |

**Test legibility in different contexts.** For example, you need to test game text for legibility on each platform on which your game runs. If testing shows that some of your text is difficult to read, consider using a larger type size, increasing contrast by modifying the text or background colors, or using typefaces designed for optimized legibility, like the system fonts.

**In general, avoid light font weights.** For example, if you’re using system-provided fonts, prefer Regular, Medium, Semibold, or Bold font weights, and avoid Ultralight, Thin, and Light font weights, which can be difficult to see, especially when text is small.


### Conveying hierarchy

**Adjust font weight, size, and color as needed to emphasize important information and help people visualize hierarchy.** Be sure to maintain the relative hierarchy and visual distinction of text elements when people adjust text sizes.

**Minimize the number of typefaces you use, even in a highly customized interface.** Mixing too many different typefaces can obscure your information hierarchy and hinder readability, in addition to making an interface feel internally inconsistent or poorly designed.

**Prioritize important content when responding to text-size changes.** Not all content is equally important. When someone chooses a larger text size, they typically want to make the content they care about easier to read; they don’t always want to increase the size of every word on the screen. For example, when people increase text size to read the content in a tabbed window, they don’t expect the tab titles to increase in size. Similarly, in a game, people are often more interested in a character’s dialog than in transient hit-damage values.


### Using system fonts

Each platform ships a system UI typeface tuned for legibility on its displays — San Francisco on Apple platforms, Roboto on Android, Segoe UI on Windows; on the web, `system-ui` resolves to the native one. System fonts cover an extensive range of weights, sizes, styles, and languages, and usually come with companion families: a **rounded** variant (for soft or rounded UI, or an alternative voice), a **serif** family for reading, and a **monospaced** family for code and aligned numbers.

Modern system fonts are **variable fonts**, which combine styles in one file and interpolate between them.

> **Note**: Variable fonts support *optical sizing* — adjusting the letterform design to fit different sizes. Many system fonts merge discrete optical sizes (like Text and Display) and weights into one continuous design, so text is tuned for every size. On the web, `font-optical-sizing: auto` enables this for fonts with an `opsz` axis.

**Use weights and widths to build hierarchy.** System fonts typically range from Ultralight to Black, and some offer widths like Condensed and Expanded. Match icon weights to adjacent text weights for precise alignment (see [Iconography & Symbols](./iconography-and-symbols.md)).

A *text style* specifies a combination of font weight, point size, and leading for each text size. For example, the *body* style supports a comfortable reading experience across paragraphs.

**Consider using the built-in text styles.** Text styles give you a convenient and consistent way to convey hierarchy through size and weight, and — with system fonts — ensure support for dynamic text sizing and larger accessibility type sizes, which let people choose the text size that works for them.

**Modify the built-in text styles if necessary.** Use *traits* like bold or italic to add a level of hierarchy without inventing new sizes. Don’t embed a platform’s system font file in your app; reference it through the platform’s font APIs or `system-ui`.

**If necessary, adjust tracking in interface mockups.** In a running app, the system font may adjust tracking at every point size automatically; in mockups and on the web, apply size-specific tracking yourself. See the tracking table in [Design Tokens](./design-tokens-and-styles.md).

### Using custom fonts

**Make sure custom fonts are legible.** People need to be able to read your custom font easily at various viewing distances and under a variety of conditions. While using a custom font, be guided by the recommended minimum font sizes for various styles and weights in Specifications.

**Implement accessibility features for custom fonts.** System fonts automatically support dynamic text sizing (where available) and respond when people turn on accessibility features, such as Bold Text. If you use a custom font, make sure it implements the same behaviors. In a game engine, use available accessibility plug-ins, or let players adjust text size in your own settings.


### Supporting dynamic text sizing

Dynamic text sizing is a system-level feature on most platforms (the browser’s font-size and zoom settings on the web) that lets people adjust the size of visible text on their device to ensure readability and comfort. For related guidance, see Accessibility.

For the full size tables, see [Design Tokens](./design-tokens-and-styles.md).


**Make sure your app’s layout adapts to all font sizes.** Verify that your design scales, and that text and glyphs are legible at all font sizes. Turn on the largest accessibility text size in system settings (and 200% zoom in the browser), and confirm that your app remains comfortably readable.

**Increase the size of meaningful interface icons as font size increases.** If you use interface icons to communicate important information, make sure they’re easy to view at larger font sizes too. Size icons in relative units (em) so they scale with text.

**Keep text truncation to a minimum as font size increases.** In general, aim to display as much useful text at the largest accessibility font size as you do at the largest standard font size. Avoid truncating text in scrollable regions unless people can open a separate view to read the rest of the content. You can prevent text truncation in a label by configuring it to use as many lines as needed to display a useful amount of text.

**Consider adjusting your layout at large font sizes.** When font size increases in a horizontally constrained context, inline items (like glyphs and timestamps) and container boundaries can crowd text and cause truncation or overlapping. To improve readability, consider using a stacked layout where text appears above secondary items. Multicolumn text can also be less readable at large sizes due to horizontal space constraints. Reduce the number of columns when the font size increases to avoid truncation and enhance readability.

**Maintain a consistent information hierarchy regardless of the current font size.** For example, keep primary elements toward the top of a view even when the font size is very large, so that people don’t lose track of these elements.


### Device-specific considerations

#### Phone & tablet
Use the system font and its text styles; a serif companion works for reading-heavy content.

#### Desktop
Desktop text is denser (body ≈ 13 pt), and some desktop platforms don’t offer a system text-size setting — provide in-app text-size or zoom controls.

**When necessary, use the system font variants that standard controls use** — control content, labels, menus, menu bar, messages, palettes, window titles, tooltips, user document text, and monospaced document text — so custom UI matches the text in system-provided controls.

### Specifications

Full type scales — phone/tablet default and accessibility sizes, desktop styles, emphasized weights, and the size-specific tracking curve — are in [Design Tokens, Typography & Visual Styles](./design-tokens-and-styles.md).

---

## Writing

The words you choose within your app are an essential part of its user experience.

Whether you’re building an onboarding experience, writing an alert, or describing an image for accessibility, designing through the lens of language will help people get the most from your app or game.


### Getting started

**Determine your app’s voice.** Think about who you’re talking to, so you can figure out the type of vocabulary you’ll use. What types of words are familiar to people using your app? How do you want people to feel? The words for a banking app might convey trust and stability, for example, while the words in a game might convey excitement and fun. Create a list of common terms, and reference that list to keep your language consistent. Consistent language, along with a voice that reflects your app’s values, helps everything feel more cohesive.

**Match your tone to the context.** Once you’ve established your app’s voice, vary your tone based on the situation. Consider what people are doing while they’re using your app — both in the physical world and within the app itself. Are they exercising and reached a goal? Or are they trying to make a payment and received an error? Situational factors affect both what you say and how you display the text on the screen.

In the first, the tone is straightforward and direct, reflecting the seriousness of the situation. In the second, the tone is light and congratulatory.

**Be clear.** Choose words that are easily understood and convey the right thing. Check each word to be sure it needs to be there. If you can use fewer words, do so. When in doubt, read your writing out loud.

**Write for everyone.** For your app to be useful for as many people as possible, it needs to speak to as many people as possible. Choose simple, plain language and write with accessibility and localization in mind, avoiding jargon and gendered terminology. For guidance, see Inclusion and Accessibility.


### Best practices

**Consider each screen’s purpose**. Pay attention to the order of elements on a screen, and put the most important information first. Format your text to make it easy to read. If you’re trying to convey more than one idea, consider breaking up the text onto multiple screens, and think about the flow of information across those screens.

**Be action oriented.** Active voice and clear labels help people navigate through your app from one step to the next, or from one screen to another. When labeling buttons and links, it’s almost always best to use a verb. Prioritize clarity and avoid the temptation to be too cute or clever with your labels. For example, just saying “Send” often works better than “Let’s do it!” For links, avoid using “Click here” in favor of more descriptive words or phrases, such as “Learn more about UX Writing.” This is especially important for people using screen readers to access your app.

**Build language patterns.** Consistency builds familiarity, helping your app feel cohesive, intuitive, and thoughtfully designed. It also makes writing for your app easier, as you can return to these patterns again and again.

**Adopt capitalization rules that align with your app’s style, then apply them consistently.** While certain components, like button labels, have specific guidelines, how you format text reflects your app’s voice. Title case is generally considered formal, while sentence case is more casual. Choose a style for each UI element type and use it consistently throughout your app — for example, title case for all alerts or sentence case for all headlines.

**Give clear guidance and use consistent language throughout processes with multiple steps.** If your app has a flow that spans multiple screens, decide how you want to label the actions that take people from one step to the next. Begin with language like “Get Started” to indicate you’re starting a flow. You can use the button label to hint at the next step, or use terms like “Continue” or “Next,” but be consistent with what you choose. Make it clear when a flow is complete by using language like “Done.”

**Use possessive pronouns sparingly.** Possessive pronouns like *my* and *your* are often unnecessary to establish context. For example, “Favorites” conveys the same message as “Your Favorites,” and is more succinct. If you do use possessive pronouns, use them consistently throughout your app, and try not to switch perspectives. Avoid using *we* altogether because it may be unclear who the “we” in question refers to. This is particularly problematic in error messages like “We’re having trouble loading this content.” Something like “Unable to load content” is much clearer.

**Write for how people use each device.** People may use your app on several types of devices. While your language needs to be consistent across them, think about where it would be helpful to adjust your text to make it suitable for different devices. Make sure you describe gestures correctly on each device — for example, not saying “click” for a touch device like phone or tablet where you mean “tap.”

Where and how people use a device, its screen size, and its location all affect how you write for your app. Bigger screens also require brevity, as the text must be large for people to see it from a distance.

**Provide clear next steps on any blank screens.** An empty state, like a completed to-do list or bookmarks folder with nothing in it, can provide a good opportunity to make people feel welcome and educate them about your app. Empty states can also showcase your app’s voice, but make sure that the content is useful and fits the context. An empty screen can be daunting if it isn’t obvious what to do next, so guide people on actions they can take, and give them a button or link to do so if possible. Remember that empty states are usually temporary, so don’t show crucial information that could then disappear.

**Write clear error messages.** It’s always best to help people avoid errors. When an error message is necessary, display it as close to the problem as possible, avoid blame, and be clear about what someone can do to fix it. For example, “That password is too short” isn’t as helpful as “Choose a password with at least 8 characters.” Remember that errors can be frustrating. Interjections like “oops!” or “uh-oh” are typically unnecessary and can sound insincere. If you find that language alone can’t address an error that’s likely to affect many people, use that as an opportunity to rethink the interaction.

**Choose the right delivery method.** There are many ways to get people’s attention, whether or not they are actively using your app. When there’s something you want to communicate, consider the urgency and importance of the message. Think about the context in which someone might see the message, whether it requires immediate action, and how much supporting information someone might need. Choose the correct delivery method, and use a tone appropriate for the situation. For guidance, see Notifications, Alerts, and Action sheets.

**Keep settings labels clear and simple.** Help people easily find the settings they need by labeling them as practically as possible. If the setting label isn’t enough, add an explanation. Describe what it does when turned on, and people can infer the opposite. It isn’t necessary to tell you that a timer won’t start when this setting is off.

If you need to direct someone to a setting, provide a direct link or button, rather than trying to describe its location. For guidance, see Settings.

**Show hints in text fields.** If your app allows people to enter their own text, like account or contact information, label all fields clearly, and use hint or placeholder text so people know how to format the information. You can give an example in hint text, like “name@example.com,” or describe the information, such as “Your name.” Show errors right next to the field, and instruct people how to enter the information correctly, rather than scolding them for not following the rules. “Use only letters for your name” is better than “Don’t use numbers or symbols.” Avoid robotic error messages with no helpful information, like “Invalid name.” For guidance, see Text fields.


---

