# Feature: Mindful nudges
Status: Draft · Phase: 1 · Default: On, adjustable (Off / Gentle / Firm)

## Why
A small, well-timed pause helps people choose instead of swiping on autopilot. It never blocks.

## User stories
- As a user, I want a gentle reminder after a number of swipes, so that I notice I'm on autopilot.
- As a user, I want to choose how often nudges appear or turn them off.

## Acceptance criteria
- [ ] After N swipes in a session (default 50), show a small overlay: 'You've swiped 50 reels. Keep going?'
- [ ] Firm level: a 5-second breathing pause or 'type why you're still scrolling' before dismissing.
- [ ] The user can always dismiss and continue. Nothing is blocked.
- [ ] Nudge frequency and style adjustable in Settings; Off is available.

## Platform notes
- Android: Accessibility overlay window over the reels app.
- iOS: Notification when a DeviceActivity threshold is reached.

## Out of scope
- Hard blocking (that belongs to swipe-budget and focus-mode).

## Open questions
- Should the threshold adapt to the user's average automatically?
