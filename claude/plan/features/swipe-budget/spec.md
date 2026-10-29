# Feature: Swipe budget (opt-in)
Status: Draft · Phase: 2 · Default: Off, opt-in

## Why
Some users want a limit. They can set a daily swipe budget and earn bonus swipes through healthy activities.

## User stories
- As a user who wants control, I want to set a daily swipe budget, so that I stay within my own limit.
- As a user, I want to earn extra swipes by walking or reading, so that the limit feels fair.

## Acceptance criteria
- [ ] Off by default. Turned on only from Settings or an onboarding question.
- [ ] When the budget runs out, the user chooses what happens: just a notice, a soft overlay, or a block.
- [ ] Earn options: steps (Health Connect), a timed reading session, a short flashcard quiz.
- [ ] The user can turn the budget off at any time (with a short confirmation).

## Platform notes
- Android: Overlay on budget end; Health Connect for steps.
- iOS: ManagedSettings shield; HealthKit for steps; budget in minutes, not swipes.

## Out of scope
- Payments to buy swipes.

## Open questions
- Should unused swipes roll over to the next day?
