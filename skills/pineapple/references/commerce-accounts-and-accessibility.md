# Commerce, Accounts & Accessibility Patterns

Distilled from Apple's guidance on in-app purchase, payments, sign-in, identity verification, screen readers, collaboration, sync, order tracking, sensitive data, and tablet-to-desktop porting — generalized into patterns for any web or app product.

---

## 1. Paywalls, Purchases & Subscriptions

**Pattern: value first, price clarity, painless exit.**
- **Let people experience the product before asking them to pay.** Prompt at relevant moments (nearing a free limit), not on launch.
- Integrate the store into the product's own look; short product names and descriptions.
- **Always show the total billing price** (and period) for every option; show the store only when the person can actually pay.
- Use the platform's standard purchase confirmation — don't imitate or pre-empt it.
- **Subscriptions:** highlight benefits during onboarding; offer a range of levels/durations; explain free trials plainly (length, what happens after, how to cancel); only market subscribing to non-subscribers; include a sign-up entry point in Settings.
- **Clear, distinguishable options** — people should compare tiers at a glance (even on a narrow phone screen).
- **Offer/promo codes:** explain the offer, how to redeem, redeem in-app when possible, unlock content immediately after redemption.
- **Management:** show a summary of current subscriptions; you may offer a retention alternative, but **cancellation must always be easy**.
- **Refunds/help:** help content before a refund request, a plain "Request a Refund" action, help finding the problem purchase, alternative fixes — and don't interpret a store's refund policy on its behalf.
- **Family/shared plans:** mention them where people learn about content; write copy that makes sense for both the purchaser and family members.

## 2. Checkout & Payments

**Pattern: fastest safe path to "paid", no forced accounts.**
- Offer the platform/browser wallet wherever supported and make it primary when a card is available; **never hide a wallet button or make it look disabled**.
- Express paths: pay buttons on product pages for single items; express checkout for carts.
- **Collect choices (size, color, shipping method, pickup location) before the payment sheet**; gather optional info before checkout starts.
- Prefer contact/shipping data from the wallet; **don't require account creation before purchase** (offer it after).
- Payment sheet: only essential fields; short line items explaining discounts, fees, recurring and future charges; disclose any post-authorization costs; identify both businesses if you're a marketplace.
- Errors: don't force your business logic on valid input; explain invalid data specifically; let the payment sheet show progress; show results in the sheet, then a confirmation page.
- Subscriptions/donations: restate frequency, trials, upfront fees; show the current charge in the total; offer predefined donation amounts.
- **Merchant-side (tap-to-pay / point of sale):** accept terms before customers are present (admin only), show the option even before setup, never make merchants wait on background configuration, final amount determined before tapping, progress while authorizing, an unmistakable approved/declined result, a recovery path for failures.

## 3. Third-Party Brand Marks & Buttons (payment, sign-in, platform badges)

**Pattern: use the provider's official assets exactly as supplied.**
- **Use only the official button/mark artwork or API-rendered buttons**; never redraw, recolor, stretch, add effects, or alter the logo (height is the only allowed change).
- **Keep minimum size and clear space** around the mark — commonly ≥ **1/10 of the mark's height** on every side.
- Buttons may adjust **corner radius to match your other buttons**; title text stays the approved wording and capitalization ("Sign in with …", "Continue with …", "Pay with …").
- Keep title and logo vertically aligned; maintain the minimum margin between title and button edge; don't add horizontal padding to a logo-only image.
- Give competing providers' buttons **equal size and prominence**.
- Use a *mark* (non-interactive badge) only to communicate acceptance/support; use a *button* only to start that provider's flow.
- **Don't put another company's name or logo in your own custom buttons**, and don't imply the provider performs your app's actions.
- **Emphasize your product over the technology** in copy; refer to third-party brands by their exact trademarked name and capitalization; in text-only payment lists, use text for all options or none.

## 4. Sign-In & Identity

**Pattern: delay, minimize, explain.**
- **Ask for sign-in only in exchange for value, as late as possible.** In commerce, let people buy first and create an account after.
- If an account is truly required, say so before showing sign-in options; allow linking existing accounts.
- Welcome people right after sign-in; always indicate signed-in state.
- **Don't ask for a password** on federated/passkey sign-in; respect relay/private emails — don't demand a "real" one.
- Mark each extra field required vs. optional; ask for optional data only after people have engaged; be transparent about collection.
- **Identity verification:** only at the exact moment it's needed, only the fields needed, state why and how long you'll retain the data, use the platform's verification UI where available.

## 5. Screen Readers

**Pattern: every screen must be fully describable and navigable without sight.**
- **Labels for all key elements**, including icon-only buttons; describe meaningful images; make charts fully accessible (summaries + per-point values/audio graphs); **hide purely decorative images**.
- Use **titles and headings** to expose hierarchy (heading navigation is how people skim).
- Specify **grouping, order, and relationships** — a card with an image, title, and price should read as one element in a logical order.
- **Announce changes** in content or layout (loading finished, error appeared, item moved).
- Support quick-navigation categories (headings, links, form fields, custom categories).
- Custom gestures aren't always accessible — always provide standard alternatives.
- Web: semantic HTML first, `aria-label` for icon buttons, real `h1–h6`, `aria-live="polite"` for updates, `alt=""` for decorative images.

## 6. Real-Time Collaboration & Shared Sessions

**Pattern: co-presence must be effortless to start, join, and leave.**
- Use for synchronous experiences (co-editing, watch parties, multiplayer); fit the activity to what the group is doing.
- One-step start, frictionless join, clear activity names; keep everyone oriented when the activity changes.
- Work across devices; support picture-in-picture for shared video.

## 7. Sync & Cloud Storage

**Pattern: sync should be invisible and safe.**
- Just work — don't ask which documents to sync; keep content current; respect people's storage.
- Degrade gracefully offline/signed-out; sync app state (not just documents) so people resume anywhere.
- Warn that deleting a synced item deletes it everywhere; make conflict resolution prompt and easy; include synced content in search; sync game progress.

## 8. Tickets, Receipts & Order Tracking

**Pattern: the right artifact at the right moment, kept up to date.**
- Offer tickets, boarding passes, and receipts in the formats people use (wallet passes, PDF, email); keep them updated and surface them when relevant (time/location).
- Ticket/pass design: uncluttered front, instantly identifiable, strong text/background contrast, device-neutral language, scannable code with quiet zone.
- Order tracking: available immediately after ordering, accurate plainly worded fulfillment status (be direct about issues/cancellations), clear item descriptions, a link to manage the order, easy merchant contact, no duplicate notifications.

## 9. Health, Care & Research Data

**Pattern: sensitive data demands explicit purpose and the platform's own consent flows.**
- Coherent privacy policy; request access only when needed with a descriptive purpose string; let system settings manage sharing.
- Care tasks: pick the task style by structure (simple, instructions, log, checklist, grid); accurate but simple wording; add video/images for complex steps; color reinforces meaning.
- Health charts: highlight trends/narratives, clear labels and units of time, distinct colors, legends, consolidate large datasets, offset data to keep proportions.
- Minimize notifications; offer detail views.
- Research onboarding order: **introduction → eligibility → informed consent (sectioned, optional comprehension quiz) → data permissions**; engaging surveys; understandable active tasks; profile + progress dashboard.

## 10. Porting Tablet → Desktop

**Pattern: a port is a redesign of layout and input, not a recompile.**
- Prerequisites: drag and drop, keyboard navigation and shortcuts, multiple windows.
- Audit layout for desktop density; adjust font sizes (desktop body ≈ 13 pt); check views and images at desktop scale.
- Keep access to every tab destination (sidebar or View menu) and offer multiple ways to move between pages.
- Move controls into the toolbar; adopt a **top-down flow**; relocate buttons from bottom/side edges; add full command menus; create a desktop-style app icon.
