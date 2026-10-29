# Architecture
Status: Draft (stack is a proposal, see decisions.md D-002)

## Proposed stack
- **Android:** Kotlin, Jetpack Compose UI, Room (local database), WorkManager (daily rollups), Hilt (DI).
- **iOS (later):** Swift, SwiftUI, Screen Time API extensions.
- **Backend (phase 3, buddy only):** Firebase (Auth, Firestore, Cloud Messaging). Nothing else leaves the device.

Why native rather than Flutter: the core of both apps (Accessibility Service on Android, Screen Time extensions on iOS)
must be written natively anyway, and the two apps behave quite differently. Shared UI would save less than it costs.

## Android components
```
SwipeAccessibilityService  -> detects reels screens and swipes
        |
SwipeEventRepository       -> writes swipe events to Room
        |
Rollup worker (daily)      -> builds daily stats; feeds Insights, Pet, Budget
        |
UI (Compose)               -> Home counter, Insights, Pet, Settings
NudgeOverlayManager        -> shows mindful nudges and opt-in budget/focus screens
```

## Core data model
- `SwipeEvent(id, timestamp, app, screenType, sessionId)`
- `Session(id, app, start, end, swipeCount)`
- `DailyStat(date, app, swipes, minutes, sessions)`
- `UserSettings(nudgeLevel, budgetEnabled, budgetLimit, focusEnabled, petType, units)`

## Privacy
- No screen text or video content is stored, only counts, timestamps and app names.
- Export and delete-all-data available in Settings.
