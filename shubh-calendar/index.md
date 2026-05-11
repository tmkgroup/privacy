---
layout: app-policy
permalink: /shubh-calendar/
title: Shubh Calendar — Privacy Policy
description: Privacy policy for Shubh Calendar, the Hindu Panchang & Muhurat daily decision tool.
last_updated: 2026-05-11

# Per-app metadata read by _layouts/app-policy.html and the landing page loop.
app_name: Shubh Calendar
app_subtitle: Hindu Panchang & Muhurat daily decision tool
app_id: com.tmkgroup.shubhcalendar
data_collected: "Nothing reaches our servers. You can save an encrypted backup file to YOUR own Drive / iCloud / device. Free tier shows AdMob ads."
order: 20
---

## Summary

Shubh Calendar gives you daily Panchang, Muhurat, Vrat, festivals, Kundli,
matching, mantras, Vastu and horoscope tools.

**TMK Group runs no server for this app and stores nothing of yours.**
Everything you create — Kundli, family profiles, bookmarks, streak,
preferences, notes — lives in encrypted on-device storage. The two
things that *can* leave your device are:

1. **An encrypted backup file (`.tmkbak`) you choose to share** through
   the system share sheet — for example to your own iCloud Drive,
   Google Drive, email, or a USB drive. The file is AES-256-GCM-encrypted
   with a passphrase you type before the share sheet opens, and only
   you know the passphrase.
2. **Anonymous ad-serving signals** to Google AdMob (free tier only —
   Premium removes ads and turns this off entirely).

## Data we collect

### From you, automatically

- **Anonymous ad signals (free tier only).** When the app shows a banner,
  app-open, or rewarded ad, Google AdMob receives the standard ad-request
  signals (device language, coarse location derived from IP, AdMob's
  Advertising ID, app version). In the EU/UK we show Google's UMP consent
  form before any ad loads, and on iOS we show Apple's App Tracking
  Transparency prompt before any tracking ID is shared. **Premium users
  see no ads and no ad signals are sent.**
- **No analytics, no crash reporting, no Firebase Analytics, no Mixpanel,
  no AppsFlyer, no Sentry, no Crashlytics, no Facebook SDK, no TMK
  account server, no sign-in.** We do not measure your in-app behaviour
  and we do not host an account or a sync server. There is nothing to
  sign up for.

### From you, with your consent

- **Approximate location** (Android: `ACCESS_COARSE_LOCATION` /
  `ACCESS_FINE_LOCATION`; iOS: `NSLocationWhenInUseUsageDescription`) —
  used **only** to compute Panchang, Muhurat and sunrise/sunset for your
  current city. The coordinates stay on your device. You can disable
  this and pick a city manually instead.
- **Calendar write access** (iOS: `NSCalendarsUsageDescription`;
  Android: handled per-event by the system) — used **only** when you tap
  "Add to calendar" on a Muhurat or festival. We do not read your
  existing calendar events.
- **Photo library write access** (iOS: `NSPhotoLibraryAddUsageDescription`)
  — used **only** when you save an exported Kundli or Muhurat PDF chart.
- **Tracking ID** (iOS: `NSUserTrackingUsageDescription`) — only if you
  tap "Allow" on Apple's prompt. Used by AdMob to personalise ads. Tap
  "Ask App Not to Track" and the app continues to work normally.
- **Notifications** (Android 13+: `POST_NOTIFICATIONS`; iOS: standard
  permission) — for muhurat reminders, festival alerts and daily Panchang
  notifications you opt into. All scheduled on-device.

### From your device, locally

Stored in encrypted on-device storage (`tmk_storage_package` — AES on
top of SQLite/SharedPreferences):

- Family / friend profiles (name, birth date/time/place — only ones you
  type yourself)
- Active Kundli inputs (birth date, time, lat/long, place name)
- Mantra bookmarks
- Daily streak (current + best)
- Settings (language, theme, calculation method, notification toggles)
- Saved cities and the city you last picked
- Vrat / Muhurat preferences
- Notes, reminders and countdowns from the events table

This data is **never** uploaded to TMK Group. It only ever leaves your
device if you explicitly export a backup or enable cloud sync to your
own Google Drive / iCloud Drive (see *Backups* and *Cloud sync* below).

## Permissions explained

| Permission | Why Shubh Calendar needs it |
|---|---|
| Location (when in use) | Compute Panchang, Muhurat, sunrise/sunset for your current city. Optional — you can pick a city manually. Coordinates stay on-device. |
| Calendar (write) | "Add to calendar" on Muhurat / festival items. Per-event, never bulk read. |
| Photos (add only, iOS) | Save exported Kundli / Muhurat PDFs. We never read your library. |
| Notifications | Muhurat reminders, festival alerts, daily Panchang notifications you opt into. Generated on-device. |
| Exact alarm (Android 12+) | Required by Android so Muhurat notifications fire at the precise minute. |
| Vibrate | Tactile feedback for the Vastu compass and ringing reminders. |
| Compass / magnetometer | Vastu direction tool. The reading is used in real time and never recorded. |
| Internet | Ads (free tier only), in-store IAP, in-store rating prompt. |
| Advertising ID (Android `AD_ID`) | AdMob ad personalisation on the free tier. Removed automatically for Premium users and revocable in Android settings → Privacy → Ads. |
| App tracking (iOS) | AdMob personalisation, only if you tap "Allow" on Apple's ATT prompt. |

You can revoke any permission in your device settings at any time.
The app falls back gracefully (manual city, silent notifications, no
calendar export, etc.) when a permission is denied.

## No accounts, no TMK servers

**Shubh Calendar has no sign-in to a TMK account.** We do not run an
auth server, a profile server, or a sync server for this app. There is
no way for us to identify you or look at your data.

When you reinstall the app or move to a new phone, you bring your data
with you using the encrypted backup feature below.

## Backups (yours to save anywhere)

Shubh Calendar includes a **passphrase-encrypted backup feature**
(Settings → Backup & Restore → Export Backup). It is free for everyone.

When you create a backup:

- A `.tmkbak` file is produced, encrypted with **AES-256-GCM** using the
  passphrase **you** type. We do not see, store, or transmit your
  passphrase.
- The app then opens the **system share sheet**. From there *you* choose
  where the file goes — examples:
  - **iOS**: "Save to Files" → iCloud Drive, On My iPhone, or any
    Files-provider app you have installed (Dropbox, OneDrive, etc.).
  - **Android**: "Save to Drive", "Save to Files", or any app that can
    receive a file (Gmail attachment, Telegram, etc.).
  - Or just AirDrop / share to another device, copy to a USB drive via
    Files, etc.
- TMK Group never receives a copy. The file goes only where you send it.
- To restore, tap Import Backup, pick the file from wherever you saved
  it, and re-enter the same passphrase.
- If you lose the passphrase, **no one** — not us, not anyone — can
  recover the backup. That is by design.

PDF exports of Kundli / Muhurat charts go to the location you choose
(your photo library or the system share sheet); we do not retain a copy.

## Third-party services

Shubh Calendar talks to the following external services. Each is listed
with its purpose and the data sent. **None of them is a TMK Group
server** — TMK Group does not run any backend for this app.

- **Google AdMob** (`*.googleadservices.com`, `*.doubleclick.net`,
  `*.googlesyndication.com`) — only on the free tier and only after the
  EU/UK consent prompt and (on iOS) the App Tracking Transparency
  prompt. Sends: standard ad request (Advertising ID, language, app
  version, approximate location from IP). Privacy:
  <https://policies.google.com/privacy>.
- **Google Play Billing** (Android) / **Apple StoreKit** (iOS) — for
  the one-time Premium purchase. Payment details never reach us.
  Privacy: [Google](https://policies.google.com/privacy) ·
  [Apple](https://www.apple.com/legal/privacy/).
- **In-app review** (Google Play / App Store) — only if you tap "Rate
  the app". The native sheet is rendered by the store, not by us; we
  never see your rating or review text.
- **Platform geocoder** (Android: Google Play Services geocoder; iOS:
  Apple's CLGeocoder) — converts a city name into coordinates when you
  pick a city manually. The query is processed by the OS, not by us.

We do **not** use Firebase Analytics, Crashlytics, Mixpanel, AppsFlyer,
Branch, Adjust, Sentry, or the Facebook SDK.

## In-app purchases

Shubh Calendar offers **one optional in-app purchase**:

- **Shubh Premium — Lifetime** (`shubh_premium_lifetime`), a one-time
  US$0.99 (≈ ₹89, €0.99) non-consumable purchase that removes all ads.
  There is **no subscription, no recurring charge, no auto-renewal**.
- The transaction is processed **entirely by Apple App Store (StoreKit)
  on iOS** or **Google Play Billing on Android**. Shubh Calendar never
  sees, receives, or stores your payment details, billing address or
  real name.
- The app stores a single boolean on your device ("is premium = yes/no")
  to know whether to hide ads. Restoring on a new device works through
  Apple's / Google's own "Restore Purchases" mechanism — we do not
  manage entitlements ourselves.
- Refunds, receipts and purchase history are handled by Apple or Google
  under their own terms and privacy policies:
  [Apple](https://www.apple.com/legal/privacy/) ·
  [Google](https://policies.google.com/privacy).

## Data retention

- **On-device data**: kept until you delete it in the app or uninstall
  the app.
- **`.tmkbak` files you saved elsewhere** (e.g. shared to iCloud Drive,
  Google Drive, email): kept wherever you put them, for as long as you
  keep them. Delete the file from that location to remove it. We never
  had a copy.
- **Ad-network data** (only on the free tier): retained by Google AdMob
  under their own retention policy:
  <https://policies.google.com/technologies/ads>.

## Children's privacy

Shubh Calendar is suitable for general audiences. Because we operate no
account and no server, we cannot identify any user — including their
age. We do not knowingly collect data from children under 13 (or under
16 in the EU); the only data leaving the device is anonymous AdMob ad
requests on the free tier (which can be disabled by buying Premium).

## Your rights

- **Access**: every profile and Kundli row is visible inside the app.
- **Export**: use Settings → Backup & Restore → Export Backup to produce
  a `.tmkbak` file containing everything. PDF export is also available
  for Kundli and selected Muhurat charts.
- **Delete (local)**: Settings → Reset all data wipes the on-device
  store, or simply uninstall the app.
- **Delete (any copy you saved elsewhere)**: open the location you
  saved the `.tmkbak` file to (iCloud Drive, Google Drive, email, etc.)
  and delete it from there. We never had a copy.
- **Correct**: edit any profile or Kundli field directly inside the app.
- **Object / restrict**: revoke any permission in your device settings;
  Shubh Calendar continues to work with reduced features. Free-tier ad
  personalisation can be turned off in Android settings → Privacy → Ads,
  in iOS Settings → Privacy → Tracking, or by purchasing Premium.

You can also email <dev@tmkgroup.vn> for any question — but we have
nothing of yours to delete server-side because we do not run a server.

## Source code transparency

Every change to this policy is recorded in the public Git history of the
[TMK Group privacy repository](https://github.com/tmkgroup/privacy)
with a timestamp.

## Changes to this policy

We will update the "Last updated" date above and ship a new app version
whenever this policy changes. Material changes (e.g. a new third-party
service, or a new category of data we collect) will be highlighted in
the in-app "What's new" screen on the next update.
