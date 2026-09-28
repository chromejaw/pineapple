# Emerging Technologies & Intelligence

Universal interaction design principles for intelligent, spatial, and location-aware software.

---

## Generative AI

Generative AI empowers you to enhance your app or game with dynamic content and offer intelligent features that unlock new levels of creativity, connection, and productivity.

Generative artificial intelligence uses machine learning models to create and transform text, images, and other content. Use it to offer novel, delightful features that help people express themselves creatively, communicate effectively, and complete tasks more easily. For instance, generative AI can enable people to edit text, create imaginative stories and images, or interact with a character in a game that uses AI-generated dialog.


### Best practices

**Design your experience responsibly.** Responsible AI is the intentional design and development of AI features that considers their direct and indirect impacts on people, systems, and society. With generative AI, it’s often easy to quickly prototype an exciting new feature for your app, yet challenging to create a robust experience that works in all real-world situations. Unlike classic programming, small changes to inputs (or even the same input, when given multiple times) often produce very different outcomes with generative AI. You also can’t always anticipate what requests people will make and how the AI will respond. Orient your design process around crafting AI experiences that are inclusive, designed with care, and protect privacy.

**Keep people in control.** While AI can manipulate and create content, respect people’s agency and ensure they remain in charge of decision making and the overall experience. Honor their requests when in scope and the expected output is clear, and handle sensitive content carefully. Give them the ability to dismiss new content they don’t want, and revert or retry content transformations or other actions they don’t agree with. Clearly identify when and where you use AI.

**Ensure an inclusive experience for all.** AI models learn from data and tend to favor the most common information. This may lead to harmful, unintended biases and stereotypes. Take extra care when designing your AI feature to consider how assumptions and personal attributes might impact the feature you have in mind. For example, if you generate images or descriptions of people, ask people to provide the information needed for the feature to work well rather than solely inferring personal or cultural characteristics. Seek clarity before making assumptions that may lead to common stereotypes, such as about gender identities or relationship types. Test your feature across a diverse set of people to identify and correct stereotypes, and ensure inclusive results. For guidance, see Inclusion and Accessibility.

**Design engaging and useful generative features.** Generative AI is a powerful tool, but it’s not the right solution for every situation. Offer generative features when and where they provide clear and specific value, like time savings, improved communication, or enhanced creativity.

**Ensure a great experience even when generative features aren’t available or people opt not to use them.** In some cases, generative AI may be essential to an experience, and there’s no reasonable non-AI substitute. In other cases, AI may play a complementary role that enhances your app’s core functionality, but isn’t critical for people achieving their goals. For example, an AI emoji generator offers a fun way to create new, original emoji, but people can still use regular emoji too. The on-device AI summarization feature makes catching up with notifications faster, but people can still read notifications without it. When possible, consider offering a non-AI fallback.


### Transparency

**Communicate where your app uses AI.** Letting people know when and where your app uses AI sets expectations and gives people the opportunity to knowingly choose to use an AI-powered feature. Never trick someone into thinking they’re interacting with or viewing content authored by a human if they’re actually interacting with AI. Ensure your approach to disclosure aligns with any regulations in the regions where you offer your app.

**Set clear expectations about what your AI-powered feature can and can’t do.** Clarifying your experience’s capabilities and limitations helps people establish a mental model of your feature. For example, when you introduce a feature, you might offer a brief tutorial. For open-ended features like a search bar or generation prompt, consider offering curated suggestions that make it easy to get started. If your feature has known limitations, let people know up front, show them how to get good results, and explain why inferior results occur. For guidance, see Limitations.


### Privacy

**Choose a model type that fits your feature’s needs and protects people’s privacy.** On-device models keep people’s information on their device, respond quickly, and work offline. When a feature needs more processing power or a larger context size, server-based models are worth considering. Always weigh privacy alongside capability and performance. For any server-based processing, take steps to protect people’s privacy. For example, process as much information locally as possible, and minimize what’s shared. Be transparent by making sure people know their information may be sent to a server, showing them what’s shared, and helping them understand what data may be stored off-device or used for training.

**Ask permission before using personal information and usage data.** Some interactions with an AI model may involve sensitive information, like personal details, messages, photos, and feature usage information. After obtaining permission, use the minimum data you need and always offer a clear way to opt out of its use. If you need sensitive data for model improvement or storage, get explicit permission and handle it with care. If you share data with third parties, understand their approach to privacy. Be aware that model outputs can inadvertently contain sensitive information. Note that apps for kids have stricter rules and laws around what data you can use. For guidance, see Requesting permission.

**Clearly disclose how your app and its model use and store personal information.** People are more likely to be comfortable sharing data when they understand how it’s used. Empower people to make an informed decision about what data they share with your AI model. When asking for permission to use someone’s information, explain the benefits in a way that’s concise, specific, and easy to understand. Articulate whether your model uses personal information for training and improvement.


### Models and datasets

**Thoughtfully evaluate model capabilities.** There are different types of generative models, some of which possess general knowledge, while others are trained for specific tasks. It’s important to understand the capabilities of any model you consider. As early as you can, get a hands-on look at the models and data available to help orient your design. Keep in mind that some model types may be unavailable to people in certain situations due to factors like device compatibility, network access, and battery level. For example, an on-device model may require a compatible device with the system AI features turned on.

**Be intentional when choosing or creating a dataset.** Whether you’re training a model from scratch or customizing an existing model, the data you choose greatly impacts the model’s behavior. When you teach and evaluate your AI model, choose datasets that include a diverse range of subject matter representations. Learn where your data comes from and how it was gathered. Ensure you have relevant licenses for all data you don’t personally own, and offer appropriate choices when using people’s data. Most datasets gathered from the real world are imperfect, so allow time for testing and evaluation to proactively mitigate bias and misinformation that a model might learn and replicate.


### Inputs

**Guide people on how to use your generative feature.** Consider how to steer and educate people toward producing great results. One technique is to offer diverse, predefined example inputs that hint at what’s possible for a feature.

**Raise awareness about and minimize the chance of hallucinations.** When a generative model is unsure how to respond to a request, it may produce content that seems plausible but is made up. These hallucinations can misinform people because the model may convincingly present the information as factual, even when it’s not. Generative models sometimes get details wrong, like dates of important events or information about people, so it’s important to clearly communicate that AI-generated content may contain errors. You can minimize the chance of hallucinations and limit their impact by carefully scoping what you ask a model to generate. Avoid requesting factual information unless you’re confident the model has access to verified and up-to-date information for the task. Avoid using AI-generated content in situations where a possible hallucination could misinform and harm someone.

**Consider consequences and get permission before performing irreversible or potentially problematic tasks.** Before performing a task, consider whether a mistake or the inability to reverse the action might cause more work or stress for people. Avoid automating destructive actions, like deleting photos, and actions that are hard to undo, like making a purchase on a person’s behalf. Generally, ask for confirmation before performing a significant action on someone’s behalf. Keep in mind that certain situations may be prohibited or have extra rules. Review and adhere to model-specific usage policies, as well as government and regulatory AI policy as it applies to each locale in which the generative features will be available.


### Outputs

**Make it easy for people to refine or revert generated results, and acknowledge when their corrections take effect.** For example, surfacing controls like Edit, Undo, Retry, or Adjust near generated content preserves people’s agency while still letting them benefit from automation. When people adjust or personalize output, provide a clear signal that their action had an effect. This kind of feedback helps people build an accurate mental model of your feature and fosters trust over time.

**Help people improve requests when blocked or undesirable results occur.** Minimize scoped or blocked output by coaching people how to be more successful next time. For example, if prompted to generate harmful content, an image generator might say it’s “Unable to use that description.” When possible, consider offering example requests that might lead to better results.

**Reduce unexpected and harmful outcomes with thoughtful design and thorough testing.** People generally use apps with good intentions, but harmful outcomes can still arise from both accidental and purposeful misuse, and when responding to potentially sensitive topics. It may not be possible to mitigate every harmful scenario, but taking a proactive approach to identify risks, devising policies to address them, and evaluating features can help minimize the chance of misuse and harm. Consider ways people might interact with your feature and test those scenarios. Challenge your policies and expected use cases. See what happens when requests are out-of-scope, unrelated to the app experience you designed, and not well-represented by the model’s training data. Try requests that are poorly phrased, vague, or ambiguous; include personal, sensitive, or controversial topics; and encourage harmful or incorrect results. Use what you learn to improve your model, inform prevention, and respond thoughtfully.

**Strive to avoid replicating copyrighted content.** Large AI models are trained using vast datasets from the internet and other sources. This means most generative models are familiar with and can unintentionally produce content similar to published work, including copyrighted content. You can reduce the likelihood of copyright infringement by building upon existing models that already protect against this, and by carefully curating inputs. For example, you might let people choose from a set of pre-approved prompts. You could also explicitly tell the model to avoid mimicking certain content or styles.

**Factor processing time into your design.** *Latency* is how much time it takes for a model to produce an output. Non-generative models, such as body-pose tracking and on-device vision models, typically have low latency and are suitable to run in real-time. Generative models typically take longer to produce a result, so design a loading experience or generate in the background while a person uses another part of the app. For guidance, see Loading.

**Consider giving specific, reassuring feedback during generation.** Messages that describe what’s actually happening can be more helpful than a vague status message. For example, instead of “Processing…”, say “Finding substitutions for ingredients” or “Summarizing key themes from your notes.” Specific feedback reduces uncertainty and makes waiting feel purposeful. If something goes wrong, describe what happened in plain language and offer a clear next step.

**Consider offering alternate versions of results.** Depending on the design of your feature, it might work best to present a single result or multiple meaningfully different results from which people can choose. Offering people a choice can give them a greater sense of control and help bridge the gap between the model’s interpretation and what someone actually wants. For example, an image generator can produce multiple images that represent a person, allowing someone to pick the one they prefer. For guidance, see Multiple options.


### Continuous improvement

**Consider ways to improve your model over time.** You may want to update your model to adapt to people’s behavior, respond to feedback, include new data, and leverage enhanced capabilities. You can make some improvements, such as updating a list of blocked words, frequently and independent of the app development cycle, and you can plan significant improvements and new features around regular app updates. Plan for fine-tuning, retesting, and prompt engineering when updating to a newer, more capable base model. If you train your own model, retrain with additional data and fine-tune to improve performance. Thoroughly test and refine all model updates to identify and correct unexpected behavior.

**Let people share feedback on outputs.** Feedback can help you identify and respond to unexpected outcomes and new potential issues that arise despite thorough testing. Feedback also gives people a way to celebrate what they like best about your AI experience and report concerns when outputs don’t match their expectations. Establish trust by taking feedback seriously and resolving issues quickly. Always make providing feedback voluntary. Respect people’s time by placing a feedback affordance in a clear location that doesn’t interrupt the experience. Consider offering a quick and easy way to give positive and negative feedback, like simple thumbs-up and thumbs-down buttons. You might also offer a way to share detailed feedback for complicated issues. For guidance, see Explicit feedback and Implicit feedback.

**Design flexible, adaptable features.** Generative AI is a rapidly advancing technology, and models and their resource needs are constantly evolving. Consider ways your app or game can adapt as capabilities and models improve. For example, you may want to separate your model from your user experience so you can swap out the model for other models over time. Lay a foundation that allows for future adjustments like this, while still offering the same great user experience.


---

## Machine learning

Machine learning enables apps and games to learn from data and usage patterns, letting you improve existing experiences and create engaging new ones.

In addition to providing familiar features like image recognition and content recommendations, your app can use machine learning to forge deep connections with people and help them accomplish more with less effort.

For related guidance on how to use machine learning models to enable intelligent experiences, see Generative AI.


### Planning your design

Features powered by machine learning use *models* to perform tasks that make people’s experiences more unique, like curated feeds, customized trip itineraries, and personalized search suggestions. These features depend on well-designed models as much as they depend on a well-designed UI and user experience.

As you design your models, keep the intended experience of your app in mind. It can take a long time to adjust the behavior of models, so be prepared to change the way you use data and metrics if the app experience needs to change.

Designing the UI and user experience of a machine learning app can be uniquely challenging. Because a machine learning app bases its behavior on the data it receives — reacting to changing information and conditions — you can’t design specific reactions to a static set of scenarios. Instead, you design the experience by teaching the app how to interpret data and react accordingly.

To help you meet this challenge, first consider the role that machine learning plays in your app. Defining the role of machine learning in your app can help you discover areas in which you can explore the ways machine learning can affect the experience your app provides.

Use the machine learning role you identify to help you define ways your app can receive and display data. There are several patterns — grouped into *inputs* and *outputs* — that provide guidance in areas such as getting feedback, displaying data, handling mistakes, and supporting corrections. Use the guidance in these patterns to help you integrate machine learning into your app in ways that people appreciate.


### The role of machine learning in your app

Machine learning systems vary widely, and the ways an app can use machine learning vary widely, too. As you approach the design of your app, think about how its features use machine learning in each of the following areas.


#### Critical or complementary

If an app can still work without the feature that machine learning supports, machine learning is complementary to the app; otherwise, it’s a critical dependency. For example:

- The keyboard uses machine learning to provide QuickType suggestions. Because the keyboard still works without these suggestions, machine learning plays a complementary role in the app.

- Face authentication relies on machine learning to perform accurate face recognition. Without machine learning, face authentication would not work.

In general, the more central a feature is to your app’s purpose — like a personalized news feed for a news app — the more people expect accurate and reliable results. On the other hand, for secondary features, people are often more forgiving if the results aren’t perfectly accurate every time.


#### Private or public

Machine learning results depend on data. To make good design decisions, you need to know as much as possible about the types of data your app’s feature needs. In general, the more sensitive the data, the more serious the consequences of inaccurate or unreliable results. For example:

- If a health app misinterprets data and incorrectly recommends a visit to the doctor, people are likely to experience anxiety and may lose trust in the app.

- If a music app misinterprets data and recommends an artist that people don’t like, they’re likely to view the result as an inconsequential mistake.

As with critical app features, features that use sensitive data must prioritize accuracy and reliability. Regardless of the sensitivity of the data, all apps must protect user privacy at all times.


#### Proactive or reactive

A *proactive* feature provides results without people requesting it to do so. Proactive features can prompt new tasks and interactions by providing unexpected, sometimes serendipitous results. In contrast, a *reactive* feature provides results when people ask for them or when they take certain actions. Reactive features typically help people as they perform their current task. For example:

- Voice-assistant suggestions can proactively suggest a shortcut based on people’s recent routines.

- QuickType suggests words in reaction to what people type.

Because people don’t ask for the results that a proactive feature provides, they may have less tolerance for low-quality information. To reduce the possibility that people will find proactive results intrusive or irrelevant, you may need to use additional data for the feature.


#### Visible or invisible

Apps may use machine learning to support visible or invisible features. People are usually aware of visible app features because they tend to offer suggestions or choices that people view and interact with. For example, an image generator lets people describe an image, adjust it visually, or remix results through quick edits.

As the name suggests, an invisible feature provides results that aren’t obvious to people. For example, the News app proactively suggests topics and channels based on a person’s previous engagement. Because this improves the app experience without requiring people to make choices, many people aren’t aware that the feature exists.

People’s impression of the reliability of results can differ depending on whether a feature is visible or invisible. With a visible feature, people form an opinion about the feature’s reliability as they choose from its results. It’s harder for an invisible feature to communicate its reliability — and potentially receive feedback — because people may not be aware of the feature at all.


#### Dynamic or static

All machine learning models can improve, but some improve dynamically, as people interact with the feature, and others improve offline and affect the feature only when the app updates.

In addition to the frequency of app updates, static or dynamic improvements can affect other parts of the user experience, too. For example, dynamic features often incorporate forms of calibration and feedback (either implicit or explicit), whereas static features might not.


### Explicit feedback

Explicit feedback provides actionable information your app can use to improve the content and experience it presents to people. Unlike implicit feedback — which is information an app gleans from user actions — explicit feedback is information people provide in response to a specific request from the app.

*Favoriting* — marking an item for quick access in the future — and *social feedback* — expressing emotions toward others — are common user interactions that seem like mechanisms that supply explicit feedback. However, these tools actually provide implicit feedback because they don’t support app-specific requests. People use favoriting and social feedback to accomplish their own goals and apps can gather implicit feedback from these interactions.

**Request explicit feedback only when necessary.** People must take action to provide explicit feedback, so it’s best to avoid requesting it if possible. Instead, consider using implicit feedback to learn how people interact with your app without asking them to do extra work.

**Always make providing explicit feedback a voluntary task.** You want to communicate that explicit feedback can help improve the experience without making people feel that providing it is mandatory.

**Use simple, direct language to describe each explicit feedback option and its consequences.** Avoid using imprecise terms such as *dislike* because such terms don’t convey consequences and can be hard to translate. Instead, describe each option in a way that helps people understand what happens when they choose the option, such as:

- Suggest less pop music

- Suggest more thrillers

- Mute politics for a week

**Add icons to an option description if it helps people understand it.** Icons can help clarify or emphasize part of an option description. Avoid using an icon by itself, because it might not be clear enough to communicate granularity or consequences.

**Consider offering multiple options when requesting explicit feedback.** Providing multiple options can give people a sense of control and help them identify unwanted suggestions and remove them from your app. To help people provide feedback, consider offering options that become progressively more specific so that it’s easy for people to clarify their response.

**Act immediately when you receive explicit feedback and persist the resulting changes.** For example, if people identify content they don’t want to see, hide it from their view and ensure it doesn’t appear elsewhere in your app. When you react immediately to feedback and show that your app remembers it, you build people’s trust in the value of providing it.

**Consider using explicit feedback to help improve when and where you show results.** For example, people might like a result, but they may not want to see it at certain times or in certain contexts. Explicit feedback on when and where to show results can help you fine-tune the experience people have in your app.


### Implicit feedback

Implicit feedback is information that arises as people interact with your app’s features. Unlike the specific responses you get from explicit feedback, implicit feedback gives you a wide range of information about user behavior and preferences. Although incorporating implicit feedback isn’t required for a great machine learning app, the feedback can help you improve your app’s user experience without asking people to do any extra work.

**Always secure people’s information.** Implicit feedback can gather potentially sensitive user information, so you must be particularly careful to maintain strict controls on user privacy.

**Help people control their information.** As an app developer, you know that the more you understand about the behavior of your users — both within your app and in other apps — the more you can improve the experience your app provides. Although most people understand the benefits of making their information available to multiple apps, they may still be surprised when things they do in one app affect experiences they have in a different app. Worse, people may assume that apps are sharing their private information, which can cause them to lose trust in the apps. It’s important to tell people how your app gets and shares their information and to give people ways to restrict the flow of their information.

**Don’t let implicit feedback decrease people’s opportunities to explore.** Implicit feedback tends to reinforce people’s behavior, which can improve the user experience in the short term, but may worsen it in the long term. For example, it might seem like a good idea to give people a set of suggestions that matches all the things they’re interested in now, but doing so doesn’t encourage them to explore new things.

**When possible, use multiple feedback signals to improve suggestions and mitigate mistakes.** Implicit feedback is indirect, so it can be difficult to discern a person’s actual intent in the information you gather. For example, if someone views a photo, shares it in a message, and adds it to a shared album, it doesn’t necessarily mean they have positive feelings about the photo. Incorporate implicit feedback from multiple sources and interactions to help you avoid misinterpreting people’s intentions.

**Consider withholding private or sensitive suggestions.** People often share their accounts and devices with others, or switch from using a personal device to a communal one. If your app receives implicit feedback related to private or sensitive topics, avoid offering recommendations based on that feedback.

**Prioritize recent feedback.** People’s tastes can change frequently, so base your recommendations on recent implicit feedback. For example, face authentication prioritizes recent facial input because it’s most likely to represent what the person looks like now. If recent feedback isn’t available, you can fall back to historical feedback.

**Use feedback to update predictions on a cadence that matches the person’s mental model of the feature.** For example, people expect typing suggestions to update immediately as they’re typing. On the other hand, giving people continuously updated song recommendations makes it hard to consider individual songs and could make them feel rushed or overwhelmed.

**Be prepared for changes in implicit feedback when you make changes to your app’s UI.** Even small UI changes can lead to noticeable changes in the amount and types of implicit feedback. For example, changing the location of a button can affect how people use it, even if there’s no change in the benefit they get from the button’s action. Take such changes into account when interpreting the implicit feedback you receive from interactions in your app.

**Beware of confirmation bias.** Implicit feedback is constrained by what people can actually see and do in your app and other apps — it rarely gives you insight into new things they might like to do. Avoid relying solely on implicit feedback to inform your results.


### Calibration

Calibration is a process during which people provide information that a feature needs to function. To use face authentication, for example, a person must first scan their face.

In general, only use calibration when your feature can’t function without that initial information. If your feature can work without calibration, consider using other ways to gather the information you need, such as implicit feedback or possibly explicit feedback.

**Always secure people’s information.** During calibration, people may provide sensitive information and you must make sure it remains secure.

**Be clear about why you need people’s information.** Typically, calibration is required before people can use a feature, so it’s essential that they understand the value of providing their information. As you briefly describe how people can benefit from your feature, emphasize what it does rather than how it works.

**Collect only the most essential information.** Designing a unique experience that requests a minimal amount of information can make people more comfortable participating in the process and increase their trust in your app.

**Avoid asking people to participate in calibration more than once.** Also, it’s best when calibration occurs early in the user experience. As people continue using your app or feature, you can use implicit or explicit feedback to evolve your information about them without asking them to participate again. An exception is a feature that needs calibration with an object instead of a person. For example, an app that helps people improve their baseball swing might need to calibrate with each new baseball field.

**Make calibration quick and easy.** Even a brief calibration experience takes time and requires effort from people. An ideal calibration experience makes it easy for people to respond, without compromising the quality of the information they provide. The following guidelines can help you create a streamlined calibration experience.

- Prioritize getting a few pieces of important information and infer the rest from other sources or by getting people’s feedback.

- Avoid asking for information that most people would have to look up.

- Avoid asking people to perform actions that might be difficult.

**Make sure people know how to perform calibration successfully.** After people decide to participate in calibration, give them an explicit goal and show their progress toward it. For example, face authentication calibration briefly describes what people need to do and changes the appearance of the tick marks encircling the face as people progress through scanning.

**Immediately provide assistance if progress stalls.** When progress stalls, people can feel stuck or powerless, and they may lose trust in your app. In this situation, it’s crucial to give people actionable recommendations that quickly get them back on track. As you provide this guidance, never imply that something’s wrong or that people are at fault, and never leave people without a clear next step.

**Confirm success.** The moment people successfully complete calibration, reward their time and effort by giving them a clear path toward using the feature. Providing an explicit completion to the calibration experience reinforces the unique nature of the experience and helps people switch their focus to your feature.

**Let people cancel calibration at any time.** Make sure you give people an easy way to cancel the experience at any point and avoid implying any judgment about their choice. There’s no need to provide any messaging that mentions the canceled calibration, because the next time people attempt to use the feature, they’ll have another chance to participate.

**Give people a way to update or remove information they provided during calibration.** Letting people edit their information gives them more control and can lead them to have greater trust in your app. Although the calibration experience can help people edit their responses, it’s a good idea to let people edit their information outside of the calibration experience so that they feel free to make changes at any time.


### Mistakes

It’s inevitable that your app will make mistakes. Although people may not expect perfection, mistakes can damage their experience and decrease their trust in your app. To help you avoid negative consequences, it’s crucial to:

- Anticipate mistakes. As much as possible, design ways to avoid mistakes and mitigate them when they happen.

- Help people handle mistakes. Mistakes can have a wide range of consequences, so the tools you provide to handle a mistake must be able to address those consequences.

- Learn from mistakes when doing so improves your app. In some cases, learning from a mistake might have undesirable effects, such as causing unpredictability in the user experience. When it makes sense, use each mistake as a data point that can refine your machine learning models and improve your app.

There are several machine learning patterns that can help you address mistakes:

- Limitations help you set people’s expectations about the accuracy of your suggestions.

- Corrections give people a way to be successful even when your results are wrong.

- Attribution gives people insight into where suggestions come from, which can help them understand mistakes.

- Confidence helps you gauge the quality of your results, which can impact how you present them.

- Feedback — both explicit and implicit — lets people tell you about mistakes that you might not be aware of.

**Understand the significance of a mistake’s consequences.** For example, incorrect keyboard suggestions might annoy people, but suggesting a travel route that results in a missed flight is a serious inconvenience. Show empathy by providing corrective actions or tools that match the seriousness of the mistake.

**Make it easy for people to correct frequent or predictable mistakes.** If you don’t give people an easy way to correct mistakes, they can lose trust in your app.

**Continuously update your feature to reflect people’s evolving interests and preferences and help avoid mistakes.** For example, you can use implicit feedback to discover changes in people’s tastes and habits. It’s also a good idea to update your feature with domain-specific information, such as current trends in popular entertainment. Ideally, people don’t have to do any work to benefit from improvements in your app.

**When possible, address mistakes without complicating the UI.** Some patterns, such as corrections and limitations, tend to integrate seamlessly with an app’s UI, whereas others, like attributions, can be harder to integrate. Balance a pattern’s effect on the UI with its potential for compounding the mistake. For example, if you update the UI with an attribution that turns out to be wrong, the effect of the original mistake is magnified.

**Be especially careful to avoid mistakes in proactive features.** A proactive feature — like a suggestion based on people’s behaviors — promises valuable results without asking people to do anything to get them. However, because people don’t request a proactive feature, they often have less patience with its mistakes. Mistakes made by proactive features can also cause people to feel that they have less control.

**As you work on reducing mistakes in one area, always consider the effect your work has on other areas and overall accuracy.** For example, optimizing an image-recognition app to improve how it recognizes dogs might result in a decreased ability to recognize cats. As your models evolve, be prepared for mistakes to evolve, too. Use what you know about people’s preferences to help you determine the areas to work on.


### Corrections

People use corrections to fix mistakes that apps make. For example, if a photo app automatically crops a photo in a way people don’t like, they can correct the mistake by cropping the photo in a different way.

**Give people familiar, easy ways to make corrections.** When your app makes a mistake, you don’t want people to be confused about how to correct it. You can avoid causing confusion by showing the steps your app takes as it performs the automated task. For example, a photos app highlights the controls it uses to auto-crop a photograph so that people can use the same controls to refine or undo the results.

**Provide immediate value when people make a correction.** Reward people’s effort by instantly displaying corrected content, especially when the feature is critical or you’re responding to direct user input. Also, be sure to persist the updates so people don’t have to make the same corrections again.

**Let people correct their corrections.** Sometimes, people make a correction without realizing that they’ve made a mistake. As you do with all corrections, respond immediately to an updated correction and persist the update.

**Always balance the benefits of a feature with the effort required to make a correction.** People may not mind when a feature that automates a task makes a mistake, but they’re likely to stop using the feature if it seems easier to perform the task themselves.

**Never rely on corrections to make up for low-quality results.** Although corrections can reduce the impact of a mistake, depending on them may erode people’s trust in your app and reduce the value of your feature.

**Learn from corrections when it makes sense.** A correction is a type of implicit feedback that can give you valuable information about ways your app doesn’t meet people’s expectations. Before you use a correction to update your models, make sure that the correction will lead to higher quality results.

**When possible, use guided corrections instead of freeform corrections.** Guided corrections suggest specific alternatives, so they require less user effort; freeform corrections don’t suggest specific alternatives, so they require more input from people. An example of guided correction is a speech-to-text feature that gives people a list of alternative text completions from which to choose. In contrast, a photos app offers freeform correction so that people can adjust the auto-cropping of a photo as they see fit. If it makes sense in your app, you can support a combination of guided and freeform corrections.


### Multiple options

Depending on the design of your feature, it might work best to present a single result or multiple results from which people can choose. Providing multiple options can give people a greater sense of control and can help bridge the gap between your model’s predictions and what people actually want. Multiple options can also encourage people to have realistic expectations about the types of results your app generates.

You might present multiple options to people in the following contexts:

- Suggested options, a proactive feature that suggests content to people based on their past interactions. For example, personalized “For You” recommendations in a music app.

- Requested options, a reactive feature that suggests potential next steps to people based on their recent actions. For example, QuickType suggestions.

- Corrections, which are actions people take to fix mistakes your app has made when it’s acting on their behalf. For example, a photo app’s auto-crop feature.

**Prefer diverse options.** When possible, balance the accuracy of a response with the diversity of multiple options. For example, a maps app generally suggests more than one route to a destination, such as a route without tolls, a scenic route, or a route that uses highways. Providing different types of options helps people choose the one that they prefer and can also suggest new items that might interest them.

**In general, avoid providing too many options.** People must evaluate each option before making a choice, so having more options increases cognitive load. When possible, list options on one screen so people don’t have to scroll to find the right one.

**List the most likely option first.** When you know how your confidence values correlate with the quality of your results, you might use them to rank the options. You might also consider using contextual information, such as the time of day or the current location, to help you determine the most likely option. If it makes sense in your app, select the first option by default so people can quickly achieve their goals without reading through every option.

**Make options easy to distinguish and choose.** For example, in a routing app, people often need to make route choices quickly to avoid going the wrong way. When options look similar, help people distinguish between them by providing a brief description of each one and taking particular care to highlight the differences. In cases where there are too many options to display in a single view, such as with content recommendations, consider grouping options in categories that people can scan rapidly.

**Learn from selections when it makes sense.** People give you implicit feedback every time they make a selection. When it doesn’t adversely affect the user experience, use this feedback to refine the options you provide and increase the chance that you’ll present the most likely option first. In general, continuing to offer incorrect results is likely to decrease people’s trust in the quality of your app’s predictions.


### Confidence

Confidence indicates the measure of certainty for a result. Not all models produce confidence values by default, so you might consider computing them if you can use them to improve the user experience of your app.

Although it might seem like higher confidence produces a higher quality result — and therefore a better user experience — it doesn’t necessarily work that way. You need to verify that your confidence values correspond to the quality of your results. For example, you might review values for multiple confidence thresholds or compare values across multiple versions of your app. If you’re not sure how your confidence values correlate with the quality of your results, it’s not a good idea to convey confidence to people.

**Know what your confidence values mean before you decide how to present them.** For example, people may forgive low-quality results from critical or complementary features — especially when results are accompanied by attribution or other contextual information — but presenting low-quality results in a prominent way is likely to erode trust in your app.

**In general, translate confidence values into concepts that people already understand.** Simply displaying a confidence value doesn’t necessarily help people understand how it relates to a result. For example, a feature that suggests new music based on a person’s listening habits might calculate that there’s a 97% match between a new song and the songs they usually listen to. However, displaying “97% match” next to the new song as an attribution doesn’t communicate enough information to help people make a choice. In contrast, providing an attribution that clearly identifies the behavior — such as “Because you listen to pop music” — can be more actionable.

**In situations where attributions aren’t helpful, consider ranking or ordering the results in a way that implies confidence levels.** If you must display confidence directly, consider expressing it in terms of semantic categories. For example, a feature that predicts travel prices might replace ranges of confidence numbers with categories like “high chance” and “low chance” to give context to the values and help people understand and compare the results.

**In scenarios where people expect statistical or numerical information, display confidence values that help them interpret the results.** For example, weather predictions, sports statistics, and polling numbers are often accompanied by specific values that express the accuracy of the data as an interval or a percentage.

**Whenever possible, help people make decisions by conveying confidence in terms of actionable suggestions.** Understanding people’s goals is key to expressing confidence in ways that help them make decisions. For example, if your feature predicts when an item will be at its lowest price, you know that people want to optimize how they spend their time and money. For a feature like this, displaying percentages or other numerical confidence values would be less valuable than providing actionable suggestions like “This is a good time to buy,” or “Consider waiting for a better price.”

**Consider changing how you present results based on different confidence thresholds.** If high or low levels of confidence have a meaningful impact on the ways people can experience the results, it’s a good idea to adapt your presentation accordingly. For example, when confidence is high, the face recognition feature in a photos app simply displays the photos that contain a specific person, but when confidence is lower, the feature asks people to confirm whether the photos contain the person before showing more.

**When you know that confidence values correspond to result quality, you generally want to avoid showing results when confidence is low.** Especially when a feature is proactive and can make unbidden suggestions, poor results can cause people to be annoyed and even lose trust in the feature. For suggestions and proactive features, it’s a good idea to set a confidence threshold below which you don’t offer results.


### Attribution

An attribution expresses the underlying basis or rationale for a result, without explaining exactly how a model works. Depending on the design of your app, you might want to use attributions to impart transparency and give people insight into your results. For example, if your app suggests books for people to read, you might use an attribution like “Because you’ve read mysteries” when you suggest books in the “thrillers” category.

To help you decide whether to include attributions in your app, consider how you want them to affect people. For example, you might want attributions to:

- Encourage people to change what they do in your app

- Minimize the impact of mistakes

- Help people build a mental model of your feature

- Promote trust in your app over time

**Consider using attributions to help people distinguish among results.** For example, if you present a set of results as multiple options, including attributions can help people choose an option based on their understanding of the premise that led to it, such as “New books by authors you’ve read.”

**Avoid being too specific or too general.** Overly specific attributions can make people feel like they have to do additional work to interpret the results, whereas overly general attributions typically don’t provide useful information. The best attributions strike a balance between these extremes.

**Keep attributions factual and based on objective analysis.** To be useful, an attribution needs to help people reason about a result; you don’t want to provoke an emotional response. Don’t provide an attribution that implies understanding or judgment of people’s emotions, preferences, or beliefs. For example, an app that recommends new content to people can use an attribution like “Because you’ve read nonfiction” instead of an attribution like “Because you love nonfiction.”

**In general, avoid technical or statistical jargon.** In most situations, using percentages, statistics, and other technical jargon doesn’t help people assess the results you provide. The exception to this is when the result itself is of a statistical or technical nature, such as information in the areas of weather, sports, polling and election results, or scientific data.


### Limitations

Every feature — whether it’s based on machine learning or not — has certain limitations to what it can deliver. In general, there are two types of limitations: things a feature can’t do well and things a feature can’t do at all. When there’s a mismatch between people’s expectations about a feature and what the feature can actually accomplish, a limitation can seem like a defect.

An important part of the design process is to identify the scenarios where limitations impact the user experience and design ways to help people work with them. For example:

- Set people’s expectations before they use the feature.

- Show people how to get the best results while they’re using the feature.

- When inferior results occur, explain why so that people can understand the feature better.

**Help people establish realistic expectations.** When a limitation may have a serious effect on user experience but happens rarely, consider making people aware of the limitation before they use your app or feature. You might describe the limitation in marketing materials or within the feature’s context so that people can decide how they want to rely on the feature. If the effects of a limitation aren’t serious, you can help set people’s expectations by providing attributions.

**Demonstrate how to get the best results.** If you don’t provide guidance for using a feature, people may assume it’ll do everything they want. When you proactively show people how to get good results, you help them benefit from the feature and establish a more accurate mental model of the feature’s capabilities. There are many ways to show people the best ways to use a feature, such as:

- Use placeholder text to suggest input. In a photos app, the search bar might display “Photos, People, Places…” to help people understand what they can search for before they begin typing, along with a description of how it scans the photo library to offer search suggestions.

- As people interact with the feature, provide feedback on their actions to guide them toward a result without overwhelming them. For example, while people are interacting with Memoji, the feature responds to current conditions and suggests how people can improve their results by adjusting the lighting or moving closer to the camera.

- Suggest alternative ways to accomplish the goal instead of showing no results. To do this successfully, you need to understand the goal well enough to suggest alternatives that make sense.

**Explain how limitations can cause unsatisfactory results.** People can get frustrated when it seems that your feature works intermittently. Ideally, your feature can recognize and describe the reasons for poor results to make people aware of the limitations and help them to adjust their expectations. For example, Memoji tells people that it doesn’t work well in the dark.

**Consider telling people when limitations are resolved.** When people use a feature frequently, they learn to avoid the interactions that fail because of the feature’s limitations. When you update your app to remove a limitation, you might want to notify people so that they can adjust their mental model of your feature and return to interactions they’d previously avoided.


---

## Augmented reality

Augmented reality (or AR) lets you deliver immersive, engaging experiences that seamlessly blend virtual objects with the real world.

Using the device’s camera to present the physical world onscreen live, your app can superimpose three-dimensional virtual objects, creating the illusion that these objects actually exist. Depending on the platform and the experiences your app offers, people can reorient the device to explore the objects from different angles, interact with objects using gestures and movement, and even join other people in multiuser AR experiences.

**Offer AR features only on capable devices.** If your app’s primary purpose is AR, make your app available only to devices that support AR. If your app includes features that require specific AR capabilities, or if AR features are optional in your app, don’t show people an error if they try to use these features on a device that doesn’t support them; instead, simply avoid offering the feature on an unsupported device.

> **Note**: The following guidance applies to handheld (phone and tablet) AR.


### Best practices

**Let people use the entire display.** Devote as much of the screen as possible to displaying the physical world and your app’s virtual objects. Avoid cluttering the screen with controls and information that diminish the immersive experience.

**Strive for convincing illusions when placing realistic objects.** Design detailed 3D assets with lifelike textures to create objects that appear to inhabit the physical environment in which you place them. Using information from the AR system, you can scale objects properly and position them on detected real-world surfaces, reflect environmental lighting conditions and simulate camera grain, cast top-down diffuse object shadows on real-world surfaces, and update visuals as the camera’s position changes. To help avoid breaking the illusion you create, make sure your app updates scenes 60 times per second so objects don’t appear to jump or flicker.

**Consider how virtual objects with reflective surfaces show the environment.** Reflections in the AR system are approximations based on the environment captured by the camera. To help maintain the illusion that an AR experience is real, prefer small or coarse reflective surfaces that downplay the effect of these approximations.

**Use audio and haptics to enhance the immersive experience.** A sound effect or bump sensation is a great way to confirm that a virtual object has made contact with a physical surface or other virtual object. Background music can also help envelop people in the virtual world. For guidance, see Playing audio and Playing haptics.

**Minimize text in the environment.** Display only the information that people need for your app experience.

**If additional information or controls are necessary, consider displaying them in screen space.** Content in *screen space* appears fixed to a consistent location either in the virtual world or, less commonly, on the device screen. It’s typically easy for people to find and view content in screen space because it remains stationary while the underlying AR environment moves with the device.

**Consider using indirect controls when you need to provide persistent controls.** *Indirect controls* are not part of the virtual environment — instead, they are 2D controls displayed in screen space. If people need access to persistent controls in your app, consider placing the controls so that people don’t have to adjust how they’re holding the device to reach them. Also, consider using translucency in an indirect control to help avoid blocking the underlying scene. For example, the Measure app uses screen space to display a mix of translucent and opaque controls that people use to measure objects in the real world.

**Anticipate that people will use your app in a wide variety of real-world environments.** People may open your app in a place where there isn’t much room to move around or there aren’t any large, flat surfaces. Clearly communicate your app’s requirements and expectations to people up front to help them understand how their physical environment can affect their AR experience. You might also consider offering different sets of features for use in different environments.

**Be mindful of people’s comfort.** Holding a device at a certain distance or angle for a prolonged period can be fatiguing. To help avoid causing fatigue, consider placing objects at a distance that reduces the need to move the device closer to the object; in a game, consider keeping levels short and intermixed with brief periods of downtime.

**If your app encourages people to move, introduce motion gradually.** For example, you might not want to make people dodge a virtual projectile as soon as they enter your AR game. Give people time to adapt to the AR experience in your app and then progressively encourage movement.

**Be mindful of people’s safety.** When people are immersed in an AR experience, they’re not necessarily aware of their physical surroundings, so making rapid, sweeping, or expansive motions might be dangerous. Consider ways of making your app safe to operate; for example, a game could avoid encouraging large or sudden movements.


### Providing coaching

Before people can enjoy an AR experience in your app, they need to move their device in ways that lets the AR system evaluate the surroundings and detect surfaces. Consider using the built-in coaching view to show people what to do and provide feedback during the initialization process. You can also use the coaching view to help people reinitialize AR — a process known as *relocalization* — after an AR experience is interrupted by, for example, people switching briefly to a different app. For guidance on relocalization, see Handling interruptions.

**Hide unnecessary app UI while people are using a coaching view.** By default, the coaching view appears automatically when initialization or relocalization starts, so be prepared to hide unrelated UI to help people concentrate on the coaching view’s instructions.

**If necessary, offer a custom coaching experience.** Although you can configure the system-provided coaching view to help people provide specific information — such as the detection of a horizontal or vertical plane — you might need additional information or want to use a different visual style. If you want to design a custom coaching experience, use the system-provided coaching view for reference.


### Helping people place objects

**Show people when to locate a surface and place an object.** You can use the system-provided coaching view to help people find a horizontal or vertical flat surface on which to place an object. After the AR system detects a surface, your app can display a custom visual indicator to show when object placement is possible. You can help people understand how the placed object will look in the environment by aligning your indicator with the plane of the detected surface.

**When people place an object, immediately integrate that object into the AR environment.** Although surface detection quickly and progressively refines accuracy, it’s best to avoid waiting for more accurate data before placing an object. Use the information available to respond instantly when people place an object; then, when surface detection completes, subtly refine the object’s position if necessary. For example, if people place an object beyond the bounds of the detected surface, gently nudge the object back onto the surface.

**Consider guiding people toward offscreen virtual objects.** Sometimes, it can be difficult for people to locate an object that’s positioned offscreen. When this is the case, you can help people find such objects by offering visual or audible cues. For example, if an object is offscreen to the left, you could display an indicator along the left edge of the screen that guides people to point the camera in that direction.

**Avoid trying to precisely align objects with the edges of detected surfaces.** In AR, surface boundaries are approximations that may change as people’s surroundings are further analyzed.

**Incorporate plane classification information to inform object placement.** For example, only let people place a virtual piece of furniture on a plane that’s classified as “floor,” or require a plane to be classified as “table” in order to place a virtual game board.


### Designing object interactions

**Let people use direct manipulation to interact with objects when possible.** It’s more immersive and intuitive when people can interact with onscreen 3D objects by touching them directly, than by using indirect controls in screen space. However, in situations where people are moving around as they use your app, indirect controls can work better.

**Let people directly interact with virtual objects using standard, familiar gestures.** For example, consider supporting a single-finger drag gesture for moving objects, and a two-finger rotation gesture for spinning objects. For guidance, see Gestures.

**In general, keep interactions simple.** Touch gestures are inherently two-dimensional, but an AR experience involves the three dimensions of the real world. Consider the following approaches to simplifying people’s interactions with virtual objects.

**Respond to gestures within reasonable proximity of interactive virtual objects.** It can be difficult for people to be precise when aiming to touch specific points on objects that are small, thin, or placed at a distance. When your app detects a gesture near an interactive object, it’s usually best to assume that people want to affect that object.

**Let people initiate object scaling when it makes sense in your app.** For example, if your app lets people explore an imaginary environment, it probably makes sense to support object scaling because your app doesn’t need to represent the real world. On the other hand, if your app helps shoppers decide on furniture to buy, letting people scale a chair object doesn’t help them visualize how the chair will look in a room.

> **Tip**: Regardless of the purpose of your app, don’t use scaling as a way to adjust the distance of an object. If you enlarge a distant object in an effort to make it appear closer, the result is a larger object that still looks far away.

**Be wary of potentially conflicting gestures.** A two-finger pinch gesture, for example, is similar to a two-finger rotation gesture. If you implement two similar gestures like this, be sure to test your app and make sure they’re interpreted properly.

**Strive for virtual object movement that’s consistent with the physics of your app’s AR environment.** People don’t necessarily expect an object to move smoothly over a rough or uneven surface, but they do expect objects to remain visible during movement. Aim to keep moving objects attached to real-world surfaces and avoid causing objects to jump or vanish and reappear as people resize, rotate, or move them.

**Explore even more engaging methods of interaction.** Gestures aren’t the only way for people to interact with virtual objects in AR. Your app can use other factors, like motion and proximity, to bring content to life. A game character, for example, could turn its head to look at a person as they walk toward it.


### Offering a multiuser experience

When multiple people share your app’s AR experience, each participant maps the environment independently and the AR system automatically merges the maps.

**Consider allowing people occlusion.** If your app supports placing virtual objects behind people who appear in the device’s camera feed, enhance the illusion of reality by letting the people occlude the objects.

**When possible, let new participants enter a multiuser AR experience.** Unless your app requires all participants to join before the experience begins, consider using implicit map merging to let new people quickly join an ongoing AR experience.


### Reacting to real-world objects

You can enhance an AR experience by using known images and objects in the real-world environment to make virtual content appear. For example, an app that recognizes theater posters for a sci-fi film could cause virtual space ships to emerge from the posters and fly around the environment. Another example is an app for an art museum that presents a virtual tour guide when it recognizes a sculpture. To support experiences like these, your app provides a set of 2D reference images or 3D reference objects, and the AR system indicates when and where it detects any of these items in the current environment.

**When a detected image first disappears, consider delaying the removal of virtual objects that are attached to it.** The AR framework doesn’t track changes to the position or orientation of each detected image. To help prevent virtual objects from flickering, consider waiting up to one second before fading them out or removing them.

**Limit the number of reference images in use at one time.** Image detection performance works best when the AR system looks for 100 or fewer distinct images in the real-world environment. If you need more than 100 reference images, you can change the set of active reference images based on context. For example, a museum guide app could ask permission to use location services to determine the part of the museum a person is in, and then look only for images displayed in that area.

**Limit the number of reference images requiring an accurate position.** Updating the position of a reference image requires more resources. Use a tracked image when the image may move in the environment or when an attached animation or virtual object is small compared to the size of the image.


### Communicating with people

**If you must display instructional text, use approachable terminology.** AR is an advanced concept that may be intimidating to some people. To help make it approachable, avoid using technical terms like SLAM, world detection, and tracking. Instead, use friendly, conversational terms that most people will understand.

| Do | Don’t |
| --- | --- |
| Unable to find a surface. Try moving to the side or repositioning your phone. | Unable to find a plane. Adjust tracking. |
| Tap a location to place the *[name of object to be placed]*. | Tap a plane to anchor an object. |
| Try turning on more lights and moving around. | Insufficient features. |
| Try moving your phone more slowly. | Excessive motion detected. |

**In a three-dimensional context, prefer 3D hints.** For example, placing a 3D rotation indicator around an object is more intuitive than displaying text-based instructions in a 2D overlay. Avoid displaying textual overlay hints in a 3D context unless people aren’t responding to contextual hints.

**Make important text readable.** Use screen space to display text used for critical labels, annotations, and instructions. If you need to display text in 3D space, make sure the text faces people and that you use the same type size regardless of the distance between the text and the labeled object.

**If necessary, provide a way to get more information.** Design a visual indicator that fits with your app experience to show people that they can tap for more information.


### Handling interruptions

The AR framework can’t track device position and orientation during an interruption, such as when people briefly switch to another app or accept a phone call. After an interruption ends, previously placed virtual objects are likely to appear in the wrong real-world positions. When you support relocalization, the AR system attempts to restore those virtual objects to their original real-world positions using new information.

**Consider using the system-provided coaching view to help people relocalize.** During relocalization, the AR system attempts to reconcile its previous state with new observations of the current environment. To make these observations more useful, you can use the coaching view to help people return the device to its previous position and orientation.

**Consider hiding previously placed virtual objects during relocalization.** To avoid flickering or other unpleasant visual effects during relocalization, it can be best to hide virtual objects and redisplay them in their new positions.

**Minimize interruptions if your app supports both AR and non-AR experiences.** One way to avoid interruptions is by embedding a non-AR experience within an AR experience so that people can handle the task without exiting and re-entering AR. For example, if your app helps people decide on a piece of furniture to purchase by placing the item in a room, you might let them change the upholstery without leaving the AR experience.

**Allow people to cancel relocalization.** If people don’t position and orient their device near where it was before an interruption, relocalization continues indefinitely without success. If coaching people to resume their session isn’t successful, consider providing a reset button or other way to restart the AR experience.

**Indicate when the front-facing camera is unable to track a face for more than about half a second.** Use a visual indicator to indicate that the camera can no longer track the person’s face. If you need to provide text instructions in this situation, keep them to a minimum.


### Suggesting problem resolutions

**Let people reset the experience if it doesn’t meet their expectations.** Don’t force people to wait for conditions to improve or struggle with object placement. Give them a way to start over again and see if they have better results.

**Suggest possible fixes if problems occur.** Analysis of the real-world environment and surface detection can fail or take too long for a variety of reasons — insufficient light, an overly reflective surface, a surface without enough detail, or too much camera motion. If your app is notified of these problems, use straightforward, friendly language to offer suggestions for resolving them.

| Problem | Possible suggestion |
| --- | --- |
| Insufficient features detected. | Try turning on more lights and moving around. |
| Excessive motion detected. | Try moving your phone slower. |
| Surface detection takes too long. | Try moving around, turning on more lights, and making sure your phone is pointed at a sufficiently textured surface. |


### Icons and badges

Apps can display an AR icon in controls that launch AR experiences, using the platform’s official AR glyph where one exists.

**Use the AR glyph as intended.** The glyph is strictly for initiating an AR experience. Never alter the glyph (other than adjusting its size and color) or use it for other purposes.

**Maintain minimum clear space.** The minimum amount of clear space required around an AR glyph is 10% of the glyph’s height. Don’t let other elements infringe on this space or occlude the glyph in any way.

Apps that include collections of products or other objects can use badging to identify specific items that can be viewed in AR. For example, an app that sells vintage collectibles might use a badge to mark items that people can preview in their home before making a purchase.

**Use the AR badges as intended and don’t alter them.** Use official AR badges (collapsed and expanded forms) exclusively to identify products or objects that can be viewed in AR. Never alter the badges, change their color, or use them for other purposes.

**Prefer the AR badge to the glyph-only badge.** In general, use the glyph-only badge for constrained spaces that can’t accommodate the AR badge. Both badges work well at their default size.

**Use badging only when your app contains a mixture of objects that can be viewed in AR and objects that cannot.** If all objects in your app can be viewed in AR, then badging is redundant.

**Keep badge placement consistent and clear.** A badge looks best when displayed in one corner of an object’s photo. Always place it in the same corner and make sure it’s large enough to be seen clearly (but not so large that it occludes important detail in the photo).

**Maintain minimum clear space.** The minimum amount of clear space required around an AR badge is 10% of the badge’s height. Don’t allow other elements to infringe on this space and occlude the badge in any way.


### Device-specific considerations

## Maps

A map displays outdoor or indoor geographical data in your app or on your website.

A map uses a familiar interface that supports much of the same functionality as the system’s maps app, such as zooming, panning, and rotation. A map can also include annotations and overlays and show routing information, and you can configure it to use a standard graphical view, a satellite image-based view, or a view that’s a hybrid of both.


### Best practices

**In general, make your map interactive.** People expect to be able to zoom, pan, and otherwise interact with maps in familiar ways. Noninteractive elements that obscure the map can interfere with people’s expectations for how maps behave.

**Pick a map emphasis style that suits the needs of your app.** There are two emphasis styles to choose from:

- The *default* style presents a version of the map with fully saturated colors, and is a good option for most standard map applications without a lot of custom elements. This style is also useful for keeping visual alignment between your map and the system maps app, in situations when people might switch between them.

- The *muted* style, by contrast, presents a desaturated version of the map. This style is great if you have a lot of information-rich content that you want to stand out against the map.


**Help people find places in your map.** Consider offering a search feature combined with a way to filter locations by category. The search field for a shopping mall map, for example, might include filters that make it easy to find common store types, like clothing, housewares, electronics, jewelry, and toys.

**Clearly identify elements that people select.** When someone selects a specific area or other element on the map, use distinct styling like an outline and color variation to call attention to the selection.

**Cluster overlapping points of interest to improve map legibility.** A *cluster* uses a single pin to represent multiple points of interest within close proximity. As people zoom in on a map, clusters expand to progressively reveal individual points of interest.

**Keep the map provider’s logo and legal link visible.** It’s fine when parts of your interface temporarily cover the logo and link, but don’t cover these elements all the time. Map providers require attribution. Follow these guidelines to keep it visible:

- Use adequate padding to separate the logo and link from the map boundaries and your custom controls. For example, it works well to use 7 points of padding on the sides of the elements and 10 points above and below them.

- Avoid causing the logo and link to move with your interface. It’s best when the attribution appears to be fixed to the map.

- If your custom interface can move relative to the map, use the lowest position of the custom element to determine the placement of the logo and link. For example, if your app lets people pull up a custom card from the bottom of the screen, place the attribution 10 points above the lowest resting position of the card.

> **Note**: Some providers hide attribution on very small maps (for example, smaller than 200x100 pixels); check your provider’s terms.


### Custom information

**Use annotations that match the visual style of your app.** Annotations identify custom points of interest on your map. The default annotation marker has a red tint and a white pin icon. You can change the tint to match the color scheme of your app. You can also change the icon to a string or image, like a logo. An icon string can contain any characters, including Unicode characters, but keep it to two to three characters in length for readability.

**If you want to display custom information that’s related to standard map features, consider making them independently selectable.** When you support selectable map features, the system treats provider-supplied features (including points of interest, territories, and physical features) independently from other annotations that you add. You can configure custom appearances and information to represent these features when people select them.

**Use overlays to define map areas with a specific relationship to your content.**

- *Above roads*, the default level, places the overlay above roads but below buildings, trees, and other features. This is great for situations where you want people to have an idea of what’s below the overlay, while still clearly understanding that it’s a defined space.

- *Above labels* places the overlay above both roads and labels, hiding everything beneath it. This is useful for content that you want to be fully abstracted from the features of the map, or when you want to hide areas of the map that aren’t relevant.


**Make sure there’s enough contrast between custom controls and the map.** Insufficient contrast makes controls hard to see and can cause them to blend in with the map. Consider using a thin stroke or light drop shadow to help a custom control stand out, or applying blend modes to the map area to increase its contrast with the controls atop it.


### Place cards

Place cards display rich place information in your app or website, such as operating hours, phone numbers, addresses, and more. This enables you to provide structured and up-to-date information for places that you specify, and add depth to search results.


#### Displaying place cards in a map

You can present a place card that appears directly in your map anytime someone selects a place. This is a great way to provide place information in a map with multiple places that you specify, like a map of bookstores that an author plans to visit on their book signing tour.

You can also display place cards for other places on a map, such as points of interest, territories, and physical features, to provide valuable context to people about nearby places.


The system defines several place card styles, which specify the size, appearance, and information included in a place card.

- The *automatic* style lets the system determine the place card style based on the size of your map view.

- The *callout* style displays a place card in a popover style next to the selected place. You can further specify the style of a callout — the *full* callout style displays a large, detailed place card, and the *compact* callout style displays a space-saving, more concise place card. If you don’t specify a callout style, the system defaults to the *automatic* callout style, which determines the callout style based on your map’s view size.

- The *caption* style displays an “Open in Maps” link to the system maps app.

- The *sheet* style displays a place card in a sheet.


Full callout style place cards appear differently depending on a person’s device. The system presents the full callout style place card in a popover style on tablets and desktop, and as a sheet on phones.

**Consider your map presentation when choosing a style.** The full callout style place card offers people the richest experience, presenting them with the most information about a place directly in your map. However, be sure to choose a place card style that fits in the context of your map. For example, if your app displays a small map with many annotations, consider using the compact callout style for a space-saving presentation that shows place information while maintaining the context of the other places that you specify in your map.

**Make sure your place card looks great on different devices and window sizes.** If you choose to specify a style, ensure that the content in your place card remains viewable on different devices and as window sizes change. For full callout style place cards, you can set a minimum width to prevent text from overflowing on smaller devices.

**Avoid duplicating information.** Consider what information you already display in your app or website when you choose a place card style. For example, the full callout style place card might display information that your app already shows. In this case, the compact callout or caption style might be a better complement.

**Keep the location on your map visible when displaying a place card.** This helps people maintain a sense of where the location is on your map while getting detailed place information. You can set an offset distance for your place card and point it to the selected location.


#### Adding place cards outside of a map

You can also display place information outside of a map in your app or website. For example, you might want to display a list of places rather than a map, like in search results or a store locator, and present a place card when people select one.

> **Important**: If you don’t display a place card directly within a map view, you must include a map in the place card.

**Use location-related cues in surrounding content to help communicate that people can open a place card.** For example, you can display place names and addresses alongside a button for more details to help indicate that people can interact with it to get place information. For a space-efficient design, you can include a map pin icon with a place name to help communicate that people can open a place card.


### Indoor maps

Apps connected with specific venues like shopping malls and stadiums can design custom interactive maps that help people locate and navigate to indoor points of interest. Indoor maps can include overlays that highlight specific areas, such as rooms, kiosks, and other locations. They can also include text labels, icons, and routes.

**Adjust map detail based on the zoom level.** Too much detail can cause a map to appear cluttered. Show large areas like rooms and buildings at all zoom levels. Then, progressively add more detailed features and labels as the map is zoomed in. An airport map might show only terminals and gates when zoomed out, but reveal individual stores and restrooms when zoomed in.

**Use distinctive styling to differentiate the features of your map.** Using color along with icons can help distinguish different types of areas, stores, and services, and make it easy for people to quickly find what they’re looking for.

**Offer a floor picker if your venue includes multiple levels.** A floor picker lets people quickly jump between floors. If you implement this feature, keep floor numbers concise for simplicity. In most cases, a list of floor numbers — rather than floor names — is sufficient.

**Include surrounding areas to provide context.** Adjacent streets, playgrounds, and other nearby locations can all help orient people when they use your map. If these areas are noninteractive, use dimming and a distinct color to make them appear supplemental.

**Consider supporting navigation between your venue and nearby transit points.** Make it easy to enter and exit your venue by offering routing to and from nearby bus stops, train stations, parking lots, garages, and other transit locations. You might also offer a way for people to quickly switch over to a maps app for additional navigation options.

**Limit scrolling outside of your venue.** This can help people avoid getting lost when they swipe too hard on your map. When possible, keep at least part of your indoor map visible onscreen at all times. To help people stay oriented, you may need to adjust the amount of scrolling you permit based on the zoom level.

**Design an indoor map that feels like a natural extension of your app.** Don’t try to replicate the appearance of a maps app. Instead, make sure area overlays, icons, and text match the visual style of your app. For guidance, see Indoor Mapping Data Format.


### Device-specific considerations
