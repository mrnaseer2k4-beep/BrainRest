# Feasibility
Status: In review

## Summary
| Capability | Android | iOS |
|---|---|---|
| Count real swipes in other apps | **Yes** (Accessibility Service) | **No** (Apple blocks access to other apps' screens) |
| Time spent per app | Yes (UsageStatsManager) | Yes, inside a Screen Time report extension |
| Show a nudge over the reels app | Yes (accessibility overlay) | Partial (notifications, or a shield screen) |
| Block an app (opt-in) | Yes (overlay when the app opens) | Yes (ManagedSettings shield) |
| Store approval risk | Medium (accessibility declaration) | Medium (Family Controls entitlement request) |

**Verdict:** Android can deliver the full product. iOS can deliver everything except true swipe counts.
On iOS we show **estimated swipes** (time in reels apps ÷ average seconds per reel), clearly labelled as an estimate.

## Android details
- **Accessibility Service** gets `TYPE_VIEW_SCROLLED` and window events with the app's package name.
  - Target packages: `com.instagram.android`, `com.zhiliaoapp.musically` and `com.ss.android.ugc.trill` (TikTok), `com.google.android.youtube`.
  - Use `packageNames` in the service config so we only receive events from these apps.
- **Telling reels apart from the normal feed:** check the active screen's view IDs and class names.
  This is fragile because those apps change often, so keep the detection rules in a config file we can update without a new release.
- **One swipe = one counted item:** debounce scroll events (for example, one count per full-page vertical scroll within ~300 ms).
- **Overlays for nudges:** `TYPE_ACCESSIBILITY_OVERLAY` windows, which need no extra permission.
- **Battery:** event-driven, so the cost is low if work in the callback stays small.
- **Play Store policy:**
  - Accessibility API use must be declared in Play Console, with a prominent in-app disclosure and consent screen before enabling.
  - A short video showing the feature is usually required in review.
  - Digital wellbeing is an accepted use case, but we must not collect screen content beyond what's needed, and data must stay private.
- **OEM battery killers** (Xiaomi, Oppo, Samsung) can stop the service. We need an onboarding step that explains how to whitelist the app.

## iOS details
- **Screen Time API** (FamilyControls, DeviceActivity, ManagedSettings), iOS 16+ supports individual (self) authorization.
- **DeviceActivityMonitor:** get callbacks when usage passes thresholds, which can trigger nudge notifications.
- **DeviceActivityReport extension:** shows usage time, but the data stays inside the extension's sandbox.
  We can display it, but can't freely send it to our backend (this affects buddy and leaderboards).
- **ManagedSettings:** shields (blocks) chosen apps, which covers opt-in budget and focus mode.
- **Entitlement:** the Family Controls (Distribution) entitlement must be requested from Apple before App Store release.

## Risks
1. Instagram or TikTok UI changes break reels detection on Android. Mitigation: remote detection config and an "unknown screen" fallback that still counts scrolls.
2. Play Store rejection over accessibility use. Mitigation: clear disclosure, minimal data, demo video, privacy policy.
3. iOS feature gap. Mitigation: design the iOS app around time and estimates and say so in the store listing.
