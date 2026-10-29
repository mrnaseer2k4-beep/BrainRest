# Feature: Accountability buddy
Status: Draft · Phase: 3 · Default: Off, opt-in

## Why
Sharing progress with one trusted friend is motivating without the pressure of public leaderboards.

## User stories
- As a user, I want to invite a friend as my buddy, so that we keep each other honest.
- As a user, I want my buddy alerted if I go far over my usual amount (only if I allow it).

## Acceptance criteria
- [ ] Invite by link; both users must accept.
- [ ] Only daily totals are shared, never per-session detail or timestamps.
- [ ] Optional alert to buddy when the user exceeds a chosen threshold.
- [ ] Optional weekly friendly leaderboard among buddies (max 10 people).
- [ ] Either person can end the link at any time.

## Platform notes
- Android: Firebase Auth, Firestore, Cloud Messaging.
- iOS: Screen Time data can't leave the report extension easily; may be limited to user-confirmed summaries.

## Out of scope
- Public global leaderboards.

## Open questions
- Account type: anonymous plus invite code, or Google/Apple sign-in?
