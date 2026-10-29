# Decision log
Add a new entry for any decision that is hard to reverse. Never delete entries; mark them Superseded.

## D-001: Awareness first, restrictions opt-in
- Date: 2026-10-29 · Status: Accepted
- Decision: The app never blocks by default. Swipe budget and focus mode are opt-in.
- Why: Punishing apps get uninstalled. Awareness is the differentiator. It also helps the Play Store accessibility review.

## D-002: Native apps per platform (Kotlin first)
- Date: 2026-10-29 · Status: Proposed
- Decision: Build Android in Kotlin + Jetpack Compose. Build iOS later in Swift.
- Why: The core features need native platform APIs on both sides anyway.
- Open: Confirm against the developer's language experience.

## D-003: Swipe data stays on device
- Date: 2026-10-29 · Status: Accepted
- Decision: Only aggregate, opt-in data (daily totals) is ever shared, and only for the buddy feature.
