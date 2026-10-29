# BrainRest: working rules (spec-driven development)

BrainRest (working name) helps people **notice** how much short-form video they swipe through
(Instagram Reels, TikTok, YouTube Shorts). Awareness comes first. Restrictions are always opt-in.

## How we work
1. **Spec first.** No code is written for a feature until its `spec.md` is marked `Approved`.
2. **Design next.** `design.md` explains how the feature is built. It must be `Approved` before tasks start.
3. **Tasks last.** `tasks.md` breaks the design into small, checkable steps. Code follows the tasks.
4. **Specs are the source of truth.** If code and spec disagree, fix one of them in the same change.
5. **Decisions are logged.** Any choice that is hard to undo goes in `plan/decisions.md`.

## Status values (top of every spec, design and tasks file)
`Draft` → `In review` → `Approved` → `In progress` → `Done`  (or `Deferred`)

## Folder map
- `plan/vision.md`: what we are building, for whom, and the product principles
- `plan/feasibility.md`: what Android and iOS allow, and store policy risks
- `plan/architecture.md`: tech stack and system design
- `plan/roadmap.md`: phases and which features ship in each
- `plan/decisions.md`: decision log (lightweight ADRs)
- `plan/features/_template/`: copy this folder to start a new feature
- `plan/features/<feature>/`: `spec.md`, `design.md`, `tasks.md` per feature

## Product principles (apply to every feature)
- **Inform, don't punish.** Default behaviour never blocks the user.
- **User chooses limits.** Budgets, blocking and focus locks are off until the user turns them on.
- **Private by default.** Swipe data stays on the device. Anything shared (buddy) is opt-in and minimal.
- **Be honest about data.** Estimated numbers are labelled as estimates.
