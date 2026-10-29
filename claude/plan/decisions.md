# Decision log
Add a new entry for any decision that is hard to reverse. Never delete entries; mark them Superseded.

## D-001: Awareness first, restrictions opt-in
- Date: 2026-10-29 · Status: Accepted
- Decision: The app never blocks by default. Swipe budget and focus mode are opt-in.
- Why: Punishing apps get uninstalled. Awareness is the differentiator. It also helps the Play Store accessibility review.

## D-002: Tech stack (Flutter or native)
- Date: 2026-10-29 · Status: **Pending** (owner: faisal)
- Rule set by faisal: choose Flutter if the idea works on both platforms, otherwise go native.
- Finding: Android works fully. iOS works only partly (no real swipe counts, no Reels-only nudges or blocks). See feasibility.md.
- Options:
  - Native (Kotlin now, Swift later): best fit if iOS will be a different, time-based product.
  - Flutter with native modules: shared UI for onboarding, settings, pet; Kotlin for the swipe service and Swift for Screen Time extensions.
    Note the iOS Insights screen must be SwiftUI inside the report extension, so less UI is shared than usual.
- Claude's recommendation: native, following the rule above.

## D-003: Swipe data stays on device
- Date: 2026-10-29 · Status: Accepted
- Decision: Only aggregate, opt-in data (daily totals) is ever shared, and only for the buddy feature.
