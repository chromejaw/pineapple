# Components

Universal interface components, controls, and presentation structures.

---

## Charts

Organize data in a chart to communicate information with clarity and visual appeal.

An effective chart highlights a few key pieces of information in a dataset, helping people gain insights and make decisions. For example, people might use a chart to:

- Learn how upcoming weather conditions might affect their plans.

- Analyze stock prices to understand past performance and discover trends.

- Review fitness data to monitor their progress and set new goals.

To learn about designing charts to enhance your experience, see Charting data.


### Anatomy

A chart comprises several graphical elements that depict the values in a dataset and convey information about them.

A *mark* is a visual representation of a data value. You create a chart by supplying one or more series of data values, assigning each value to a mark. To specify the style of chart you want to display — such as bar chart, line chart, or scatter plot — you choose a mark type, such as bar, line, or point (for guidance, see Marks). The general task of depicting individual data values in a chart is called *plotting*, and the area that contains the marks is called the *plot area*.

To depict a value, each type of mark uses visual attributes that are determined by a scale, which maps data values like numbers, dates, or categories to visual characteristics like position, color, or height. For example, a bar mark can use a particular height to represent the magnitude of a value and a particular position to represent the time at which the value occurred.

To give people the context they need to interpret a chart’s visual characteristics, you supply descriptive content that can take a few different forms.

You can use an *axis* to help define a frame of reference for the data represented by a set of marks. Many charts display a pair of axes at the edges of the plot area — one horizontal and one vertical — where each axis represents a variable like time, amount, or category.

An axis can include *ticks*, which are reference points that help people visually locate the position of important values along the axis, such as a 0, 50%, and 100%. Many charts display *grid lines* that each extend from a tick across the plot area to help people visually estimate a data value when its mark isn’t near an axis.

You also have multiple ways to describe chart elements to help people interpret the data and to highlight the key information you want to communicate. For example, you can supply *labels* that name items like axes, grid lines, ticks, or marks, and *accessibility labels* that describe chart elements for people who use assistive technologies. To provide context and additional details, you can create descriptive titles, subtitles, and annotations. When needed, you can also create a legend, which describes chart properties that aren’t related to a mark’s position, such as the use of color or shape to denote different value categories.

Clear, accurate descriptions can help make a chart more approachable and accessible; to learn about additional ways to improve the accessibility of your chart, see Enhancing the accessibility of a chart.


### Marks

**Choose a mark type based on the information you want to communicate about the data.** Some of the most familiar mark types are bar, line, and point.

*Bar* marks work well in charts that help people compare values in different categories or view the relative proportions of various parts in a whole. When used to help people understand data that changes over time, bar charts work especially well when each value can represent a sum, like the total number of steps taken in a day.

*Line* marks can also show how values change over time. In a line chart, a line connects all data values in one series of data. The slope of the line reveals the magnitude of change between data values and can help people visualize overall trends.

*Point* marks help you depict individual data values as visually distinct marks. A set of point marks can show how two different properties of your data relate to each other, helping people inspect individual data values and identify outliers and clusters.

**Consider combining mark types when it adds clarity to your chart.** For example, if you use a line chart to show a change over time, you might want to add point marks on top of the line to highlight individual data points. By combining points with a line, you can help people understand the overall trend while also drawing their attention to individual values.


### Axes

**Use a fixed or dynamic axis range depending on the meaning of your chart.** In a *fixed* range, the upper and lower bounds of the axis never change, whereas in a *dynamic* range, the upper and lower bounds can vary with the current data. Consider using a fixed range when specific minimum and maximum values are meaningful for all possible data values. For example, people expect a chart that shows a battery’s current charge to have a minimum value of 0% (completely empty) and a maximum value of 100% (completely full).

In contrast, consider using a dynamic range when the possible data values can vary widely and you want the marks to fill the available plot area. For example, the upper bound of the Y axis range in the health app’s Steps chart varies so that the largest number of steps in a particular time period is close to the top of the chart.

**Define the value of the lower bound based on mark type and chart usage.** For example, bar charts can work well when you use zero for the lower bound of the Y axis, because doing so lets people visually compare the relative heights of individual bars to get a reasonable estimate of their values. In contrast, defining a lower bound of zero can sometimes make meaningful differences between values more difficult to discern. For example, a heart rate chart that always uses zero for the lower bound could obscure important differences between resting and active readings because the differences occur in a range that’s far from zero.

**Prefer familiar sequences of values in the tick and grid-line labels for an axis.** For example, if you use a common number sequence like 0, 5, 10, etc., people are likely to know at a glance that each tick value equals the previous value plus five. Even though a sequence like 1, 6, 11, etc., follows the same rule, it’s not common, so most people are likely to spend extra time thinking about the interval between values.

**Tailor the appearance of grid lines and labels to a chart’s use cases.** Too many grid lines can be visually overwhelming, distracting people from the data; too few grid lines can make it difficult to estimate a mark’s value. To help you determine the appropriate density and visual weight of these elements, consider a chart’s context in the interface, the interactions you support, and the tasks people can do in the chart. For example, if people can inspect individual data points by interacting with a chart, you might use fewer grid lines and light label colors to ensure the data remains visually prominent.


### Descriptive content

**Write descriptions that help people understand what a chart does before they view it.** When you provide information-rich titles and labels that describe the purpose and functionality of a chart, you give people the context they need before they dive in and examine the details. Providing context in this way is especially important for screen reader users and those with certain types of cognitive disabilities because they rely on your descriptions to understand the purpose and primary message of your chart before they decide to investigate it further.

**Summarize the main message of your chart to help make it approachable and useful for everyone.** Although a primary reason to use a chart is to display the data that supports the main message, it’s essential to summarize key information so that people can grasp it quickly. For example, a weather app provides a title and subtitle that succinctly describe the expected precipitation for the next hour, giving people the most important information without requiring them to examine the details of the chart.


### Best practices

**Establish a consistent visual hierarchy that helps communicate the relative importance of various chart elements.** Typically, you want the data itself to be most prominent, while letting the descriptions and axes provide additional context without competing with the data.

**In a compact environment, maximize the width of the plot area to give people enough space to comfortably examine a chart.** To help important data fit well in a given width, ensure that labels on a vertical axis are as short as possible without losing clarity. You might also consider describing units in other areas of the chart, such as in a title, and placing a longer axis label, such as a category name, inside the plot area when doing so doesn’t obscure important information.

**Make every chart in your app accessible.** Charts — like all infographics — need to be fully accessible to everyone, regardless of how they perceive content. For example, it’s essential to support the screen reader, which describes onscreen content to help people get information and navigate without needing to see the screen (to learn more about the screen reader, see Vision). In addition to supplying accessibility labels that describe the components of your chart, you can enhance the screen reader experience by also using audio graphs. Audio graphs provides chart information to the screen reader, which constructs a set of tones that audibly represent a chart’s data values and their trend; it also lets you present high-level text summaries that provide additional context. For guidance, see Enhancing the accessibility of a chart.

**Let people interact with the data when it makes sense, but don’t require interaction to reveal critical information.** In a stocks app, for example, people are often most interested in a stock’s performance over time, so the app displays a line graph that depicts performance during the time period people choose, such as one day, three months, or five years. If people want to explore additional details, they can drag a vertical indicator through the line graph, revealing the value at the selected time.

**Make it easy for everyone to interact with a chart.** Sometimes, chart marks are too small to target with a finger or a pointer, making your chart hard to use for people with reduced motor control and uncomfortable for everyone. When this is the case, consider expanding the hit target to include the entire plot area, letting people scrub across the area to reveal various values.

**Make an interactive chart easy to navigate when using keyboard commands (including full keyboard access) or Switch Control.** By default, these input types tend to visit individual onscreen elements in a linear sequence, such as the sequence of values in a data file. If you want to provide a custom navigation experience in your chart, here are two main ways to do so. The first way is to use accessibility APIs to specify a logical and predictable path through your chart’s information. For example, you might want to let people navigate along the X axis instead of jumping back and forth. The second way — which is particularly useful if you need to present a very large dataset — is to let people move focus among subsets of values instead of navigating through all individual data points. Note that both of these customizations can also enhance the screen reader experience, even when your chart isn’t interactive. For guidance, see Accessibility.

**Help people notice important changes in a chart.** For example, if people don’t notice when marks or axes change, they can misread a chart. Animating such changes can help people notice them, but you need to highlight the changes in other ways, too, to ensure that screen reader users and people who turn off animations know about them.

**Align a chart with surrounding interface elements.** For example, it often works well to align the leading edge of a chart with the leading edge of other views in a screen. One way to maintain a clean leading edge in a chart is to display the label for each vertical grid line on its trailing side. You might also consider shifting the Y axis to the trailing side of the chart so that its tick labels don’t protrude past the chart’s leading edge. If you end up with a label that doesn’t appear to be associated with anything, you can use a tick to anchor it to a grid line.


### Color

As in all other parts of your interface, using color in a chart can help you clarify information, evoke your brand, and provide visual continuity. For general guidance on using color in ways that everyone can appreciate, see Inclusive color.

**Avoid relying solely on color to differentiate between different pieces of data or communicate essential information in a chart.** Using meaningful color in a chart works well to highlight differences and elevate key details, but it’s crucial to include alternative ways to convey this information so that people can use your chart regardless of whether they can discern colors. One way to supplement color is to use different shapes or patterns to depict different parts of data. For example, in addition to using red and black or red and white colors, a health app uses two different shapes in the point marks that represent the two components of blood pressure.

**Aid comprehension by adding visual separation between contiguous areas of color.** For example, in a bar chart that stacks marks in a single row or column, it’s common to assign a different color to each mark. In this design, adding separators between the marks can help people distinguish individual ones.


### Enhancing the accessibility of a chart


If you don’t use audio graphs, you need to provide an overview of the chart’s structure and purpose. For example, you need to identify the chart’s type — such as bar or line — explain what each axis represents, and describe details like the upper and lower axis bounds.

> **Important**: Unlike an image — which requires one descriptive accessibility label — a chart often needs to offer an accessibility label for each important or interactive element. Depending on the purpose of your chart and the scope and density of its marks, you need to decide whether it’s essential to describe each mark or whether it improves the accessibility experience to describe groups of marks. In some cases, it can make sense to use a single accessibility label that provides a succinct, high-level description of the chart, such as when you use a small version of a chart in a button that reveals a more detailed version.

**Write accessibility labels that support the purpose of your chart.** For example, a maps app shows elevation for a cycling route using a chart that represents the change in elevation over the course of the route. The purpose of the chart is to give people a sense of the terrain for the entire route, not to provide individual elevations. For this reason, a maps app provides accessibility labels that summarize the elevation changes over a portion of the route, rather than providing labels for each individual moment. In contrast, a health app offers an accessibility label for each bar in the Steps chart, because the purpose of the chart is to give people their actual step count for each tracking period.

The following guidelines can help you write useful accessibility labels for chart elements.

- **Prioritize clarity and comprehensiveness.** In general, it’s rarely enough to merely report a data value unless you also include context that helps people understand it, like the date or location that’s associated with it. Aim to concisely describe the context for a value without repeating information that people can get in other ways, like an axis name that audio graphs or your overview provides. Follow context-setting information with a succinct description of the element’s details.

- **Avoid using subjective terms.** Subjective words — like rapidly, gradually, and almost — communicate your interpretation of the data. To help people form their own interpretations, use actual values in your descriptions.

- **Maximize clarity in data descriptions by avoiding potentially ambiguous formats and abbreviations.** For example, using “June 6” is clearer than using “6/6”; similarly, spelling out “60 minutes” or “60 meters” is clearer than using the abbreviation “60m.”

- **Describe what the chart’s details represent, not what they look like.** Consider a chart that uses red and blue colors to help people visually distinguish two different data series. It’s crucial to create accessibility labels that identify what each series represents, but describing the colors that visually represent them can add unnecessary information and be distracting.

- **Be consistent throughout your app when referring to a specific axis.** For example, if you always mention the X axis first, people can spend less time figuring out which axis is relevant in a description.

**Hide visible text labels for axes and ticks from assistive technologies.** Axis and tick labels help people visually assess trends in a chart and estimate mark values. The screen reader users can get mark values and trend information through accessibility labels and audio graphs, so they don’t generally need the content in the visible labels.


### Device-specific considerations

## Image views

An image view displays a single image — or in some cases, an animated sequence of images — on a transparent or opaque background.

Within an image view, you can stretch, scale, size to fit, or pin the image to a specific location. Image views are typically not interactive.


### Best practices

**Use an image view when the primary purpose of the view is simply to display an image.** In rare cases where you might want an image to be interactive, configure a system-provided button to display the image instead of adding button behaviors to an image view.

**If you want to display an icon in your interface, consider using a symbol or interface icon instead of an image view.** The symbol library provides a large library of streamlined, vector-based images that you can render with various colors and opacities. An icon (also called a glyph or template image) is typically a bitmap image in which the nontransparent pixels can receive color. Both symbols and interface icons can use the accent colors people choose.


### Content

An image view can contain rich image data in various formats, like PNG, JPEG, and PDF. For more guidance, see Images.

**Take care when overlaying text on images.** Compositing text on top of images can decrease both the clarity of the image and the legibility of the text. To help improve the results, ensure the text contrasts well with the image, and consider ways to make the text object stand out, like adding a text shadow or background layer.

**Aim to use a consistent size for all images in an animated sequence.** When you prescale images to fit the view, the system doesn’t have to perform any scaling. In cases where the system must do the scaling, performance is generally better when all images are the same size and shape.


### Device-specific considerations

#### Desktop
**If your app needs an editable image view, use an image well.** An image well is an image view that supports copying, pasting, dragging, and using the Delete key to clear its content.

**Use an image button instead of an image view to make a clickable image.** An image button contains an image or icon, appears in a view, and initiates an instantaneous app-specific action.


## Text views

A text view displays multiline, styled text content, which can optionally be editable.

Text views can be any height and allow scrolling when the content extends outside of the view. By default, content within a text view is aligned to the leading edge and uses the system label color. On phones and tablets, if a text view is editable, a keyboard appears when people select the view.


### Best practices

**Use a text view when you need to display text that’s long, editable, or in a special format.** Text views differ from text fields and labels in that they provide the most options for displaying specialized text and receiving text input. If you need to display a small amount of text, it’s simpler to use a label or — if the text is editable — a text field.

**Keep text legible.** Although you can use multiple fonts, colors, and alignments in creative ways, it’s essential to maintain the readability of your content. It’s a good idea to adopt dynamic text sizing so your text still looks good if people change text size on their device. Be sure to test your content with accessibility options turned on, such as bold text. For guidance, see Accessibility and Typography.

**Make useful text selectable.** If a text view contains useful information such as an error message, a serial number, or an IP address, consider letting people select and copy it for pasting elsewhere.


### Device-specific considerations

#### Phone & tablet
**Show the appropriate keyboard type.** Several different keyboard types are available, each designed to facilitate a different type of input. To streamline data entry, the keyboard you display when editing a text view needs to be appropriate for the type of content. For guidance, see Virtual keyboards.


## Web views

A web view loads and displays rich web content, such as embedded HTML and websites, directly within your app.

For example, a mail app uses a web view to show HTML content in messages.


### Best practices

**Support forward and back navigation when appropriate.** Web views support forward and back navigation, but this behavior isn’t available by default. If people are likely to use your web view to visit multiple pages, allow forward and back navigation, and provide corresponding controls to initiate these features.

**Avoid using a web view to build a web browser.** Using a web view to let people briefly access a website without leaving the context of your app is fine, but the browser is the primary way people browse the web. Attempting to replicate the functionality of the browser in your app is unnecessary and discouraged.


---

## Boxes

A box creates a visually distinct group of logically related information and components.

By default, a box uses a visible border or background color to separate its contents from the rest of the interface. A box can also include a title.


### Best practices

**Prefer keeping a box relatively small in comparison with its containing view.** As a box’s size gets close to the size of the containing window or screen, it becomes less effective at communicating the separation of grouped content, and it can crowd other content.

**Consider using padding and alignment to communicate additional grouping within a box.** A box’s border is a distinct visual element — adding nested boxes to define subgroups can make your interface feel busy and constrained.


### Content

**Provide a succinct introductory title if it helps clarify the box’s contents.** The appearance of a box helps people understand that its contents are related, but it might make sense to provide more detail about the relationship. Also, a title can help screen reader users predict the content they encounter within the box.

**If you need a title, write a brief phrase that describes the contents.** Use sentence-style capitalization. Avoid ending punctuation unless you use a box in a settings pane, where you append a colon to the title.


### Device-specific considerations

#### Phone & tablet
By default, phones and tablets use the secondary and tertiary background colors in boxes.


#### Desktop
By default, desktop displays a box’s title above it.


---

## Collections

A collection manages an ordered set of content and presents it in a customizable and highly visual layout.

Generally speaking, collections are ideal for showing image-based content.


### Best practices

**Use the standard row or grid layout whenever possible.** Collections display content by default in a horizontal row or a grid, which are simple, effective appearances that people expect. Avoid creating a custom layout that might confuse people or draw undue attention to itself.

**Consider using a table instead of a collection for text.** It’s generally simpler and more efficient to view and digest textual information when it’s displayed in a scrollable list.

**Make it easy to choose an item.** If it’s too difficult to get to an item in your collection, people will get frustrated and lose interest before reaching the content they want. Use adequate padding around images to keep focus or hover effects easy to see and prevent content from overlapping.

**Add custom interactions when necessary.** By default, people can tap to select, touch and hold to edit, and swipe to scroll. If your app requires it, you can add more gestures for performing custom actions.

**Consider using animations to provide feedback when people insert, delete, or reorder items.** Collections support standard animations for these actions, and you can also use custom animations.


### Device-specific considerations

#### Phone & tablet
**Use caution when making dynamic layout changes.** The layout of a collection can change dynamically. Be sure any changes make sense and are easy to track. If possible, try to avoid changing the layout while people are viewing and interacting with it, unless it’s in response to an explicit action.


---

## Column views

A column view — also called a *browser* — lets people view and navigate a data hierarchy using a series of vertical columns.

Each column represents one level of the hierarchy and contains horizontal rows of data items. Within a column, any parent item that contains nested child items is marked with a triangle icon. When people select a parent, the next column displays its children. People can continue navigating in this way until they reach an item with no children, and can also navigate back up the hierarchy to explore other branches of data.

> **Note**: If you need to manage the presentation of hierarchical content in your tablet app, consider using a split view.


### Best practices

Consider using a column view when you have a deep data hierarchy in which people tend to navigate back and forth frequently between levels, and you don’t need the sorting capabilities that a list or table provides. For example, the file manager offers a column view (in addition to icon, list, and gallery views) for navigating directory structures.

**Show the root level of your data hierarchy in the first column.** People know they can quickly scroll back to the first column to begin navigating the hierarchy from the top again.

**Consider showing information about the selected item when there are no nested items to display.** The file manager, for example, shows a preview of the selected item and information like the creation date, modification date, file type, and size.

**Let people resize columns.** This is especially important if the names of some data items are too long to fit within the default column width.


---

## Disclosure controls

Disclosure controls reveal and hide information and functionality related to specific controls or views.


### Best practices

**Use a disclosure control to hide details until they’re relevant.** Place controls that people are most likely to use at the top of the disclosure hierarchy so they’re always visible, with more advanced functionality hidden by default. This organization helps people quickly find the most essential information without overwhelming them with too many detailed options.


### Disclosure triangles

A disclosure triangle shows and hides information and functionality associated with a view or a list of items. For example, a presentation app uses a disclosure triangle to show advanced options when exporting a presentation, and the file manager uses disclosure triangles to progressively reveal hierarchy when navigating a folder structure in list view.

A disclosure triangle points inward from the leading edge when its content is hidden and down when its content is visible. Clicking or tapping the disclosure triangle switches between these two states, and the view expands or collapses accordingly to accommodate the content.

**Provide a descriptive label when using a disclosure triangle.** Make sure your labels indicate what is disclosed or hidden, like “Advanced Options.”


### Disclosure buttons

A disclosure button shows and hides functionality associated with a specific control. For example, the desktop Save sheet shows a disclosure button next to the Save As text field. When people click or tap this button, the Save dialog expands to give advanced navigation options for selecting an output location for their document.

A disclosure button points down when its content is hidden and up when its content is visible. Clicking or tapping the disclosure button switches between these two states, and the view expands or collapses accordingly to accommodate the content.

**Place a disclosure button near the content that it shows and hides.** Establish a clear relationship between the control and the expanded choices that appear when a person clicks or taps a button.

**Use no more than one disclosure button in a single view.** Multiple disclosure buttons add complexity and can be confusing.


### Device-specific considerations

#### Phone, tablet


---

## Labels

A label is a static piece of text that people can read and often copy, but not edit.

Labels display text throughout the interface, in buttons, menu items, and views, helping people understand the current context and what they can do next.

The term *label* refers to uneditable text that can appear in various places. For example:

- Within a button, a label generally conveys what the button does, such as Edit, Cancel, or Send.

- Within many lists, a label can describe each item, often accompanied by a symbol or an image.

- Within a view, a label might provide additional context by introducing a control or describing a common action or task that people can perform in the view.


The guidance below can help you use a label to display text.


### Best practices

**Use a label to display a small amount of text that people don’t need to edit.** If you need to let people edit a small amount of text, use a text field. If you need to display a large amount of text, and optionally let people edit it, use a text view.

**Prefer system fonts.** A label can display plain or styled text, and it supports dynamic text sizing (where available) by default. If you adjust the style of a label or use custom fonts, make sure the text remains legible.

**Use system-provided label colors to communicate relative importance.** The system defines four label colors that vary in appearance to help you give text different levels of visual importance. For additional guidance, see Color.

| System color | Example usage | phones and tablets | desktop |
| --- | --- | --- | --- |
| Label | Primary information | label | labelColor |
| Secondary label | A subheading or supplemental text | secondaryLabel | secondaryLabelColor |
| Tertiary label | Text that describes an unavailable item or behavior | tertiaryLabel | tertiaryLabelColor |
| Quaternary label | Watermark text | quaternaryLabel | quaternaryLabelColor |

**Make useful label text selectable.** If a label contains useful information — like an error message, a location, or an IP address — consider letting people select and copy it for pasting elsewhere.


### Device-specific considerations

#### Desktop


## Lists and tables

Lists and tables present data in one or more columns of rows.

A table or list can represent data that’s organized in groups or hierarchies, and it can support user interactions like selecting, adding, deleting, and reordering. Apps and games in all platforms can use tables to present content and options; many apps use lists to express an overall information hierarchy and help people navigate it. For example, phones Settings uses a hierarchy of lists to help people choose options, and several apps — such as a mail app on tablets and desktop — use a table within a split view.

Sometimes, people need to work with complex data in a multicolumn table or a spreadsheet. Apps that offer productivity tasks often use a table to represent various characteristics or attributes of the data in separate, sortable columns.


### Best practices

**Prefer displaying text in a list or table.** A table can include any type of content, but the row-based format is especially well suited to making text easy to scan and read. If you have items that vary widely in size — or you need to display a large number of images — consider using a collection instead.

**Let people edit a table when it makes sense.** People appreciate being able to reorder a list, even if they can’t add or remove items. On phones and tablets, people must enter an edit mode before they can select table items.

**Provide appropriate feedback when people select a list item.** The feedback can vary depending on whether selecting the item reveals a new view or toggles the item’s state. In general, a table that helps people navigate through a hierarchy persistently highlights the selected row to clarify the path people are taking. In contrast, a table that lists options often highlights a row only briefly before adding an image — such as a checkmark — indicating that the item is selected.


### Content

**Keep item text succinct so row content is comfortable to read.** Short, succinct text can help minimize truncation and wrapping, making text easier to read and scan. If each item consists of a large amount of text, consider alternatives that help you avoid displaying over-large table rows. For example, you could list item titles only, letting people choose an item to reveal its content in a detail view.

**Consider ways to preserve readability of text that might otherwise get clipped or truncated.** When a table is narrow — for example, if people can vary its width — you want content to remain recognizable and easy to read. Sometimes, an ellipsis in the middle of text can make an item easier to distinguish because it preserves both the beginning and the end of the content.

**Use descriptive column headings in a multicolumn table.** Use nouns or short noun phrases with title-style capitalization, and don’t add ending punctuation. If you don’t include a column heading in a single-column table view, use a label or a header to help people understand the context.


### Style

**Choose a table or list style that coordinates with your data and platform.** Some styles use visual details to help communicate grouping and hierarchy or to provide specific experiences.

**Choose a row style that fits the information you need to display.** For example, you might need to display a small image in the leading end of a row, followed by a brief explanatory label. Some platforms provide built-in row styles you can use to arrange content in list rows — use them to lay out content in rows, headers, and footers consistently.


### Device-specific considerations


#### Phone, tablet
**Use an info button only to reveal more information about a row’s content.** An info button — called a *detail disclosure button* when it appears in a list row — doesn’t support navigation through a hierarchical table or list. If you need to let people drill into a list or table row’s subviews, use a disclosure indicator accessory control.

**Avoid adding an index to a table that displays controls — like disclosure indicators — in the trailing ends of its rows.** An *index* typically consists of the letters in an alphabet, displayed vertically at the trailing side of a list. People can jump to a specific section in the list by choosing the index letter that maps to it. Because both the index and elements like disclosure indicators appear on the trailing side of a list, it can be difficult for people to use one element without activating the other.


#### Desktop
**When it provides value, let people click a column heading to sort a table view based on that column**. If people click the heading of a column that’s already sorted, re-sort the data in the opposite direction.

**Let people resize columns.** Data displayed in a table view often varies in width. People appreciate resizing columns to help them concentrate on different areas or reveal clipped data.

**Consider using alternating row colors in a multicolumn table.** Alternating colors can help people track row values across columns, especially in a wide table.

**Use an outline view instead of a table view to present hierarchical data.** An outline view looks like a table view, but includes disclosure triangles for exposing nested levels of data. For example, an outline view might display folders and the items they contain.


## Outline views

An outline view presents hierarchical data in a scrolling list of cells that are organized into columns and rows.

An outline view includes at least one column that contains primary hierarchical data, such as a set of parent containers and their children. You can add columns, as needed, to display attributes that supplement the primary data; for example, sizes and modification dates. Parent containers have disclosure triangles that expand to reveal their children.

The file manager windows offer an outline view for navigating the file system.


### Best practices

Outline views work well to display text-based content and often appear in the leading side of a split view, with related content on the opposite side.

**Use a table instead of an outline view to present data that’s not hierarchical.** For guidance, see Lists and tables.

**Expose data hierarchy in the first column only.** Other columns can display attributes that apply to the hierarchical data in the primary column.

**Use descriptive column headings to provide context.** Use nouns or short noun phrases with title-style capitalization and no punctuation; in particular, avoid adding a trailing colon. Always provide column headings in a multi-column outline view. If you don’t include a column heading in a single-column outline view, use a label or other means to make sure there’s enough context.

**Consider letting people click column headings to sort an outline view.** In a sortable outline view, people can click a column heading to perform an ascending or descending sort based on that column. You can implement additional sorting based on secondary columns behind the scenes, if necessary. If people click the primary column heading, sorting occurs at each hierarchy level. For example, in the file manager, all top-level folders are sorted, then the items within each folder are sorted. If people click the heading of a column that’s already sorted, the folders and their contents are sorted again in the opposite direction.

**Let people resize columns.** Data displayed in an outline view often varies in width. It’s important to let people adjust column width as needed to reveal data that’s wider than the column.

**Make it easy for people to expand or collapse nested containers.** For example, clicking a disclosure triangle for a folder in a file manager window expands only that folder. However, Option/Alt-clicking the disclosure triangle expands all of its subfolders.

**Retain people’s expansion choices.** If people expand various levels of an outline view to reach a specific item, store the state so you can display it again the next time. This way, people won’t need to navigate back to the same place again.

**Consider using alternating row colors in multi-column outline views.** Alternating colors can make it easier for people to track row values across columns, especially in wide outline views.

**Let people edit data if it makes sense in your app.** In an editable outline view cell, people expect to be able to single-click a cell to edit its contents. Note that a cell can respond differently to a double click. For example, an outline view listing files might let people single-click a file’s name to edit it, but double-click a file’s name to open the file. You can also let people reorder, add, and remove rows if it would be useful.

**Consider using a centered ellipsis to truncate cell text instead of clipping it.** An ellipsis in the middle preserves the beginning and end of the cell text, which can make the content more distinct and recognizable than clipped text.

**Consider offering a search field to help people find values quickly in a lengthy outline view.** Windows with an outline view as the primary feature often include a search field in the toolbar. For guidance, see Search fields.


---

## Split views

A split view manages the presentation of multiple adjacent panes of content, each of which can contain a variety of components, including tables, collections, images, and custom views.

Typically, you use a split view to show multiple levels of your app’s hierarchy at once and support navigation between them. In this scenario, selecting an item in the view’s primary pane displays the item’s contents in the secondary pane. Similarly, a split view can display a tertiary pane if items in the secondary pane contain additional content.

It’s common to use a split view to display a sidebar for navigation, where the leading pane lists the top-level items or collections in an app, and the secondary and optional tertiary panes can present child collections and item details. Rarely, you might also use a split view to provide groups of functionality that supplement the primary view — for example, a presentation app on desktop uses split view panes to present the slide navigator, the presenter notes, and the inspector pane in areas that surround the main slide canvas.


### Best practices

**To support navigation, persistently highlight the current selection in each pane that leads to the detail view.** The selected appearance clarifies the relationship between the content in various panes and helps people stay oriented.

**Consider letting people drag and drop content between panes.** Because a split view provides access to multiple levels of hierarchy, people can conveniently move content from one part of your app to another by dragging items to different panes. For guidance, see Drag and drop.


### Device-specific considerations


#### Phone
**Prefer using a split view in a regular — not a compact — environment.** A split view needs horizontal space in which to display multiple panes. In a compact environment, such as phone in portrait orientation, it’s difficult to display multiple panes without wrapping or truncating the content, making it less legible and harder to interact with.


#### Tablet
On tablets, a split view can include either two vertical panes, like a mail app, or three vertical panes, like a presentation app.

**Account for narrow, compact, and intermediate window widths.** Since tablet windows are fluidly resizable, it’s important to consider the design of a split view layout at multiple widths. In particular, ensure that it’s possible to navigate between the various panes in a logical way. For guidance, see Layout.


#### Desktop
On desktop, you can arrange the panes of a split view vertically, horizontally, or both. A split view includes dividers between panes that can support dragging to resize them.

**Set reasonable defaults for minimum and maximum pane sizes.** If people can resize the panes in your app’s split view, make sure to use sizes that keep the divider visible. If a pane gets too small, the divider can seem to disappear, becoming difficult to use.

**Consider letting people hide a pane when it makes sense.** If your app includes an editing area, for example, consider letting people hide other panes to reduce distractions or allow more room for editing — in a presentation app, people can hide the navigator and presenter notes panes when they want to edit slide content.

**Provide multiple ways to reveal hidden panes.** For example, you might provide a toolbar button or a menu command — including a keyboard shortcut — that people can use to restore a hidden pane.

**Prefer the thin divider style.** The thin divider measures one point in width, giving you maximum space for content while remaining easy for people to use. Avoid using thicker divider styles unless you have a specific need. For example, if both sides of a divider present table rows that use strong linear elements that might make a thin divider hard to distinguish, it might work to use a thicker divider.


## Tab views

A tab view presents multiple mutually exclusive panes of content in the same area, which people can switch between using a tabbed control.


### Best practices

**Use a tab view to present closely related areas of content.** The appearance of a tab view provides a strong visual indication of enclosure. People expect each tab to display content that is in some way similar or related to the content in the other tabs.

**Make sure the controls within a pane affect content only in the same pane.** Panes are mutually exclusive, so ensure they’re fully self-contained.

**Provide a label for each tab that describes the contents of its pane.** A good label helps people predict the contents of a pane before clicking or tapping its tab. In general, use nouns or short noun phrases for tab labels. A verb or short verb phrase may make sense in some contexts. Use title-style capitalization for tab labels.

**Avoid using a pop-up button to switch between tabs.** A tabbed control is efficient because it requires a single click or tap to make a selection, whereas a pop-up button requires two. A tabbed control also presents all choices onscreen at the same time, whereas people must click a pop-up button to see its choices. Note that a pop-up button can be a reasonable alternative in cases where there are too many panes of content to reasonably display with tabs.

**Avoid providing more than six tabs in a tab view.** Having more than six tabs can be overwhelming and create layout issues. If you need to present six or more tabs, consider another way to implement the interface. For example, you could instead present each tab as a view option in a pop-up button menu.


### Anatomy

The tabbed control appears on the top edge of the content area. You can choose to hide the control, which is appropriate for an app that switches between panes programmatically.

When you hide the tabbed control, the content area can be borderless, bezeled, or bordered with a line. A borderless view can be solid or transparent.

**In general, inset a tab view by leaving a margin of window-body area on all sides of a tab view.** This layout looks clean and leaves room for additional controls that aren’t directly related to the contents of the tab view. You can extend a tab view to meet the window edges, but this layout is unusual.


### Device-specific considerations

#### Phone & tablet
For similar functionality, consider using a segmented control instead.


## Activity views

An activity view — often called a *share sheet* — presents a range of tasks that people can perform in the current context.

Activity views present sharing activities like messaging and actions like Copy and Print, in addition to quick access to frequently used apps. An activity view can appear as a sheet or a popover, depending on the device and orientation.

You can provide app-specific activities that can appear in a share sheet when people open it within your app or game. For example, a photos app provides app-specific actions like Copy Photo, Add to Album, and Adjust Location. By default, the system lists app-specific actions before actions — such as Add to a files app or casting — that are available in multiple apps or throughout the system. People can edit the list of actions to ensure that it displays the ones they use most and to add new ones.


### Best practices

**Avoid creating duplicate versions of common actions that are already available in the activity view.** For example, providing a duplicate Print action is unnecessary and confusing because people wouldn’t know how to distinguish your action from the system-provided one. If you need to provide app-specific functionality that’s similar to an existing action, give it a custom title. For example, if you let people use custom formatting to print a bank transaction, use a title that helps people understand what your print activity does, like “Print Transaction.”

**Consider using a symbol to represent your custom activity.** The symbol library provides a comprehensive set of configurable symbols you can use to communicate items and concepts in an activity view. If you need to create a custom interface icon, center it in an area measuring about 70x70 pixels. For guidance, see Icons.

**Write a succinct, descriptive title for each custom action you provide.** If a title is too long, the system wraps it and may truncate it. Prefer a single verb or a brief verb phrase that clearly communicates what the action does. Avoid including your company or product name in an action title. In contrast, the share sheet displays the title of a share activity — typically a company name — below the icon that represents it.

**Make sure activities are appropriate for the current context.** Although you can’t reorder system-provided tasks in an activity view, you can exclude tasks that aren’t applicable to your app. For example, if it doesn’t make sense to print from within your app, you can exclude the Print activity. You can also identify which custom tasks to show at any given time.

**Use the Share button to display an activity view.** People are accustomed to accessing system-provided activities when they choose the Share button. Avoid confusing people by providing an alternative way to do the same thing.


### Share and action extensions

Share extensions give people a convenient way to share information from the current context with apps, social media accounts, and other services. Action extensions let people initiate content-specific tasks — like adding a bookmark, copying a link, editing an inline image, or displaying selected text in another language — without leaving the current context.

The system presents share and action extensions differently depending on the platform:

- On phones and tablets, share and action extensions are displayed in the share sheet that appears when people tap a Share button.

- On desktop, people access share extensions by clicking a Share button in the toolbar or choosing Share in a context menu. People can access an action extension by holding the pointer over certain types of embedded content — like an image they add to a mail app compose window — clicking a toolbar button, or choosing a quick action in a file manager window.

**If necessary, create a custom interface that feels familiar to people.** For a share extension, prefer the system-provided composition view because it provides a consistent sharing experience that people already know. For an action extension, include your app name. If you need to present an interface, include elements of your app’s interface to help people understand that your extension and your app are related.

**Streamline and limit interaction.** People appreciate extensions that let them perform a task in just a few steps. For example, a share extension might immediately post an image to a social media account with a single tap or click.

**Avoid placing a modal view above your extension.** By default, the system displays an extension within a modal view. While it might be necessary to display an alert above an extension, avoid displaying additional modal views.

**If necessary, provide an image that communicates the purpose of your extension.** A share extension automatically uses your app icon, helping give people confidence that your app provided the extension. For an action extension, prefer using a symbol or creating an interface icon that clearly identifies the task.

**Use your main app to denote the progress of a lengthy operation.** An activity view dismisses immediately after people complete the task in your share or action extension. If a task is time-consuming, continue it in the background, and give people a way to check the status in your main app. Although you can use a notification to tell people about a problem, don’t notify them simply because the task completes.


---

## Buttons

A button initiates an instantaneous action.

Versatile and highly customizable, buttons give people simple, familiar ways to do tasks in your app. In general, a button combines three attributes to clearly communicate its function:

- **Style.** A visual style based on size, color, and shape.

- **Content.** A symbol (or icon), text label, or both that a button displays to convey its purpose.

- **Role.** A system-defined role that identifies a button’s semantic meaning and can affect its appearance.

There are also many button-like components that have distinct appearances and behaviors for specific use cases, like toggles, pop-up buttons, and segmented controls.


### Best practices

When buttons are instantly recognizable and easy to understand, an app tends to feel intuitive and well designed.

**Make buttons easy for people to use.** It’s essential to include enough space around a button so that people can visually distinguish it from surrounding components and content. Giving a button enough space is also critical for helping people select or activate it, regardless of the method of input they use.

**Always include a press state for a custom button.** Without a press state, a button can feel unresponsive, making people wonder if it’s accepting their input.


### Style

System buttons offer a range of styles that support customization while providing built-in interaction states, accessibility support, and appearance adaptation. Different platforms define different styles that help you communicate hierarchies of actions in your app.

**In general, use a button that has a prominent visual style for the most likely action in a view.** To draw people’s attention to a specific button, use a prominent button style so the system can apply an accent color to the button’s background. Buttons that use color tend to be the most visually distinctive, helping people quickly identify the actions they’re most likely to use. Keep the number of prominent buttons to one or two per view. Presenting too many prominent buttons increases cognitive load, requiring people to spend more time considering options before making a choice.

**Use style — not size — to visually distinguish the preferred choice among multiple options.** When you use buttons of the same size to offer two or more options, you signal that the options form a coherent set of choices. By contrast, placing two buttons of different sizes near each other can make the interface look confusing and inconsistent. If you want to highlight the preferred or most likely option in a set, use a more prominent button style for that option and a less prominent style for the remaining ones.

**Avoid applying a similar color to button labels and content layer backgrounds.** If your app already has bright, colorful content in the content layer, prefer using the default monochromatic appearance of button labels. For more guidance, see glass color.


### Content

**Ensure that each button clearly communicates its purpose.** Depending on the platform, a button can contain a symbol (or icon), a text label, or both to help people understand what it does.

> **Note**: On desktop, the system displays a tooltip after people hover over a button for a moment. A tooltip displays a brief phrase that explains what a button does; for guidance, see Offering help.

**Try to associate familiar actions with familiar icons.** For example, people can predict that a button containing the square.and.arrow.up symbol will help them perform share-related activities. If it makes sense to use an icon in your button, consider using an existing or customized symbol. For a list of symbols that represent common actions, see Standard icons.

**Consider using text when a short label communicates more clearly than an icon.** To use text, write a few words that succinctly describe what the button does. Using title-style capitalization, consider starting the label with a verb to help convey the button’s action — for example, a button that lets people add items to their shopping cart might use the label “Add to Cart.”


### Role

A system button can have one of the following roles:

- **Normal.** No specific meaning.

- **Primary.** The button is the default button — the button people are most likely to choose.

- **Cancel.** The button cancels the current action.

- **Destructive.** The button performs an action that can result in data destruction.

A button’s role can have additional effects on its appearance. For example, a primary button uses an app’s accent color, whereas a destructive button uses the system red color.

**Assign the primary role to the button people are most likely to choose.** When a primary button responds to the Return key, it makes it easy for people to quickly confirm their choice. In addition, when the button is in a temporary view — like a sheet, an editable view, or an alert — assigning it the primary role means that the view can automatically close when people press Return.

**Don’t assign the primary role to a button that performs a destructive action, even if that action is the most likely choice.** Because of its visual prominence, people sometimes choose a primary button without reading it first. Help people avoid losing content by assigning the primary role to nondestructive buttons.


### Device-specific considerations

#### Phone & tablet
**Configure a button to display an activity indicator when you need to provide feedback about an action that doesn’t instantly complete.** Displaying an activity indicator within a button can save space in your user interface while clearly communicating the reason for the delay. To help clarify what’s happening, you can also configure the button to display a different label alongside the activity indicator. For example, the label “Checkout” could change to “Checking out…” while the activity indicator is visible. When a delay occurs after people click or tap your configured button, the system displays the activity indicator next to the original or alternative label, hiding the button image, if there is one.


#### Desktop
Several specific button types are unique to desktop.


##### Push buttons

The standard button type on desktop is known as a *push button*. You can configure a push button to display text, a symbol, an icon, or an image, or a combination of text and image content. Push buttons can act as the default button in a view and you can tint them.

**Use a flexible-height push button only when you need to display tall or variable height content.** Flexible-height buttons support the same configurations as regular push buttons — and they use the same corner radius and content padding — so they look consistent with other buttons in your interface. If you need to present a button that contains two lines of text or a tall icon, use a flexible-height button; otherwise, use a standard push button.

**Append a trailing ellipsis to the title when a push button opens another window, view, or app.** Throughout the system, an ellipsis in a control title signals that people can provide additional input. For example, the Edit buttons in the AutoFill pane of the browser Settings include ellipses because they open other views that let people modify autofill values.

**Consider supporting spring loading.** On systems with a trackpad, *spring loading* lets people activate a button by dragging selected items over it and force clicking — that is, pressing harder — without dropping the selected items. After force clicking, people can continue dragging the items, possibly to perform additional actions.


##### Square buttons

A *square button* (also known as a *gradient button*) initiates an action related to a view, like adding or removing rows in a table.

Square buttons contain symbols or icons — not text — and you can configure them to behave like push buttons, toggles, or pop-up buttons. The buttons appear in close proximity to their associated view — usually within or beneath it — so people know which view the buttons affect.

**Use square buttons in a view, not in the window frame.** Square buttons aren’t intended for use in toolbars or status bars. If you need a button in a toolbar, use a toolbar item.

**Prefer using a symbol in a square button.** The symbol library provides a wide range of symbols that automatically receive appropriate coloring in their default state and in response to user interaction.

**Avoid using labels to introduce square buttons.** Because square buttons are closely connected with a specific view, their purpose is generally clear without the need for descriptive text.


##### Help buttons

A *help button* appears within a view and opens app-specific help documentation.

Help buttons are circular, consistently sized buttons that contain a question mark. For guidance on creating help documentation, see Offering help.

**Use the system-provided help button to display your help documentation.** People are familiar with the appearance of the standard help button and know that choosing it opens help content.

**When possible, open the help topic that’s related to the current context.** For example, the help button in the Rules pane of a mail app settings opens the mail app User Guide to a help topic that explains how to change these settings. If no specific help topic applies directly to the current context, open the top level of your app’s help documentation when people choose a help button.

**Include no more than one help button per window.** Multiple help buttons in the same context make it hard for people to predict the result of clicking one.

**Position help buttons where people expect to find them.** Use the following locations for guidance.

| View style | Help button location |
| --- | --- |
| Dialog with dismissal buttons (like OK and Cancel) | Lower corner, opposite to the dismissal buttons and vertically aligned with them |
| Dialog without dismissal buttons | Lower-left or lower-right corner |
| Settings window or pane | Lower-left or lower-right corner |

**Use a help button within a view, not in the window frame.** For example, avoid placing a help button in a toolbar or status bar.

**Avoid displaying text that introduces a help button.** People know what a help button does, so they don’t need additional descriptive text.


##### Image buttons

An *image button* appears in a view and displays an image, symbol, or icon. You can configure an image button to behave like a push button, toggle, or pop-up button.

**Use an image button in a view, not in the window frame.** For example, avoid placing an image button in a toolbar or status bar. If you need to use an image as a button in a toolbar, use a toolbar item. See Toolbars.

**Include about 10 pixels of padding between the edges of the image and the button edges.** An image button’s edges define its clickable area even when they aren’t visible. Including padding ensures that a click registers correctly even if it’s not precisely within the image. In general, avoid including a system-provided border in an image button.

**If you need to include a label, position it below the image button.** For related guidance, see Labels.


## Context menus

A context menu provides access to functionality that’s directly related to an item, without cluttering the interface.

Although a context menu provides convenient access to frequently used items, it’s hidden by default, so people might not know it’s there. To reveal a context menu, people generally choose a view or select some content and then perform an action, using the input modes their current configuration supports. For example:


- Pressing the Control key while clicking a pointing device on desktop and tablets

- Using a secondary click on a trackpad on desktop or tablets


### Best practices

**Prioritize relevancy when choosing items to include in a context menu.** A context menu isn’t for providing advanced or rarely used items; instead, it helps people quickly access the commands they’re most likely to need in their current context. For example, the context menu for a mail app message in the Inbox includes commands for replying and moving the message, but not commands for editing message content, managing mailboxes, or filtering messages.

**Aim for a small number of menu items.** A context menu that’s too long can be difficult to scan and scroll.

**Support context menus consistently throughout your app.** If you provide context menus for items in some places but not in others, people won’t know where they can use the feature and may think there’s a problem.

**Always make context menu items available in the main interface, too.** For example, in a mail app on phones and tablets, the context menu items that are available for a message in the Inbox are also available in the toolbar of the message view. On desktop, an app’s menu bar menus list all the app’s commands, including those in various context menus.

**If you need to use submenus to manage a menu’s complexity, keep them to one level.** A submenu is a menu item that reveals a secondary menu of logically related commands. Although submenus can shorten a context menu and clarify its commands, more than one level of submenu complicates the experience and can be difficult for people to navigate. If you need to include a submenu, give it an intuitive title that helps people predict its contents without opening it. For guidance, see Submenus.

**Hide unavailable menu items, don’t dim them.** Unlike a regular menu, which helps people discover actions they can perform even when the action isn’t available, a context menu displays only the actions that are relevant to the currently selected view or content. On desktop, the exceptions are the Cut, Copy, and Paste menu items, which may appear unavailable if they don’t apply to the current context.

**Aim to place the most frequently used menu items where people are likely to encounter them first.** When a context menu opens, people often read it starting from the part that’s closest to where their finger or pointer revealed it. Depending on the location of the selected content, a context menu might open above or below it, so you might also need to reverse the order of items to match the position of the menu.

**Show keyboard shortcuts in your app’s main menus, not in context menus.** Context menus already provide a shortcut to task-specific commands, so it’s redundant to display keyboard shortcuts too.

**Follow best practices for using separators.** As with other types of menus, you can use separators to group items in a context menu and help people scan the menu more quickly. In general, you don’t want more than about three groups in a context menu. For guidance, see Menus.

**On phones and tablets, warn people about context menu items that can destroy data.** If you need to include potentially destructive items in your context menu — such as Delete or Remove — list them at the end of the menu and identify them as destructive. The system can display a destructive menu item using a red text color.


### Content

A context menu seldom displays a title. In contrast, each item in a context menu needs to display a short label that clearly describes what it does. For guidance, see Menus > Labels.

**Include a title in a context menu only if doing so clarifies the menu’s effect.** For example, when people select multiple a mail app messages and tap the Mark toolbar button on phones and tablets, the resulting context menu displays a title that states the number of selected messages, reminding people that the command they choose affects all the messages they selected.

**Represent menu item actions with familiar icons.** Icons help people recognize common actions throughout your app. Use the same icons as the system to represent actions such as Copy, Share, and Delete, wherever they appear. For a list of icons that represent common actions, see Standard icons. For additional guidance, see Menus.


### Device-specific considerations

#### Phone & tablet
**Provide either a context menu or an edit menu for an item, but not both.** If you provide both features for the same item, it can be confusing to people — and difficult for the system to detect their intent. See Edit menus.

**On tablets, consider using a context menu to let people create a new object in your app.** Tablets let you reveal a context menu when people perform a long press on the touchscreen or use a secondary click with an attached trackpad or keyboard. For example, a files app lets people create a new folder by revealing a context menu in an area between existing files and folders.

On phones and tablets, a context menu can display a preview of the current content near the list of commands. People can choose a command in the menu or — in some cases — they can tap the preview to open it or drag it to another area.

**Prefer a graphical preview that clarifies the target of a context menu’s commands.** For example, when people reveal a context menu on a list item in a notes app or a mail app, the preview shows a condensed version of the actual content to help people confirm that they’re working with the item they intend.

**Ensure that your preview looks good as it animates.** As people reveal a context menu on an onscreen object, the system animates the preview image as it emerges from the content, dimming the screen behind the preview and the menu. It’s important to adjust the preview’s clipping path to match the shape of the preview image so that its contours, such as the rounded corners, don’t appear to change during animation.


#### Desktop
On a computer, a context menu is sometimes called a *contextual* menu.


## Edit menus

An edit menu lets people make changes to selected content in the current view, in addition to offering related commands like Copy, Select, Translate, and Look Up.

In addition to text, an edit menu’s commands can apply to many types of selectable content, such as images, files, and objects like contact cards, charts, or map locations. On phones and tablets, the system automatically detects the data type of a selected item, which can result in the addition of a related action to the edit menu. For example, selecting an address can add an item like *Get directions* to the edit menu.

Edit menus can look and behave slightly differently in different platforms.

- On phones, the edit menu displays commands in a compact, horizontal list that appears when people touch and hold or double-tap to select content in a view. People can tap a chevron on the trailing edge to expand it into a context menu.

- On tablets, the edit menu looks different depending on how people reveal it. When people use touch interactions to reveal the menu, it uses the compact, horizontal appearance. In contrast, when people use a keyboard or pointing device to reveal it, the edit menu opens directly in a context menu.

- On desktop, people can access editing commands in a context menu they can reveal while in an editing task, as well as through the app’s Edit menu in the menu bar.


### Best practices

**Prefer the system-provided edit menu.** People are familiar with the contents and behavior of the system-provided component, so creating a custom menu that presents the same commands is redundant and likely to be confusing.


**Offer commands that are relevant in the current context, removing or dimming commands that don’t apply.** For example, if nothing is selected, avoid showing options that require a selection, such as Copy or Cut. Similarly, avoid showing a Paste option when there’s nothing to paste.

**List custom commands near relevant system-provided ones.** For example, if you offer custom formatting commands, you can help maintain the ordering people expect by listing them after the system-provided commands in the format section. Avoid overwhelming people with too many custom commands.

**When it makes sense, let people select and copy noneditable text.** People appreciate being able to paste static content — such as an image caption or social media status — into a message, note, or web search. In general, let people copy content text, but not control labels.

**Support undo and redo when possible.** Like all menus, an edit menu doesn’t require confirmation before performing its actions, so people can easily use undo and redo to recover a previous state. For guidance, see Undo and redo.

**In general, avoid implementing other controls that perform the same functions as edit menu items.** People typically expect to choose familiar edit commands in an edit menu, or use standard keyboard shortcuts. Offering redundant controls can crowd your interface, giving you less space for presenting actions that people might not already know about.

**Differentiate different types of deletion commands when necessary.** For example, a Delete menu item behaves the same as pressing a Delete key, but a Cut menu item copies the selected content to the system pasteboard before deleting it.


### Content

**Create short labels for custom commands.** Use verbs or short verb phrases that succinctly describe the action your command performs. For guidance, see Labels.


### Device-specific considerations

#### Phone & tablet
**Ensure your edit menu works well in both styles.** The system displays the compact, horizontal style when people use Multi-Touch gestures to reveal the edit menu, and the vertical style when people use a keyboard or pointing device to reveal it. For guidance using the vertical menu layout, see Menus > phones and tablets.

**Adjust an edit menu’s placement, if necessary.** Depending on available space, the default menu position is above or below the insertion point or selection. The system also displays a visual indicator that points to the targeted content. Although you can’t change the shape of the menu or its pointer, you can change the menu’s position. For example, you might need to move the menu to prevent it from covering important content or parts of your interface.


#### Desktop
To learn about the order of items in a desktop app’s Edit menu, see Edit menu.


---

## Menus

A menu reveals its options when people interact with it, making it a space-efficient way to present commands in your app or game.

Menus are ubiquitous in apps and games, so most people already know how to use them. Whether you use system-provided components or custom ones, people expect menus to behave in familiar ways. For example, people understand that opening a menu reveals one or more *menu items*, each of which represents a command, option, or state that affects the current selection or context. The guidance for labeling and organizing menu items applies to all types of menus in all experiences.

> **Note**: Several system-provided components also include menus that support specific use cases. For example, a pop-up button or pull-down button can reveal a menu of options directly related to its action; a context menu lets people access a small number of frequently used actions relevant to their current view or task; and on desktop and tablets, menu bar menus contain all the commands people can perform in the app or game.


### Labels

A menu item’s label describes what it does and may include a symbol if it helps to clarify meaning. In an app, a menu item can also display the associated keyboard command, if there is one; in a game, a menu item rarely displays a keyboard command because a game typically needs to handle input from a wider range of devices and may offer game-specific mappings for various keys.

> **Note**: Depending on menu layout, a phone or tablet app can display a few unlabeled menu items that use only symbols or icons to identify them. For guidance, see phones and tablets.

**For each menu item, write a label that clearly and succinctly describes it.** In general, label a menu item that initiates an action using a verb or verb phrase that describes the action, such as View, Close, or Select. For guidance labeling menu items that show and hide something in the interface or show the currently selected state of something, see Toggled items. As with all the copy you write, let your app’s or game’s communication style guide the tone of the menu-item labels you create.

**To be consistent with platform experiences, use title-style capitalization.** Although a game might have a different writing style, generally prefer using title-style capitalization, which capitalizes every word except articles, coordinating conjunctions, and short prepositions, and capitalizes the last word in the label, regardless of the part of speech. For complete guidance on this style of capitalization in English, see title-style capitalization.

**Remove articles like *a*, *an*, and *the* from menu-item labels to save space.** In English, articles always lengthen labels, but rarely enhance understanding. For example, changing a menu-item label from View Settings to View the Settings doesn’t provide additional clarification.

**Show people when a menu item is unavailable.** An unavailable menu item often appears dimmed and doesn’t respond to interactions. If all of a menu’s items are unavailable, the menu itself needs to remain available so people can open it and learn about the commands it contains.

**Append an ellipsis to a menu item’s label when the action requires more information before it can complete.** The ellipsis character (…) signals that people need to input information or make additional choices, typically within another view.


### Icons

**Represent common actions consistently.** The system provides standard icons to represent common actions like Share, Print, and Search. Using standard icons makes your app easier to use and more familiar. For a list of icons that represent common actions, see Standard icons.

**Use menu item icons sparingly and with purpose.** Icons allow people to find menu items more quickly, and help clarify what selecting an item does. Use an icon to highlight the most common actions and key features of your app, file system locations, connected devices, visual concepts like rotating or flipping an image, and user-generated content like folders and documents. Don’t display an icon if you can’t find one that clearly represents the menu item.

**Apply a uniform visual treatment across menu items in the same group.** For visual consistency and balance, provide icons for all menu items in a group, or none of them.


### Organization

Organizing menu items in ways that reflect how people use your app or game can make your experience feel straightforward and easy to use.

**Prefer listing important or frequently used menu items first.** People tend to start scanning a menu from the top, so listing high-priority items first often means that people can find what they want without reading the entire menu.

**Consider grouping logically related items.** For example, grouping editing commands like Copy, Cut, and Paste or camera commands like Look Up, Look Down, and Look Left can help people remember where to find them. To help people visually distinguish such groups, use a separator. Depending on the platform and type of menu, a *separator* appears between groups of items as a horizontal line or a short gap in the menu’s background appearance.

**Prefer keeping all logically related commands in the same group, even if the commands don’t all have the same importance.** For example, people generally use Paste and Match Style much less often than they use Paste, but they expect to find both commands in the same group that contains more frequently used editing commands like Copy and Cut.

**Be mindful of menu length.** People need more time and attention to read a long menu, which means they may miss the command they want. If a menu is too long, consider dividing it into separate menus. Alternatively, you might be able to use a submenu to shorten the list, such as listing difficulty levels in a submenu of a New Game menu item. The exception is when a menu contains user-defined or dynamically generated content, like the History and Bookmarks menus in the browser. People expect such a menu to accommodate all the items they add to it, so a long menu is fine, and scrolling is acceptable.


### Submenus

Sometimes, a menu item can reveal a set of closely related items in a subordinate list called a *submenu*. A menu item indicates the presence of a submenu by displaying a symbol — like a chevron — after its label. Submenus are functionally identical to menus, aside from their hierarchical positioning.

**Use submenus sparingly.** Each submenu adds complexity to the interface and hides the items it contains. You might consider creating a submenu when a term appears in more than two menu items in the same group. For example, instead of offering separate menu items for Sort by Date, Sort by Score, and Sort by Time, a game could present a menu item that uses a submenu to list the sorting options Date, Score, and Time. It generally works well to use the repeated term — in this case, *Sort by* — in the menu item’s label to help people predict the contents of the submenu.

**Limit the depth and length of submenus.** It can be difficult for people to reveal multiple levels of hierarchical submenus, so it’s generally best to restrict them to a single level. Also, if a submenu contains more than about five items, consider creating a new menu.

**Make sure a submenu remains available even when its nested menu items are unavailable.** A submenu item — like all menu items — needs to let people open it and learn about the commands it contains.

**Prefer using a submenu to indenting menu items.** Using indentation is inconsistent with the system and doesn’t clearly express the relationships between the menu items.


### Toggled items

Menu items often represent attributes or objects that people can turn on or off. If you want to avoid listing a separate menu item for each state, it can be efficient to create a single, toggled menu item that communicates the current state and lets people change it.

**Consider using a changeable label that describes an item’s current state.** For example, instead of listing two menu items like Show Map and Hide Map, you could include one menu item whose label changes from Show Map to Hide Map, depending on whether the map is visible.

**Include a verb if a changeable label isn’t clear enough.** For example, people might not know whether the changeable labels HDR On and HDR Off describe actions or states. If you needed to clarify that these items represent actions, you could add verbs to the labels, like Turn HDR On and Turn HDR Off.

**If necessary, display both menu items instead of one toggled item.** Sometimes, it helps people to view both actions or states at the same time. For example, a game could list both Take Account Online and Take Account Offline items, so when someone’s account is online, only the Take Account Offline menu item appears available.

**Consider using a checkmark to show that an attribute is currently in effect.** It’s easy for people to scan for checkmarks in a list of attributes to find the ones that are selected. For example, in the standard Format > Font menu, checkmarks can make it easy for people notice the styles that apply to selected text.

**Consider offering a menu item that makes it easy to remove multiple toggled attributes.** For example, if you let people apply several styles to selected text, it can work well to provide a menu item — such as Plain — that removes all applied formatting attributes at one time.


### In-game menus

In-game menus give players ways to control gameplay as well as determine settings for the game as a whole.

**Let players navigate in-game menus using the platform’s default interaction method.** People expect to use the same interactions to navigate your menus as they use for navigating other menus on the device.

**Make sure your menus remain easy to open and read on all platforms you support.** Each platform defines specific sizes that work best for fonts and interaction targets. Sometimes, scaling your game content to display on a different screen — especially a mobile device screen — can make in-game menus too small for people to read or interact with. If this happens, modify the size of the tap targets and consider alternative ways to communicate the menu’s content. For guidance, see Typography and Touch controls.


### Device-specific considerations

#### Phone & tablet
On phones and tablets, a menu can display items in one of the following three layouts.

- **Small.** A row of four items appears at the top of the menu, above a list that contains the remaining items. For each item in the top row, the menu displays a symbol or icon, but no label.

- **Medium.** A row of three items appears at the top of the menu, above a list that contains the remaining items. For each item in the top row, the menu displays a symbol or icon above a short label.

- **Large (the default).** The menu displays all items in a list.


**Choose a small or medium menu layout when it can help streamline people’s choices.** Consider using the medium layout if your app has three important actions that people often want to perform. For example, a notes app uses the medium layout to give people a quick way to perform the Scan, Lock, and Pin actions. Use the small layout only for closely related actions that typically appear as a group, such as Bold, Italic, Underline, and Strikethrough. For each action, use a recognizable symbol that helps people identify the action without a label.


## Pop-up buttons

A pop-up button displays a menu of mutually exclusive options.

After people choose an item from a pop-up button’s menu, the menu closes, and the button can update its content to indicate the current selection.


### Best practices

**Use a pop-up button to present a flat list of mutually exclusive options or states.** A pop-up button helps people make a choice that affects their content or the surrounding view. Use a pull-down button instead if you need to:

- Offer a list of actions

- Let people select multiple items

- Include a submenu

**Provide a useful default selection.** A pop-up button can update its content to identify the current selection, but if people haven’t made a selection yet, it shows the default item you specify. When possible, make the default selection an item that most people are likely to want.

**Give people a way to predict a pop-up button’s options without opening it.** For example, you can use an introductory label or a button label that describes the button’s effect, giving context to the options.

**Consider using a pop-up button when space is limited and you don’t need to display all options all the time.** Pop-up buttons are a space-efficient way to present a wide array of choices.

**If necessary, include a Custom option in a pop-up button’s menu to provide additional items that are useful in some situations.** Offering a Custom option can help you avoid cluttering the interface with items or controls that people need only occasionally. You can also display explanatory text below the list to help people understand how the options work.


### Device-specific considerations

#### Tablet
**Within a popover or modal view, consider using a pop-up button instead of a disclosure indicator to present multiple options for a list item.** For example, people can quickly choose an option from the pop-up button’s menu without navigating to a detail view. Consider using a pop-up button in this scenario when you have a fairly small, well-defined set of options that work well in a menu.


---

## Pull-down buttons

A pull-down button displays a menu of items or actions that directly relate to the button’s purpose.

After people choose an item in a pull-down button’s menu, the menu closes, and the app performs the chosen action.


### Best practices

**Use a pull-down button to present commands or items that are directly related to the button’s action.** The menu lets you help people clarify the button’s target or customize its behavior without requiring additional buttons in your interface. For example:

- An Add button could present a menu that lets people specify the item they want to add.

- A Sort button could use a menu to let people select an attribute on which to sort.

- A Back button could let people choose a specific location to revisit instead of opening the previous one.

If you need to provide a list of mutually exclusive choices that aren’t commands, use a pop-up button instead.

**Avoid putting all of a view’s actions in one pull-down button.** A view’s primary actions need to be easily discoverable, so you don’t want to hide them in a pull-down button that people have to open before they can do anything.

**Balance menu length with ease of use.** Because people have to interact with a pull-down button before they can view its menu, listing a minimum of three items can help the interaction feel worthwhile. If you need to list only one or two items, consider using alternative components to present them, such as buttons to perform actions and toggles or switches to present selections. In contrast, listing too many items in a pull-down button’s menu can slow people down because it takes longer to find a specific item.

**Display a succinct menu title only if it adds meaning.** In general, a pull-down button’s content — combined with descriptive menu items — provides all the context people need, making a menu title unnecessary.

**Let people know when a pull-down button’s menu item is destructive, and ask them to confirm their intent.** Menus use red text to highlight actions that you identify as potentially destructive. When people choose a destructive action, the system displays an action sheet (phones) or popover (tablets) in which they can confirm their choice or cancel the action. Because an action sheet appears in a different location from the menu and requires deliberate dismissal, it can help people avoid losing data by mistake.

**Include an interface icon with a menu item when it provides value.** If you need to clarify an item’s meaning, you can display an icon or image after its label. Using the symbol library for this purpose can help you provide a familiar experience while ensuring that the symbol remains aligned with the text at every scale.


### Device-specific considerations

#### Phone & tablet
> **Note**: You can also let people reveal a pull-down menu by performing a specific gesture on a button. For example, on phones, a browser can respond to a touch and hold gesture on the Tabs button by displaying a menu of tab-related actions, like New Tab and Close All Tabs.

**Consider using a More pull-down button to present items that don’t need prominent positions in the main interface.** A More button can help you offer a range of items where space is constrained, but it can also hinder discoverability. Although people generally understand that a More button offers additional functionality related to the current context, the ellipsis icon doesn’t necessarily help them predict its contents. To design an effective More button, weigh the convenience of its size against its impact on discoverability to find a balance that works in your app.


---

## The menu bar

On a computer or a tablet, the menu bar at the top of the screen displays the top-level menus in your app or game.

Desktop users are very familiar with the desktop menu bar, and they rely on it to help them learn what an app does and find the commands they need. To help your app or game feel at home on desktop, it’s essential to provide a consistent menu bar experience.

Menu bar menus on tablet are similar to those on desktop, appearing in the same order and with familiar sets of menu items. When you adopt the menu structure that people expect from their experience on desktop, it helps them immediately understand and take advantage of the menu bar on tablet as well.

Keyboard shortcuts on tablets use the same patterns as on desktop. For guidance, see Standard keyboard shortcuts.

Menus in the menu bar share most of the appearance and behavior characteristics that all menu types have. To learn about menus in general — and how to organize and label menu items — see Menus.


### Anatomy

When present in the menu bar, the following menus appear in the order listed below.

- *YourAppName* (you supply a short version of your app’s name for this menu’s title)

- File

- Edit

- Format

- View

- App-specific menus, if any

- Window

- Help

In addition, a desktop menu bar may include a system menu on the leading side and status-area items (menu bar extras / tray icons) on the trailing side. See the Desktop device-specific considerations for guidance.


### Best practices

**Support the default system-defined menus and their ordering.** People expect to find menus and menu items in an order they’re familiar with. In many cases, the system implements the functionality of standard menu items so you don’t have to. For example, when people select text in a standard text field, the system makes the Edit > Copy menu item available.

**Always show the same set of menu items.** Keeping menu items visible helps people learn what actions your app supports, even if they’re unavailable in the current context. If a menu bar item isn’t actionable, disable the action instead of hiding it from the menu.

**Represent menu item actions with familiar icons.** Icons help people recognize common actions throughout your app. Use the same icons as the system to represent actions such as Copy, Share, and Delete, wherever they appear. For a list of icons that represent common actions, see Standard icons. For additional guidance, see Menus.

**Support the keyboard shortcuts defined for the standard menu items you include.** People expect to use the keyboard shortcuts they already know for standard menu items, like Copy, Cut, Paste, Save, and Print. Define custom keyboard shortcuts only when necessary. For guidance, see Standard keyboard shortcuts.

**Prefer short, one-word menu titles.** Various factors — like different display sizes and the presence of menu bar extras — can affect the spacing and appearance of your menus. One-word menu titles work especially well in the menu bar because they take little space and are easy for people to scan. If you need to use more than one word in the menu title, use title-style capitalization.


### App menu

The app menu lists items that apply to your app or game as a whole, rather than to a specific task, document, or window. To help people quickly identify the active app, the menu bar displays your app name in bold.

The app menu typically contains the following menu items listed in the following order.

| Menu item | Action | Guidance |
| --- | --- | --- |
| About *YourAppName* | Displays the About window for your app, which includes copyright and version information. | Prefer a short name of 16 characters or fewer. Don’t include a version number. |
| Settings… | Opens your settings window, or your app’s page on tablets Settings. | Use only for app-level settings. If you also offer document-specific settings, put them in the File menu. |
| Optional app-specific items | Performs custom app-level setting or configuration actions. | List custom app-configuration items after the Settings item and within the same group. |
| Services (desktop only) | Displays a submenu of services from the system and other apps that apply to the current context. | |
| Hide *YourAppName* (desktop only) | Hides your app and all of its windows, and then activates the most recently used app. | Use the same short app name you supply for the About item. |
| Hide Others (desktop only) | Hides all other open apps and their windows. | |
| Show All (desktop only) | Shows all other open apps and their windows behind your app’s windows. | |
| Quit *YourAppName* | Quits your app. Pressing Option changes Quit *YourAppName* to Quit and Keep Windows. | Use the same short app name you supply for the About item. |

**Display the About menu item first.** Include a separator after the About menu item so that it appears by itself in a group.


### File menu

The File menu contains commands that help people manage the files or documents an app supports. If your app doesn’t handle any types of files, you can rename or eliminate this menu.

The File menu typically contains the following menu items listed in the following order.

| Menu item | Action | Guidance |
| --- | --- | --- |
| New *Item* | Creates a new document, file, or window. | For *Item*, use a term that names the type of item your app creates. For example, Calendar uses *Event* and *Calendar*. |
| Open | Can open the selected item or present an interface in which people select an item to open. | If people need to select an item in a separate interface, an ellipsis follows the command to indicate that more input is required. |
| Open Recent | Displays a submenu that lists recently opened documents and files that people can select, and typically includes a *Clear Menu* item. | List document and filenames that people recognize in the submenu; don’t display file paths. List the documents in the order people last opened them, with the most recently opened document first. |
| Close | Closes the current window or document. Pressing Option changes Close to Close All. For a tab-based window, Close Tab replaces Close. | In a tab-based window, consider adding a Close Window item to let people close the entire window with one click or tap. |
| Close Tab | Closes the current tab in a tab-based window. Pressing Option changes Close Tab to Close Other Tabs. | |
| Close File | Closes the current file and all its associated windows. | Consider supporting this menu item if your app can open multiple views of the same file. |
| Save | Saves the current document or file. | Automatically save changes periodically as people work so they don’t need to keep choosing File > Save. For a new document, prompt people for a name and location. If you need to let people save a file in multiple formats, prefer a pop-up menu that lets people choose a format in the Save sheet. |
| Save All | Saves all open documents. | |
| Duplicate | Duplicates the current document, leaving both documents open. Pressing Option changes Duplicate to Save As. | Prefer Duplicate to menu items like Save As, Export, Copy To, and Save To because these items don’t clarify the relationship between the original file and the new one. |
| Rename… | Lets people change the name of the current document. | |
| Move To… | Prompts people to choose a new location for the document. | |
| Export As… | Prompts people for a name, output location, and export file format. After exporting the file, the current document remains open; the exported file doesn’t open. | Reserve the Export As item for when you need to let people export content in a format your app doesn’t typically handle. |
| Revert To | When people turn on autosaving, displays a submenu that lists recent document versions and an option to display the version browser. After people choose a version to restore, it replaces the current document. | |
| Page Setup… | Opens a panel for specifying printing parameters like paper size and printing orientation. A document can save the printing parameters that people specify. | Include the Page Setup item if you need to support printing parameters that apply to a specific document. Parameters that are global in nature, like a printer’s name, or that people change frequently, like the number of copies to print, belong in the Print panel. |
| Print… | Opens the standard Print panel, which lets people print to a printer, send a fax, or save as a PDF. | |


### Edit menu

The Edit menu lets people make changes to content in the current document or text container, and provides commands for interacting with the Clipboard. Because many editing commands apply to any editable content, the Edit menu is useful even in apps that aren’t document-based.

**Determine whether Find menu items belong in the Edit menu.** For example, if your app lets people search for files or other types of objects, Find menu items might be more appropriate in the File menu.

The Edit menu typically contains the following top-level menu items, listed in the following order.

| Menu item | Action | Guidance |
| --- | --- | --- |
| Undo | Reverses the effect of the previous user operation. | Clarify the target of the undo. For example, if people just selected a menu item, you can append the item’s title, such as Undo Paste and Match Style. For a text entry operation, you might append the word *Typing* to give Undo Typing. |
| Redo | Reverses the effect of the previous Undo operation. | Clarify the target of the redo. For example, if people just reversed a menu item selection, you can append the item’s title, such as Redo Paste and Match Style. For a text entry operation, you might append the word *Typing* to give Redo Typing. |
| Cut | Removes the selected data and stores it on the Clipboard, replacing the previous contents of the Clipboard. | |
| Copy | Duplicates the selected data and stores it on the Clipboard. | |
| Paste | Inserts the contents of the Clipboard at the current insertion point. The Clipboard contents remain unchanged, permitting people to choose Paste multiple times. | |
| Paste and Match Style | Inserts the contents of the Clipboard at the current insertion point, matching the style of the inserted text to the surrounding text. | |
| Delete | Removes the selected data, but doesn’t place it on the Clipboard. | Provide a Delete menu item instead of an Erase or Clear menu item. Choosing Delete is the equivalent of pressing the Delete key, so it’s important for the naming to be consistent. |
| Select All | Highlights all selectable content in the current document or text container. | |
| Find | Displays a submenu containing menu items for performing search operations in the current document or text container. Standard submenus include: Find, Find and Replace, Find Next, Find Previous, Use Selection for Find, and Jump to Selection. | |
| Spelling and Grammar | Displays a submenu containing menu items for checking for and correcting spelling and grammar in the current document or text container. Standard submenus include: Show Spelling and Grammar, Check Document Now, Check Spelling While Typing, Check Grammar With Spelling, and Correct Spelling Automatically. | |
| Substitutions | Displays a submenu containing items that let people toggle automatic substitutions while they type in a document or text container. Standard submenus include: Show Substitutions, Smart Copy/Paste, Smart Quotes, Smart Dashes, Smart Links, Data Detectors, and Text Replacement. | |
| Transformations | Displays a submenu containing items that transform selected text. Standard submenus include: Make Uppercase, Make Lowercase, and Capitalize. | |
| Speech | Displays a submenu containing Start Speaking and Stop Speaking items, which control when the system audibly reads selected text. | |
| Start Dictation | Opens the dictation window and converts spoken words into text that’s added at the current insertion point. The system automatically adds the Start Dictation menu item at the bottom of the Edit menu. | |
| Emoji & Symbols | Displays a Character Viewer, which includes emoji, symbols, and other characters people can insert at the current insertion point. The system automatically adds the Emoji & Symbols menu item at the bottom of the Edit menu. | |


### Format menu

The Format menu lets people adjust text formatting attributes in the current document or text container. You can exclude this menu if your app doesn’t support formatted text editing.

The Format menu typically contains the following top-level menu items, listed in the following order.

| Menu item | Action |
| --- | --- |
| Font | Displays a submenu containing items for adjusting font attributes of the selected text. Standard submenus include: Show Fonts, Bold, Italic, Underline, Bigger, Smaller, Show Colors, Copy Style, and Paste Style. |
| Text | Displays a submenu containing items for adjusting text attributes of the selected text. Standard submenus include: Align Left, Align Center, Justify, Align Right, Writing Direction, Show Ruler, Copy Ruler, and Paste Ruler. |


### View menu

The View menu lets people customize the appearance of all an app’s windows, regardless of type.

> **Important**: The View menu doesn’t include items for navigating between or managing specific windows; the Window menu provides these commands.

**Provide a View menu even if your app supports only a subset of the standard view functions.** For example, if your app doesn’t include a tab bar, toolbar, or sidebar, but does support full-screen mode, provide a View menu that includes only the Enter/Exit Full Screen menu item.

**Ensure that each show/hide item title reflects the current state of the corresponding view.** For example, when the toolbar is hidden, provide a Show Toolbar menu item; when the toolbar is visible, provide a Hide Toolbar menu item.

The View menu typically contains the following top-level menu items, listed in the following order.

| Menu item | Action |
| --- | --- |
| Show/Hide Tab Bar | Toggles the visibility of the tab bar above the body area in a tab-based window |
| Show All Tabs/Exit Tab Overview | Enters and exits a view (similar to a system window overview) that provides an overview of all open tabs in a tab-based window |
| Show/Hide Toolbar | In a window that includes a toolbar, toggles the toolbar’s visibility |
| Customize Toolbar | In a window that includes a toolbar, opens a view that lets people customize toolbar items |
| Show/Hide Sidebar | In a window that includes a sidebar, toggles the sidebar’s visibility |
| Enter/Exit Full Screen | In an app that supports a full-screen experience, opens the window at full-screen size in a new space |


### App-specific menus

Your app’s custom menus appear in the menu bar between the View menu and the Window menu. For example, the browser’s menu bar includes app-specific History and Bookmarks menus.

**Provide app-specific menus for custom commands.** People look in the menu bar when searching for app-specific commands, especially when using an app for the first time. Even when commands are available elsewhere in your app, it’s important to list them in the menu bar. Putting commands in the menu bar makes them easier for people to find, lets you assign keyboard shortcuts to them, and makes them more accessible to people using Full Keyboard Access. Excluding commands from the menu bar — even infrequently used or advanced commands — risks making them difficult for everyone to find.

**As much as possible, reflect your app’s hierarchy in app-specific menus.** For example, a mail app lists the Mailbox, Message, and Format menus in an order that mirrors the relationships of these items: mailboxes contain messages, and messages contain formatting.

**Aim to list app-specific menus in order from most to least general or commonly used.** People tend to expect menus in the leading end of a list to be more specialized than menus in the trailing end.


### Window menu

The Window menu lets people navigate, organize, and manage an app’s windows.

> **Important**: The Window menu doesn’t help people customize the appearance of windows or close them. To customize a window, people use commands in the View menu; to close a window, people choose Close in the File menu.

**Provide a Window menu even if your app has only one window.** Include the Minimize and Zoom menu items so people using Full Keyboard Access can use the keyboard to invoke these functions.

**Consider including menu items for showing and hiding panels.** A panel provides information, configuration options, or tools for interacting with content in a primary window, and typically appears only when people need it. There’s no need to provide access to the font panel or text color panel because the Format menu lists these panels.

The Window menu typically contains the following top-level menu items, listed in the following order.

| Menu item | Action | Guidance |
| --- | --- | --- |
| Minimize | Minimizes the active window to the dock. Pressing the Option/Alt key changes this item to Minimize All. | |
| Zoom | Toggles between a predefined size appropriate to the window’s content and the window size people set. Pressing the Option/Alt key changes this item to Zoom All. | Avoid using Zoom to enter or exit full-screen mode. The View menu supports these functions. |
| Show Previous Tab | Shows the tab before the current tab in a tab-based window. | |
| Show Next Tab | Shows the tab after the current tab in a tab-based window. | |
| Move Tab to New Window | Opens the current tab in a new window. | |
| Merge All Windows | Combines all open windows into a single tabbed window. | |
| Enter/Exit Full Screen | In an app that supports a full-screen experience, opens the window at full-screen size in a new space. | Include this item in the Window menu only if your app doesn’t have a View menu. In this scenario, continue to provide separate Minimize and Zoom menu items. |
| Bring All to Front | Brings all an app’s open windows to the front, maintaining their onscreen location, size, and layering order. (Clicking the app icon in the dock has the same effect.) Pressing the Option/Alt key changes this item to Arrange in Front, which brings an app’s windows to the front in a neatly tiled arrangement. | |
| *Name of an open app-specific window* | Brings the selected window to the front. | List the currently open windows in alphabetical order for easy scanning. Avoid listing panels or other modal views. |


### Help menu

The Help menu — located at the trailing end of the menu bar — provides access to an app’s help documentation. When you use the Help Book format for this documentation, desktop automatically includes a search field at the top of the Help menu.

| Menu item | Action | Guidance |
| --- | --- | --- |
| Send *YourAppName* Feedback | Opens your feedback channel so people can report problems or suggestions. | |
| *YourAppName* Help | When the content uses the Help Book format, opens the content in the built-in Help Viewer. | |
| *Additional Item* | | Use a separator between your primary help documentation and additional items, which might include registration information or release notes. Keep the total the number of items you list in the Help menu small to avoid overwhelming people with too many choices when they need help. Alternatively, consider linking to additional items from within your help documentation. |

For guidance, see Offering help.


### Dynamic menu items

In rare cases, it can make sense to present a *dynamic menu item*, which is a menu item that changes its behavior when people choose it while pressing a modifier key (Control, Option/Alt, Shift, or Command/Ctrl). For example, the *Minimize* item in the Window menu changes to *Minimize All* when people press the Option key.

**Avoid making a dynamic menu item the only way to accomplish a task.** Dynamic menu items are hidden by default, so they’re best suited to offer shortcuts to advanced actions that people can accomplish in other ways. For example, if someone hasn’t discovered the *Minimize All* dynamic menu item in the Window menu, they can still minimize each open window.

**Use dynamic menu items primarily in menu bar menus.** Adding a dynamic menu item to contextual or dock menus can make the item even harder for people to discover.

**Require only a single modifier key to reveal a dynamic menu item.** It can be physically awkward to press more than one key while simultaneously opening a menu and choosing a menu item, in addition to reducing the discoverability of the dynamic behavior.

> **Tip**: Desktop automatically sets the width of a menu to hold the widest item, including dynamic menu items.


### Device-specific considerations

#### Tablet
The menu bar displays the top-level menus for your app or game, including both system-provided menus and any custom ones you choose to add. People reveal the menu bar by moving the pointer to the top edge of the screen, or swiping down from it. When visible, the menu bar occupies the same vertical space as the status bar at the top edge of the screen.

As with the desktop menu bar, the tablet menu bar provides a familiar way for people to learn what an app does, find the commands they need, and discover keyboard shortcuts. While they are similar in most respects, there are a few key differences between the menu bars on each platform.

| | tablets | desktop |
| --- | --- | --- |
| Menu bar visibility | Hidden until revealed | Visible by default |
| Horizontal alignment | Centered | Leading side |
| Menu bar extras | Not available | System default and custom |
| Window controls | In the menu bar when the app is full screen | Never in the menu bar |
| System menu | Not available | Always available |
| App menu | About, Services, and app visibility-related items not available | Always available |

**Because the menu bar is often hidden when running an app full screen, ensure that people can access all of your app’s functions through its UI.** In particular, always offer other ways to accomplish tasks assigned to dynamic menu items, since these are only available when a hardware keyboard is connected. Avoid using the menu bar as a catch-all location for functionality that doesn’t fit in elsewhere.

**Reserve the YourAppName > Settings menu item for opening your app’s page on tablets Settings.** If your app includes its own internal preferences area, link to it with a separate menu item beneath Settings in the same group. Place any other custom app-wide configuration options in this section as well.

**For apps with tab-style navigation, consider adding each tab as a menu item in the View menu.** Since each tab is a different view of the app, the View menu is a natural place to offer an additional way to navigate between tabs. If you do this, consider assigning key bindings to each tab to make navigation even more convenient.

**Consider grouping menu items into submenus to conserve vertical space.** Menu item rows on tablet use more space than on desktop to make them easier to tap. Because of this, and the smaller screen sizes of some tablets, it can be helpful to group related items into submenus more frequently than in the menu bar on desktop.


#### Desktop
A desktop menu bar may begin with a system menu that holds system-defined items; you can’t modify or remove it. Space permitting, the system can also display menu bar extras (tray/status icons) in the trailing end of the menu bar. For guidance, see Menu bar extras.

When menu bar space is constrained, the system prioritizes the display of menus and essential menu bar extras. To ensure that menus remain readable, the system may decrease the space between the titles, truncating them if necessary.

When people enter full-screen mode, the menu bar typically hides until they reveal it by moving the pointer to the top of the screen. For guidance, see Going full screen.


##### Menu bar extras

A menu bar extra exposes app-specific functionality using an icon that appears in the menu bar when your app is running, even when it’s not the frontmost app. Menu bar extras are on the opposite side of the menu bar from your app’s menus.

When necessary, the system hides menu bar extras to make room for app menus. Similarly, if there are too many menu bar extras, the system may hide some to avoid crowding app menus.

**Consider using a symbol to represent your menu bar extra.** You can create an icon or you can choose one of the symbol library, using it as-is or customizing it to suit your needs. Both interface icons and symbols use black and clear colors to define their shapes; the system can apply other colors to the black areas in each image so it looks good on both dark and light menu bars, and when your menu bar extra is selected. The menu bar’s height is 24 pt.

**Display a menu — not a popover — when people click your menu bar extra.** Unless the app functionality you want to expose is too complex for a menu, avoid presenting it in a popover.

**Let people — not your app — decide whether to put your menu bar extra in the menu bar.** Typically, people add a menu bar extra to the menu bar by changing a setting in an app’s settings window. To ensure discoverability, however, consider giving people the option of doing so during setup.

**Avoid relying on the presence of menu bar extras.** The system hides and shows menu bar extras regularly, and you can’t be sure which other menu bar extras people have chosen to display or predict the location of your menu bar extra.

**Consider exposing app-specific functionality in other ways, too.** For example, you can provide a dock/taskbar menu (jump list) that appears when people right-click your app’s icon. People can hide or choose not to use your menu bar extra, but a dock menu is aways available when your app is running.


---

## Toolbars

A toolbar provides convenient access to frequently used commands, controls, navigation, and search.

A toolbar consists of one or more sets of controls arranged horizontally along the top or bottom edge of the view, grouped into logical sections.

Toolbars act on content in the view, facilitate navigation, and help orient people in the app. They include three types of content:

- The title of the current view

- Navigation controls, like back and forward, and search fields

- Actions, or bar items, like buttons and menus

In contrast to a toolbar, a tab bar is specifically for navigating between areas of an app.


### Best practices

**Choose items deliberately to avoid overcrowding.** People need to be able to distinguish and activate each item, so you don’t want to put too many items in the toolbar. To accommodate variable view widths, define which items move to the overflow menu as the toolbar becomes narrower.

> **Note**: The system automatically adds an overflow menu on desktop or tablets when items no longer fit. Don’t add an overflow menu manually, and avoid layouts that cause toolbar items to overflow by default.

**Add a More menu to contain additional actions.** Prioritize less important actions for inclusion in the More menu. Try to include all actions in the toolbar if possible, and only add this menu if you really need it.

**On tablets and desktop apps, consider letting people customize the toolbar to include their most common items.** Toolbar customization is especially useful in apps that provide a lot of items — or that include advanced functionality that not everyone needs — and in apps that people tend to use for long periods of time. For example, it works well to make a range of editing actions available for toolbar customization, because people often use different types of editing commands based on their work style and their current project.

**Reduce the use of toolbar backgrounds and tinted controls.** Any custom backgrounds and appearances you use might overlay or interfere with background effects that the system provides. Instead, use the content layer to inform the color and appearance of the toolbar, and use a ScrollEdgeEffectStyle when necessary to distinguish the toolbar area from the content area. This approach helps your app express its unique personality without distracting from content.

**Avoid applying a similar color to toolbar item labels and content layer backgrounds.** If your app already has bright, colorful content in the content layer, prefer using the default monochromatic appearance of toolbars. For more guidance, see glass color.

**Prefer using standard components in a toolbar.** By default, standard buttons, text fields, headers, and footers have corner radii that are concentric with bar corners. If you need to create a custom component, ensure that its corner radius is also concentric with the bar’s corners.

**Consider temporarily hiding toolbars for a distraction-free experience.** Sometimes people appreciate a minimal interface to reduce distractions or reveal more content. If you support this, do so contextually when it makes the most sense, and offer ways to reliably restore hidden interface elements. For guidance, see Going full screen.


### Titles

**Provide a useful title for each window.** A title helps people confirm their location as they navigate your app, and differentiates between the content of multiple open windows. If titling a toolbar seems redundant, you can leave the title area empty. For example, a notes app doesn’t title the current note when a single window is open, because the first line of content typically supplies sufficient context. However, when opening notes in separate windows, the system titles them with the first line of content so people can tell them apart.

**Don’t title windows with your app name.** Your app’s name doesn’t provide useful information about your content hierarchy or any window or area in your app, so it doesn’t work well as a title.

**Write a concise title.** Aim for a word or short phrase that distills the purpose of the window or view, and keep the title under 15 characters long so you leave enough room for other controls.


### Navigation

A toolbar with navigation controls appears at the top of a window, helping people move through a hierarchy of content. A toolbar also often contains a search field for quick navigation between areas or pieces of content. On phones, a navigation-specific toolbar is sometimes called a navigation bar.

**Use the standard Back and Close buttons.** People know that the standard Back button lets them retrace their steps through a hierarchy of information, and the standard Close button closes a modal view. Prefer the standard symbols for each, and don’t use a text label that says *Back* or *Close*. If you create a custom version of either, make sure it still looks the same, behaves as people expect, and matches the rest of your interface, and ensure you consistently implement it throughout your app or game. For guidance, see Icons.


### Actions

**Provide actions that support the main tasks people perform.** In general, prioritize the commands that people are most likely to want. These commands are often the ones people use most frequently, but in some apps it might make sense to prioritize commands that map to the highest level or most important objects people work with.

**Make sure the meaning of each control is clear.** Don’t make people guess or experiment to figure out what a toolbar item does. Prefer simple, recognizable symbols for items instead of text, except for actions like *edit* that aren’t well-represented by symbols. For guidance on symbols that represent common actions, see Standard icons.

**Prefer system-provided symbols without borders.** System-provided symbols are familiar, automatically receive appropriate coloring and vibrancy, and respond consistently to user interactions. Borders (like outlined circle symbols) aren’t necessary because the section provides a visible container, and the system defines hover and selection state appearances automatically. For guidance, see the symbol library.

**Use the .prominent style for key actions such as Done or Submit.** This separates and tints the action so there’s a clear focal point. Only specify one primary action, and put it on the trailing side of the toolbar.


### Item groupings

You can position toolbar items in three locations: the leading edge, center area, and trailing edge of the toolbar. These areas provide familiar homes for navigation controls, window or document titles, common actions, and search.

- **Leading edge.** Elements that let people return to the previous document and show or hide a sidebar appear at the far leading edge, followed by the view title. Next to the title, the toolbar can include a document menu that contains standard and app-specific commands that affect the document as a whole, such as Duplicate, Rename, Move, and Export. To ensure that these items are always available, items on the toolbar’s leading edge aren’t customizable.

- **Center area.** Common, useful controls appear in the center area, and the view title can appear here if it’s not on the leading edge. On desktop and tablets, people can add, remove, and rearrange items here if you let them customize the toolbar, and items in this section automatically collapse into the system-managed overflow menu when the window shrinks enough in size.

- **Trailing edge.** The trailing edge contains important items that need to remain available, buttons that open nearby inspectors, an optional search field, and the More menu that contains additional items and supports toolbar customization. It also includes a primary action like Done when one exists. Items on the trailing edge remain visible at all window sizes.

To position items in the groupings you want, pin them to the leading edge, center, or trailing edge, and insert space between buttons or other items where appropriate.

**Group toolbar items logically by function and frequency of use.** For example, a presentation app includes several sections that are based on functionality, including one for presentation-level commands, one for playback commands, and one for object insertion.

**Group navigation controls and critical actions like Done, Close, or Save in dedicated, familiar, and visually distinct sections.** This reflects their importance and helps people discover and understand these actions.

**Keep consistent groupings and placement across platforms.** This helps people develop familiarity with your app and trust that it behaves similarly regardless of where they use it.

**Minimize the number of groups.** Too many groups of controls can make a toolbar feel cluttered and confusing, even with the added space on tablet and desktop. In general, aim for a maximum of three.

**Keep actions with text labels separate.** Placing an action with a text label next to an action with a symbol can create the illusion of a single action with a combined text and symbol, leading to confusion and misinterpretation. If your toolbar includes multiple text-labeled buttons, the text of those buttons may appear to run together, making the buttons indistinguishable. Add separation by inserting fixed space between the buttons.


### Device-specific considerations

#### Phone
**Prioritize only the most important items for inclusion in the main toolbar area.** Because space is so limited, carefully consider which actions are essential to your app and include those first. Create a More menu to include additional items.

**Use a large title to help people stay oriented as they navigate and scroll.** By default, a large title transitions to a standard title as people begin scrolling the content, and transitions back to large when people scroll to the top, reminding them of their current location.


#### Tablet
**Consider combining a toolbar with a tab bar.** On tablets, a toolbar and a tab bar can coexist in the same horizontal space at the top of the view. This is particularly useful for layouts where you want to navigate between a few main app areas while keeping the full width of the window available for content. For guidance, see Layout and Windows.


#### Desktop
In a desktop app, the toolbar resides in the frame at the top of a window, either below or integrated with the title bar. Note that window titles can display inline with controls, and toolbar items don’t include a bezel.

**Make every toolbar item available as a command in the menu bar.** Because people can customize the toolbar or hide it, it can’t be the only place that presents a command. In contrast, it doesn’t make sense to provide a toolbar item for every menu item, because not all menu commands are important enough or used often enough to warrant space in the toolbar.


## Path controls

A path control shows the file system path of a selected file or folder.

For example, choosing View > Show Path Bar in the file manager displays a path bar at the bottom of the window. It shows the path of the selected item, or the path of the window’s folder if nothing is selected.

There are two styles of path control.


### Best practices

**Use a path control in the window body, not the window frame.** Path controls aren’t intended for use in toolbars or status bars. Note that the path control in the file manager appears at the bottom of the window body, not in the status bar.


---

## Search fields

A search field lets people search a collection of content for specific terms they enter.

A search field is an editable text field that displays a Search icon, a Clear button, and placeholder text where people can enter what they are searching for. Search fields can use a scope bar as well as tokens to help filter and refine the scope of their search. Across each platform, there are different patterns for accessing search based on the goals and design of your app.


### Best practices

**Use placeholder text to help people know what they can search for.** Placeholder text can be helpful when you need to reinforce the scope of your search or to educate people about the type of content that search has access to.

**If possible, start search immediately when a person types.** Searching while someone types makes the search experience feel more responsive because it provides results that are continuously refined as the text becomes more specific.

**Consider showing suggested search terms.** For example, you can display recent searches before search begins, or predictive search suggestions as a person types. This can help someone search faster, even when the search itself doesn’t begin immediately.

**Simplify search results.** Provide the most relevant search results first to minimize the need for someone to scroll to find what they’re looking for. In addition to prioritizing the most likely results, consider categorizing them to help people find what they want.

**Consider letting people filter search results.** For example, you can include a scope bar in the search results content area to help people quickly and easily filter search results.


### Scope bars and tokens

Scope bars and tokens are components you can use to let someone narrow the parameters of a search either before or after they make it.

- A *scope bar* is a control for filtering and adjusting the scope of a search.

- A *token* is a visual representation of a search term that someone can select and edit, and acts as a filter for any additional terms in the search.

**Use a scope bar to filter among clearly defined search categories.** A scope bar can help someone move from a broader scope to a narrower one. For example, in a mail app on phone, a scope bar helps people move from searching their entire mailbox to just the specific mailbox they’re viewing.

**Default to a broader scope and let people refine it as they need.** A broader scope provides context for the full set of available results, which helps guide people in a useful direction when they choose to narrow the scope.

**Use tokens to filter by common search terms or items.** When you define a token, the term it represents gains a visual treatment that encapsulates it, indicating that people can select and edit it as a single item. Tokens can clarify a search term, like filtering by a specific contact in a mail app, or focus a search to a specific set of attributes, like filtering by photos in a messaging app. For the related desktop component, see Token fields.

**Consider pairing tokens with search suggestions.** People may not know which tokens are available, so pairing them with search suggestions can help people learn how to use them.


### Device-specific considerations


#### Phone
There are three main places you can position the entry point for search:

- As a tab in a tab bar

- In a toolbar at the bottom or top of the screen

- Directly inline with content

Where search makes the most sense depends on the layout, content, and navigation of your app.


##### Search as a tab

You can place search as a tab in a tab bar, which keeps search visible and always available as people switch between the sections of your app. There are two styles of search tabs:

- **Standard tab.** This style displays the search tab uniformly with the rest of the tab bar. Tapping the search tab navigates people to a search landing page with a search field at the top.

- **Button appearance.** This style displays the search tab as a separate button and allows people to start searching immediately. Tapping the search tab brings focus to the search field and displays the keyboard.

**Choose the standard tab style to provide suggestions, promote discovery, and encourage exploration.** This style of search tab creates a dedicated landing page for search, providing an opportunity to reveal any content or suggestions that might be helpful before someone taps the field to begin the search. This approach is great for an app with a variety of rich content that people might want to explore.

**Choose the button appearance to help people quickly find what they need.** When someone interacts with this style of search tab, the keyboard immediately appears with the search field above it, ready to begin the search. This approach provides a more transient experience that brings people directly back to their previous tab after they exit search, and is ideal when you want search to resolve quickly and seamlessly.


##### Search in a toolbar

As an alternative to search in a tab bar, you can also place search in a toolbar either at the bottom or top of the screen.

- You can include search in a bottom toolbar either as an expanded field or as a toolbar button, depending on how much space is available. When someone taps it, it animates into a search field above the keyboard so they can begin typing.

- You can include search in a top toolbar, also called a navigation bar, where it appears as a toolbar button. When someone taps it, it animates into a search field that appears either above the keyboard or at the top if there isn’t space at the bottom.

**Place search at the bottom if there’s room.** You can either add a search field to an existing toolbar, or as a new toolbar where search is the only item. Search at the bottom is useful in any situation where search is a priority, since it keeps the search experience easy to reach. Examples of apps with search at the bottom in various toolbar layouts include Settings, where it’s the only item, and a mail app and a notes app, where it fits alongside other important controls.

**Place search at the top when itʼs important to defer to content at the bottom of the screen, or thereʼs no bottom toolbar.** Use search at the top in cases where covering the content might interfere with a primary function of the app. The a wallet app, for example, includes event passes in a stack at the bottom of the screen for easy access and viewing at a glance.


##### Search as an inline field

In some cases you might want your app to include a search field inline with content.

**Place search as an inline field when its position alongside the content it searches strengthens that relationship.** When you need to filter or search within a single view, it can be helpful to have search appear directly next to content to illustrate that the search applies to it, rather than globally. This pattern is useful if your app has more than one search field and if location plays a critical role in the scope of your search. For example, although the main search in the music app is a tab, people can navigate to their library and use an inline search field to filter their songs and albums.

**When at the top, position an inline search field above the list it searches, and consider pinning it to the top toolbar when scrolling.** This helps keep it distinct from search that appears in other locations.


#### Tablet & desktop
The placement and behavior of the search field on tablets and desktop is similar. If your app is available on both tablet and desktop, try to keep the search experience as consistent as possible across both platforms.

**Put a search field at the trailing side of the toolbar for many common uses.** Many apps benefit from the familiar pattern of search in the toolbar, particularly apps with split views that need to search across multiple columns of information, like a mail app, a notes app, and a voice memo app. This placement makes great use of space because it lets people navigate results while keeping their selection visible in the detail view. Additionally, consider placing search in the toolbar if results appear in the detail view of your app, like in a whiteboard app, where search in the toolbar filters the boards in the detail view below.

**Include search at the top of the sidebar when filtering content or navigation there.** Apps such as Settings take advantage of search to quickly filter the sidebar and expose sections that may be multiple levels deep, providing a simple way for people to search, preview, and navigate to the section or setting they’re looking for. This approach is useful if your app has a rich detail view and you need to create a distinct separation between the sidebar you’re filtering and the adjacent view.

**Include search as an item in the sidebar or tab bar when you want an area dedicated to discovery.** If your search is paired with rich suggestions, categories, or content that needs more space, it can be helpful to have a dedicated area for it. A dedicated area also ensures search is always available as people navigate and switch sections of your app.

**In a search field in a dedicated area, consider immediately focusing the field when a person navigates to the area to help them search faster and locate the field more easily.** An exception to this is on tablet when only a virtual keyboard is available, in which case it’s better to leave the field unfocused to prevent the keyboard from unexpectedly covering the view.

**Account for window resizing with the placement of the search field.** On tablet, the search field fluidly resizes with the app window like it does on desktop. However, for compact views on tablet, itʼs important to ensure that search is available where it’s most contextually useful. For example, a notes app and a mail app place search above the column for the content list when they resize down to a compact view.


## Sidebars

A sidebar appears on the leading side of a view and lets people navigate between areas of your app or top-level collections of content, like folders and playlists.

A sidebar requires a large amount of vertical and horizontal space. When space is limited or you want to devote more of the screen to other information or functionality, a more compact control such as a tab bar may provide a better navigation experience. For many apps, you don’t need to choose between a tab bar or sidebar for navigation; instead, you can adopt a style of tab bar that provides both. For guidance, see Tab bars and Layout.


### Best practices

**Extend visually rich content beneath the sidebar.** On phones, tablets and desktop, as with other controls such as toolbars and tab bars, sidebars can float above content in the glass layer. To reinforce the separation, you can extend content beneath the sidebar either by letting it horizontally scroll or by applying a *background extension effect*. A background extension effect mirrors adjacent content to give the impression of stretching it under the sidebar.

**When possible, let people customize the contents of a sidebar.** A sidebar lets people navigate to important areas in your app, so it works well when people can decide which areas are most important and in what order they appear.

**Group hierarchy with disclosure controls if your app has a lot of content.** Using disclosure controls helps keep the sidebar’s vertical space to a manageable level.

**Consider using familiar symbols to represent items in the sidebar.** The symbol library provides a wide range of customizable symbols you can use to represent items in your app. If you need to use a custom icon, consider creating a custom symbol rather than using a bitmap image.

**Consider letting people hide the sidebar.** People sometimes want to hide the sidebar to create more room for content details or to reduce distraction. When possible, let people hide and show the sidebar using the platform-specific interactions they already know. For example, on tablets, people expect to use the built-in edge swipe gesture; on desktop, you can include a show/hide button or add Show Sidebar and Hide Sidebar commands to your app’s View menu. Avoid hiding the sidebar by default to ensure that it remains discoverable.

**In general, show no more than two levels of hierarchy in a sidebar.** When a data hierarchy is deeper than two levels, consider using a split view interface that includes a content list between the sidebar items and detail view.

**If you need to include two levels of hierarchy in a sidebar, use succinct, descriptive labels to title each group.** To help keep labels short, omit unnecessary words.

**Make sure any sidebar icon colors you choose serve a clear purpose.** By default, sidebar icons use your app’s accent color. On desktop, people can change the system accent color, which applies to all apps. When they do this, they expect all sidebar icons to appear in that color, so make sure your sidebar icons display the color people choose. However, if you use them sparingly, fixed colors can help clarify the meaning of an icon or draw attention to it. For example, the VIP icon in a mail app uses a yellow color to set it apart from other sidebar icons, providing a visual cue about its importance.


### Device-specific considerations

#### Phone & tablet
When you use the sidebarAdaptable style of tab view to present a sidebar, you choose whether to display a sidebar or a tab bar when your app opens. Both variations include a button that people can use to switch between them. This style also adapts its appearance depending on the platform, and responds automatically to rotation and window resizing, providing a version of the control that’s appropriate to the width of the view.


**Consider using a tab bar first.** A tab bar provides more space to feature content, and offers enough flexibility to navigate between many apps’ main areas. If you need to expose more areas than fit in a tab bar, the tab bar’s convertible sidebar-style appearance can provide access to content that people use less frequently. For guidance, see Tab bars.


#### Desktop
A sidebar’s row height, text, and glyph size depend on its overall size, which can be small, medium, or large. You can set the size programmatically, but people can also change it by selecting a different sidebar icon size in General settings.

**Consider automatically hiding and revealing a sidebar when its container window resizes.** For example, reducing the size of a mail app viewer window can automatically collapse its sidebar, making more room for message content.

**Avoid putting critical information or actions at the bottom of a sidebar.** People often relocate a window in a way that hides its bottom edge.


## Tab bars

A tab bar lets people navigate between top-level sections of your app.

Tab bars help people understand the different types of information or functionality that an app provides. They also let people quickly switch between sections of the view while preserving the current navigation state within each section.


### Best practices

**Use a tab bar to support navigation, not to provide actions.** A tab bar lets people navigate among different sections of an app, like the Alarm, Stopwatch, and Timer tabs in the clock app. If you need to provide controls that act on elements in the current view, use a toolbar instead.

**Make sure the tab bar is visible when people navigate to different sections of your app.** If you hide the tab bar, people can forget which area of the app they’re in. The exception is when a modal view covers the tab bar, because a modal is temporary and self-contained.

**Use the appropriate number of tabs required to help people navigate your app.** As a representation of your app’s hierarchy, it’s important to weigh the complexity of additional tabs against the need for people to frequently access each section; keep in mind that it’s generally easier to navigate among fewer tabs. Where available, consider a sidebar or a tab bar that adapts to a sidebar as an alternative for an app with a complex information structure.

**Avoid overflow tabs.** Depending on device size and orientation, the number of visible tabs can be smaller than the total number of tabs. If horizontal space limits the number of visible tabs, the trailing tab becomes a More tab on phones and tablets, revealing the remaining items in a separate list. The More tab makes it harder for people to reach and notice content on tabs that are hidden, so limit scenarios in your app where this can happen.

**Don’t disable or hide tab bar buttons, even when their content is unavailable.** Having tab bar buttons available in some cases but not others makes your app’s interface appear unstable and unpredictable. If a section is empty, explain why its content is unavailable.

**Include tab labels to help with navigation.** A tab label appears beneath or beside a tab bar icon, and can aid navigation by clearly describing the type of content or functionality the tab contains. Use single words whenever possible.

**Consider using the symbol library to provide familiar, scalable tab bar icons.** When you use the symbol library, tab bar icons automatically adapt to different contexts. For example, the tab bar can be regular or compact, depending on the device and orientation. Tab bar icons appear above tab labels in compact views, whereas in regular views, the icons and labels appear side by side. Prefer filled symbols or icons for consistency with the platform.


**Use a badge to indicate that critical information is available.** You can display a badge — a red oval containing white text and either a number or an exclamation point — on a tab to indicate that there’s new or updated information in the section that warrants a person’s attention. Reserve badges for critical information so you don’t dilute their impact and meaning. For guidance, see Notifications.

**Avoid applying a similar color to tab labels and content layer backgrounds.** If your app already has bright, colorful content in the content layer, prefer a monochromatic appearance for tab bars, or choose an accent color with sufficient visual differentiation. For more guidance, see glass color.


### Device-specific considerations

#### Phone
A tab bar floats above content at the bottom of the screen. Its items rest on a glass background that allows content beneath to peek through.

For tab bars with an attached accessory, like the MiniPlayer in a music app, you can choose to minimize the tab bar and move the accessory inline with it when a person scrolls down. A person can exit the minimized state by tapping a tab or scrolling to the top of the view.

A tab bar can include a dedicated search tab at the trailing end. For guidance, see Search fields.


#### Tablet
The system displays a tab bar near the top of the screen. You can choose to have the tab bar appear as a fixed element, or with a button that converts it to a sidebar.

> **Note**: To present a sidebar without the option to convert it to a tab bar, use a navigation split view instead of a tab view. For guidance, see Sidebars.

**Prefer a tab bar for navigation.** A tab bar provides access to the sections of your app that people use most. If your app is more complex, you can provide the option to convert the tab bar to a sidebar so people can access a wider set of navigation options.

**Let people customize the tab bar.** In apps with a lot of sections that people might want to access, it can be useful to let people select items that they use frequently and add them to the tab bar, or remove items that they use less frequently. For example, in the music app, a person can choose a favorite playlist to display in the tab bar. If you let people select their own tabs, aim for a default list of five or fewer to preserve continuity between compact and regular view sizes.


## Token fields

A token field is a type of text field that can convert text into *tokens* that are easy to select and manipulate.

For example, a mail app uses token fields for the address fields in the compose window. As people enter recipients, a mail app converts the text that represents each recipient’s name into a token. People can select these recipient tokens and drag to reorder them or move them into a different field.

You can configure a token field to present people with a list of suggestions as they enter text into the field. For example, a mail app suggests recipients as people type in an address field. When people select a suggested recipient, a mail app inserts the recipient into the field as a token.

An individual token can also include a contextual menu that offers information about the token or editing options. For example, a recipient token in a mail app includes a contextual menu with commands for editing the recipient name, marking the recipient as a VIP, and viewing the recipient’s contact card, among others.

Tokens can also represent search terms in some situations; for guidance, see Search fields.


### Best practices

**Add value with a context menu.** People often benefit from a context menu with additional options or information about a token.

**Consider providing additional ways to convert text into tokens.** By default, text people enter turns into a token whenever they type a comma. You can specify additional shortcuts, such as pressing Return, that also invoke this action.

**Consider customizing the delay the system uses before showing suggested tokens.** By default, suggestions appear immediately. However, suggestions that appear too quickly may distract people while they’re typing. If your app suggests tokens, consider adjusting the delay to a comfortable level.


---

## Action sheets

An action sheet is a modal view that presents choices related to an action people initiate.


### Best practices

**Use an action sheet — not an alert — to offer choices related to an intentional action.** For example, when people cancel the message they’re editing in a mail app on phone, an action sheet provides two choices: delete the draft, or save the draft. Although an alert can also help people confirm or cancel an action that has destructive consequences, it doesn’t provide additional choices related to the action. More importantly, an alert is usually unexpected, generally telling people about a problem or a change in the current situation that might require them to act. For guidance, see Alerts.

**Use action sheets sparingly.** Action sheets give people important information and choices, but they interrupt the current task to do so. To encourage people to pay attention to action sheets, avoid using them more than necessary.

**Aim to keep titles short enough to display on a single line.** A long title is difficult to read quickly and might get truncated or require people to scroll.

**Provide a message only if necessary.** In general, the title — combined with the context of the current action — provides enough information to help people understand their choices.


**Make destructive choices visually prominent.** Use the destructive style for buttons that perform destructive actions, and place these buttons at the top of the action sheet where they tend to be most noticeable.


### Device-specific considerations

#### Phone & tablet
**Use an action sheet — not a menu — to provide choices related to an action.** People are accustomed to having an action sheet appear when they perform an action that might require clarifying choices. In contrast, people expect a menu to appear when they choose to reveal it.

**Avoid letting an action sheet scroll.** The more buttons an action sheet has, the more time and effort it takes for people to make a choice. Also, scrolling an action sheet can be hard to do without inadvertently tapping a button.


## Alerts

An alert gives people critical information they need right away.

For example, an alert can tell people about a problem, warn them when their action might destroy data, and give them an opportunity to confirm a purchase or another important action they initiated.


### Best practices

**Use alerts sparingly.** Alerts give people important information, but they interrupt the current task to do so. Encourage people to pay attention to your alerts by making certain that each one offers only essential information and useful actions.

**Avoid using an alert merely to provide information.** People don’t appreciate an interruption from an alert that’s informative, but not actionable. If you need to provide only information, prefer finding an alternative way to communicate it within the relevant context. For example, when a server connection is unavailable, a mail app displays an indicator that people can choose to learn more.

**Avoid displaying alerts for common, undoable actions, even when they’re destructive.** For example, you don’t need to alert people about data loss every time they delete an email or file because they do so with the intention of discarding data, and they can undo the action. In comparison, when people take an uncommon destructive action that they can’t undo, it’s important to display an alert in case they initiated the action accidentally.

**Avoid showing an alert when your app starts.** If you need to inform people about new or important information the moment they open your app, design a way to make the information easily discoverable. If your app detects a problem at startup, like no network connection, consider alternative ways to let people know. For example, you could show cached or placeholder data and a nonintrusive label that describes the problem.


### Anatomy

An alert is a modal view that can look different in different platforms and devices.


### Content

In all platforms, alerts display a title, optional informative text, and up to three buttons. On some platforms, alerts can include additional elements.

- On phones, tablets and desktop, an alert can include a text field.

- Alerts on desktop can include an icon and an accessory view.

- Desktop alerts can add a suppression checkbox and a Help button.

**In all alert copy, be direct, and use a neutral, approachable tone.** Alerts often describe problems and serious situations, so avoid being oblique or accusatory, or masking the severity of the issue.

**Write a title that clearly and succinctly describes the situation.** You need to help people quickly understand the situation, so be complete and specific, without being verbose. As much as possible, describe what happened, the context in which it happened, and why. Avoid writing a title that doesn’t convey useful information — like “Error” or “Error 329347 occurred” — but also avoid overly long titles that wrap to more than two lines. If the title is a complete sentence, use sentence-style capitalization and appropriate ending punctuation. If the title is a sentence fragment, use title-style capitalization, and don’t add ending punctuation.

**Include informative text only if it adds value.** If you need to add an informative message, keep it as short as possible, using complete sentences, sentence-style capitalization, and appropriate punctuation.

**Avoid explaining alert buttons.** If your alert text and button titles are clear, you don’t need to explain what the buttons do. In rare cases where you need to provide guidance on choosing a button, use a term like *choose* to account for people’s current device and interaction method, and refer to a button using its exact title without quotes. For guidance, see Buttons.

**If supported, include a text field only if you need people’s input to resolve the situation.** For example, you might need to present a secure text field to receive a password.


### Buttons

**Create succinct, logical button titles.** Aim for a one- or two-word title that describes the result of selecting the button. Prefer verbs and verb phrases that relate directly to the alert text — for example, “View All,” “Reply,” or “Ignore.” In informational alerts only, you can use “OK” for acceptance, avoiding “Yes” and “No.” Always use “Cancel” to title a button that cancels the alert’s action. As with all button titles, use title-style capitalization and no ending punctuation.

**Avoid using OK as the default button title unless the alert is purely informational.** The meaning of “OK” can be unclear even in alerts that ask people to confirm that they want to do something. For example, does “OK” mean “OK, I want to complete the action” or “OK, I now understand the negative results my action would have caused”? A specific button title like “Erase,” “Convert,” “Clear,” or “Delete” helps people understand the action they’re taking.

**Place buttons where people expect.** In general, place the button people are most likely to choose on the trailing side in a row of buttons or at the top in a stack of buttons. Always place the default button on the trailing side of a row or at the top of a stack. Cancel buttons are typically on the leading side of a row or at the bottom of a stack.

**Use the destructive style to identify a button that performs a destructive action people didn’t deliberately choose.** For example, when people deliberately choose a destructive action — such as Empty Trash — the resulting alert doesn’t apply the destructive style to the Empty Trash button because the button performs the person’s original intent. In this scenario, the convenience of pressing Return to confirm the deliberately chosen Empty Trash action outweighs the benefit of reaffirming that the button is destructive. In contrast, people appreciate an alert that draws their attention to a button that can perform a destructive action they didn’t originally intend.

**If there’s a destructive action, include a Cancel button to give people a clear, safe way to avoid the action.** Always use the title “Cancel” for a button that cancels an alert’s action. Note that you don’t want to make a Cancel button the default button. If you want to encourage people to read an alert and not just automatically press Return to dismiss it, avoid making any button the default button. Similarly, if you must display an alert with a single button that’s also the default, use a Done button, not a Cancel button.

**Provide alternative ways to cancel an alert when it makes sense.** In addition to choosing a Cancel button, people appreciate using keyboard shortcuts or other quick ways to cancel an onscreen alert. For example:

| Action | Platform |
| --- | --- |
| Exit to the home screen | phones and tablets |
| Pressing Escape (Esc) (or Cmd-Period on Mac) on an attached keyboard | phones, tablets and desktop |


### Device-specific considerations

#### Phone & tablet
**Use an action sheet — not an alert — to offer choices related to an intentional action.** For example, when people cancel the mail app message they’re editing, an action sheet provides three choices: delete the edits (or the entire draft), save the draft, or return to editing. Although an alert can also help people confirm or cancel an action that has destructive consequences, it doesn’t provide additional choices related to the action. For guidance, see Action sheets.

**When possible, avoid displaying an alert that scrolls.** Although an alert might scroll if the text size is large enough, be sure to minimize the potential for scrolling by keeping alert titles short and including a brief message only when necessary.


#### Desktop
Desktop automatically displays your app icon in an alert, but you can supply an alternative icon or symbol. In addition, desktop lets you:

- Configure repeating alerts to let people suppress subsequent occurrences of the same alert.

- Append a custom view if it’s necessary to provide additional information.

- Include a Help button that opens your help documentation (see Help buttons).

**Use a caution symbol sparingly.** Using a caution symbol like exclamationmark.triangle too frequently in your alerts diminishes its significance. Use the symbol only when extra attention is really needed, as when confirming an action that might result in unexpected loss of data. Don’t use the symbol for tasks whose only purpose is to overwrite or remove data, such as a save or empty trash.


## Page controls

A page control displays a row of indicator images, each of which represents a page in a flat list.

The scrolling row of indicators helps people navigate the list to find the page they want. Page controls can handle an arbitrary number of pages, making them particularly useful in situations where people can create custom lists.

Page controls appear as a series of small indicator dots by default, representing the available pages. A solid dot denotes the current page. Visually, these dots are always equidistant, and are clipped if there are too many to fit in the window.


### Best practices

**Use page controls to represent movement between an ordered list of pages.** Page controls don’t represent hierarchical or nonsequential page relationships. For more complex navigation, consider using a sidebar or split view instead.

**Center a page control at the bottom of the view or window.** To ensure people always know where to find a page control, center it horizontally and position it near the bottom of the view.

**Although page controls can handle any number of pages, don’t display too many**. More than about 10 dots are hard to count at a glance. If your app needs to display more than 10 pages as peers, consider using a different arrangement‚ such as a grid, that lets people navigate the content in any order.


### Customizing indicators

By default, a page control uses the system-provided dot image for all indicators, but it can also display a unique image to help people identify a specific page. For example, a weather app uses the location.fill symbol to distinguish the current location’s page.

If it enhances your app or game, you can provide a custom image to use as the default image for all indicators and you can also supply a different image for a specific page.

**Make sure custom indicator images are simple and clear.** Avoid complex shapes, and don’t include negative space, text, or inner lines, because these details can make an icon muddy and indecipherable at very small sizes. Consider using simple the symbol library as indicators or design your own icons. For guidance, see Icons.

**Customize the default indicator image only when it enhances the page control’s overall meaning.** For example, if every page you list contains bookmarks, you might use the bookmark.fill symbol as the default indicator image.

**Avoid using more than two different indicator images in a page control.** If your list contains one page with special meaning — like the current-location page in a weather app — you can make the page easy to find by giving it a unique indicator image. In contrast, a page control that uses several unique images to mark several important pages is hard to use because people must memorize the meaning of each image. A page control that displays more than two types of indicator images tends to look messy and haphazard, even when each image is clear.

**Avoid coloring indicator images.** Custom colors can reduce the contrast that differentiates the current-page indicator and makes the page control visible on the screen. To ensure that your page control is easy to use and looks good in different contexts, let the system automatically color the indicators.


### Device-specific considerations

#### Phone & tablet
A page control can adjust the appearance of indicators to provide more information about the list. For example, the control highlights the indicator of the current page so people can estimate the page’s relative position in the list. When there are more indicators than fit in the space, the control can shrink indicators at both sides to suggest that more pages are available.

People interact with page controls by tapping or scrubbing (to *scrub*, people touch the control and drag left or right). Tapping on the leading or trailing side of the current-page indicator reveals the next or previous page; on tablets, people can also use the pointer to target a specific indicator. Scrubbing opens pages in sequence, and scrubbing past the leading or trailing edge of the control helps people quickly reach the first or last page.


**Avoid animating page transitions during scrubbing.** People can scrub very quickly, and using the scrolling animation for every transition can make your app lag and cause distracting visual flashes. Use the animated scrolling transition only for tapping.

A page control can include a translucent, rounded-rectangle background appearance that provides visual contrast for the indicators. You can choose one of the following background styles:

- Automatic — Displays the background only when people interact with the control. Use this style when the page control isn’t the primary navigational element in the UI.

- Prominent — Always displays the background. Use this style only when the control is the primary navigational control in the screen.

- Minimal — Never displays the background. Use this style when you just want to show the position of the current page in the list and you don’t need to provide visual feedback during scrubbing.


**Avoid supporting the scrubber when you use the minimal background style.** The minimal style doesn’t provide visual feedback during scrubbing. If you want to let people scrub a list of pages in your app, use the automatic or prominent background styles.


## Panels

In a desktop app, a panel typically floats above other open windows providing supplementary controls, options, or information related to the active window or current selection.

In general, a panel has a less prominent appearance than an app’s main window. When the situation calls for it, a panel can also use a dark, translucent style to support a heads-up display (or *HUD*) experience.

When your app runs in other platforms, consider using a modal view to present supplementary content that’s relevant to the current task or selection. For guidance, see Modality.


### Best practices

**Use a panel to give people quick access to important controls or information related to the content they’re working with.** For example, you might use a panel to provide controls or settings that affect the selected item in the active document or window.

**Consider using a panel to present inspector functionality.** An *inspector* displays the details of the currently selected item, automatically updating its contents when the item changes or when people select a new item. In contrast, if you need to present an *Info* window — which always maintains the same contents, even when the selected item changes — use a regular window, not a panel. Depending on the layout of your app, you might also consider using a split view pane to present an inspector.

**Prefer simple adjustment controls in a panel.** As much as possible, avoid including controls that require typing text or selecting items to act upon because these actions can require multiple steps. Instead, consider using controls like sliders and steppers because these components can give people more direct control.

**Write a brief title that describes the panel’s purpose.** Because a panel often floats above other open windows in your app, it needs a title bar so people can position it where they want. Create a short title using a noun — or a noun phrase with title-style capitalization — that can help people recognize the panel onscreen. For example, desktop provides familiar panels titled “Fonts” and “Colors,” and many apps use the title “Inspector.”

**Show and hide panels appropriately.** When your app becomes active, bring all of its open panels to the front, regardless of which window was active when the panel opened. When your app is inactive, hide all of its panels.

**Avoid including panels in the Window menu’s documents list.** It’s fine to include commands for showing or hiding panels in the Window menu, but panels aren’t documents or standard app windows, and they don’t belong in the Window menu’s list.

**In general, avoid making a panel’s minimize button available.** People don’t usually need to minimize a panel, because it displays only when needed and disappears when the app is inactive.

**Refer to panels by title in your interface and in help documentation.** In menus, use the panel’s title without including the term *panel*: for example, “Show Fonts,” “Show Colors,” and “Show Inspector.” In help documentation, it can be confusing to introduce “panel” as a different type of window, so it’s generally best to refer to a panel by its title or — when it adds clarity — by appending *window* to the title. For example, the title “Inspector” often supplies enough context to stand on its own, whereas it can be clearer to use “Fonts window” and “Colors window” instead of just “Fonts” and “Colors.”


### HUD-style panels

A HUD-style panel serves the same function as a standard panel, but its appearance is darker and translucent. HUDs work well in apps that present highly visual content or that provide an immersive experience, such as media editing or a full-screen slide show. For example, QuickTime Player uses a HUD to display inspector information without obstructing too much content.

**Prefer standard panels.** People can be distracted or confused by a HUD when there’s no logical reason for its presence. Also, a HUD might not match the current appearance setting. In general, use a HUD only:

- In a media-oriented app that presents movies, photos, or slides

- When a standard panel would obscure essential content

- When you don’t need to include controls — with the exception of the disclosure triangle, most system-provided controls don’t match a HUD’s appearance.

**Maintain one panel style when your app switches modes.** For example, if you use a HUD when your app is in full-screen mode, prefer maintaining the HUD style when people take your app out of full-screen mode.

**Use color sparingly in HUDs.** Too much color in the dark appearance of a HUD can be distracting. Often, you need only small amounts of high-contrast color to highlight important information in a HUD.

**Keep HUDs small.** HUDs are designed to be unobtrusively useful, so letting them grow too large defeats their primary purpose. Don’t let a HUD obscure the content it adjusts, and make sure it doesn’t compete with the content for people’s attention.


---

## Popovers

A popover is a transient view that appears above other content when people click or tap a control or interactive area.


### Best practices

**Use a popover to expose a small amount of information or functionality.** Because a popover disappears after people interact with it, limit the amount of functionality in the popover to a few related tasks. For example, a calendar event popover makes it easy for people to change the date or time of an event, or to move it to another calendar. The popover disappears after the change, letting people continue reviewing the events on their calendar.

**Consider using popovers when you want more room for content.** Views like sidebars and panels take up a lot of space. If you need content only temporarily, displaying it in a popover can help streamline your interface.

**Position popovers appropriately.** Make sure a popover’s arrow points as directly as possible to the element that revealed it. Ideally, a popover doesn’t cover the element that revealed it or any essential content people may need to see while using it.

**Use a Close button for confirmation and guidance only.** A Close button, including Cancel or Done, is worth including if it provides clarity, like exiting with or without saving changes. Otherwise, a popover generally closes when people click or tap outside its bounds or select an item in the popover. If multiple selections are possible, make sure the popover remains open until people explicitly dismiss it or they click or tap outside its bounds.

**Always save work when automatically closing a nonmodal popover.** People can unintentionally dismiss a nonmodal popover by clicking or tapping outside its bounds. Discard people’s work only when they click or tap an explicit Cancel button.

**Show one popover at a time.** Displaying multiple popovers clutters the interface and causes confusion. Never show a cascade or hierarchy of popovers, in which one emerges from another. If you need to show a new popover, close the open one first.

**Don’t show another view over a popover.** Make sure nothing displays on top of a popover, except for an alert.

**When possible, let people close one popover and open another with a single click or tap.** Avoiding extra gestures is especially desirable when several different bar buttons each open a popover.

**Avoid making a popover too big.** Make a popover only big enough to display its contents and point to the place it came from. If necessary, the system can adjust the size of a popover to ensure it fits well in the interface.

**Provide a smooth transition when changing the size of a popover.** Some popovers provide both condensed and expanded views of the same information. If you adjust the size of a popover, animate the change to avoid giving the impression that a new popover replaced the old one.

**Avoid using the word *popover* in help documentation.** Instead, refer to a specific task or selection. For example, instead of “Select the Show button at the bottom of the popover,” you might write “Select the Show button.”

**Avoid using a popover to show a warning.** People can miss a popover or accidentally close it. If you need to warn people, use an alert instead.


### Device-specific considerations

#### Phone & tablet
**Avoid displaying popovers in compact views.** Make your app or game dynamically adjust its layout based on the size class of the content area. Reserve popovers for wide views; for compact views, use all available screen space by presenting information in a full-screen modal view like a sheet instead. For related guidance, see Modality.


#### Desktop
You can make a popover detachable on desktop, which becomes a separate panel when people drag it. The panel remains visible onscreen while people interact with other content.

**Consider letting people detach a popover.** People might appreciate being able to convert a popover into a panel if they want to view other information while the popover remains visible.

**Make minimal appearance changes to a detached popover.** A panel that looks similar to the original popover helps people maintain context.


---

## Scroll views

A scroll view lets people view content that’s larger than the view’s boundaries by moving the content vertically or horizontally.

The scroll view itself has no appearance, but it can display a translucent *scroll indicator* that typically appears after people begin scrolling the view’s content. Although the appearance and behavior of scroll indicators can vary per platform, all indicators provide visual feedback about the scrolling action. For example, on phones, tablets and desktop, the indicator shows whether the currently visible content is near the beginning, middle, or end of the view.


### Best practices

**Support default scrolling gestures and keyboard shortcuts.** People are accustomed to the systemwide scrolling behavior and expect it to work everywhere. If you build custom scrolling for a view, make sure your scroll indicators use the elastic behavior that people expect.

**Make it apparent when content is scrollable.** Because scroll indicators aren’t always visible, it can be helpful to make it obvious when content extends beyond the view. For example, displaying partial content at the edge of a view indicates that there’s more content in that direction. Although most people immediately try scrolling a view to discover if additional content is available, it’s considerate to draw their attention to it.

**Avoid putting a scroll view inside another scroll view with the same orientation.** Nesting scroll views that have the same orientation can create an unpredictable interface that’s difficult to control. It’s alright to place a horizontal scroll view inside a vertical scroll view (or vice versa), however.

**Consider supporting page-by-page scrolling if it makes sense for your content.** In some situations, people appreciate scrolling by a fixed amount of content per interaction instead of scrolling continuously. On most platforms, you can define the size of such a *page* — typically the current height or width of the view — and define an interaction that scrolls one page at a time. To help maintain context during page-by-page scrolling, you can define a unit of overlap, such as a line of text, a row of glyphs, or part of a picture, and subtract the unit from the page size.

**In some cases, scroll automatically to help people find their place.** Although people initiate almost all scrolling, automatic scrolling can be helpful when relevant content is no longer in view, such as when:

- Your app performs an operation that selects content or places the insertion point in an area that’s currently hidden. For example, when your app locates text that people are searching for, scroll the content to bring the new selection into view.

- People start entering information in a location that’s not currently visible. For example, if the insertion point is on one page and people navigate to another page, scroll back to the insertion point as soon as they begin to enter text.

- The pointer moves past the edge of the view while people are making a selection. In this case, follow the pointer by scrolling in the direction it moves.

- People select something and scroll to a new location before acting on the selection. In this case, scroll until the selection is in view before performing the operation.

In all cases, automatically scroll the content only as much as necessary to help people retain context. For example, if part of a selection is visible, you don’t need to scroll the entire selection into view.

**If you support zoom, set appropriate maximum and minimum scale values.** For example, zooming in on text until a single character fills the screen doesn’t make sense in most situations.


### Scroll edge effects

On phones, tablets and desktop, a *scroll edge effect* provides a visual separation between certain interface elements, such as toolbars, and the scrolling content area behind them. If you use custom bars, you might want to add this effect manually if the top layer of your interface needs extra clarity, or adjust its style from automatic to the hard or soft style.

**Prefer the automatic scroll edge effect style.** Where possible, use the default automatic style of the scroll edge effect. This style provides a more opaque visual separation for top toolbars that contain a large number of controls, text that appears outside of glass controls, and pinned table headers. If you use the soft scroll edge effect style instead, thoroughly test your interface to ensure your controls maintain legibility in a variety of contexts.

**Only use a scroll edge effect when a scroll view is behind floating interface elements.** Scroll edge effects aren’t decorative. They don’t block or darken like overlays; they exist to ensure controls stay visually distinct.

**Apply one scroll edge effect per view.** In split view layouts on tablet and desktop, each pane can have its own scroll edge effect; in this case, keep them consistent in height to maintain alignment.


### Device-specific considerations


#### Phone & tablet
**Consider showing a page control when a scroll view is in page-by-page mode.** Page controls show how many pages, screens, or other chunks of content are available and indicates which one is currently visible. For example, a weather app uses a page control to indicate movement between people’s saved locations. If you show a page control with a scroll view, don’t show the scrolling indicator on the same axis to avoid confusing people with redundant controls.


#### Desktop
On desktop, a *scroll indicator* is commonly called a *scroll bar*.

**If necessary, use small or mini scroll bars in a panel.** When space is tight, you can use smaller scroll bars in panels that need to coexist with other windows. Be sure to use the same size for all controls in such a panel.


## Sheets

A sheet helps people perform a scoped task that’s closely related to their current context.

A sheet is useful for requesting specific information from people or presenting a simple task that they can complete before returning to the parent view. For example, a sheet might let people supply information needed to complete an action, such as attaching a file or choosing a location to save it.


### Anatomy

On desktop, a sheet is always *modal*. A modal sheet presents a targeted experience that prevents people from interacting with the parent view until they dismiss the sheet (for more on modal presentation, see Modality).

On phones and tablets, a sheet can be either modal or *nonmodal*. When a nonmodal sheet is onscreen, people use its functionality to affect the parent view without dismissing the sheet. For example, a notes app on phone and tablet uses a nonmodal sheet to let people format various text selections as they edit a note.

There are several common buttons that help people navigate through and dismiss sheets.

- The **Cancel** (or Close) button dismisses a sheet without saving any changes. This type of button is common in most sheets.

- The **Done** button dismisses a sheet after completing a task or explicitly saving changes.

- The **Back** button lets people navigate to a previous step in a multi-step flow or to a parent view in a hierarchy. It isn’t intended to dismiss a sheet.

The placement of these buttons varies between platforms; see Platform considerations.


### Best practices

**For complex or prolonged user flows, consider alternatives to sheets.** For example, phones and tablets offer a full-screen style of modal view that can work well to display content like videos, photos, or camera views or to help people perform multistep tasks like document or photo editing. In a desktop experience, you might want to open a new window or let people enter full-screen mode instead of using a sheet. For example, a self-contained task like editing a document tends to work well in a separate window, whereas going full screen can help people view media.

**Display only one sheet at a time from the main interface.** When people close a sheet, they expect to return to the parent view or window. If closing a sheet takes people back to another sheet, they can lose track of where they are in your app. If something people do within a sheet results in another sheet appearing, close the first sheet before displaying the new one. If necessary, you can display the first sheet again after people dismiss the second one.


**Provide an alternative to the Done button.** If you provide a Done button, always pair it with a Cancel button to give people a clear way to dismiss the sheet without confirming or saving their changes, or a Back button to move to a previous step in the sheet. Relying solely on the Done button implies that completing the task is the only way to exit the sheet, which can feel restrictive or misleading.

Avoid showing all three buttons — Cancel, Done, and Back — together.


### Device-specific considerations

#### Phone & tablet
On phones and tablets, for sheets with a single view, the Cancel button belongs on the leading edge of the top toolbar. When present, the Done button belongs on the trailing edge.

For sheets with a multi-step flow, the placement of buttons can vary across steps.

A resizable sheet expands when people scroll its contents or drag the *grabber*, which is a small horizontal indicator that can appear at the top edge of a sheet. Sheets resize according to their *detents*, which are particular heights at which a sheet naturally rests. Designed for phone, detents specify particular heights at which a sheet naturally rests. The system defines two detents: *large* is the height of a fully expanded sheet and *medium* is about half of the fully expanded height. Sheets can have one or more custom detent values.

Sheets automatically support the large detent. Adding the medium detent allows the sheet to rest at both heights, whereas specifying only medium prevents the sheet from expanding to full height.

**In a phone app, consider supporting the medium detent to allow progressive disclosure of the sheet’s content.** For example, a share sheet displays the most relevant items within the medium detent, where they’re visible without resizing. To view more items, people can scroll or expand the sheet. In contrast, you might not want to support the medium detent if a sheet’s content is more useful when it displays at full height. For example, the compose sheets in a messaging app and a mail app display only at full height to give people enough room to create content.

**Include a grabber in a resizable sheet.** A grabber shows people that they can drag the sheet to resize it; they can also tap it to cycle through the detents. In addition to providing a visual indicator of resizability, a grabber also works with the screen reader so people can resize the sheet without seeing the screen.

**Support swiping to dismiss a sheet.** People expect to swipe vertically to dismiss a sheet instead of tapping a dismiss button. If people have unsaved changes in the sheet when they begin swiping to dismiss it, use an action sheet to let them confirm their action.

**Prefer using the page or form sheet presentation styles in an tablet app.** Each style uses a default size for the sheet, centering its content on top of a dimmed background view and providing a consistent experience.


#### Desktop
On desktop, a sheet is a cardlike view with rounded corners that floats on top of its parent window. The parent window is dimmed while the sheet is onscreen, signaling that people can’t interact with it until they dismiss the sheet. However, people expect to interact with other app windows before dismissing a sheet.

**Present a sheet in a reasonable default size.** People don’t generally expect to resize sheets, so it’s important to use a size that’s appropriate for the content you display. In some cases, however, people appreciate a resizable sheet — such as when they need to expand the contents for a clearer view — so it’s a good idea to support resizing.

**Let people interact with other app windows without first dismissing a sheet.** When a sheet opens, you bring its parent window to the front — if the parent window is a document window, you also bring forward its modeless document-related panels. When people want to interact with other windows in your app, make sure they can bring those windows forward even if they haven’t dismissed the sheet yet.

**Use a panel instead of a sheet if people need to repeatedly provide input and observe results.** A find and replace panel, for example, might let people initiate replacements individually, so they can observe the result of each search for correctness. For guidance, see Panels.


## Windows

A window presents UI views and components in your app or game.

On tablets and desktop, windows help define the visual boundaries of app content and separate it from other areas of the system, and enable multitasking workflows both within and between apps. Windows include system-provided interface elements such as frames and window controls that let people open, close, resize, and relocate them.

Conceptually, apps use two types of windows to display content:

- A *primary* window presents the main navigation and content of an app, and actions associated with them.

- An *auxiliary* window presents a specific task or area in an app. Dedicated to one experience, an auxiliary window doesn’t allow navigation to other app areas, and it typically includes a button people use to close it after completing the task.

For guidance laying out content within a window on any platform, see Layout.


### Best practices

**Make sure that your windows adapt fluidly to different sizes to support multitasking and multiwindow workflows.** For guidance, see Layout and Multitasking.

**Choose the right moment to open a new window.** Opening content in a separate window is great for helping people multitask or preserve context. For example, a mail app opens a new window whenever someone selects the Compose action, so both the new message and the existing email are visible at the same time. However, opening new windows excessively creates clutter and can make navigating your app more confusing. Avoid opening new windows as default behavior unless it makes sense for your app.

**Consider providing the option to view content in a new window.** While it’s best to avoid opening new windows as default behavior unless it benefits your user experience, it’s also great to give people the flexibility of viewing content in multiple ways. Consider letting people view content in a new window using a command in a context menu or in the File menu.

**Avoid creating custom window UI.** System-provided windows look and behave in a way that people understand and recognize. Avoid making custom window frames or controls, and don’t try to replicate the system-provided appearance. Doing so without perfectly matching the system’s look and behavior can make your app feel broken.

**Use the term *window* in user-facing content.** The system refers to app windows as *windows* regardless of type. Using different terms — including *scene*, which refers to window implementation — is likely to confuse people.


### Device-specific considerations

#### Tablet
Windows present in one of two ways depending on a person’s choice in Multitasking & Gestures settings.

- **Full screen.** App windows fill the entire screen, and people switch between them — or between multiple windows of the same app — using the app switcher.

- **Windowed.** People can freely resize app windows. Multiple windows can be onscreen at once, and people can reposition them and bring them to the front. The system remembers window size and placement even when an app is closed.

**Make sure window controls don’t overlap toolbar items.** When windowed, app windows include window controls at the leading edge of the toolbar. If your app has toolbar buttons at the leading edge, they might be hidden by window controls when they appear. To prevent this, instead of placing buttons directly on the leading edge, move them inward when the window controls appear.

**Consider letting people use a gesture to open content in a new window.** For example, people can use the pinch gesture to expand a notes app item into a new window.

> **Tip**: If you only need to let people view one file, you can present it without creating your own window, but you must support multiple windows in your app.


#### Desktop
On desktop, people typically run several apps at the same time, often viewing windows from multiple apps on one desktop and switching frequently between different windows — moving, resizing, minimizing, and revealing the windows to suit their work style.


##### desktop window anatomy

A desktop window consists of a frame and a body area. People can move a window by dragging the frame and can often resize the window by dragging its edges.

The *frame* of a window appears above the body area and can include window controls and a toolbar. In rare cases, a window can also display a bottom bar, which is a part of the frame that appears below body content.


##### desktop window states

A desktop window can have one of three states:

- **Main.** The frontmost window that people view is an app’s main window. There can be only one main window per app.

- **Key.** Also called the *active window*, the key window accepts people’s input. There can be only one key window onscreen at a time. Although the front app’s main window is usually the key window, another window — such as a panel floating above the main window — might be key instead. People typically click a window to make it key; when people click an app’s dock icon to bring all of that app’s windows forward, only the most recently accessed window becomes key.

- **Inactive.** A window that’s not in the foreground is an inactive window.

The system gives main, key, and inactive windows different appearances to help people visually identify them. For example, the key window uses color in the title bar options for closing, minimizing, and zooming; inactive windows and main windows that aren’t key use gray in these options. Also, inactive windows don’t use vibrancy (an effect that can pull color into a window from the content underneath it), which makes them appear subdued and seem visually farther away than the main and key windows.

> **Note**: Some windows — typically, panels like Colors or Fonts — become the key window only when people click the window’s title bar or a component that requires keyboard input, such as a text field.

**Make sure custom windows use the system-defined appearances.** People rely on the visual differences between windows to help them identify the foreground window and know which window will accept their input. When you use system-provided components, a window’s background and button appearances update automatically when the window changes state; if you use custom implementations, you need to do this work yourself.

**Avoid putting critical information or actions in a bottom bar, because people often relocate a window in a way that hides its bottom edge.** If you must include one, use it only to display a small amount of information directly related to a window’s contents or to a selected item within it. For example, the file manager uses a bottom bar (called the status bar) to display the total number of items in a window, the number of selected items, and how much space is available on the disk. A bottom bar is small, so if you have more information to display, consider using an inspector, which typically presents information on the trailing side of a split view.


## Color wells

A color well lets people adjust the color of text, shapes, guides, and other onscreen elements.

A color well displays a color picker when people tap or click it. This color picker can be the system-provided one or a custom interface that you design.


### Best practices

**Consider the system-provided color picker for a familiar experience.** Using the built-in color picker provides a consistent experience, in addition to letting people save a set of colors they can access from any app. The system-defined color picker can also help provide a familiar experience when developing apps across phones, tablets and desktop.


### Device-specific considerations

#### Desktop
When people click a color well, it receives a highlight to provide visual confirmation that it’s active. It then opens a color picker so people can choose a color. After they make a selection, the color well updates to show the new color.

Color wells also support drag and drop, so people can drag colors from one color well to another, and from the color picker to a color well.


---

## Combo boxes

A combo box combines a text field with a pull-down button in a single control.

People can enter a custom value into the field or click the button to choose from a list of predefined values. When people enter a custom value, it’s not added to the list of choices.


### Best practices

**Populate the field with a meaningful default value from the list.** Although the field can be empty by default, it’s best when the default value refers to the hidden choices. The default value doesn’t have to be the first item in the list.

**Use an introductory label to let people know what types of items to expect.** Generally, use title-style capitalization for labels and end them with a colon. For related guidance, see Labels.

**Provide relevant choices.** People appreciate the ability to enter a custom value, as well as the convenience of choosing from a list of the most likely choices.

**Make sure list items aren’t wider than the text field.** If an item is too wide, the text field might truncate it, which is hard for people to read.

For guidance, see Text fields and Pull-down buttons.


---

## Image wells

An image well is an editable version of an image view.

After selecting an image well, people can copy and paste its image or delete it. People can also drag a new image into an image well without selecting it first.


### Best practices

**Revert to a default image when necessary.** If your image well requires an image, display the default image again if people clear the content of the image well.

**If your image well supports copy and paste, make sure the standard copy and paste menu items are available.** People generally expect to choose these menu items — or use the standard keyboard shortcuts — to interact with an image well. For guidance, see Edit menu.

For related guidance, see Image views.


---

## Pickers

A picker displays one or more scrollable lists of distinct values that people can choose from.

The system provides several styles of pickers, each of which offers different types of selectable values and has a different appearance. The exact values shown in a picker, and their order, depend on the device language.

Pickers help people enter information by letting them choose single or multipart values. Date pickers specifically offer additional ways to choose values, like selecting a day in a calendar view or entering dates and times using a numeric keypad.


### Best practices

**Consider using a picker to offer medium-to-long lists of items.** If you need to display a fairly short list of choices, consider using a pull-down button instead of a picker. Although a picker makes it easy to scroll quickly through many items, it may add too much visual weight to a short list of items. On the other hand, if you need to present a very large set of items, consider using a list or table. Lists and tables can adjust in height, and tables can include an index, which makes it much faster to target a section of the list.

**Use predictable and logically ordered values.** Before people interact with a picker, many of its values can be hidden. It’s best when people can predict what the hidden values are, such as with an alphabetized list of countries, so they can move through the items quickly.

**Avoid switching views to show a picker.** A picker works well when displayed in context, below or in proximity to the field people are editing. A picker typically appears at the bottom of a window or in a popover.

**Consider providing less granularity when specifying minutes in a date picker.** By default, a minute list includes 60 values (0 to 59). You can optionally increase the minute interval as long as it divides evenly into 60. For example, you might want quarter-hour intervals (0, 15, 30, and 45).


### Device-specific considerations

#### Phone & tablet
A date picker is an efficient interface for selecting a specific date, time, or both, using touch, a keyboard, or a pointing device. You can display a date picker in one of the following styles:

- Compact — A button that displays editable date and time content in a modal view.

- Inline — For time only, a button that displays wheels of values; for dates and times, an inline calendar view.

- Wheels — A set of scrolling wheels that also supports data entry through built-in or external keyboards.

- Automatic — A system-determined style based on the current platform and date picker mode.

A date picker has four modes, each of which presents a different set of selectable values.

- Date — Displays months, days of the month, and years.

- Time — Displays hours, minutes, and (optionally) an AM/PM designation.

- Date and time — Displays dates, hours, minutes, and (optionally) an AM/PM designation.

- Countdown timer — Displays hours and minutes, up to a maximum of 23 hours and 59 minutes. This mode isn’t available in the inline or compact styles.

The exact values shown in a date picker, and their order, depend on the device location.

Here are several examples of date pickers showing different combinations of style and mode.

**Use a compact date picker when space is constrained.** The compact style displays a button that shows the current value in your app’s accent color. When people tap the button, the date picker opens a modal view, providing access to a familiar calendar-style editor and time picker. Within the modal view, people can make multiple edits to dates and times before tapping outside the view to confirm their choices.


#### Desktop
**Choose a date picker style that suits your app.** There are two styles of date pickers on desktop: textual and graphical. The textual style is useful when you’re working with limited space and you expect people to make specific date and time selections. The graphical style is useful when you want to give people the option of browsing through days in a calendar or selecting a range of dates, or when the look of a clock face is appropriate for your app.


## Segmented controls

A segmented control is a linear set of two or more segments, each of which functions as a button.

Within a segmented control, all segments are usually equal in width. Like buttons, segments can contain text or images. Segments can also have text labels beneath them (or beneath the control as a whole).

A segmented control offers a single choice from among a set of options, or on desktop, either a single choice or multiple choices. For example, on desktop a presentation app people can select only one segment in the alignment options control to align selected text. In contrast, people can choose multiple segments in the font attributes control to combine styles like bold, italics, and underline. The toolbar of a presentation app window also uses a segmented control to let people show and hide various editing panes within the main window area.

In addition to representing the state of a single or multiple-choice selection, a segmented control can function as a set of buttons that perform actions without showing a selection state. For example, the Reply, Reply all, and Forward buttons on desktop a mail app.


### Best practices

**Use a segmented control to provide closely related choices that affect an object, state, or view.** For example, a segmented control in an inspector could let people choose one or more attributes to apply to a selection, or a segmented control in a toolbar could offer a set of actions to perform on the current view.

**Consider a segmented control when it’s important to group functions together, or to clearly show their selection state.** Unlike other button styles, segmented controls preserve their grouping regardless of the view size or where they appear. This grouping can also help people understand at a glance which controls are currently selected.

**Keep control types consistent within a single segmented control.** Don’t assign actions to segments in a control that otherwise represents selection state, and don’t show a selection state for segments in a control that otherwise performs actions.

**Limit the number of segments in a control.** Too many segments can be hard to parse and time-consuming to navigate. Aim for no more than about five to seven segments in a wide interface and no more than about five segments on phone.

**In general, keep segment size consistent.** When all segments have equal width, a segmented control feels balanced. To the extent possible, it’s best to keep icon and title widths consistent too.


### Content

**Prefer using either text or images — not a mix of both — in a single segmented control.** Although individual segments can contain text labels or images, mixing the two in a single control can lead to a disconnected and confusing interface.

**As much as possible, use content with a similar size in each segment.** Because all segments typically have equal width, it doesn’t look good if content fills some segments but not others.

**Use nouns or noun phrases for segment labels.** Write text that describes each segment and uses title-style capitalization. A segmented control that displays text labels doesn’t need introductory text.


### Device-specific considerations

#### Phone & tablet
**Consider a segmented control to switch between closely related subviews.** A segmented control can be useful as a way to quickly switch between related subviews. For example, the segmented control in a calendar app’s New Event sheet switches between the subviews for creating a new event and a new reminder. For switching between completely separate sections of an app, use a tab bar instead.


#### Desktop
**Consider using introductory text to clarify the purpose of a segmented control.** When the control uses symbols or interface icons, you could also add a label below each segment to clarify its meaning. If your app includes tooltips, provide one for each segment in a segmented control.

**Use a tab view in the main window area — instead of a segmented control — for view switching.** A tab view supports efficient view switching and is similar in appearance to a box combined with a segmented control. Consider using a segmented control to help people switch views in a toolbar or inspector pane.

**Consider supporting spring loading.** On a computer equipped with a trackpad, spring loading lets people activate a segment by dragging selected items over it and force clicking without dropping the selected items. People can also continue dragging the items after a segment activates.


## Sliders

A slider is a horizontal track with a control, called a thumb, that people can adjust between a minimum and maximum value.

As a slider’s value changes, the portion of track between the minimum value and the thumb fills with color. A slider can optionally display left and right icons that illustrate the meaning of the minimum and maximum values.


### Best practices

**Customize a slider’s appearance if it adds value.** You can adjust a slider’s appearance — including track color, thumb image and tint color, and left and right icons — to blend with your app’s design and communicate intent. A slider that adjusts image size, for example, could show a small image icon on the left and a large image icon on the right.

**Use familiar slider directions.** People expect the minimum and maximum sides of sliders to be consistent in all apps, with minimum values on the leading side and maximum values on the trailing side (for horizontal sliders) and minimum values at the bottom and maximum values at the top (for vertical sliders). For example, people expect to be able to move a horizontal slider that represents a percentage from 0 percent on the leading side to 100 percent on the trailing side.

**Consider supplementing a slider with a corresponding text field and stepper.** Especially when a slider represents a wide range of values, people may appreciate seeing the exact slider value and having the ability to enter a specific value in a text field. Adding a stepper provides a convenient way for people to increment in whole values. For related guidance, see Text fields and Steppers.


### Device-specific considerations

#### Phone & tablet


#### Desktop
Sliders on desktop can also include tick marks, making it easier for people to pinpoint a specific value within the range.

In a linear slider either with or without tick marks, the thumb is a narrow lozenge shape, and the portion of track between the minimum value and the thumb is filled with color. A linear slider often includes supplementary icons that illustrate the meaning of the minimum and maximum values.

In a circular slider, the thumb appears as a small circle. Tick marks, when present, appear as evenly spaced dots around the circumference of the slider.

**Consider giving live feedback as the value of a slider changes.** Live feedback shows people results in real time. For example, your dock icons are dynamically scaled when adjusting the Size slider in dock settings.

**Choose a slider style that matches peoples’ expectations.** A horizontal slider is ideal when moving between a fixed starting and ending point. For example, a graphics app might offer a horizontal slider for setting the opacity level of an object between 0 and 100 percent. Use circular sliders when values repeat or continue indefinitely. For example, a graphics app might use a circular slider to adjust the rotation of an object between 0 and 360 degrees. An animation app might use a circular slider to adjust how many times an object spins when animated — four complete rotations equals four spins, or 1440 degrees of rotation.

**Consider using a label to introduce a slider.** Labels generally use sentence-style capitalization and end with a colon. For guidance, see Labels.

**Use tick marks to increase clarity and accuracy.** Tick marks help people understand the scale of measurements and make it easier to locate specific values.

**Consider adding labels to tick marks for even greater clarity.** Labels can be numbers or words, depending on the slider’s values. It’s unnecessary to label every tick mark unless doing so is needed to reduce confusion. In many cases, labeling only the minimum and maximum values is sufficient. When the values of the slider are nonlinear, like in the Energy Saver settings pane, periodic labels provide context. It’s also a good idea to provide a tooltip that displays the value of the thumb when people hold their pointer over it.


## Steppers

A stepper is a two-segment control that people use to increase or decrease an incremental value.

A stepper sits next to a field that displays its current value, because the stepper itself doesn’t display a value.


### Best practices

**Make the value that a stepper affects obvious.** A stepper itself doesn’t display any values, so make sure people know which value they’re changing when they use a stepper.

**Consider pairing a stepper with a text field when large value changes are likely.** Steppers work well by themselves for making small changes that require a few taps or clicks. By contrast, people appreciate the option to use a field to enter specific values, especially when the values they use can vary widely. On a printing screen, for example, it can help to have both a stepper and a text field to set the number of copies.


### Device-specific considerations

#### Desktop
**For large value ranges, consider supporting Shift-click to change the value quickly.** If your app benefits from larger changes in a stepper’s value, it can be useful to let people Shift-click the stepper to change the value by more than the default increment (by 10 times the default, for example).


---

## Text fields

A text field is a rectangular area in which people enter or edit small, specific pieces of text.


### Best practices

**Use a text field to request a small amount of information, such as a name or an email address.** To let people input larger amounts of text, use a text view instead.

**Show a hint in a text field to help communicate its purpose.** A text field can contain placeholder text — such as “Email” or “Password” — when there’s no other text in the field. Because placeholder text disappears when people start typing, it can also be useful to include a separate label describing the field to remind people of its purpose.

**Use secure text fields to hide private data.** Always use a secure text field when your app asks for sensitive data, such as a password.

**To the extent possible, match the size of a text field to the quantity of anticipated text.** The size of a text field helps people visually gauge the amount of information to provide.

**Evenly space multiple text fields.** If your layout includes multiple text fields, leave enough space between them so people can easily see which input field belongs with each introductory label. Stack multiple text fields vertically when possible, and use consistent widths to create a more organized layout. For example, the first and last name fields on an address form might be one width, while the address and city fields might be a different width.

**Ensure that tabbing between multiple fields flows as people expect.** When tabbing between fields, move focus in a logical sequence. The system attempts to achieve this result automatically, so you won’t need to customize this too often.

**Validate fields when it makes sense.** For example, if the only legitimate value for a field is a string of digits, your app needs to alert people if they’ve entered characters other than digits. The appropriate time to check the data depends on the context: when entering an email address, it’s best to validate when people switch to another field; when creating a user name or password, validation needs to happen before people switch to another field.

**Use a number formatter to help with numeric data.** A number formatter automatically configures the text field to accept only numeric values. It can also display the value in a specific way, such as with a certain number of decimal places, as a percentage, or as currency. Don’t assume the actual presentation of data, however, as formatting can vary significantly based on people’s locale.

**Adjust line breaks according to the needs of the field.** By default, the system clips any text extending beyond the bounds of a text field. Alternatively, you can set up a text field to wrap text to a new line at the character or word level, or to truncate (indicated by an ellipsis) at the beginning, middle, or end.

**Consider using an expansion tooltip to show the full version of clipped or truncated text.** An expansion tooltip behaves like a regular tooltip and appears when someone places the pointer over the field.

**In phone and tablet apps, show the appropriate keyboard type.** Several different keyboard types are available, each designed to facilitate a different type of input, such as numbers or URLs. To streamline data entry, display the keyboard that’s appropriate for the type of content people are entering. For guidance, see Virtual keyboards.


### Device-specific considerations

#### Phone & tablet
**Display a Clear button in the trailing end of a text field to help people erase their input.** When this element is present, people can tap it to clear the text field’s contents, without having to keep tapping the Delete key.

**Use images and buttons to provide clarity and functionality in text fields.** You can display custom images in both ends of a text field, or you can add a system-provided button, such as the Bookmarks button. In general, use the leading end of a text field to indicate a field’s purpose and the trailing end to offer additional features, such as bookmarking.


#### Desktop
**Consider using a combo box if you need to pair text input with a list of choices.** For related guidance, see Combo boxes.


## Toggles

A toggle lets people choose between a pair of opposing states, like on and off, using a different appearance to indicate each state.

A toggle can have various styles, such as switch and checkbox, and different platforms can use these styles in different ways. For guidance, see Platform considerations.

In addition to toggles, all platforms also support buttons that behave like toggles by using a different appearance for each state.


### Best practices

**Use a toggle to help people choose between two opposing values that affect the state of content or a view.** A toggle always lets people manage the state of something, so if you need to support other types of actions — such as choosing from a list of items — use a different component, like a pop-up button.

**Clearly identify the setting, view, or content the toggle affects.** In general, the surrounding context provides enough information for people to understand what they’re turning on or off. In some cases, often on desktop apps, you can also supply a label to describe the state the toggle controls. If you use a button that behaves like a toggle, you generally use an interface icon that communicates its purpose, and you update its appearance — typically by changing the background — based on the current state.

**Make sure the visual differences in a toggle’s state are obvious.** For example, you might add or remove a color fill, show or hide the background shape, or change the inner details you display — like a checkmark or dot — to show that a toggle is on or off. Avoid relying solely on different colors to communicate state, because not everyone can perceive the differences.


### Device-specific considerations

#### Phone & tablet
**Use the switch toggle style only in a list row.** You don’t need to supply a label in this situation because the content in the row provides the context for the state the switch controls.

**Change the default color of a switch only if necessary.** The default green color tends to work well in most cases, but you might want to use your app’s accent color instead. Be sure to use a color that provides enough contrast with the uncolored appearance to be perceptible.

**Outside of a list, use a button that behaves like a toggle, not a switch.** For example, the Phone app uses a toggle on the filter button to let users filter their recent calls. The app adds a blue highlight to indicate when the toggle is active, and removes it when the toggle is inactive.

**Avoid supplying a label that explains the button’s purpose.** The interface icon you create — combined with the alternative background appearances you supply — help people understand what the button does.


#### Desktop
In addition to the switch toggle style, desktop supports the checkbox style and also defines radio buttons that can provide similar behaviors.

**Use switches, checkboxes, and radio buttons in the window body, not the window frame.** In particular, avoid using these components in a toolbar or status bar.


##### Switches

**Prefer a switch for settings that you want to emphasize.** A switch has more visual weight than a checkbox, so it looks better when it controls more functionality than a checkbox typically does. For example, you might use a switch to let people turn on or off a group of settings, instead of just one setting.

**Within a grouped form, consider using a mini switch to control the setting in a single row.** The height of a mini switch is similar to the height of buttons and other controls, resulting in rows that have a consistent height. If you need to present a hierarchy of settings within a grouped form, you can use a regular switch for the primary setting and mini switches for the subordinate settings.

**In general, don’t replace a checkbox with a switch.** If you’re already using a checkbox in your interface, it’s probably best to keep using it.


##### Checkboxes

A checkbox is a small, square button that’s empty when the button is off, contains a checkmark when the button is on, and can contain a dash when the button’s state is mixed. Typically, a checkbox includes a title on its trailing side. In an editable checklist, a checkbox can appear without a title or any additional content.

**Use a checkbox instead of a switch if you need to present a hierarchy of settings.** The visual style of checkboxes helps them align well and communicate grouping. By using alignment — generally along the leading edge of the checkboxes — and indentation, you can show dependencies, such as when the state of a checkbox governs the state of subordinate checkboxes.

**Consider using radio buttons if you need to present a set of more than two mutually exclusive options.** When people need to choose from options in addition to just “on” or “off,” using multiple radio buttons can help you clarify each option with a unique label.

**Consider using a label to introduce a group of checkboxes if their relationship isn’t clear.** Describe the set of options, and align the label’s baseline with the first checkbox in the group.

**Accurately reflect a checkbox’s state in its appearance.** A checkbox’s state can be on, off, or mixed. If you use a checkbox to globally turn on and off multiple subordinate checkboxes, show a mixed state when the subordinate checkboxes have different states. For example, you might need to present a text-style setting that turns all styles on or off, but also lets people choose a subset of individual style settings like bold, italic, or underline.


##### Radio buttons

A radio button is a small, circular button followed by a label. Typically displayed in groups of two to five, radio buttons present a set of mutually exclusive choices.

A radio button’s state is either selected (a filled circle) or deselected (an empty circle). Although a radio button can also display a mixed state (indicated by a dash), this state is rarely useful because you can communicate multiple states by using additional radio buttons. If you need to show that a setting or item has a mixed state, consider using a checkbox instead.

**Prefer a set of radio buttons to present mutually exclusive options.** If you need to let people choose multiple options in a set, use checkboxes instead.

**Avoid listing too many radio buttons in a set.** A long list of radio buttons takes up a lot of space in the interface and can be overwhelming. If you need to present more than about five options, consider using a component like a pop-up button instead.

**To present a single setting that can be on or off, prefer a checkbox.** Although a single radio button can also turn something on or off, the presence or absence of the checkmark in a checkbox can make the current state easier to understand at a glance. In rare cases where a single checkbox doesn’t clearly communicate the opposing states, you can use a pair of radio buttons, each with a label that specifies the state it controls.

**Use consistent spacing when you display radio buttons horizontally.** Measure the space needed to accommodate the longest button label, and use that measurement consistently.


---

## Virtual keyboards

On devices without physical keyboards, the system offers various types of virtual keyboards people can use to enter data.

A virtual keyboard can provide a specific set of keys that are optimized for the current task; for example, a keyboard that supports entering email addresses can include the “@” character and a period or even “.com”. A virtual keyboard doesn’t support keyboard shortcuts.



### Best practices

**Choose a keyboard that matches the type of content people are editing.** For example, you can help people enter numeric data by providing the numbers and punctuation keyboard. When you specify a semantic meaning for a text input area, the system can automatically provide a keyboard that matches the type of input you expect, potentially using this information to refine the keyboard corrections it offers.

**Consider customizing the Return key type if it helps clarify the text-entry experience.** The Return key type is based on the keyboard type you choose, but you can change this if it makes sense in your app. For example, if your app initiates a search, you can use a search Return key type rather than the standard one so the experience is consistent with other places people initiate search.


### Custom input views

In some cases, you can create an *input view* if you want to provide custom functionality that enhances data-entry tasks in your app. For example, a spreadsheet app provides a custom input view for entering numeric values while editing a spreadsheet. A custom input view replaces the system-provided keyboard while people are in your app.

**Make sure your custom input view makes sense in the context of your app.** In addition to making data entry simple and intuitive, you want people to understand the benefits of using your custom input view. Otherwise, they may wonder why they can’t regain the system keyboard while in your app.

**Play the standard keyboard sound while people type.** The keyboard sound provides familiar feedback when people tap a key on the system keyboard, so they’re likely to expect the same sound when they tap keys in your custom input view. People can turn keyboard sounds off for all keyboard interactions in Settings > Sounds.


### Custom keyboards


After people choose your custom keyboard in Settings, they can use it for text entry within any app, except when editing secure text fields and phone number fields. People can choose multiple custom keyboards and switch between them at any time.

Custom keyboards make sense when you want to expose unique keyboard functionality systemwide, such as a novel way of inputting text or the ability to type in a language the system doesn’t support. If you want to provide a custom keyboard for people to use only while they’re in your app, consider creating a custom input view instead.

**Provide an obvious and easy way to switch between keyboards.** People know that the Globe key on the standard keyboard — which replaces the dedicated Emoji key when multiple keyboards are available — quickly switches to other keyboards, and they expect a similarly intuitive experience in your keyboard.

**Avoid duplicating system-provided keyboard features.** On some devices, the Emoji/Globe key and Dictation key automatically appear beneath the keyboard, even when people are using custom keyboards. Your app can’t affect these keys, and it’s likely to be confusing if you repeat them in your keyboard.

**Consider providing a keyboard tutorial in your app.** People are used to the standard keyboard, and learning how to use a new keyboard can take time. You can help make the process easier by providing usage instructions in your app — for example, you might tell people how to choose your keyboard, activate it during text entry, use it, and switch back to the standard keyboard. Avoid displaying help content within the keyboard itself.


### Device-specific considerations

#### Phone & tablet
**Use the keyboard layout guide to make the keyboard feel like an integrated part of your interface.** Using the layout guide also helps you keep important parts of your interface visible while the virtual keyboard is onscreen.

**Place custom controls above the keyboard thoughtfully.** Some apps position an input accessory view containing custom controls above the keyboard to offer app-specific functionality related to the data people are working with. For example, a spreadsheet app displays controls that help people apply standard or custom calculations to spreadsheet data. If your app offers custom controls that augment the keyboard, make sure they’re relevant to the current task. If other views in your app use glass, or if your view looks out of place above the keyboard, apply glass to the view that contains your controls to maintain consistency. If you use a standard toolbar to contain your controls, it automatically adopts glass. Use the keyboard layout guide and standard padding to ensure the system positions your controls as expected within the view.


## Gauges

A gauge displays a specific numerical value within a range of values.

In addition to indicating the current value in a range, a gauge can provide more context about the range itself. For example, a temperature gauge can use text to identify the highest and lowest temperatures in the range and display a spectrum of colors that visually reinforce the changing values.


### Anatomy

A gauge uses a circular or linear path to represent a range of values, mapping the current value to a specific point on the path. A standard gauge displays an indicator that shows the current value’s location; a gauge that uses the capacity style displays a fill that stops at the value’s location on the path.


> **Note**: In addition to gauges, desktop also supports level indicators, some of which have visual styles that are similar to gauges. For guidance, see desktop.


### Best practices

**Write succinct labels that describe the current value and both endpoints of the range.** Although not every gauge style displays all labels, the screen reader reads the visible labels to help people understand the gauge without seeing the screen.

**Consider filling the path with a gradient to help communicate the purpose of the gauge.** For example, a temperature gauge might use colors that range from red to blue to represent temperatures that range from hot to cold.


### Device-specific considerations

#### Desktop
In addition to supporting gauges, desktop also defines a level indicator that displays a specific numerical value within a range. You can configure a level indicator to convey capacity, rating, or — rarely — relevance.

The capacity style can depict discrete or continuous values.

**Consider using the continuous style for large ranges.** A large value range can make the segments of a discrete capacity indicator too small to be useful.

**Consider changing the fill color to inform people about significant parts of the range.** By default, the fill color for both capacity indicator styles is green. If it makes sense in your app, you can change the fill color when the current value reaches certain levels, such as very low, very high, or just past the middle. You can change the fill color of the entire indicator or you can use the tiered state to show a sequence of several colors in one indicator, as shown below.

For guidance using the rating style to help people rank something, see Rating indicators.

Although rarely used, the relevance style can communicate relevancy using a shaded horizontal bar. For example, a relevance indicator might appear in a list of search results, helping people visualize the relevancy of the results when sorting or comparing multiple items.


---

## Progress indicators

Progress indicators let people know that your app isn’t stalled while it loads content or performs lengthy operations.

Some progress indicators also give people a way to estimate how long they have to wait for something to complete. All progress indicators are transient, appearing only while an operation is ongoing and disappearing after it completes.

Because the duration of an operation is either known or unknown, there are two types of progress indicators:

- *Determinate*, for a task with a well-defined duration, such as a file conversion

- *Indeterminate*, for unquantifiable tasks, such as loading or synchronizing complex data

Both determinate and indeterminate progress indicators can have different appearances depending on the platform. A determinate progress indicator shows the progress of a task by filling a linear or circular track as the task completes. *Progress bars* include a track that fills from the leading side to the trailing side. *Circular progress indicators* have a track that fills in a clockwise direction.

An indeterminate progress indicator — also called an *activity indicator* — uses an animated image to indicate progress. All platforms support a circular image that appears to spin; however, desktop also supports an indeterminate progress bar.


### Best practices

**When possible, use a determinate progress indicator.** An indeterminate progress indicator shows that a process is occurring, but it doesn’t help people estimate how long a task will take. A determinate progress indicator can help people decide whether to do something else while waiting for the task to complete, restart the task at a different time, or abandon the task.

**Be as accurate as possible when reporting advancement in a determinate progress indicator.** Consider evening out the pace of advancement to help people feel confident about the time needed for the task to complete. Showing 90 percent completion in five seconds and the last 10 percent in 5 minutes can make people wonder if your app is still working and can even feel deceptive.

**Keep progress indicators moving so people know something is continuing to happen.** People tend to associate a stationary indicator with a stalled process or a frozen app. If a process stalls for some reason, provide feedback that helps people understand the problem and what they can do about it.

**When possible, switch a progress bar from indeterminate to determinate.** If an indeterminate process reaches a point where you can determine its duration, switch to a determinate progress bar. People generally prefer a determinate progress indicator, because it helps them gauge what’s happening and how long it will take.

**Don’t switch from the circular style to the bar style.** Activity indicators (also called *spinners*) and progress bars are different shapes and sizes, so transitioning between them can disrupt your interface and confuse people.

**If it’s helpful, display a description that provides additional context for the task.** Be accurate and succinct. Avoid vague terms like *loading* or *authenticating* because they seldom add value.

**Display a progress indicator in a consistent location.** Choosing a consistent location for a progress indicator helps people reliably find the status of an operation across platforms or within or between apps.

**When it’s feasible, let people halt processing.** If people can interrupt a process without causing negative side effects, include a Cancel button. If interrupting the process might cause negative side effects — such as losing the downloaded portion of a file — it can be useful to provide a Pause button in addition to a Cancel button.

**Let people know when halting a process has a negative consequence.** When canceling a process results in lost progress, it’s helpful to provide an alert that includes an option to confirm the cancellation or resume the process.


### Device-specific considerations

#### Phone & tablet
##### Refresh content controls

A refresh control lets people immediately reload content, typically in a table view, without waiting for the next automatic content update to occur. A refresh control is a specialized type of activity indicator that’s hidden by default, becoming visible when people drag down the view they want to reload. In a mail app, for example, people can drag down the list of Inbox messages to check for new messages.

**Perform automatic content updates.** Although people appreciate being able to do an immediate content refresh, they also expect automatic refreshes to occur periodically. Don’t make people responsible for initiating every update. Keep data fresh by updating it regularly.

**Supply a short title only if it adds value.** Optionally, a refresh control can include a title. In most cases, this is unnecessary, as the animation of the control indicates that content is loading. If you do include a title, don’t use it to explain how to perform a refresh. Instead, provide information of value about the content being refreshed. A refresh control in a podcast app, for example, uses a title to tell people when the last podcast update occurred.


#### Desktop
On desktop, an indeterminate progress indicator can have a bar or circular appearance. Both versions use an animated image to indicate that the app is performing a task.

**Prefer an activity indicator (spinner) to communicate the status of a background operation or when space is constrained.** Spinners are small and unobtrusive, so they’re useful for asynchronous background tasks, like retrieving messages from a server. Spinners are also good for communicating progress within a small area, such as within a text field or next to a specific control, such as a button.

**Avoid labeling a spinning progress indicator.** Because a spinner typically appears when people initiate a process, a label is usually unnecessary.


## Rating indicators

A rating indicator uses a series of horizontally arranged graphical symbols — by default, stars — to communicate a ranking level.

A rating indicator doesn’t display partial symbols; it rounds the value to display complete symbols only. Within a rating indicator, symbols are always the same distance apart and don’t expand or shrink to fit the component’s width.


### Best practices

**Make it easy to change rankings.** When presenting a list of ranked items, let people adjust the rank of individual items inline without navigating to a separate editing screen.

**If you replace the star with a custom symbol, make sure that its purpose is clear.** The star is a very recognizable ranking symbol, and people may not associate other symbols with a rating scale.


---

## Notifications

A notification gives people timely, high-value information they can understand at a glance.

Before you can send any notifications to people, you have to get their consent. After agreeing, people generally use settings to specify the styles of notification they want to receive, and to specify delivery times for notifications that have different levels of urgency. To learn more about the ways people can customize the notification experience, see Managing notifications.


### Anatomy

Depending on the platform, a notification can use various styles, such as:

- A banner or view on a lock screen, home screen, Home View, or desktop

- A badge on an app icon

- An item in the notification center

In addition, a notification related to direct communication — like a phone call or message — can provide an interface that’s distinct from noncommunication notifications, featuring prominent contact images (or *avatars*) and group names instead of the app icon.


### Best practices

**Provide concise, informative notifications.** People turn on notifications to get quick updates, so you want to provide valuable information succinctly.

**Avoid sending multiple notifications for the same thing, even if someone hasn’t responded.** People attend to notifications at their convenience. If you send multiple notifications for the same thing, you fill up the notification center, and people may turn off all notifications from your app.

**Avoid sending a notification that tells people to perform specific tasks within your app.** If it makes sense to offer simple tasks that people can perform without opening your app, you can provide notification actions. Otherwise, avoid telling people what to do because it’s hard for people to remember such instructions after they dismiss the notification.

**Use an alert — not a notification — to display an error message.** People are familiar with both alerts and notifications, so you don’t want to cause confusion by using the wrong component. For guidance, see Alerts.

**Handle notifications gracefully when your app is in the foreground.** Your app’s notifications don’t appear when your app is in the front, but your app still receives the information. In this scenario, present the information in a way that’s discoverable but not distracting or invasive, such as incrementing a badge or subtly inserting new data into the current view. For example, when a new message arrives in a mailbox that people are currently viewing, a mail app simply adds it to the list of unread messages because sending a notification about it would be unnecessary and distracting.

**Avoid including sensitive, personal, or confidential information in a notification.** You can’t predict what people will be doing when they receive a notification, so it’s essential to avoid including private information that could be visible to others.


### Content

When a notification includes a title, the system displays it at the top where it’s most visible. In a notification related to direct communication, the system automatically displays the sender’s name in the title area; in a noncommunication notification, the system displays your app name if you don’t provide a title.


**Write succinct, easy-to-read notification content.** Use complete sentences, sentence case, and proper punctuation, and don’t truncate your message — the system does this automatically when necessary.

**Provide generically descriptive text to display when notification previews aren’t available.** In Settings, people can choose to hide notification previews for all apps. In this situation, the system shows only your app icon and the default title *Notification*. To give people sufficient context to know whether they want to view the full notification, write body text that succinctly describes the notification content without revealing too many details, like “Friend request,” “New comment,” “Reminder,” or “Shipment”. Use sentence-style capitalization for this text.

**Avoid including your app name or icon.** The system automatically displays a large version of your app icon at the leading edge of each notification; in a communication notification, the system displays the sender’s contact image badged with a small version of your icon.

**Consider providing a sound to supplement your notifications.** Sound can be a great way to distinguish your app’s notifications and get someone’s attention when they’re not looking at the device. You can create a custom sound that coordinates with the style of your app or use a system-provided alert sound. If you use a custom sound, make sure it’s short, distinctive, and professionally produced. A notification sound can enhance the user experience, but don’t rely on it to communicate important information, because people may not hear it. Although people might also want a vibration to accompany alert sounds, you can’t provide such a vibration programmatically.


### Notification actions

A notification can present a customizable detail view that contains up to four buttons people use to perform actions without opening your app. For example, a calendar app event notification provides a Snooze button that postpones the event’s alarm for a few minutes.

**Provide beneficial actions that make sense in the context of your notification.** Prefer actions that let people perform common, time-saving tasks that eliminate the need to open your app. For each button, use a short, title-case term or phrase that clearly describes the result of the action. Don’t include your app name or any extraneous information in the button label, keep the text brief to avoid truncation, and take localization into account as you write it.


**Prefer nondestructive actions.** If you must provide a destructive action, make sure people have enough context to avoid unintended consequences. The system gives a distinct appearance to the actions you identify as destructive.

**Provide a simple, recognizable interface icon for each notification action.** An interface icon reinforces an action’s meaning, helping people instantly understand what it does. The system displays your interface icon on the trailing side of the action title. When you use the symbol library, you can choose an existing symbol that represents your command or edit a related symbol to create a custom icon.


### Badging

A badge is a small, filled oval containing a number that can appear on an app icon to indicate the number of unread notifications that are available. After people address unread notifications, the badge disappears from the app icon, reappearing when new notifications arrive. People can choose whether to allow an app to display badges in their notification settings.

**Use a badge only to show people how many unread notifications they have.** Don’t use a badge to convey numeric information that isn’t related to notifications, such as weather-related data, dates and times, stock prices, or game scores.

**Make sure badging isn’t the only method you use to communicate essential information.** People can turn off badging for your app, so if you rely on it to show people when there’s important information, people can miss the message. Always make sure that you make important information easy for people to find as soon as they open your app.

**Keep badges up to date.** Update your app’s badge as soon as people open the corresponding notifications. You don’t want people to think there are new notifications available, only to find that they’ve already viewed them all. Note that reducing a badge’s count to zero removes all related notifications from the notification center.

**Avoid creating a custom image or component that mimics the appearance or behavior of a badge.** People can turn off notification badges if they choose, and will become frustrated if they have done so and then see what appears to be a badge.


### Device-specific considerations
