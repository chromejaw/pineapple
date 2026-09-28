# Dark Patterns & Ethical Design

Apple's **Responsibility** principle — *act in people's best interest* — and its Agency principle forbid designs that trick, trap, or pressure people. This file names the common manipulative patterns and gives the honest alternative for each. Treat every item as a hard "don't," regardless of what a conversion metric says.

---

## 1. The Test

Before shipping a flow, ask:
1. **Would people make the same choice if they fully understood it?** If the design only works when people misunderstand, it's a dark pattern.
2. **Is leaving as easy as joining?** Cancel, unsubscribe, delete, and opt out must take no more effort than sign up, subscribe, and opt in.
3. **Would we be comfortable if the flow were screenshotted and published?**
4. **Does the default serve the person or us?** Defaults are decisions most people never change.

## 2. Patterns to Avoid → What to Do Instead

| Dark pattern | What it looks like | Do this instead |
| :--- | :--- | :--- |
| **Confirmshaming** | "No thanks, I don't like saving money" | Neutral, equal-weight choices: "Not now" |
| **Roach motel / hard cancel** | Subscribe in one tap; cancel requires a call, chat, or hidden page | Cancel in the same place, same number of steps; offer a retention option once, never block |
| **Hidden costs / drip pricing** | Fees appear at the last step | Show the total, including fees and taxes, from the first price shown |
| **Sneak into basket** | Add-ons or insurance pre-selected | Every add-on starts unselected |
| **Forced continuity** | Free trial silently becomes paid | State trial length, price after, and cancel path up front; remind before charging |
| **Disguised ads** | Ads styled as content or navigation | Clearly label sponsored content |
| **Misdirection / visual interference** | "Accept all" bright, "Reject" gray and tiny | Equal visual weight for equal choices (especially consent) |
| **Privacy zuckering** | Defaults share maximum data; settings buried | Privacy-protective defaults, just-in-time permission requests with a clear reason |
| **Pre-permission tricks** | Fake alerts or screens that mimic the system prompt, or incentives to allow tracking | Explain value in plain language, then show the real system prompt — or don't ask |
| **Nagging** | Repeated prompts to enable notifications, rate, or upgrade after "no" | Ask once at a relevant moment; respect the answer; offer a settings path |
| **Fake urgency / scarcity** | Countdown timers that reset; "Only 2 left!" when untrue | Only show real deadlines and stock levels |
| **Trick questions** | Double negatives in opt-outs ("Uncheck to not receive…") | Plain, positive phrasing; one decision per checkbox |
| **Forced account / registration wall** | Must sign up before seeing value or buying | Let people browse and buy as a guest; offer account creation after |
| **Bait and switch** | Button does something other than its label | Labels state exactly what happens ("Delete 3 photos") |
| **Infinite engagement traps** | Autoplay and endless feeds with no stopping cues | Natural stopping points, "You're all caught up," easy autoplay off |
| **Obstructed data deletion** | Account deletion hidden or only "deactivate" | Real deletion available in-app, with a clear timeline and confirmation |

## 3. Respecting Attention & Well-being

- **Notifications are a privilege.** Send only what people asked for or would clearly want; make every category controllable; never use notifications for marketing without explicit opt-in.
- **Interruptions only before a big mistake.** Confirmation dialogs for irreversible actions; undo for everything else.
- **Streaks and rewards should motivate, not punish.** Allow pauses and freezes; avoid shaming language for missed days.
- **Kids and vulnerable users:** no manipulative monetization, no social pressure mechanics, conservative defaults.
- **AI features:** disclose when content is AI-generated, let people review before AI acts on their behalf, and remove features whose failures could cause real harm (see [Technologies › Generative AI](./technologies.md)).

## 4. Consent & Privacy UI

- Consent dialogs: **Accept** and **Reject** equally prominent, **Reject all** on the first layer, granular choices on the second.
- Ask for permissions **in context**, at the moment of need, with a one-sentence purpose ("To scan receipts, allow camera access").
- If people decline, the app still works for everything that doesn't strictly need the permission — and tells them how to enable it later.
- Collect the minimum, explain retention, and make export and deletion easy.
