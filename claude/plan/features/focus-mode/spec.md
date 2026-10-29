# Feature: Focus mode (opt-in)
Status: Draft · Phase: 2 · Default: Off, opt-in

## Why
For study or work sessions, some users want reels out of reach for a set time.

## User stories
- As a user, I want to start a focus timer that hides reels apps, so that I can study without distraction.
- As a user, I want to schedule focus blocks (e.g. weekdays 9 to 12).

## Acceptance criteria
- [ ] Off by default; started manually or by schedule.
- [ ] Pomodoro presets (25/5, 50/10) and custom length.
- [ ] During focus, opening a reels app shows a calm screen with time left and an 'end focus early' option.
- [ ] Completed focus sessions feed the pet and Insights.

## Platform notes
- Android: Overlay when a target app opens during focus.
- iOS: ManagedSettings shield during a DeviceActivity schedule.

## Out of scope
- Blocking websites in the browser.

## Open questions
- Should 'end early' need a delay (e.g. 10 seconds) to reduce impulse quitting?
