# Feature: Insights
Status: Draft · Phase: 1 · Default: On

## Why
Patterns matter more than single days. Insights show when and where swiping happens.

## User stories
- As a user, I want a daily and weekly summary, so that I can see trends.
- As a user, I want to know my peak swiping hours, so that I can plan around them.

## Acceptance criteria
- [ ] Daily view: total swipes, minutes, sessions, split by app.
- [ ] Weekly view: bar chart by day, change versus last week.
- [ ] Peak hour heatmap (hour of day × day of week).
- [ ] Longest session of the week is highlighted.
- [ ] Optional weekly summary notification (Sunday evening by default).

## Platform notes
- Android: Built from Room DailyStat and Session tables.
- iOS: Shown inside a DeviceActivityReport extension.

## Out of scope
- Data export to CSV (later).

## Open questions
- How far back should history go? (Proposed: 90 days.)
