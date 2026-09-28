# Design Process, Evaluation Rubric & Prototyping

This reference captures the design philosophy, prototyping methodology, evaluation criteria, and field wisdom from Apple's Design Evangelism, Prototyping, and Apple Design Awards teams.

---

## 1. The Apple Design Awards: 6-Pillar Evaluation Rubric

Every year, Apple evaluates and recognizes world-class software across six foundational categories. These criteria represent Apple's standard for design excellence and serve as a universal rubric for reviewing any application or game:

### Delight and Fun
> *Experiences that provide memorable, engaging, and satisfying interactions.*
- **Clever Simplicity**: Software that does not take itself too seriously, stripping out unnecessary cruft (extraneous logins, heavy setup flows, superfluous chrome) in favor of simple, immediate joy.
- **Micro-interactions & Easter Eggs**: Playful, unexpected responses when exploring or tapping elements; tactile audio/visual feedback that rewards curiosity.
- **Atmosphere & Charm**: Creating a cohesive world with distinct personality, charming illustration, or thoughtful details that make using the product a pleasure rather than a chore.

### Inclusivity
> *Providing a great experience for all by reflecting a variety of backgrounds, abilities, and languages.*
- **Sensory & Visual Access**: Robust screen reader support (meaningful labels and traits for VoiceOver/TalkBack), Dynamic Type / scalable typography that never truncates or clips, Increased Contrast, and Differentiating Without Color (ensuring color is never the sole communicator of status or information).
- **Cognitive & Neurodivergent Ease**: Clear layouts, thoughtful defaults, pre-filled suggestions, low cognitive load, and deliberate support for breaks and pacing rather than overwhelming lists.
- **Motor & Input Flexibility**: Support for diverse control schemes (touch, pointer, keyboard, voice, switch control) with generous hit areas and customizable sensitivity.
- **Universal Comprehension**: Natural controls and intuitive visual cues that can be operated without requiring dense reading, making experiences accessible to young ages and across language barriers.
- **Cultural Representation**: Broad and respectful representation of diverse cultures, histories, and backgrounds.

### Innovation
> *State-of-the-art experiences through novel uses of technology that set the product apart in its genre.*
- **Rethinking Category Paradigms**: Moving beyond existing conventions to invent new interaction models rather than simply replicating established solutions.
- **Leveraging Modern Platform Capabilities**: Integrating cutting-edge frameworks, machine learning, and hardware capabilities in ways that feel natural, purposeful, and seamless.
- **Novel Workflows**: Transforming complex, time-consuming tasks (like editing, authoring, or analysis) into fast, effortless, and accessible flows.

### Interaction
> *Intuitive interfaces and effortless controls that are perfectly tailored to their platform and input medium.*
- **Effortless Affordance**: Controls and gestures that feel so natural they require zero tutorial or explanation.
- **Direct Manipulation & Zero-Lag Physics**: Inputs that track 1:1 with user gestures without perceptible latency or unnatural acceleration.
- **Context-Specific Controls**: Input mechanics cleanly adapted to the physical reality of the device (touch gestures for mobile screens, precision pointer and keyboard shortcuts for desktop).
- **Clarity of Hierarchy**: Data presentations and navigational structures that are instantly scannable and understandable.

### Social Impact
> *Improving lives in a meaningful way and shining a light on crucial issues.*
- **Human Well-being**: Tools that support health, recovery, balance, education, and mutual support.
- **Respect for Attention & Time**: Experiences that avoid dark patterns, predatory engagement loops, or attention-hijacking mechanics.
- **Ethical Handling of Data**: Transparent rationale for data collection, minimal permissions, and privacy as an explicit design value.

### Visuals and Graphics
> *Stunning imagery, skillfully drawn interfaces, and high-quality animations that lend to a distinctive and cohesive theme.*
- **Visual Polish**: Meticulous attention to typography, spatial balance, alignments, and rendering craft.
- **Purposeful Motion**: Fluid, physics-based transitions that orient users, explain spatial relationships, and bring life without delaying interaction.
- **Thematic Cohesion**: Color palettes, iconography, materials, and typography that harmoniously reinforce the product's identity.

---

## 2. Q&A: 10 Questions with Design Evangelism

*Source: Apple Developer Design Evangelism team conversation.*

### Do you ever feel like your design isn’t quite right, but you’re not sure why?
> All the time! In fact, “Feeling like the design isn’t quite right” can sometimes seem like an everyday mood. When this happens, there are a few strategies we find helpful, and the first is: Phone a friend! Sometimes it takes another person to gut-check why we’re feeling uncertain about a design, and it’s always great to engage in a conversation and critique. Plus, this not only requires you to explain the problem (which alone can help you identify what’s not working), it also allows you to personally step away from it — at least for a moment.

### How do you know when to start cutting features to make your app less cluttered and more user-friendly?
> This is a great exercise for a whiteboard or sticky notes. First, write down all the features/areas of your app. Then, bucket them into what fulfills the goals your users will have. If something feels superfluous, consider whether you need that feature. There's a balance between what you need visible all the time, what can be a few taps away, and what doesn't need to be there at all. (It's also a helpful way to prioritize the most important functionality of your app — which can help you better organize your app's hierarchy!)

### Is it considered best practice to limit device orientation?
> You should really leave device orientation up to users. We love when apps support both portrait and landscape and would only recommend limiting orientation in certain app scenarios, such as when movement or device mounting would make orientation-switching feel distracting.

### What are some guidelines for colors and shades?
> Using color for actions is a subtle way to brand the interface without being distracting or intrusive. Start by selecting a main tint color, establishing your workflows and actions, then sketching those out with the tint color representing actions. (You’ll notice our first-party apps all have one key tint color; for instance, Mail is blue and Podcasts is purple.) When you’re working on high-fidelity visual designs, use a palette that complements that color.

### Is it necessary to include tab bar labels for common tabs like Home, Search, or Profile?
> In many cases, labels are recommended for clarity and accessibility. Home, Search, and Profile are generally sufficient for communicating meaning on their own, but they’re exceptions to the rule. Many icons are not as widely understood. Tab bar labels create a stronger distinction from toolbars, which don’t have labels. Plus, removing the labels doesn’t provide much benefit to users. It doesn’t save any space, nor does it significantly reduce visual information from the interface.

### How should I think about keyboard shortcuts that feel intuitive and don’t interfere with system shortcuts? When should I use one modifier over another?
> In general, the go-to modifier key is Command (or Control) because it’s easiest to reach with your thumb. And speaking of, here are a few more rules of thumb:
> - The fewer modifier keys, the better.
> - Using the first letter of the action name helps people remember the shortcut.
> - From an ergonomic standpoint, keys nearest modifiers and easily reachable using one's index and middle fingers — **Q, W, E, A, S, D, O, and P** — tend to be more successful as shortcuts.

### How large are the specified margins for safe areas and layout?
> Layout margins provide structured breathing room (such as 16pt in compact width and 20pt in regular width). But safe areas work in tandem with margins. Safe areas are dynamic and change with device orientation, display cutouts/notches, and active toolbars/navigation bars. Backgrounds extend edge-to-edge; interactive controls and critical text stay inside safe boundaries.

### When designing for lists, how can I stop rows and cells from feeling overcrowded?
> Think about progressive disclosure and hierarchy. What information do people need at each level of your app? When cells feel overcrowded, question the purpose of each element. Maybe a photo or icon isn’t beneficial, or maybe the secondary text can be a description on the detail view.

### Do you always try to adhere as much as possible to guidelines, or do you try to do something different with every design?
> We do try to adhere to our foundations and follow our own design patterns for the benefit of consistency and understanding. (We also try to use standard system components because they're so efficient to build with.) But that being said, we're also willing to push on guidelines where it makes sense — if it means an overall benefit for users. The guidelines shouldn't be a set of rules, but very good suggestions. Evolve constantly based on user needs, community insights, and pushing aesthetics and interactions forward.

### Is it good practice to hide the tab bar when navigating to sub-pages?
> Nope. :)
> (It’s OK to cover it for brief periods when a modal sheet is displayed. Otherwise, hiding a tab bar can make people feel lost.)

---

## 3. Prototyping Methodology: Meet the Prototypers

*Source: Apple Prototyping Team conversation.*

### What’s your process when beginning a new prototyping project?
> We make something, show it to people, learn from their feedback — and do it over and over again. We don't really count how many "drafts" we make, but everything we work on undergoes many, many iterations.

### How do you even know where to start?
> It’s important to know your biggest questions around an idea. The goal of prototypes is to answer these kinds of questions before investing a lot of time into making things real — hence why it's important to keep your prototyping process light and nimble. We try not to be too rigid. Often, we’re starting with a specific problem to solve. But sometimes we make things just because they seem interesting, and then figure out why and what they can help solve. It’s about giving ourselves space to figure out what feels great.

### What kinds of tools do you use for initial sketches and ideas?
> The best tool is whatever you're most comfortable with — what is going to let you try things rapidly? For some people, that's code; others, sketching or animation. Everyone uses different tools and workflows that work for them.

### What’s the ratio of looks to functionality when making a prototype?
> Looks for the sake of looks are rarely worth spending lots of early time on, but sometimes different aesthetic directions or visual metaphors are definitely things you want to prototype! The key is to make the least amount you need and still learn something.

### How extensively do you test your early designs?
> We show prototypes to broader teams as well as our own. It's less about testing in a traditional, thorough sense, and more about getting lots of people from different backgrounds to try it and tell us what they think.

### How do you approach giving feedback to each other?
> Always bring positive feedback when sharing the work. It should never be about personal judgement, but how to make the app experience better. For example, avoid something like "I don't like this color" in favor of a comment like "I think blue instead of red would better communicate what the experience is about."

### How often do you change direction or evolve a prototype after feedback sessions?
> We try to keep more than one direction open at a time. It might mean having multiple different prototypes, or a single option that has sliders and preferences and can be adjusted. If someone gives us good feedback, we’ll incorporate it or try it out. If it’s in conflict with the previous direction, we keep both around to let people compare.

### Have you ever had a product that had little to no changes after feedback? A “hole-in-one”?
> Never! If we’re not getting feedback on something, we’re just not showing it to the right people. We’ll eventually show it to someone who will have feedback — either improvements or reasons why it won’t work.

### How do you go about adding magic, delight, and whimsy to a prototype?
> Give yourself time to not worry about solving the problem. “What other ideas does this give us?” can mean something completely unrelated. But if something seems interesting, it’s worth trying. Those weird-but-interesting ideas can inspire us to connect the weird/whimsical inspiration to something that actually solves the problem.

### How does your team go about prototyping advanced interactions without having to fully build something?
> We find a way to fake it! Simple paper printouts, clever video capture, interactive Keynote animations, or simple throwaway code spikes can teach a lot without building the underlying architecture.

### Do you ever have to stop and refocus a vision or design — say, if too many new ideas have been added?
> Definitely. When that happens, we typically try to focus on what people loved the most. If you have dozens of things competing for your attention, focusing on the two or three that seem to be winning hearts over is a good way to move forward without getting bogged down. Also, sometimes you may have to accept that while you have a bunch of kinda cool things, there's no one true winner. That's OK! There's always a way for things you liked to make their way into other work in the future.

### What’s one piece of advice you’d want to share?
> Always remember what you’re building a prototype for and what you’re trying to answer. We sometimes get caught up in trying for a perfectly polished prototype. But it should always be about quickly and efficiently testing a panel of different ideas. Sometimes it helps to get away from the screen and use low-tech tools.

### How would you sum up the team’s design philosophy?
> **"Make things, show them to people, learn from their feedback!"** That should be a tattoo at this point.

---

## 4. Essential Design Principles

*Source: Apple Design Evangelism (Mike Stern, WWDC17 Session 802).*

> *"The word 'user' can have a clinical or anonymizing effect. 'Human' evokes a much more nuanced picture of who it is that we are designing for. Designing an interface is fundamentally about serving other human beings. The goal isn't to make a beautiful, simple, or focused app for its own sake; the real goal is satisfying the emotional and practical needs of the people you are designing for."*

Human beings bring four fundamental needs to every interface:
1. **Safety and Predictability**: Making it easy to predict the consequences actions will have; feeling stable, solid, trustworthy.
2. **Knowledge, Meaning, and Understanding**: Helping people make informed choices with clear, helpful information.
3. **Task Accomplishment**: Streamlined, simplified workflows so people effectively achieve their personal and professional goals.
4. **Beauty and Joy**: Aesthetically pleasing, enjoyable, and gratifying experiences.

To serve these needs, great software relies on ten universal principles:

### 1. Wayfinding
Interface navigation is a wayfinding system. Just as an airport uses signage to orient stressed, tired travelers, every screen in your app must answer five fundamental questions:
- **Where am I?** (Navigation bar title, active selected tab or menu state).
- **Where can I go?** (Visible navigation bars, tab bars, sidebars, content links).
- **What will I find when I get there?** (Recognizable glyphs, understandable labels, descriptive section titles).
- **What is nearby?** (Contextual menus, related content sections, adjacent items).
- **How do I get out?** (Prominent back buttons, cancel actions, visible exit routes back to safety).

### 2. Feedback
Interactive software is a real-time conversation between the person and the system. Feedback answers: *What can I do? What just happened? What is currently happening? What will happen next?*
- **Status Feedback**: Communicates ongoing conditions so people can plan ahead (e.g., fuel gauges, unread message badges, recording indicators). Surface critical status directly at top levels.
- **Completion Feedback**: Reassurance that an action succeeded (e.g., subtle audio cues, email archiving animations, checkmarks).
- **Warning Feedback**: Alerts people in advance to potential hazards before irreversible harm occurs.
- **Error Feedback & Intent Inferencing**: Don't just throw modal errors. Provide inline validation to guide people in real time. Infer what the person intended to do when a benign mistake occurs (e.g., automatically rolling invalid "June 31" over to "July 1" instead of showing an error alert).

### 3. Visibility
Usability is directly tied to the visibility of controls and status information.
- Surfacing essential controls in plain sight saves time and prevents confusion.
- Densely packed interfaces can overwhelm novice users, while completely hiding controls in hamburger menus slows down discovery and hides capability. Balance visibility against cognitive load.

### 4. Consistency
Consistency improves usability because people apply existing knowledge rather than re-learning how to operate your software:
- **External / Platform Consistency**: Respect conventions users already know (e.g., standard platform share glyphs, common gestures, system navigation patterns). Inconsistency about simple things (like custom back buttons or non-standard icons) trips people up. Only diverge when you have an undeniable user benefit.
- **Internal Consistency**: Cohesion within your own app. Icons share a matching weight and stroke; typography uses a disciplined set of sizes; controls follow identical interactive behaviors across every screen. Internal consistency gives a product visual integrity and signals deep craftsmanship.

### 5. Mental Models (System Model vs. Interaction Model)
Every person holds an internal mental model of how a system works and how they can interact with it.
- When an interface matches a person's mental model, expectations are met and the interface is perceived as **intuitive**.
- When an interface diverges from expectations, it is perceived as **unintuitive** (the *Mortimer Faucet* problem: redesigning a two-handle sink to separate flow from temperature looks brilliant to the designer, but leaves users scalded and confused).
- Changing deeply ingrained mental models is high-risk. Before altering familiar interactions, verify beyond doubt that the innovation is objectively superior.

### 6. Proximity
Distance indicates connection. The closer a control is to the object it modifies, the stronger the perceived relationship.
- Place controls adjacent to the views they affect (e.g., placement tools directly above the canvas; editing panels docked alongside selected layers).
- Placing controls within natural reach matches ergonomic expectations.

### 7. Grouping
Grouping clusters related elements visually to give an interface clear structural hierarchy.
- Use whitespace, separator lines, cards, and section containers to separate distinct task areas.
- Controls grouped together are presumed to share a functional domain.

### 8. Mapping
Controls should mirror the physical shape, orientation, and motion of what they control:
- Use horizontal sliders for horizontal spatial adjustments.
- Use circular dials for rotation.
- Arrange light switches or grid buttons in the exact spatial order of the objects they trigger.
- Where possible, prefer direct manipulation (dragging an object directly with finger or pointer) over indirect sliders and steppers.

### 9. Affordance
An object's physical and visual traits indicate how it can be operated:
- Visual cues (rounded button corners, subtle elevation/shadows separating a slider thumb from its track, pills, drag handles) tell people what is tappable, draggable, or resizable.
- Subtle animation (e.g., brief view bouncing on first appearance) hints that a container is scrollable.
- Make action possibilities unmistakable so non-interactive elements are never mistaken for buttons, and interactive controls are never overlooked.

### 10. Progressive Disclosure & The 80/20 Rule
Manage complexity by stepping users from the simple to the advanced:
- **80/20 Principle**: In most interfaces, 80% of users need only 20% of the available functionality.
- Surface the most vital 20% prominently (e.g., printer name, copies, page range in a print dialog).
- Hide the remaining 80% of specialized configuration behind secondary disclosure ("More Options", detail views, advanced sheets) to keep interfaces welcoming for newcomers while preserving full power for experts.

---

## 5. The Qualities of Great Design

*Source: Apple Design Evangelism (Lauren Strehlow & Apple Design Team, WWDC18 Session 801).*

> *"If something is quality, it implies that there is nothing random about it. Great designs are considered. They are organized, and they show a thought process has taken place."*

### What Quality Really Is
- **Not Random**: Quality is deliberate, intentional, and considered through every gap, alignment, and margin.
- **Rooted in Care**: Caring means taking yourself out of the equation and putting yourself in the shoes of the person using your product.
- **The Human Moment in the Background**: Quality is not about showing off the UI or clever code; the interface should recede into the background so the user's concentration remains completely on their task, their creation, or their moment.
- **Earned Trust**: Quality is like coolness—you cannot declare yourself high quality with a badge or label. Quality is earned through every single touchpoint, from store descriptions to error recovery.

### The 4 Design Aspirations
1. **Simple**: Does not try to do more than it needs to do. What it does, it does exceptionally well. It respects that users live in the real world and should not waste mental energy deciphering a confusing interface.
2. **Stunning**: Visual, interactive, and auditory polish where touch, motion, and aesthetics align seamlessly. Fosters active discovery (letting users explore and discover capability naturally) rather than bombarding them with modal tooltips.
3. **Timeless**: Designs built for durability over trends. A great design avoids short-lived fads and remains elegant, recognizable, and comfortable five to ten years later.
4. **Positive Impact**: Software that leaves a substantial, positive effect on people's daily lives—making their days easier, calmer, healthier, or more creative.

### Collaborative Design Techniques
- **Drawing Caricatures to Communicate**: When a shape, curve, or spacing feels uncomfortable but verbal description fails, sketch an exaggerated caricature of the flaw. Pushing an imperfection to its extreme helps collaborators immediately see and agree on the underlying issue.
- **Contextual In-Situ Validation**: Never assume a design will work based on screen mockups in conference rooms. Take prototypes out into the real environment and test them directly with people who have never seen the product.
- **Accepting Critique & Dismantling Blind Spots**: Staring at your own work creates natural blind spots. Avoid defensive reactions; treat feedback as a collaborative tool to elevate the work.
- **Modesty ("Know What You Don't Know")**: Never assume your personal habits, technical literacy, or physical abilities represent the universal experience. Ask continuous questions: *Will this work for someone using a screen reader? Someone in a hurry? Someone using a keyboard only?*
- **Shedding the Unessential ("Two or Three Hearts")**: When too many ideas clutter a vision, focus ruthlessly on the two or three moments or interactions testers genuinely loved most, and let the rest fall away.


---

## 6. Principles in Practice (Apple Design Evangelism, 2026)

Paraphrased from Apple's *Principles of great design* session.

- **Design = making something with intention.** Every feature spends people's time, attention, and trust — choosing what to build is mostly deciding what *not* to include. Ask whether it has purpose before sketching or coding.
- **Principles pull against each other.** Leaning into one (e.g. simplicity) can cost another (e.g. flexibility); there's no formula — judgment decides.
- **Agency = choices + forgiveness.** Let people dive in rather than follow a predetermined path; make every action undoable; interrupt only right before a *big* mistake. Forgiveness is what makes exploration feel safe.
- **Responsibility = privacy + safety.** Asking for data before explaining why is like a stranger demanding your phone number. Ask at the right moment, only for what's needed, say why. Ask *"How could this be misused? Who could be harmed? How do I prevent it?"*
- **AI features need safeguards.** Assume a model will sometimes output something wrong (e.g. a recipe suggestion that ignores a logged allergy). Add previews, confirmations, and disclaimers — and **remove the feature if the risk to safety outweighs its value.**
- **Familiarity = metaphor + consistency.** Metaphors must be neither too literal (unrecognizable) nor too abstract (meaningless); never redefine a known metaphor (trash = delete). Things that look the same must behave the same, and live in the same place (the window close button never moves).
- **Flexibility = context + ability + personalization.** The same task (music) differs at home, running, and driving; each device deserves a solution that uses what makes it unique; learn who your audience is (age, language, expertise, assistive tech); when no single layout suits everyone, let people rearrange or hide controls.
- **Simplicity ≠ minimalism.** Burying everything in one menu looks minimal but isn't simple. Simple = **concise** (plain language, no redundancy, fewer steps) + **clear** (hierarchy via order, spacing, contrast; answers *what matters, what's interactive, how do I interact*). Sometimes simpler means **adding** context — a play/pause button becomes clearer with elapsed/remaining time. You've arrived when you have *exactly enough*.
- **Craft is felt.** Laggy taps, jittery scrolling, misaligned icons, and layouts that break on rotation read as "cheap" and erode trust in the results. Ingredients: quality fonts, adaptive colors, clear icons, fluid immediate animation, reliable foundations — plus continual maintenance as hardware and features evolve.
- **Delight is a result, not a garnish.** Not confetti bolted on at the end: pick the emotion (relaxed, confident, excited) and reinforce it everywhere; it emerges from getting the other principles right.

## 7. From Idea to Interface (Apple Design Evangelism, 2025)

A walkthrough method for structuring any app, paraphrased from Apple's *Design foundations from idea to interface* session.

**Every screen must answer three questions immediately:** *Where am I? What can I do? Where can I go from here?* Looking polished can hide failing all three.

**Information architecture loop**
1. List everything the app does — features, workflows, nice-to-haves — without judging.
2. Imagine real use: when, where, in what routine; what helps vs. gets in the way. Add to the list.
3. Clean up: remove non-essentials, rename unclear things, group what belongs together. If you can't say what's essential, the UI can't either.

**Navigation**
- Tabs are for **navigation, never actions** (an "Add" tab is wrong — put Add in the toolbar of the screen where it's used).
- Every extra tab is another decision; merge tabs that are just sub-groupings of another.
- Label tabs plainly and pair with familiar icons.
- A toolbar with a **title** (not a menu, not branding) answers "where am I"; its screen-specific actions answer "what can I do."

**Content**
- Separate mixed content types into titled sections.
- **Progressive disclosure:** show a few items + a disclosure to see all; the expanded screen keeps the same arrangement so it feels like an expansion.
- Pick the container by content: a **list** for structured, text-heavy, scannable items (denser than image grids); a **collection/grid** for large sets of visual items with consistent spacing and little text.
- **Group large sets** to fight choice overload: by **time** (recent, seasonal, current events), by **progress** (drafts, continue watching, unfinished), by **patterns** (related items, genre, style).

**Visual design**
- **Squint test:** the heaviest, most colorful element wins attention — make sure that's the most important thing, and that sense of place isn't lost.
- Build hierarchy with **named text styles** (size + weight + contrast), which also survive longer strings, localization, and user text scaling.
- Text over imagery: add a gradient or blur behind the text; legibility first.
- Establish a small, rule-based palette and imagery style for personality; for everything dynamic (text, backgrounds, separators), use semantic colors named by purpose. Accent color sparingly — buttons, selection.
- "Lean on the system; add personality where it counts."

## 8. Design-System Lessons (Apple's 2025 visual refresh)

Key rules are captured in [Materials & Glass](./materials-and-glass.md) and [Adaptive Layout & Foldables](./adaptive-layout-and-foldables.md). The process lessons:
- **Design systemically:** every element, from the smallest control to the largest surface, is considered in relation to the whole.
- **Hierarchy through layout and grouping, not decoration.** Strip legacy bar backgrounds and borders.
- **Group bar items by function and frequency**; a crowded bar is a cue to cut or move secondary actions into a More menu; keep the primary action (Done) separate and tinted.
- **Tab-bar accessories** are for persistent features (a mini player) — never for screen-specific actions like Checkout.
- **Surfaces spring from their source** (action sheets from the tapped button) to show relationships; sheets that interrupt get a dimming layer, parallel tasks don't.
- **Design the anatomy once**, express it per device; components share anatomy and core interactions across platforms.
