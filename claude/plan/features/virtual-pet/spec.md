# Feature: Virtual pet or plant
Status: Draft · Phase: 2 · Default: On

## Why
An emotional hook keeps people engaged with the app and makes progress feel rewarding.

## User stories
- As a user, I want a pet or plant that grows when I swipe less than my usual amount, so that progress feels rewarding.
- As a user, I want to pick my companion type.

## Acceptance criteria
- [ ] Companion state (thriving, okay, tired) is based on today's swipes versus the user's own 7-day average, not a fixed number.
- [ ] Growth stages unlock over days with below-average swiping.
- [ ] The pet never 'dies'. Worst state is 'tired', and it recovers.
- [ ] Shown on the home screen and as a home-screen widget.

## Platform notes
- Android: Compose UI plus a Glance widget.
- iOS: SwiftUI plus WidgetKit, using estimates.

## Out of scope
- Buying items or paid upgrades for the pet (later, if ever).

## Open questions
- Pet or plant or both? Art style?
