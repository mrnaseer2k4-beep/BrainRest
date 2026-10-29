# Feature: Swipe counter
Status: Draft · Phase: 1 · Default: On

## Why
Users can't fix what they don't notice. A live, accurate swipe count is the core of the app.

## User stories
- As a user, I want to see how many reels I swiped today, so that I notice my habit.
- As a user, I want the count split by app, so that I know which app pulls me in most.

## Acceptance criteria
- [ ] Each full swipe to a new reel in Instagram Reels, TikTok or YouTube Shorts adds exactly 1.
- [ ] Normal feed scrolling is not counted as reels (or is counted separately if detection is unsure).
- [ ] Today's total is visible on the home screen and in a persistent notification (optional).
- [ ] Counts survive app restarts and phone reboots.
- [ ] The count is within 5% of a manual count in a 100-swipe test per app.

## Platform notes
- Android: Accessibility Service with package filter, debounced scroll events, remote detection rules.
- iOS: No real counts. Show estimated swipes from Screen Time minutes, labelled as an estimate.

## Out of scope
- Counting likes, comments, or what the videos contain.

## Open questions
- Which apps are in v1? (Proposed: Instagram, TikTok, YouTube.)
- Should we also count Facebook Reels and Snapchat Spotlight?
