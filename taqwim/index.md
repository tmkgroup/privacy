---
layout: app-policy
permalink: /taqwim/
title: Taqwim — Privacy Policy
description: Privacy policy for Taqwim, the privacy-first Islamic calendar and prayer-times app.
last_updated: 2026-05-10

# Per-app metadata read by _layouts/app-policy.html and the landing page loop.
app_name: Taqwim
app_subtitle: Islamic Calendar & Prayer Times
app_id: com.tmkgroup.taqwim
data_collected: "None — Taqwim is fully offline and stores all data on your device only."
order: 10
---

## Summary

**Taqwim is fully offline. We collect nothing.**

There is no account, no sign-in, no analytics SDK, no advertising SDK,
no crash reporter, and no remote backend. Everything you do in the
app — prayer logs, notes, bookmarks, hifz progress, dua wall entries,
sadaqah ledger — is stored exclusively on your device, in encrypted
local storage you alone control.

If you uninstall Taqwim, every byte of data the app ever had is gone
with it. We cannot recover anything for you, and neither can anyone
else, because no copy ever left your phone.

## Data we collect

### From you, automatically

**None.** Taqwim has no telemetry, no analytics, no crash reporting,
and no remote backend. We have no way to identify you, see what you
do in the app, or know that you exist as a user.

### From you, with your consent

Two pieces of data stay on your device only:

- **Approximate location** (Android: `ACCESS_COARSE_LOCATION` /
  `ACCESS_FINE_LOCATION`; iOS: `NSLocationWhenInUseUsageDescription`)
  — used **only** to compute prayer times and Qibla direction for your
  current city. It is never uploaded, never logged remotely, and never
  shared with any third party. You can disable this and enter
  coordinates manually instead.
- **Camera access** (Android: `CAMERA`; iOS: `NSCameraUsageDescription`)
  — used **only** when you tap "AR Qibla" to overlay the Qibla
  direction on your camera view. No image, video, or frame is saved or
  transmitted. The camera turns off the moment you leave that screen.

### From your device, locally

Stored in encrypted on-device storage (`tmk_storage_package`):

- Prayer log (which prayers you marked as done / on time / in jamaah)
- Sunnah ratibah rakat counts
- Notes, bookmarks, dua wall entries, sadaqah log
- Quran reading progress (last read, hifz progress, khatm planner)
- Settings (calculation method, madhab, language, theme, etc.)
- Saved locations (with names you chose)
- Hayd cycle log (if used)

This data is **never** uploaded anywhere. It is yours, and only yours.

## Permissions explained

| Permission | Why Taqwim needs it |
|---|---|
| Location (when in use) | Compute prayer times and Qibla — never uploaded. Optional; you can use manual coordinates. |
| Camera | AR Qibla mode only. Frames are never recorded or shared. Optional. |
| Notifications | Prayer adhan, pre-prayer reminders, iqamah, suhoor, iftar, Tahajjud, Jumu'ah, daily verse, daily hadith, eclipse alerts. Generated on-device only. |
| Exact alarm (Android 12+) | Required by Android so prayer notifications fire at the precise minute, not "approximately". |
| Boot completed (Android) | Re-arms scheduled prayer notifications after a phone reboot. No network access. |
| Vibrate | Tasbih counter feedback. |

You can revoke any permission in your device settings at any time.
The app gracefully falls back (e.g. silent notifications, manual
location) when a permission is denied.

## Third-party services

Taqwim uses **one** optional internet service, only when you ask it to:

- **Quran ayah audio (CDN)**. When you tap "Play" on a Quran verse,
  the app fetches that one MP3 file from
  `https://verses.quran.com/...` (a public CDN run by quran.com). The
  request includes only the standard HTTP headers any browser would
  send. The downloaded file is cached on your device for offline replay.
  If you never tap "Play", no audio request is ever made.

- **Mosque map tiles** (when you open the in-app mosque map, only
  while that screen is open). Tiles are fetched from the OpenStreetMap
  community tile server. The request includes only the standard HTTP
  headers. No identifier of you is sent.

We do not use Google Analytics, Firebase Analytics, Mixpanel,
AppsFlyer, Sentry, Crashlytics, AdMob, Facebook SDK, or any similar
third-party SDK. You can verify this by searching the public source
code or by inspecting the APK with any tool of your choice.

## In-app purchases

Taqwim offers **one optional in-app purchase** — "Supporter", a one-time
tip to support development. It is entirely optional; every feature of
the app remains fully usable whether you buy it or not.

- The transaction is processed **entirely by Apple App Store
  (StoreKit) on iOS** or **Google Play Billing on Android**. Taqwim
  never sees, receives, or stores your payment details, billing
  address, or real name.
- The app only learns whether the purchase succeeded — a single
  on-device boolean — so it can show a "thank you" state. Nothing about
  the purchase is sent to us or to any third party.
- There is no subscription, no recurring charge, and no auto-renewal.
- Refunds, receipts, and purchase history are handled by Apple or
  Google under their own terms and privacy policies:
  [Apple](https://www.apple.com/legal/privacy/) ·
  [Google](https://policies.google.com/privacy).

## Backups

Taqwim includes an **optional, on-device, passphrase-encrypted backup
feature**. When you create a backup:

- The file is AES-encrypted with the passphrase **you** type. We do
  not see, store, or transmit your passphrase.
- The backup file lives wherever you save it — your phone, your USB
  drive, your own cloud drive. We never receive a copy.
- If you lose the passphrase, **no one** — not us, not anyone — can
  recover the backup. That is by design.

## Data retention

- On-device data: kept until you delete it or uninstall the app.
- Off-device data: there is no off-device data to retain.

## Children's privacy

Taqwim is suitable for all ages. Because we collect no personal data,
the app cannot identify the age of any user. We do not knowingly
collect data from children under 13 (or 16 in the EU); we do not
collect data from anyone.

## Your rights

You have full control because the data lives on your device:

- **Access**: open the app and look at it; the in-app data is the
  whole record.
- **Export**: use the in-app encrypted backup feature.
- **Delete**: use the in-app "Reset all data" in Settings, or just
  uninstall the app.
- **Correct**: edit any field in the relevant in-app screen.
- **Object / restrict**: revoke permissions in your device settings;
  Taqwim continues to work with reduced features.

You may also contact [dev@tmkgroup.vn](mailto:dev@tmkgroup.vn) for any
question, but we cannot delete what we never had.

## Source code transparency

Taqwim's promise of "no data leaves your device" is independently
verifiable. The app's source code is open for inspection, and the
public commits in the [TMK Group privacy repository](https://github.com/tmkgroup/privacy)
record any change to this policy with a timestamp.

## Changes to this policy

We will update the "Last updated" date above and ship a new app
version whenever this policy changes. Because Taqwim collects no data,
any change to the policy will only clarify or expand your rights — never
restrict them.
