# Feature: Make it real
Status: Draft · Phase: 1 · Default: On

## Why
Numbers like '412 swipes' feel abstract. Turning them into distance and time makes them hit home.

## User stories
- As a user, I want to see how far I've scrolled in metres or kilometres, so that the number feels physical.
- As a user, I want to see time spent and what I could have done instead, so that I can reflect.

## Acceptance criteria
- [ ] Distance = swipes × screen height in physical units (from the device's display metrics).
- [ ] Time spent per app shown alongside swipes.
- [ ] At least 10 'equivalents' (e.g. 'about 2 chapters of a book', 'a 3 km walk') rotate on the home screen.
- [ ] Units follow the user's setting (metric or imperial).

## Platform notes
- Android: Display metrics give screen height; time from UsageStatsManager.
- iOS: Distance from estimated swipes; time from Screen Time report.

## Out of scope
- Shaming language. Tone must stay neutral or encouraging.

## Open questions
- Should users be able to add their own equivalents (e.g. 'practise guitar')?
