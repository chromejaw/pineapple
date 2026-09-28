# Patterns

Guidance on common actions, workflows, and core user experiences.

---

## Charting data

Presenting data in a chart can help you communicate information with clarity and appeal.

Charts provide efficient ways to communicate complex information without requiring people to read and interpret a lot of text. The graphical nature of charts also gives you additional opportunities to express the personality of your experience and add visual interest to your interface. To learn about the components you use to create a chart, see Charts.

A chart can range from a simple graphic that provides glanceable information to a rich, interactive experience that can form the centerpiece of your app and encourage people to explore the data from various perspectives. Whether simple or complex, you can use charts to help people perform data-driven tasks that are important to them, such as:

- Analyzing trends based on historical or predicted values

- Visualizing the current state of a process, system, or quantity that changes over time

- Evaluating different items — or the same item at different times — by comparing data across multiple categories

Not every collection of data needs to be displayed in a chart. If you simply need to provide data — and you don’t need to convey information about it or help people analyze it — consider offering the data in other ways, such as in a list or table that people can scroll, search, and sort.


### Best practices

**Use a chart when you want to highlight important information about a dataset.** Charts are visually prominent, so they tend to draw people’s attention. Take advantage of this prominence by clearly communicating what people can learn from the data they care about.

**Keep a chart simple, letting people choose when they want additional details.** Resist the temptation to pack as much data as possible into a chart. Too much data can make a chart visually overwhelming and difficult to use, obscuring the relationships and other information you want to convey. If you have a lot of data to present — or a lot of functionality to provide — consider giving people a way to reveal it gradually. For example, you might let people choose to view different levels of detail or subsets of data to match their interest. To help people learn how to use an interactive chart, you might offer several versions of the chart, each with more functionality than the last.

**Make every chart in your app accessible.** A chart communicates visually through graphical representations of data and visual descriptions. In addition to the visual descriptions you display, it’s crucial to provide both accessibility labels that describe chart values and components, and accessibility elements that help people interact with the chart. For guidance, see Enhancing the accessibility of a chart.


### Designing effective charts

**In general, prefer using common chart types.** People tend to be familiar with common chart types — such as bar charts and line charts — so using one of these types in your app can make it more likely that people will already know how to read your chart. For guidance, see Charts.


**Examine the data from multiple levels or perspectives to find details you can display to enhance the chart.** For example, viewing the data from a macro level can help you determine high-level summaries that people might be interested in, like totals or averages. From a mid-level perspective, you might find ways to help people identify useful subsets of the data, whereas examining individual data points might help you find ways to draw people’s attention to specific values or items. Displaying information that helps people view the chart from various perspectives can encourage them to engage with it.

**Aid comprehension by adding descriptive text to the chart.** Descriptive text titles, subtitles, and annotations help emphasize the most important information in a chart and can highlight actionable takeaways. You can also display brief descriptive text that serves as a headline or summary for a chart, helping people grasp essential information at a glance. For example, a weather app displays text that summarizes the information people need right now — such as “Chance of light rain in the next hour” — above the scrolling list of hourly forecasts for the next 24 hours. Although a descriptive headline or summary can make a chart more accessible, it doesn’t take the place of accessibility labels.

**Match the size of a chart to its functionality, topic, and level of detail.** In general, a chart needs to be large enough to comfortably display the details you need to include and expansive enough for the interactivity you want to support. For example, you always want to make it easy for people to read a chart’s details and descriptive text — like labels and annotations — but you might also want to give people enough room to change the scope of a chart or investigate the data from different perspectives. On the other hand, you might want to use a small chart to offer glanceable information about an individual item or to provide a snapshot or preview of a larger version of the chart that people can reveal in a different view.

**Prefer consistency across multiple charts, deviating only when you need to highlight differences.** If multiple charts in your app serve a similar purpose, you generally don’t want to imply that the charts are unrelated by using a different type or style for each one. Also, using a consistent visual approach for the charts in your app lets people use what they learn about one chart to help them understand another. Consider using different chart types and styles when you need to highlight meaningful differences between charts.

**Maintain continuity among multiple charts that use the same data.** When you use multiple charts to help people explore one dataset from different perspectives, it’s important to use one chart type and consistent colors, annotations, layouts, and descriptive text to signal that the dataset remains the same. For example, the Health Trends screen shows small charts that each use a specific visual style to depict a recent trend in an area like steps or resting heart rate. When people choose a chart to reveal all their data in that area, the expanded version uses the same style, colors, marks, and annotations to strengthen the relationship between the versions.


---

## Collaboration and sharing

Great collaboration and sharing experiences are simple and responsive, letting people engage with the content while communicating effectively with others.

System interfaces and messaging apps can help you provide consistent and convenient ways for people to collaborate and share. For example, people can share content or begin a collaboration by dropping a document into a messaging app conversation or selecting a destination in the familiar share sheet.

After a collaboration begins, people can use the Collaboration button in your app to communicate with others, perform custom actions, and manage details. In addition, people can receive messaging notifications when collaborators mention them, make changes, join, or leave.

You can take advantage of messaging integration and the system-provided sharing interfaces whether you build collaboration on a platform cloud service, a third-party service, or a custom solution. Make sure shared links are universal/deep links that open the right view in your app.

With real-time co-presence features, people can also take part in your app’s activities together from their own devices. For guidance, see [Commerce, Accounts & Accessibility › Real-Time Collaboration](./commerce-accounts-and-accessibility.md).


### Best practices

**Place the Share button in a convenient location, like a toolbar, to make it easy for people to start sharing or collaborating.** Modern share sheets include ways to choose a file-sharing method (collaborate vs. send a copy) and set permissions for a new collaboration; larger screens present the same options in a sharing popover.

**If necessary, customize the share sheet or sharing popover to offer the types of file sharing your app supports.** For example, support both inviting people to collaborate on a live document and sending them a static copy — including a file, or a plain-text representation of it, alongside the collaboration link so the share sheet can offer “send copy.”

**Write succinct phrases that summarize the sharing permissions you support.** For example, you might write phrases like “Only invited people can edit” or “Everyone can make changes.” The system uses your permission summary in a button that reveals a set of sharing options that people use to define the collaboration.

**Provide a set of simple sharing options that streamline collaboration setup.** You can customize the view that appears when people choose the permission summary button to provide choices that reflect your collaboration functionality. For example, you might offer options that let people specify who can access the content and whether they can edit it or just read it, and whether collaborators can add new participants. Keep the number of custom choices to a minimum and group them in ways that help people understand them at a glance.

**Prominently display the Collaboration button as soon as collaboration starts.** The system-provided Collaboration button reminds people that the content is shared and identifies who’s sharing it. Because the Collaboration button typically appears after people interact with the share sheet or sharing popover, it works well to place it next to the Share button.

**Provide custom actions in the collaboration popover only if needed.** Choosing the Collaboration button in your app reveals a popover that consists of three sections. The top section lists collaborators and provides communication buttons that can open a messaging app or video calls, the middle section contains your custom items, and the bottom section displays a button people use to manage the shared file. You don’t want to overwhelm people with too much information, so it’s crucial to offer only the most essential items that people need while they use your app to collaborate. For example, a notes app summarizes the most recent updates and provides buttons that let people get more information about the updates or view more activities.

**If it makes sense in your app, customize the title of the modal view’s collaboration-management button.** People choose this button — titled “Manage Shared File” by default — to reveal the collaboration-management view where they can change settings and add or remove collaborators. If you use CloudKit sharing, the system provides a management view for you; otherwise, you create your own.

**Consider posting collaboration event notifications in the conversation where the collaboration started.** Choose the type of event that occurred — such as a change in the content or the collaboration membership, or the mention of a participant — and include a universal link people can use to open the relevant view in your app.


### Device-specific considerations

## Drag and drop

Using drag and drop, people can move or duplicate selected photos, text, and other content by dragging the selection from one location to another.

To perform drag and drop, people select content in one location, called the *source*, and drop it in another, called the *destination*. These locations can be in the same container — like a text view — or in different containers, like text views on opposite sides of a split view, or even in different apps.

Depending on various factors, the drag and drop action might *move* the selected content to the destination or *copy* it. After a successful drop, moved content exists only in the destination; copied content exists in both locations. As a general rule, dropping selected content within the same container moves it, whereas dropping content in a different container copies it. Dragging and dropping content between apps always results in a copy.

People use different interactions to perform drag and drop depending on platform. For example:


- Phones and tablets support drag and drop through gestures on the touchscreen, interactions with a pointing device, and through full keyboard-access mode.

- Cross-device input sharing lets people drag content between a computer and a nearby tablet.

- On a computer, people can interact with a pointing device, use full keyboard access mode, or use the screen reader to perform drag and drop.


### Best practices

**As much as possible, support drag and drop throughout your app.** Most people are familiar with drag and drop and they often try it everywhere. When you use system-provided components — such as text fields and text views — you get built-in support for drag and drop.

**Offer alternative ways to accomplish drag-and-drop actions.** Sometimes, drag-and-drop operations are inconvenient or impossible for people to perform, so it’s important to provide other ways to do the same things. For example, you can include menu commands that people can use to copy an item and move it to another location. Use accessibility APIs to identify drag sources and destinations so that people can use assistive technologies to drag and drop in your app.

**Determine when dragging and dropping content within your app results in a move or a copy.** In general, a move makes sense when the source and destination containers are the same — such as dragging text from one location to another within a document — and a copy makes sense when they’re different, like dragging an image from one document to another. Before you change these defaults, consider the behavior that most people expect and prefer the one that is least likely to result in frustration or data loss.

**Support multi-item drag and drop when it makes sense.** People appreciate the convenience of dragging a group of items to a destination, instead of dragging each item separately. On phones, tablets and desktop, people can select multiple items and drag them as a group; desktop also lets people select multiple items from several apps and drag them as a group. On tablets, people can select an item, start dragging it, and add other items to the group without stopping the drag operation.

**Prefer letting people undo a drag-and-drop operation.** Sometimes, people inadvertently drop content in the wrong destination, so they appreciate being able to undo the action and return to their previous state. You might also be able to help people avoid mistakes by asking for confirmation before completing a drag-and-drop operation that can’t be undone. On desktop, for example, the file manager asks for confirmation when people drag a file into a write-only folder because they won’t be able to open the folder and remove the dropped item. In some situations, it might make sense to provide a way to reverse the results of drag and drop when people can’t undo it. For example, a photos app lets people cancel photo sharing after dropping a photo into a shared photo stream.

**Consider offering multiple versions of dragged content, ordered from highest to lowest fidelity.** By providing multiple alternatives, the destination can choose the highest quality version it can accept. For example, if people can drag a line drawing they created in your app, you could offer a PDF vector representation, a lossless PNG image with transparency, and a lossy JPEG image without transparency, in that order. Another example is an app that uses rich, complicated objects, like charts. This app might offer the native chart object followed by a simpler version — like an image of the chart — for destinations that don’t support chart objects.

**Consider supporting spring loading.** Spring loading lets people activate certain controls, like buttons and segmented controls, by dragging selected content over them. For example, a calendar app lets people drag a selected event over the day, week, month, or year segments in the toolbar, giving them a convenient way to move the event to a different date. On a computer equipped with a trackpad, a button or segmented control can activate when people force-click it while continuing to hold the content; on tablet, these components can activate when people hover over them while holding the content.


### Providing feedback

Drag and drop is a dynamic process that can result in multiple outcomes. To help people feel in control the process, it’s crucial to provide clear and continuous feedback throughout.

**Display a drag image as soon as people drag a selection about three points.** It works well to create a translucent representation of the content people are dragging. Translucency helps distinguish the representation from the original content and lets people see destinations as they pass over them. Display the drag image until people drop the content.

**If it adds clarity, modify the drag image to help people predict the result of a drag-and-drop operation.** For example, when dragging a photo into a document, the drag image could expand to show the default size of the photo in the document. You can also use drag *flocking* to visually group multiple drag items — letting people confirm that they haven’t missed an item they want to drag — and then ungroup the items when people drop them. Although changing the drag image can provide valuable feedback, avoid creating a distracting experience in which the drag image is constantly and radically changing.

**Show people whether a destination can accept dragged content.** For example, you might display an insertion point or highlight a containing view only when the destination can accept a dragged item, and show no visual feedback — or an explicit “not allowed” image, like the circle.slash from the symbol library — when it can’t. Display highlighting or other visual cues only while the content is positioned above the destination, removing the visual feedback when people drag the content away. When there are multiple possible destinations, provide visual cues that help people identify one at a time.

**When people drop an item on an invalid destination, or when dropping fails, provide visual feedback.** For example, the item can move back from its current location to its source (if the source is still visible) or it can scale up and fade out to give the impression of the item evaporating instead of landing successfully.


### Accepting drops

**Scroll the contents of a destination when necessary.** When people drag an item within a scrolling container that has a lot of content, the content can automatically scroll as people move the item over it. This behavior makes it easy for people to find the right place to drop the item, but if they continue the drag operation outside of the container, automatic scrolling is no longer necessary. System-provided text views and text fields behave this way by default.

**When there’s a choice, pick the richest version of dropped content your app can accept.** For example, if people drag a chart object from another app, the drag operation might offer both the rich, native chart object and a simple image of it. If your app supports charts, extract and display the native chart object; it it doesn’t, use the image instead.

**Extract only the relevant portion of dropped content if necessary.** For example, when people drag a contact to a recipient field in an email, a mail app displays only the name and email address, not the contact’s address information.

**When a physical keyboard is attached, check for the Option key at drop time.** When people hold the Option key while dragging, they can force a drag-and-drop operation within the same container to behave like a copy. If people stop holding Option before dropping content in the same container, the drag operation results in a move.

**Provide feedback when dropped content needs time to transfer.** For example, you might display a progress indicator to help people estimate how long the transfer will take. In collections, lists, and tables, you might also display a placeholder at the drop location so people know where to find the content after it finishes transferring. The system can display an alert when a time-consuming transfer occurs between apps.

**Provide feedback when dropped content initiates a task or action.** If people drop content onto a control that initiates a task — such as printing — show people that the task has begun and keep them informed of its progress.

**Apply appropriate styling to dropped text.** When the source and destination both support the same text styles, make sure dropped text maintains its original font, typeface, size, and other attributes. Otherwise, apply the destination’s style to dropped text.

**After a drop, maintain the content’s selection state in the destination, updating it in the source as needed.** People expect the content they drop to remain selected so they can immediately act on it. When the source and destination are the same container, the content disappears from its original location when the drag operation performs a move. When a drag operation within the same container performs a copy, remove the selection state from the content that remains in the original location. When people drag selected content to a different container, deselect the content in the source.


### Device-specific considerations

#### Phone & tablet
**Let people perform multiple simultaneous drag activities.** On tablets, people can sequentially add items to an in-progress drag session, gathering as many items as their fingers can handle. For example, people can select an app icon on the home screen, start dragging it, and select additional app icons before dropping all of them in a different home screen or in a folder. To support this interaction, you need to let people add items during a drag — providing visual feedback through flocking — and accept multiple, simultaneous drops.


#### Desktop
**Consider letting people drag content from your app into the file manager.** When you support this, be sure to present the content in a format your app can open later. For example, a calendar app lets people drag an event to the file manager as a .ics file. People can share this file with others or drag it back to a calendar app to open it. When necessary, you can output dragged content in a *clipping*, which is a temporary container for storing dragged content. For example, most system apps let people drag text to the file manager, where it appears as a clipping. Later, people can drag the clipping into a text field or other location that accepts text. Note that a drag-and-drop clipping isn’t related to the Clipboard.

**Let people drag selected content from an inactive window without first making the window active.** Selected content in an inactive window is known as a *background selection* and has a different appearance from selected content in the active window. In general, people expect to drag a background selection to the active window without bringing the inactive window forward.

**When possible, let people drag individual items from an inactive window without affecting an existing background selection.** For example, people can drag an unselected file from an inactive file manager window without deselecting any of the window’s selected files.

**Consider displaying a badge during multi-item drag operations.** A badge is a small filled oval containing a number you can use to indicate the number of items people are dragging. If a destination can accept only a subset of dragged items, update the badge to show the new number.

**Consider changing the pointer appearance to indicate what will happen when people drop content.** In addition to using the *copy* pointer, you might want to use the *drag link*, *disappearing item*, and *operation not allowed* pointers, depending on the situation. For guidance, see Pointers.

**As much as possible, let people select and drag content with a single motion.** Unless people are selecting multiple items, they appreciate it when they don’t have to pause between making a selection and starting the drag operation.


## Entering data

When you need information from people, design ways that make it easy for them to provide it without making mistakes.

Entering information can be a tedious process regardless of the interaction methods people use. Improve the experience by:

- Pre-gathering as much information as possible to minimize the amount of data that people need to supply

- Supporting all available input methods so people can choose the method that works for them


### Best practices

**Get information from the system whenever possible.** Don’t ask people to enter information that you can gather automatically — such as from settings — or by getting their permission, such as their location or calendar information.

**Be clear about the data you need.** For example, you might display a prompt in a text field — like “username@company.com” — or provide an introductory label that describes the information, like “Email.” You can also prefill fields with reasonable default values, which can minimize decision making and speed data entry.

**Use a secure text-entry field when appropriate.** If your app or game needs sensitive data, use a field that obscures people’s input as they enter it, typically by displaying a small filled circle symbol for each character.

**Never prepopulate a password field.** Always ask people to enter their password or use biometric or keychain authentication. For guidance, see Managing accounts.

**When possible, offer choices instead of requiring text entry.** It’s usually easier and more efficient to choose from lists of options than to type information, even when a keyboard is conveniently available. When it makes sense, consider using a picker, menu, or other selection component to give people an easy way to provide the information you need.

**As much as possible, let people provide data by dragging and dropping it or by pasting it.** Supporting these interactions can ease data entry and make your experience feel more integrated with the rest of the system.

**Dynamically validate field values.** People can get frustrated when they have to go back and correct mistakes after filling out a lengthy form. When you verify values as soon as people enter them — and provide feedback as soon as you detect a problem — you give them the opportunity to correct errors right away. For numeric data in particular, consider using a number formatter, which automatically configures a text field to accept only numeric values. You can also configure a formatter to display the value in a specific way, such as with a certain number of decimal places, as a percentage, or as currency.

**When data entry is necessary, make sure people understand that they must provide the required data before they can proceed.** For example, if you include a Next or Continue button after a set of text fields, make the button available only after people enter the data you require.


### Device-specific considerations

#### Desktop
**Consider using an expansion tooltip to show the full version of clipped or truncated text in a field.** An *expansion tooltip* behaves like a regular tooltip, appearing when the pointer rests on top of a field. Apps running with a pointer — including phone and tablet apps running on a computer — can use an expansion tooltip to help people view the complete data they entered when a text field is too small to display it. For guidance, see Offering help.


---

## Feedback

Feedback helps people know what’s happening, discover what they can do next, understand the results of actions, and avoid mistakes.

Providing clear, consistent feedback as people interact with your app or game can make it feel intuitive and encourage deeper exploration. Feedback can communicate several different things, such as:

- The current status of something

- The success or failure of an important task or action

- A warning about an action that can have negative consequences

- An opportunity to correct a mistake or problematic situation

The most effective feedback tends to match the significance of the information to the way it’s delivered. For example, it often works well to display status information in a passive way so that people can view it when they need it. In contrast, a warning about possible data loss needs to interrupt people so they have a chance to avoid the problem.


### Best practices

**Make sure all feedback is accessible.** When you use multiple ways to provide feedback, you reach more people and give them the opportunity to receive the feedback in ways that work for them. For example, when you provide feedback using color, text, sound, and haptics, people can receive it whether they silence their device, look away from the screen, or use the screen reader. (For guidance on providing haptic feedback, see Playing haptics.)

**Consider integrating status feedback into your interface.** When status feedback is available near the items it describes, people get important information without having to take action or leave their current context. For example, a mail app on phones and tablets describes the most recent update and displays the number of unread messages in the toolbar of the mailbox screen, making the information unobtrusive but easy for people to check when they’re interested.

**Use alerts to deliver critical — and ideally actionable — information.** By design, alerts disrupt the current context, so you need to match the importance of the information to the level of interruption. Alerts can lose their impact if you use them too often or to deliver unimportant information. For guidance, see Alerts.

**Warn people when they initiate a task that can cause data loss that’s unexpected and irreversible.** In contrast, don’t warn people when data loss is the expected result of their action. For example, the file manager doesn’t warn people every time they throw away a file because deleting the file is the expected result.

**When it makes sense, confirm that a significant action or task has completed.** For example, people appreciate getting feedback that confirms a successful payment. It’s generally best to reserve this type of confirmation for activities that are sufficiently important — because people typically expect their action or task to succeed, they only need to know when it doesn’t.

**Show people when a command can’t be carried out and help them understand why.** For example, if people request directions without specifying a destination, a maps app tells them that it can’t provide directions to and from the same location.


### Device-specific considerations

## File management

Some apps can support documents and files that people expect to manage throughout the system.

Document-based apps — such as word processors, presentation apps, photo editors, and image viewers — help people create, edit, and save documents and files, often providing customized ways for people to browse for content they want to open in the app.

People also expect to browse documents without first opening a document-based app. On a computer, for example, people use the file manager to access the desktop file system; on phones and tablets, people use a files app to manage the documents and files on their device.


### Creating and opening files

**Use app menus and keyboard shortcuts to give people convenient ways to create and open documents.** On tablets and desktop, people expect to create new documents or open existing ones using familiar menu commands. When you provide commands like New or Open, tablets can list them in a keyboard-shortcut overlay, and desktop apps present them in the File menu. Regardless of the availability of keyboard shortcuts, include an Add (+) button to help people create a new document. In a desktop app, you put the add action in the File menu (for guidance, see File menu).

**If your app requires a custom file browser, support people’s understanding of the platform’s file system.** People who are familiar with their platform’s file manager already understand the basic layout of their device’s file system. Although you might want to show the most relevant part of the file system when your custom file browser opens — for example, a Documents or cloud-synced folder or the most recently selected location — let people use your browser to view the rest of the file system if they want.


### Saving work

**Help people be confident that their work is always preserved unless they cancel or delete it.** In general, avoid making people take an explicit action to save their work. Instead, automatically perform periodic saves while they’re editing and when they close a file or switch to another app.

**Hide file extensions by default, but let people view them if they choose.** Be sure to reflect the current choice in all the save or open interfaces you display.


### File previews

A system file previewer helps you create previews of the files your app handles so that people can view them within your app and in some cases interact with them. For example, you can use the previewer to let people listen to a preview of an audio file, add markup to a photo’s preview, or rotate and scale a 3D file preview to examine it in different ways.

**Use a preview viewer to let people preview a file even when your app can’t open it.** If your app lets people attach or otherwise interact with files that it doesn’t support, implementing a previewer lets people preview those files without leaving your app.

**Consider providing a preview/thumbnail generator if your app produces custom file types.** It lets other apps — including the file manager — display previews of your documents, making them easier to find.


### Device-specific considerations

#### Phone & tablet
##### Document launcher

Where the platform provides one, document-based apps can use a system document launcher to give people a consistent, highly graphical way to browse, open, and create files. The document launcher presents a full-screen experience that highlights key elements of your app’s theme, while making it easy for people to create new documents.

The document launcher consists of three main parts:

- A *title card* that displays the app title and two app-specific buttons

- A background image that appears behind the title card and additional images — called *accessories* — that can appear around it

- A sheet that contains a file browser and optional app-specific controls

You can customize all three parts of the document launcher. Although the system automatically displays your app name in the title card, you specify the text and functions of the card’s primary and secondary buttons. You can also create a custom background image, one or more accessory images to surround the title card, and provide some custom controls that can appear in the file browser’s toolbar.

**Assign the title card’s buttons to your app’s most important functions.** The primary button typically creates a new document, and the secondary button can provide additional options. For example, a word processor’s primary button might be Start Writing and the secondary button Choose a Template.

**Provide a background that’s clearly distinct from the accessories and title card.** You can use a solid color, a gradient, or a pattern. Avoid including complex images or patterns that might distract from foreground elements.

**Be mindful of accessory placement.** For example, you can place accessories both in front of and behind the title card to create the appearance of depth, but you need to make sure that your app name and both buttons remain clearly visible. Avoid cluttering the title card with too many accessories, and be sure to test its overall appearance across the range of screen sizes and device orientations that you support.

**Use animation sparingly.** Too much motion on the display can confuse or disorient people. If you want to animate your accessories, consider creating gentle, repeating animations that subtly highlight and enhance your app’s content. For example, you might create an animation that makes an accessory appear to breathe or sway softly. For guidance, see Motion.


#### Desktop
##### Custom file management

People have strong associations with the familiar file browsing experience of the file manager and most document-based apps. Use the default file browser unless you have an important reason to create a custom one.

**Make your custom file-opening interface convenient.** For example, people might appreciate an “open recent” action in addition to the simple “open” action. You might also want to let people choose criteria on which to filter the file-browsing experience, or select multiple documents to open at once. In a desktop open panel, you can customize the title of the Open button to reflect the task — for example, if your app lets people insert a file’s contents into the current document, you might change the title to Insert.

**Provide a save interface to let people change a file’s name, format, or location.** By default, a new document’s title is “Untitled” until people choose a custom name. As with a document-opening interface, a save view can also provide a browsing experience that defaults to a logical location to help people place the saved document where they want. If you support saving content in different formats, also give people a way to choose a specific file format.

**Consider extending the functionality of the Save dialog.** If it makes sense in your app, you can add a custom accessory view containing useful settings or options to the Save dialog. For example, the dialog for saving mail messages as files contains an option to include attachments.


##### the file manager Sync extensions

If your app syncs local and remote files, integrate with the file manager (sync-provider extensions or shell integration) to express file synchronization status and control within it.

For example, you can:

- Display badges in the file manager to indicate the sync status of items

- Provide custom contextual menu items that perform file and folder management tasks, like favoriting and adding password-protection

- Provide custom toolbar buttons that perform global actions, like initiating a sync operation

**Help people avoid losing work if they turn off autosaving.** Some systems let people turn off autosaving globally. In this scenario, show that a document has unsaved changes and present a save dialog when people choose to close the document, quit your app, log out, or restart.

**When autosaving is off, make sure people know when a document has unsaved changes.** To show that there are unsaved changes, display a dot on the document window’s close button and next to the document’s name in your app’s Window menu. When autosaving is on, showing a dot in these locations is confusing, because it implies that people need to take action to avoid losing their work. Regardless of autosave status, you can append “Edited” to the document’s title in the title bar, but be sure to remove this suffix as soon as autosave occurs or when people explicitly save their work.


---

## Going full screen

Phone, tablet and desktop offer full-screen modes that let people expand a window to fill the screen, hiding system controls and providing a distraction-free environment.


### Best practices

**Support full-screen mode when it makes sense for your experience.** People appreciate full-screen mode when they want to concentrate on a task or be immersed in content. Consider offering a full-screen mode if your experience lets people play a game; view media like videos or photo slideshows; or perform an in-depth task that benefits from a distraction-free environment.

**If necessary, adjust your layout in full-screen mode, but don’t programmatically resize your window.** When a window is larger in full-screen mode than in non-full-screen mode, you want to keep essential content prominent while making good use of the extra space. For example, it might make sense to adjust the proportions of your interface without changing which items appear. If you make such adjustments, be sure they’re subtle enough to maintain a consistent interface and avoid causing visually jarring transitions between modes.

**Continue to provide access to essential features and controls so people can complete their task without exiting full-screen mode.** For example, a full-screen media experience needs to make playback controls persistently available or easy to reveal when people need them.

**Except in games, let people reveal the dock while your tablet or desktop app is in full-screen mode.** On tablets and desktop, it’s important to preserve access to the dock so people can quickly open other apps and dock items. To help prevent people from accidentally revealing the dock while they’re playing your full-screen game, you can ask the system to ignore an initial swipe up from the screen’s bottom edge, or hide the dock/taskbar entirely on desktop.

**After people switch away from your full-screen experience, help them resume where they left off when they return.** For example, a game or a slideshow needs to pause automatically when people leave the experience so they don’t miss anything.

**Let people choose when to exit full-screen mode.** People generally don’t expect full-screen mode to end automatically when they switch to a different experience or finish an absorbing activity, like playing a game or viewing a movie.

**Prioritize content by temporarily hiding toolbars and navigation controls.** You can offer a distraction-free environment by hiding elements when content is the primary focus, such as when viewing full-screen photos or reading a document. If you implement such behavior, let people restore the hidden elements with a familiar gesture or action like tapping, swiping down, or moving the cursor to the top of the screen. Be sure to keep controls visible when they’re essential for navigation or performing tasks.


### Device-specific considerations

#### Phone & tablet
**Consider deferring system gestures to prevent accidental exits in a full-screen app or game.** By default, the home screen indicator automatically hides shortly after someone switches to your app or game. It reappears when someone interacts with the bottom portion of the screen, allowing them to swipe once to exit. Whenever possible, retain this behavior because it’s familiar and what people expect. If supporting this results in unexpected exits, you can enable two swipes rather than one to exit.


#### Desktop
**Use the system-provided full-screen experience.** Using the system’s full-screen support ensures that your full-screen window works well in all contexts. For example, some laptops include a camera notch that occupies an area at the top-center of the screen. Using the system’s full-screen support automatically accommodates this area.

**In a game, don’t change the display mode when players go full screen.** People expect to be in control of their display mode, and changing it automatically doesn’t improve performance.


**Always let people choose when to enter full-screen mode.** Prefer letting people use your window’s Enter Full Screen button, View menu item, or the standard full-screen shortcut (Ctrl-Cmd-F on Mac, F11 on Windows). Avoid offering a custom menu of window modes. In a game, you might also provide a custom toggle that turns full-screen mode on and off.


---

## Launching

A streamlined launch experience helps people start using your app or game immediately.

Launching begins when someone opens your app or game, includes an initial download, and ends when the first screen is ready. After launching completes, you might offer an onboarding experience, which can give people a high-level view of your app or game.


### Best practices

**Launch instantly.** People want to start interacting with your app or game right away, and sometimes they don’t want to wait more than a couple of seconds.

**If the platform requires it, provide a launch screen.** On phones and tablets, the system displays your launch screen the moment your app or game starts and quickly replaces it with your first screen, giving people the impression that your experience is fast and responsive. For guidance, see Launch screens.

**If you need a splash screen, consider displaying it at the beginning of your onboarding flow.** A splash screen is a beautiful graphic that succinctly communicates branding and other information you need to provide. If you don’t provide an onboarding experience, you might display your splash screen as soon as launching completes.

**Restore the previous state when your app restarts so people can continue where they left off.** Avoid making people retrace steps to reach their previous location in your app or game. Restore granular details of the previous state as much as possible. For example, scroll the view to people’s most recent position, and display windows in the same state and location in which people left them.


### Launch screens

*Not applicable for desktop.*

**Downplay the launch experience.** A launch screen isn’t part of an onboarding experience or a splash screen, and it isn’t an opportunity for artistic expression. A launch screen’s sole function is to enhance the perception of your experience as quick to launch and immediately ready to use.

**Design a launch screen that’s nearly identical to the first screen of your app or game.** If you include elements that look different when launching completes, people may experience an unpleasant flash between the launch screen and your first screen. If your app or game displays a solid color before transitioning to the first screen, create a launch screen that displays only that solid color. Also make sure that your launch screen matches the device’s current orientation and appearance mode.

**Avoid including text on your launch screen, even if your first screen displays text.** Because the content in a launch screen doesn’t change, any text you display won’t be localized.

**Don’t advertise.** The launch screen isn’t a branding opportunity. Avoid creating a screen that looks like a splash screen or an “About” window, and don’t include logos or other branding elements unless they’re a fixed part of your app’s first screen.


### Device-specific considerations

#### Phone & tablet
**Launch in the appropriate orientation.** If your app or game supports both portrait and landscape modes, launch using the device’s current orientation. If your interface only runs in one orientation, launch in that orientation and let people rotate the device if necessary. Ensure a landscape-only interface responds correctly, regardless of whether people enter landscape orientation by rotating the device left or right. For guidance, see Layout.


## Loading

The best content-loading experience finishes before people become aware of it.

If your app or game loads assets, levels, or other content, design the behavior so it doesn’t disrupt or negatively impact the user experience.


### Best practices

**Show something as soon as possible.** If you make people wait for loading to complete before displaying anything, they can interpret the lack of content as a problem with your app or game. Instead, consider showing placeholder text, graphics, or animations as content loads, replacing these elements as content becomes available.

**Let people do other things in your app or game while they wait for content to load.** Loading content in the background helps give people access to other actions. For example, a game could load content in the background while players learn about the next level or view an in-game menu.

**If loading takes an unavoidably long time, give people something interesting to view while they wait.** For example, you might provide gameplay hints, display tips, or introduce people to new features. Gauge the remaining loading time as accurately as possible to help you avoid giving people too little time to enjoy your placeholder content or having so much time that you need to repeat it.

**Improve installation and launch time by downloading large assets in the background.** Consider using the Background Assets framework to schedule asset downloads — like game level packs, 3D character models, and textures — to occur immediately after installation, during updates, or at other nondisruptive times.


### Showing progress

**Clearly communicate that content is loading and how long it might take to complete.** Ideally, content displays instantly, but for situations where loading takes more than a moment or two, you can use system-provided components — called *progress indicators* — to show that loading is ongoing. In general, you use a *determinate* progress indicator when you know how long loading will take, and you use an *indeterminate* progress indicator when you don’t. For guidance, see Progress indicators.

**For games, consider creating a custom loading view.** Standard progress indicators work well in most apps, but can sometimes feel out of place in a game. Consider designing a more engaging experience by using custom animations and elements that match the style of your game.


### Device-specific considerations

## Managing accounts

When it doesn’t create an unnecessary barrier to your experience, an account can be a convenient way for people to access their content and track personal details.

Ask people to create an account only if your core functionality requires it; otherwise, let people enjoy your app or game without one. If you require an account, consider offering federated sign-in (platform or major identity providers) and passkeys to give people a consistent sign-in experience they can trust and the convenience of not having to remember multiple accounts and authentication methods.


### Best practices

**Explain the benefits of creating an account and how to sign up.** If your app or game requires an account, write a brief, friendly description of the reasons for the requirement and its benefits. Display this message in your sign-in view.

**Delay sign-in for as long as possible.** People often abandon apps when they’re forced to sign in before they can do anything useful. To help avoid this situation, give people a chance to get a sense of what your app or game does before asking them to make a commitment to it. For example, a shopping app might let people browse as much as they want, requiring sign-in only when they’re ready to make a purchase.

**Prefer passkeys over passwords.** Passkeys simplify account creation and authentication, eliminating the need for people to create or enter passwords. When an app supports passkeys, people simply provide their user name when creating a new account or signing in to an existing one. If you need to continue using passwords for authentication, augment security by requiring two-factor authentication.

**Always identify the authentication method you offer.** For example, if you display a button for signing in to your app with face authentication, title it using a phrase like “Sign In with face authentication” instead of a generic phrase like “Sign In.”

**Refer only to authentication methods that are available in the current context.** For example, don’t reference face authentication on a device that doesn’t offer it. Check the device’s capabilities and use the appropriate terminology.

**In general, avoid offering an app-specific setting for opting in to biometric authentication.** People turn on biometric authentication at the system level, so presenting an in-app setting is redundant and could be confusing.

**Avoid using the term *passcode* to refer to account authentication.** People create a passcode to unlock their device or authenticate for platform services. If you use the term in your interface, people might think you’re asking them to reuse their passcode in your app or game.


### Deleting accounts

If you help people create an account within your app or game, you must also help them delete it, not just deactivate it. In addition to following the guidelines below, be sure to understand and comply with your region’s legal requirements related to account deletion and the right to be forgotten.

> **Important**: If legal requirements compel your app to maintain accounts or information — such as digital health records — or to follow a specific account-deletion process, clearly describe the situation so people can understand the information or accounts you must maintain and the process you must follow.

**Provide a clear way to initiate account deletion within your app or game.** If people can’t perform account deletion within your app, you must provide a direct link to the webpage on which people can do so. Make the link easy to discover — for example, don’t bury it in your Privacy Policy or Terms of Service pages.


**Provide a consistent account-deletion experience whether people perform it within your app or game or on the website.** For example, avoid making one version of the deletion flow longer or more complicated than the other.

**Consider letting people schedule account deletion to occur in the future.** People can appreciate the opportunity to use their remaining services or wait until their subscription auto-renews before deleting their account. If you offer a way to schedule account deletion, offer an option for immediate deletion as well.

**Tell people when account deletion will complete, and notify them when it’s finished.** Because it can sometimes take a while to fully delete an account, it’s essential to keep people informed about the status of the deletion process so they know what to expect.

**If you support in-app purchases, help people understand how billing and cancellation work when they delete their account.** For example, you might need to help people understand the following scenarios:

- Billing for an auto-renewable subscription continues through the app store until people cancel the subscription, regardless of whether they delete their account.

- After they delete their account, people need to cancel their subscription or request a refund.

In addition to helping people understand these scenarios, provide information that describes how to cancel subscriptions and manage purchases. For guidance, see Helping people manage their subscriptions and Providing help.

> **Note**: Even if people didn’t use your app to purchase the subscription, you still need to support account deletion.


### Device-specific considerations

## Managing notifications

Notifications can give people timely and important information, whether the device is locked or in use.

You need to get permission before sending any notification. The system lets people change this decision in settings, where they can also silence all notifications (except for government alerts in some locales).


### Integrating with Focus

People appreciate receiving a notification for something they care about, but they don’t always appreciate being interrupted. To help people manage the experience, the system lets them specify delivery times and set up a Focus.

- A Focus helps people filter notifications during a time period they reserve for an activity like sleeping, working, reading, or driving.

- Delivery scheduling lets people choose whether to receive notification alerts immediately or in a summary that’s delivered at times they choose.

People identify the contacts and apps that can break through a Focus to deliver notification alerts. In a Work Focus, for example, people might want to receive alerts from work colleagues, family members, and work-related apps as soon as notifications arrive. People might also want to receive all Time Sensitive notification alerts during a Focus. A *Time Sensitive* notification contains essential information people appreciate getting right away.

> **Important**: Even though a Focus might delay the delivery of a notification alert, the notification itself is available as soon as it arrives.

To support these behavior customizations, you first identify the types of notifications your app or game can send. If you support direct communications — like phone calls and messages — you use *communication* notifications; for all other types of tasks, you use *noncommunication* notifications. 

You need to specify a system-defined interruption level for each noncommunication notification you send. The system uses the interruption level to help determine when to deliver the alert; when a communication notification arrives, the system uses the sender to determine when to deliver the alert.

The system defines four interruption levels for noncommunication notifications:

- *Passive*. Information people can view at their leisure, like a restaurant recommendation.

- *Active* (the default). Information people might appreciate knowing about when it arrives, like a score update on their favorite sports team.

- *Time Sensitive*. Information that directly impacts the person and requires their immediate attention, like an account security issue or a package delivery.

- *Critical*. Urgent information about health and safety that directly impacts the person and demands their immediate attention. Critical notifications are extremely rare and typically come from governmental and public agencies or apps that help people manage their health or home.

Notification alerts in each system-defined interruption level can behave in the following ways:

| Interruption level | Overrides scheduled delivery | Breaks through Focus | Overrides silent mode |
| --- | --- | --- | --- |
| Passive | No | No | No |
| Active | No | No | No |
| Time Sensitive | Yes | Yes | No |
| Critical | Yes | Yes | Yes |


### Best practices

**Build trust by accurately representing the urgency of each notification.** People have several ways to adjust how they receive your notifications — including turning off all notifications — so it’s essential to be as realistic as possible when assigning an interruption level. You don’t want people to feel that a notification uses a high level of urgency to interrupt them with low-priority information.

**Use the Time Sensitive interruption level only for notifications that are relevant in the moment.** To help people understand the benefits of letting Time Sensitive notifications break through a Focus or scheduled delivery, make sure the notification is about an event that’s happening now or will happen within an hour. The first time a Time Sensitive notification arrives from your app, the system describes how such a notification works and gives people a way to turn it off if they don’t agree that the information requires their immediate attention. Going forward, the system periodically gives people additional opportunities to evaluate how your Time Sensitive notification is working for them.


### Sending marketing notifications

Don’t use notifications to send marketing or promotional content unless people explicitly agree to receive such information. When people want to learn about new features, content, or events related to your app or game, they can grant their permission to receive marketing notifications. For example, people who use a subscription app might appreciate getting an offer to become a subscriber, and game players might want to receive a special offer related to a live game event.

**Never use the Time Sensitive interruption level to send a marketing notification.** People may have agreed to receive marketing notifications from your app, but such a notification must never break through a Focus or scheduled delivery setting.

**Get people’s permission if you want to send them promotional or marketing notifications.** Before you send these notifications to people, you must receive their explicit permission to do so. Create an alert, modal view, or other interface that describes the types of information you want to send and gives people a clear way to opt in or out.

**Make sure people can manage their notification settings within your app.** In addition to requesting permission to send informational or marketing notifications, you must also provide an in-app settings screen that lets people change their choice. For guidance, see Settings.


### Device-specific considerations

## Modality

Modality is a design technique that presents content in a separate, dedicated mode that prevents interaction with the parent view and requires an explicit action to dismiss.

Presenting content modally can:

- Ensure that people receive critical information and, if necessary, act on it

- Provide options that let people confirm or modify their most recent action

- Help people perform a distinct, narrowly scoped task without losing track of their previous context

- Give people an immersive experience or help them concentrate on a complex task

Depending on the platform, you might use different components to present these types of modal experiences. For example, all platforms can present an *alert*, which is a modal view that delivers important information related to your app or game. In addition, each platform may define various types of modal views for presenting context-specific options, such as *activity views,* *sheets*, and *confirmation dialogs* or *action sheets*. To help people perform a distinct task, phone, tablet and desktop apps tend to use sheets or popovers, but tablet and desktop apps might also just use a separate window.

To provide a temporary experience, like viewing media, or to help people perform a distinct, multistep task, like editing content, apps can offer a full-screen modal experience. In contrast, apps may also offer nonmodal types of full-screen experiences; for guidance, see Going full screen.


### Best practices

**Present content modally only when there’s a clear benefit.** A modal experience takes people out of their current context and requires an action to dismiss, so it’s important to use modality only when it helps people focus or make choices that affect their content or device.

**Aim to keep modal tasks simple, short, and streamlined.** If a modal task is too complicated, people can lose track of the task they suspended when they entered the modal view, especially if the modal view obscures their previous context.

**Take care to avoid creating a modal experience that feels like an app within your app.** In particular, presenting a hierarchy of views within a modal task can make people forget how to retrace their steps. If a modal task must contain subviews, provide a single path through the hierarchy and avoid including buttons that people might mistake for the button that dismisses the modal view.

**Consider using a full-screen modal style for in-depth content or a complex task.** A modal experience that fills a window or the device display minimizes distractions, so it can work well for presenting videos, photos, or camera views, or to support a multistep task like marking up a document or editing a photo.

**Always give people an obvious way to dismiss a modal view.** In general, it works well to follow the platform conventions people already know. For example, in phone and tablet apps, people typically expect to find a button in the top toolbar or swipe down; in desktop apps, people expect to find a button in the main content view.

**When necessary, help people avoid data loss by getting confirmation before closing a modal view.** Regardless of whether people use a dismiss gesture or a button, if closing the view could result in the loss of user-generated content, be sure to explain the situation and give people ways to resolve it. For example, on phones, you might present an action sheet that includes a save option.

**Make it easy to identify a modal view’s task.** When people enter a modal view, they switch away from their previous context and might not return to it right away. When you provide a title that names the modal view’s task — or additional text that describes the task or provides guidance — you can help people keep their place in your app.

**Let people dismiss a modal view before presenting another one.** Allowing multiple modal views to be visible at the same time tends to create visual clutter and can make your app seem scattered and disorganized. People need to remember the context they were in before a modal view appears, so presenting multiple views adds to people’s cognitive load, especially when a modal view hides another one by appearing on top of it. Although an alert can appear on top of all other content — including other modal views — you never want to display more than one alert at the same time.


---

## Multitasking

Multitasking lets people switch quickly from one app to another, performing tasks in each.

People expect to use multitasking on their devices, and they may think something is wrong if your app doesn’t allow it.

In addition to app switching, multitasking can present different experiences on different devices; see Platform considerations.


### Best practices

A great multitasking experience helps people accomplish tasks in multiple apps by managing content in a variety of simultaneous contexts. Because you don’t know when people will initiate multitasking, your app or game always needs to be prepared to save and restore their context.

**Pause activities that require people’s attention or active participation when they switch away.** If your app is a game or a media-viewing app, for example, make sure people don’t miss anything when they switch to another app. When they switch back, let them continue as if they never left.

**Respond smoothly to audio interruptions.** Occasionally, audio from another app or the system itself may interrupt your app’s audio. For example, an incoming phone call or another app starting playback might interrupt your app’s audio. When situations like these occur, people expect your app to respond in the following ways:

- Pause audio indefinitely for primary audio interruptions, such as playing music, podcasts, or audiobooks.

- Temporarily lower the volume or pause the audio for shorter interruptions, such as GPS directional notifications, and resume the original volume or playback when the interruption ends.

For guidance, see Playing audio.

**Finish user-initiated tasks in the background.** When someone starts a task like downloading assets or processing a video file, they expect it to finish even if they switch away from your app. If your app is in the middle of performing a task that doesn’t need additional input, complete it in the background before suspending.

**Use notifications sparingly.** Your app can send notifications when it’s suspended or running in the background. If people start an important or time-sensitive task in your app, and then switch away from it, they might appreciate receiving a notification when the task completes so they can switch back to your app and take the next step. In contrast, people don’t generally need to know the moment a routine or secondary task completes. In this scenario, avoid sending an unnecessary notification; instead, let people check on the task when they return to your app. For guidance, see Managing notifications.


### Device-specific considerations

#### Phone
On phone, multitasking lets people use video calls or watch a video in picture-in-picture while they also use a different app.


#### Tablet
On tablet, people can view and interact with the windows of several different apps at the same time. An individual app can also support multiple open windows, which lets people view and interact with more than one window in the same app at one time.

People can use tablet with either full-screen or windowed apps. When full screen, apps occupy the full screen, and people can switch between individual app windows using the app switcher.

When using windowed apps, app windows are resizable, and people can arrange them to suit their needs with behavior similar to desktop. The system provides window controls for common tiling configurations, entering full screen, minimizing, and closing windows. The system identifies the frontmost window by coloring its window controls and casting a drop shadow on windows behind it. For guidance, see Windows.

Additionally, videos and video calls can also play in a picture-in-picture overlay above other content regardless of whether apps are full screen or windowed.

> **Note**: Apps don’t control multitasking configurations or receive any indication of the ones that people choose.

To help your app respond correctly when people open it while windowed, make sure it adapts gracefully to different screen sizes. For guidance, see Layout and Windows.


#### Desktop
On desktop, multitasking is the default experience because people typically run more than one app at a time, switching between windows and tasks as they work. When multiple app windows are open, desktop applies drop shadows that make the windows appear layered on the desktop, and applies other visual effects to help people distinguish different window states; for guidance, see Windows.


## Offering help

Although the most effective experiences are approachable and intuitive, you can provide contextual help when necessary.


### Best practices

**Let your app’s tasks inform the types of help people might need.** For example, you might help people perform simple, one- or two-step tasks by displaying an inline view that succinctly describes the task. In contrast, if your app or game supports complex or multistep tasks you might want to provide a tutorial that teaches people how to accomplish larger goals. In general, directly relate the help you provide to the precise action or task people are doing right now and make it easy for people to dismiss or avoid the help if they don’t need it.

**Use relevant and consistent language and images in your help content.** Always make sure guidance is appropriate for the current context. Also be sure the terms and descriptions you use are consistent with the platform. For example, don’t write copy that tells people to click a button on a phone or tap a menu item on a computer.

**Make sure all help content is inclusive.** For guidance, see Inclusion.

**Avoid bloating your help content by explaining how standard components or patterns work.** Instead, describe the specific action or task that a standard element performs in your app or game.


### Creating tips

A tip is a small, transient view that briefly describes how to use a feature in your app. Tips are a great way to teach people about new or less obvious features in your app, or help them discover faster ways to accomplish a task.

**Use the most appropriate tip type for your app’s user interface.** Display a popover tip when you want to preserve the content flow, or an inline tip when you want to ensure that surrounding information is visible. You can use an annotation-style inline tip when pointing to a specific UI element, or a hint-style tip when it’s not related to a specific piece of UI.

**Use tips for simple features.** Tips work best on features that are easy to describe and that people can complete with a few simple steps. If a feature requires more than three actions, it’s probably too complicated for a tip.

**Make tips short, actionable, and engaging.** A tip’s goal is to encourage people to try new features. Use direct, action-oriented language to describe what the feature does and explain how to use it. Keep your tips to one or two sentences and avoid including content that’s promotional or related to a different feature or user flow. Promotional content is anything that advertises, sells, or isn’t aligned with the current context of what the person is doing.

**Define rules to help ensure your tips reach the intended audience.** Not everyone benefits from every tip. For example, people who’ve already used a feature won’t appreciate viewing a tip that describes it. Use parameter-based or event-based eligibility rules to control when a tip appears, and only display a tip if someone might benefit from its use. When your app has more than one tip, set the display frequency so tips display at a reasonable cadence — for example, once every 24 hours.

**If there’s an image or symbol that people associate with the feature, consider including it in the tip, and prefer the filled variant.** For example, a tip with a star can help people understand that the tip is related to favorites.

If the feature is represented by an image that the tip connects to directly, avoid repeating the same image in both the tip and the UI.

**Use buttons to direct people to information or options.** If your feature has settings people can customize, or you want to redirect people to an area where they can learn more about a feature, consider adding a button. Buttons can take people directly to the settings where they make adjustments. Or if there’s more information people might find useful, add a button to take them to additional resources, such as a setup flow.


### Device-specific considerations

#### Desktop
A *tooltip* (called a *help tag* in user documentation) displays a small, transient view that briefly describes how to use a component in the interface.

**Describe only the control that people indicate interest in.** When people want to know how to use a specific control, they don’t want to learn how to use nearby controls or how to perform a larger task.

**Explain the action or task the control initiates.** It often works well to begin the description with a verb — for example, “Restore default settings” or “Add or remove a language from the list.”

**In general, avoid repeating a control’s name in its tooltip.** Repeating the name takes up space in the tooltip and rarely adds value to the description.

**Be brief.** As much as possible, limit tooltip content to a maximum of 60 to 75 characters (note that localization often changes the length of text). To make a description brief and direct, consider using a sentence fragment and omitting articles. If you need a lot of text to describe a control, consider simplifying your interface design.

**Use sentence case.** Sentence case tends to appear more casual and approachable. If you write complete sentences, omit ending punctuation unless it’s required to be consistent with your app’s style.

**Consider offering context-sensitive tooltips.** For example, you could provide different text for a control’s different states.


---

## Onboarding

Onboarding can help people get a quick start using your app or game.

Ideally, people can understand your app or game simply by experiencing it, but if onboarding is necessary, design a flow that’s fast, fun, and optional. When available, onboarding occurs after launching is complete — it isn’t part of the launch experience.


### Best practices

**Teach through interactivity.** People tend to grasp and retain information better when they can actually perform the task they’re learning about instead of just viewing instructional material. As much as possible, provide an interactive onboarding experience where people can safely test an action, discover a feature, or try out a game mechanic.

**Consider providing a collection of context-specific tips instead of a single onboarding flow.** Integrating contextually relevant tips into your experience can help people learn about their current task while they make progress in your app or game. A context-specific tip can also help people learn better because it lets them concentrate on a single action or task before encountering new information. When you have instructional content that refers to a specific area of the interface, display these instructions near that area.

**If you need to present a prerequisite onboarding flow, design a brief, enjoyable experience that doesn’t require people to memorize a lot of information.** When onboarding is quick and entertaining, people are more likely to complete it. In contrast, if you try to teach too much, people can feel overwhelmed and may be less likely to remember what they learned.

**If it makes sense to offer a separate tutorial, consider making it optional.** If you let people skip the tutorial when they first launch your app or game, don’t present it again on subsequent launches, but make sure it’s easy for people to find if they want to view it later. For example, you could make the tutorial available in a help, account, or settings area within your app or game.

**Keep onboarding content focused on the experience you provide.** People enter your onboarding flow to learn about your app or game; they don’t need to learn how to use the system or the device.


### Additional content

**Briefly display a splash screen if necessary.** If you need to include a splash screen, design a beautiful graphic that communicates succinctly. Aim to display your splash screen just long enough for people to absorb the information at a glance without feeling that it’s delaying their experience.

**Don’t let large downloads hinder onboarding.** People want to start using your app or game immediately after first launching it, whether they participate in an onboarding flow or skip it. Consider including enough media and other content in your software package to prevent people from having to wait for downloads to complete before they can start interacting with your app or game. For guidance, see Launching.

**Avoid displaying licensing details within your onboarding flow.** Let the app store display agreements and disclaimers so people can read them before downloading your app or game. If you must include these items within the onboarding flow, integrate them in a balanced way that doesn’t disrupt the experience.


### Additional requests

**Postpone nonessential setup flows or customization steps.** Provide reasonable default settings so most people can immediately start interacting with your app or game without performing additional configuration.

**If your app or game needs access to private data or resources before it can function, consider integrating the permission request into your onboarding flow.** In this scenario, making the request during your onboarding flow gives you the opportunity to show people why your app or game needs their permission and the benefits of granting it. Otherwise, present a permission request when people first access the specific function that relies on private data or resources. For guidance, see Requesting permission.

**Prefer letting people experience your app or game before prompting them for ratings or purchases.** People can be more likely to respond positively to such requests when they’ve had a chance to become engaged with your app or game.


---

## Playing audio

People expect rich audio experiences that automatically adjust when the context changes on the device.

Devices can play audio in a variety of ways, such as through internal or external speakers, headphones, and wirelessly through devices that use Bluetooth or casting. To manipulate sound on their devices people use several types of controls, including volume buttons, the silent-mode switch on phones, headphone controls, the system volume slider, and sound controls in third-party accessories. Whether sound is a primary part of your experience or an embellishment, you need to make sure it behaves as people expect as they make changes to volume and output.

**Silence.** People switch a device to silent when they want to avoid being interrupted by unexpected sounds like ringtones and incoming message tones. In this scenario, they also want to silence nonessential sounds, such as keyboard clicks, sound effects, game soundtracks, and other audible feedback. When a device is in silent mode, it plays only the audio that people explicitly initiate, like media playback, alarms, and audio/video messaging.

**Volume.** People expect their volume settings to affect all sound in the system — including music and in-app sound effects — regardless of the method they use to adjust the volume. An exception is the ringer volume on phone, which people can adjust separately in Settings.

**Headphones.** People use headphones to keep their listening private and in some cases to free their hands. When connecting headphones, people expect sound to reroute automatically without interruption; when disconnecting headphones, they expect playback to pause immediately.


### Best practices

**Adjust levels automatically when necessary — don’t adjust the overall volume.** Your app can adjust relative, independent volume levels to achieve a great mix of audio, but the system volume always governs the final output.

**Permit rerouting of audio when possible.** People often want to select a different audio output device. Support this capability unless there’s a compelling reason not to.


**Choose an audio category that fits the way your app or game uses sound.** Depending on the audio category you choose, your app’s sounds can mix with other audio, play while your app is in the background, or stop when people set the Ring/Silent switch to silent. As much as possible, pick a category that helps your app meet people’s expectations. For example, don’t make people stop listening to music from another app if you don’t need to.

| Category | Meaning | Behavior |
| --- | --- | --- |
| Solo ambient | Sound isn’t essential, but it silences other audio. For example, a game with a soundtrack. | Responds to the silence switch. Doesn’t mix with other sounds. Doesn’t play in the background. |
| Ambient | Sound isn’t essential, and it doesn’t silence other audio. For example, a game that lets people play music from another app during gameplay in place of the game’s soundtrack. | Responds to the silence switch. Mixes with other sounds. Doesn’t play in the background. |
| Playback | Sound is essential and might mix with other audio. For example, an audiobook or educational app that teaches a foreign language, which people might want to listen to after leaving the app. | Doesn’t respond to the silence switch. May or may not mix with other sounds. Can play in the background. |
| Record | Sound is recorded. For example, a note-taking app that offers an audio recording mode. An app of this nature might switch its category to playback if it lets people play the recorded notes. | Doesn’t respond to the silence switch. Doesn’t mix with other sounds. Can record in the background. |
| Play and record | Sound is recorded and played, potentially simultaneously. For example, an audio messaging or video calling app. | Doesn’t respond to the silence switch. May or may not mix with other sounds. Can record and play in the background. |

**Respond to audio controls only when it makes sense.** People can control audio playback from outside your app’s interface — such as in the system media controls or with controls on their headphones — regardless of whether your app is in the foreground or background. If your app is actively playing audio, in a clear audio-related context, or connected to a device that uses Bluetooth or casting, it’s fine to respond to audio controls. Otherwise, when people activate a control, avoid halting audio currently playing from another app.

**Avoid repurposing audio controls.** People expect audio controls to behave consistently in all apps, so it’s essential to avoid redefining the meaning of an audio control in your app. If your app doesn’t support certain controls, don’t respond to them.

**Consider creating custom audio player controls only if you need to offer commands that the system doesn’t support.** For example, you might want to define custom increments for skipping forward or backward, or present content that’s related to the playing audio, such as a sports score.

**Let other apps know when your app finishes playing temporary audio.** If your app can temporarily interrupt the audio of other apps, be sure to flag your audio session in a way that lets other apps know when they can resume.


### Handling interruptions

Although most apps and games rely on the system’s default interruption behavior, you can customize this behavior to better accommodate your needs.

**Determine how to respond to audio-session interruptions.** For example, if your app supports recording or other audio tasks people don’t want interrupted, ask the system not to interrupt for an incoming call unless people accept it. Never silently resume microphone capture after the system muted it (for example, when a tablet cover closes) — that invades people’s privacy. Inspect each interruption to choose the right response.

**When an interruption ends, determine whether to resume audio playback automatically.** Sometimes, audio from a different app can interrupt the audio your app is playing. An interruption can be *resumable*, like an incoming phone call, or *nonresumable*, like when people start a new music playlist. Use the interruption type and your app’s type to decide whether to resume playback automatically. For example, a media playback app that’s actively playing audio when an interruption occurs can check to be sure the type is resumable before continuing playback when the interruption ends. On the other hand, a game doesn’t need to check the interruption type before automatically resuming playback, because a game plays audio without an explicit user choice.


### Device-specific considerations


#### Phone & tablet
**Use the system’s sound services to play short sounds and vibrations.**


#### Desktop
On desktop, notification sounds mix with other audio by default.


## Playing video

People expect to enjoy rich video experiences on their devices, regardless of the app or game they’re using.

The system provides video players designed for you to use to embed playback experiences within your app or game on phones, tablets and desktop.

The system-provided video players support different aspect-ratio playback modes and in most platforms, picture-in-picture (PiP) viewing mode. Although people can switch modes during playback, by default, the system selects one of the following playback modes based on a video’s aspect ratio:

- In full-screen — or *aspect-fill* — mode, the video scales to fill the display, and some edge cropping may occur. This mode is the default for wide video (2:1 through 2.40:1).

- In fit-to-screen — or *aspect* — mode, the entire video is visible onscreen, and letterboxing or pillarboxing occurs as needed. This mode is the default for standard video (4:3, 16:9, and anything up to 2:1) and ultrawide video (anything above 2.40:1).

Below the transport controls, the video player displays *content tabs*, like Info, Episodes, or Chapters, that can provide supporting information and help streamline navigation.


### Best practices

**Use the system video player to give people a familiar and convenient experience.** The built-in video player provides an exceptional video playback experience that offers consistent interactions and behaviors that let people concentrate on enjoying immersive content. If your app truly requires a custom video player, reference the behavior and interface of the system video player to help you provide an experience that people can instantly understand. A custom experience that diverges slightly from the system-provided experience can cause frustration because people don’t know which of their habitual interactions they can continue to use.

**Always display video content at its original aspect ratio.** When video content uses embedded letterbox or pillarbox padding to conform to a specific aspect ratio, the system may be unable to correctly scale the video based on the current playback mode. Padding embedded within the video frame can cause videos to appear smaller in both full-screen and fit-to-screen modes. It also prevents videos from displaying correctly in edge-to-edge, non-full-screen contexts, like picture-in-picture on a tablet.

Embedded padding makes the video appear smaller than it should on wide phone screens.

**Create a thumbnail track if you want to support scrubbing.** Show thumbnails as people scrub so they can find the section they want; keep thumbnails small and at regular intervals for performance.

**Provide additional information when it adds value.** On phones and tablets, you can customize a video’s additional information by providing an image, title, description, and other useful information. In general, restrict this content so that it doesn’t obscure media playback.


**Avoid allowing audio from different sources to mix as viewers switch between modes.** Mixed audio is an unpleasant and frustrating user experience. In general, audio mixes when at least one of the audio sources fails to handle secondary audio correctly. In the full-screen window, the viewer starts a game that plays background music, then switches to the PiP window and unmutes the video. If the game doesn’t handle secondary audio appropriately, its audio mixes with the audio from the unmuted video.


### Integrating with a system media hub

Follow these guidelines so that handoff feels like an integrated part of your app.

**Ensure a smooth transition to your app.** The hub fades to black when transitioning to your app and doesn’t show your app’s launch screen. Maintain visual continuity with this transition by immediately presenting your own black screen before starting to play or resume content.

**Show the expected content immediately.** People expect the content they choose to begin playing as soon as the transition to your app completes, especially when resuming playback. Jump right from your app’s black screen into content, and avoid displaying splash screens, detail screens, intro animations, or any other barriers that make it take longer to reach content. In rare situations where you must display an interstitial element before the selected media plays, people can choose Select to step through the element, or choose Play if they want to skip the interstitial content and start playback.

**Avoid asking people if they want to resume playback.** If playback can be resumed, do so automatically without prompting for confirmation.

**Play or pause playback when people press Space on a connected Bluetooth keyboard.** Pressing Space to control media playback is an interaction people expect, regardless of the keyboard they’re using.

**Make sure content plays for the correct viewer.** If your app supports multiple user profiles, the hub can specify a profile when issuing a playback request. Make your app automatically switch to this profile before starting playback. If a playback request doesn’t specify a profile, ask the viewer to choose one before playback begins so this information is available in the future.

**Use the previous end time when resuming playback of a long video clip.** Resuming playback at the previous stopping point lets people quickly continue where they left off.


#### Loading content

**Avoid displaying loading screens when possible.** A loading screen is unnecessary if your content loads quickly, but if loading takes more than two seconds, consider showing a black loading screen with a centered activity spinner and no surrounding content.

**Start playback immediately.** If you must display a loading screen, display it only until enough content loads for playback to begin. Continue loading remaining content in the background.

**Minimize loading screen content.** If you include branding or images on your loading screen, do so minimally while maintaining the black background that helps provide a seamless transition to playback.


#### Exiting playback

After exiting playback, people remain in your app rather than returning to the hub, so it’s a good idea to help them avoid becoming disoriented.


**Be prepared for an immediate exit.** Prepare an exit view as soon as possible after receiving a playback notification so you’re ready to display the view if people exit immediately after playback begins.


### Device-specific considerations

## Printing

A phone, tablet or desktop app can integrate system-provided print functionality when it makes sense, presenting custom printer- and document-specific options if necessary.


### Best practices

**Make printing discoverable.** Help people find your print action by placing it in standard system locations. For example, include a Print item in your desktop app’s File menu; in your phone or tablet app, add a toolbar button that opens an action sheet. If your desktop app has a toolbar, you might want to put a Print button there, too, but consider making it an optional button that people can add when they customize the toolbar.

**Present a printing option only when it’s possible.** If there’s nothing onscreen to print, or no printers are available, dim the Print item in a desktop app’s File menu and remove the Print action from the share/action sheet in a phone or tablet app. If you implement a custom print button, dim or hide it when printing isn’t possible.

**Present relevant printing options.** If it makes sense to offer options like selecting a page range, requesting multiple copies, or printing on both sides — and the printer supports the options — use the system-provided view to present them.


### Device-specific considerations

#### Desktop
**If your desktop app offers app-specific print options that the system doesn’t offer, consider creating a custom category for the print panel.** By default, the print panel offers several categories of settings, such as Layout, Paper Handling, and Media & Quality. Give your custom category a unique name, such as your app name, and include options that help people have a great print experience in your app. For example, a presentation app offers presentation-specific options, like the ability to print presenter notes, slide backgrounds, and skipped slides.

**If your app supports document-specific page settings, consider presenting a page setup dialog.** A *page setup dialog* includes rarely changed settings for page size, orientation, and scaling that apply to printing a particular document. If this makes sense in your app, avoid implementing features the system already provides. For example, you don’t need to include options like changing the page orientation or printing in reverse order because the system implements these options.

**Make sure interdependencies between options are clear.** For example, if double-sided printing is available, an option to print on transparencies becomes unavailable.

**Separate advanced features from frequently used features.** Consider using a disclosure control to hide advanced options until they’re needed. Label advanced options as *Advanced Options*.

**Consider letting people preview the effect of a setting.** For example, you could update a thumbnail image to show the effect of changing a tone control.

**Consider storing modified settings with the document.** At minimum, it makes sense to store print settings until the document is closed in case people want to print it again.


---

## Ratings and reviews

People often view the ratings and reviews for an app or game before they download it.

Delivering a great overall experience is the best way to encourage positive ratings and reviews, but it’s also crucial to choose the right time to ask people for feedback. Although every app is different, some possible ways to do this involve looking at how many times or how frequently people launch your app, the number of features someone explores, or the number of tasks they complete.

People can always rate your app in the app store.


### Best practices

**Ask for a rating only after people have demonstrated engagement with your app or game.** For example, you might prompt people when they complete a game level or a significant task. Avoid asking for a rating on first launch or during onboarding, because people haven’t had enough time to gain a clear understanding of your app’s value or form an opinion. People may even be more likely to leave negative feedback if they feel an app is asking for a rating before they get a chance to use it.

**Avoid interrupting people while they’re performing a task or playing a game.** Asking for feedback can disrupt the user experience and feel like a burden. Look for natural breaks or stopping points in your app or game where a rating request is less likely to be bothersome.

**Avoid pestering people.** Repeated rating requests can be irritating, and may even negatively influence people’s opinion of your app. Consider allowing at least a week or two between requests, prompting again after people demonstrate additional engagement with your experience.

**Prefer the system-provided prompt.** Phones, tablets and desktop offer a consistent, nonintrusive way for apps and games to request ratings and reviews. When you identify places in your experience where it makes sense to ask for feedback, the system checks for previous feedback and — if there isn’t any — displays an in-app prompt that asks for a rating and an optional written review. People can supply feedback or dismiss the prompt with a single tap or click; they can also opt out of receiving these prompts for all apps they have installed. Systems typically cap how often the prompt appears (for example, three times per app per year).

**Weigh the benefits of resetting your summary rating against the potential disadvantage of showing fewer ratings.** When you release a new version of your app or game, you can reset the summary of individual ratings you received since the last reset. Although resetting means that the ratings reflect the current version, it also tends to result in having fewer ratings overall, which can discourage some people from downloading your app.


---

## Searching

People use various search techniques to find content on their device, within an app, and within a document or file.

To search for content within an app, people generally expect to use a search field. When it makes sense, you can personalize the search experience by using what you know about how people interact with your app. For example, you might display recent searches, search suggestions, completions, or corrections based on terms people searched earlier in your app.

In some cases, people appreciate the ability to scope a search or filter the results. For example, people might want to search for items by specifying attributes like creation date, file size, or file type. For guidance, see Scope bars and tokens. You can also help people find content within an open document or file by implementing ways to find content in a window or page in your phone, tablet or desktop app.



### Best practices

**If search is important, give it a primary position in your app or view.** For example, in a notes app, a search field can sit in the bottom toolbar alongside other important actions. In apps that use tab bars, like photo and streaming apps, search is often a dedicated tab.

**Aim to make your app’s content searchable through a single location.** People appreciate having one clearly identified location they can use to find anything they’re looking for in your app. For apps with clearly distinct sections, it may still be useful to offer a local search. For example, search acts as a filter on the current view when searching your songs and albums in a music app’s library.

**Clearly display the current scope of a search.** Use a descriptive placeholder text, a scope bar, or a title to help reinforce what someone is currently searching. For example, a mail app always shows a clear reference to the mailbox someone is searching.

**Provide suggestions to make searching easier.** When you display a personʼs recent searches before they start typing or offer predictive search suggestions while they’re typing, you can help people search faster and type less.

**Take privacy into consideration before displaying search history.** People might not appreciate having their search history appear where others might see it. If you do show search history, provide a way for people to clear it if they want.


---

## Settings

People expect apps and games to just work, but they also appreciate having ways to customize the experience to fit their needs.

On most platforms, the system-provided Settings app lets people adjust things like the overall appearance of the system, network connections, account details, accessibility requirements, and language and region settings. On some platforms, the system-provided Settings app can also include settings for specific apps and games, often letting people adjust whether the app or game can access location information, use device features like microphone or camera, and integrate with system features like notifications.

When necessary, you can provide a custom settings area within your app or game to offer general settings that affect your overall experience, like interface style or game-saving behavior. If you need to offer settings that affect only a specific task, you can provide these options within the task itself, so people don’t have to leave the experience to customize it.


### Best practices

**Aim to provide default settings that give the best experience to the largest number of people.** For example, you can automatically maximize performance for the device your game is running on instead of asking players to make this choice after your game launches. When you choose appropriate default settings, people may not have to make any adjustments before they can start enjoying your app or game.

**Minimize the number of settings you offer.** Although people appreciate having control over an app or game, too many settings can make the experience feel less approachable, while also making it hard to find a particular setting.

**Make settings available in ways people expect.** For example, when a physical keyboard is connected, people often use the standard Cmd/Ctrl-Comma (,) keyboard shortcut to open an app’s settings, whereas in a game, players often use the Esc (Escape) key.

**Avoid using settings to ask for setup information you can get in other ways.** For example, a game can automatically detect a connected controller or accessory instead of asking the player to identify it; an app can detect whether people are currently using Dark Mode.

**Respect people’s systemwide settings and avoid including redundant versions of them in your custom settings area.** People expect to use the system-provided Settings app to manage global options like accessibility accommodations, scrolling behavior, and authentication methods, and they expect all apps and games to adhere to their choices. Including custom versions of global options in your settings area is likely to confuse people because it implies that systemwide settings may not apply to your app or game and that changing your custom version of a global setting may affect other apps and games, too.


### General settings

**Put general, infrequently changed settings in your custom settings area.** People must suspend what they’re doing to open an app’s or game’s settings area, so you want to include options that people don’t need to change all the time. For example, an app might list options for adjusting window configuration; a game might let players specify game-saving behavior or keyboard mappings; both apps and games might offer options related to people’s accounts.


### Task-specific options

**When possible, prefer letting people modify task-specific options without going to your settings area.** For example, if people can adjust things like showing or hiding parts of the current view, reordering a collection of items, or filtering a list, make these options available in the screens they affect, where they’re discoverable and convenient. Putting this type of option in a separate settings area disconnects it from its context, requiring people to suspend their task to make adjustments, and often hiding the results until people resume the task.

> **Note**: In games, players tend to adjust their approach to a specific task as part of the gameplay, not as a settings option to change.


### Device-specific considerations

#### Desktop
When people choose the Settings item in your app’s or game’s App menu, your custom settings window opens. Typically, a custom settings window contains a toolbar that includes buttons for switching between views — called *panes* — that each contain a group of related settings.

**Include a settings item in the App menu.** Avoid adding settings buttons to a window’s toolbar, because doing so decreases the space available for essential commands that people use frequently. If you provide document-level options, add this item to your app’s File menu.

**Dim a settings window’s minimize and maximize buttons.** It’s quick to open a custom settings window using the standard Cmd/Ctrl–Comma (,) keyboard command, so there’s no need to keep the window in the dock, and because a settings window accommodates the size of the current pane, people don’t need to expand the window to see more.

**In your settings window, use a noncustomizable toolbar that remains visible and always indicates the active toolbar button.** A settings window’s toolbar identifies the areas people can customize and helps people navigate among those areas. People rely on a stable settings interface to help them find what they need.

**Update the window’s title to reflect the currently visible pane.** If your settings window doesn’t have multiple panes, use the title *App Name* Settings.

**Restore the most recently viewed pane.** People often adjust related settings more than once, so it can be convenient when a settings window opens to the last pane people used.


## Undo and redo

Undo and redo gives people easy ways to reverse many types of actions, which can also help people explore and experiment safely as they learn a new interface or task.

People expect undo and redo to let them reverse their recent actions, so they’re likely to try undoing — often multiple times — until something changes. In a situation like this, people might not remember which of their previous actions an undo is targeting, which can lead to unintended changes and frustration. To help people remain in control, it’s essential to help people predict the outcome of undoing and redoing and to highlight the results.


### Best practices

**Help people predict the results of undo and redo as much as possible.** On phone, for example, you can describe the result in the alert that displays when people shake the device, giving them the option of performing the undo or canceling it. If you provide undo and redo menu items, you can modify the menu item labels to identify the result. For example, a document-based app might use menu item labels like Undo Typing or Redo Bold.

**Show the results of an undo or redo.** Sometimes, the most recent action that people want to undo affects content or an area that’s no longer visible. In cases like this, it’s crucial to highlight the result of each undo and redo to keep people from thinking that the action had no effect, which can lead them to perform it repeatedly. For example, if people undo after deleting a paragraph in a document area that’s no longer onscreen, you might scroll the document to show the restored paragraph.

**Let people undo multiple times.** Avoid placing unnecessary limits on the number of times people can undo or redo. People generally expect to undo every action they’ve performed since taking a logical step like opening a document or saving their work.

**Consider giving people the option to revert multiple changes at once.** In some scenarios, people might appreciate the ability to undo a batch of discrete but related actions — like incremental adjustments to a single property or attribute — so they don’t have to undo each individual adjustment. In other cases, it can make sense to give people a convenient way to undo all the changes they made since opening a document or saving their work.

**Provide undo and redo buttons only when necessary.** People generally expect to initiate undo and redo in system-supported ways, such as choosing the items in a desktop app’s Edit menu, using keyboard shortcuts on a computer or tablet, or shaking their phone. If it’s important to provide dedicated undo and redo buttons in your app, use the standard system-provided symbols and put the buttons in a toolbar.


### Device-specific considerations

#### Phone & tablet
**Avoid redefining standard gestures for undo and redo.** For example, people can use a three-finger swipe to initiate an undo or redo, or shake their phone. As with all standard gestures, redefining them in your interface runs the risk of confusing people and making your experience unpredictable.

**Briefly and precisely describe the operation to be undone or redone.** The undo and redo alert title automatically includes a prefix of “Undo ” or “Redo ” (including the trailing space). You need to provide an additional word or two that describes what’s being undone or redone, to appear after this prefix. For example, you might create alert titles such as “Undo Name” or “Redo Address Change.”


#### Desktop
**Place undo and redo commands in the Edit menu and support the standard keyboard shortcuts.** Desktop users expect to find undo and redo at the top of the Edit menu; they also expect Cmd/Ctrl–Z for undo and Shift–Cmd–Z (Mac) or Ctrl–Y (Windows) for redo.


---

