---
layout: app-policy
permalink: /tmk_gospel/
title: "TMK Gospel — Privacy Policy"
description: "Privacy policy for TMK Gospel, a privacy-first multi-language Protestant Bible, devotion, hymn, and prayer app."
last_updated: 2026-05-16
app_name: TMK Gospel
app_subtitle: Bible · Devotion · Hymns · Prayer
app_id: com.tmkgroup.gospel
data_collected: "Your readings, notes, and progress stay on your device. The app fetches a public hymn / sermon catalogue and shows AdMob ads — both removable with the optional in-app purchase."
order: 40
---

## Summary

TMK Gospel is a privacy-first Bible, devotion, and worship app for Protestant believers. Your scripture readings, devotional notes, prayer journal, sermon notes, memorised verses, streaks, and backup files are computed and stored on **your device** — no account, no cloud database, no TMK servers see your spiritual data.

The app makes two kinds of outbound network requests: (1) downloading a public, read-only catalogue of hymns / sermons / radio streams from `cal.tmkgroup.vn`, and (2) loading anonymous banner / interstitial / rewarded advertisements via Google AdMob. Both can be eliminated by purchasing the one-time **Remove Ads** in-app upgrade.

---

## Data we collect

### Automatically (no action required from you)

| What | Why | Who sees it |
|------|-----|-------------|
| **Nothing on our servers.** No analytics SDK, no crash reporter, no telemetry. | — | — |
| Advertising identifiers (Android Advertising ID / iOS IDFA), device type, country, approximate language — **only while an ad is displayed** | Google AdMob uses these to choose which non-personalised ad to serve and to bill the developer | Google (see "Third-party services" below). Disappears the moment ads are removed via the in-app purchase. |

### With your consent

| What | Why | When asked |
|------|-----|-----------|
| Notification permission (Android 13+ / iOS) | Deliver the daily 7 AM devotion reminder, reading-plan nudges, and weekly prayer-intentions reminder | When you enable the daily reminder toggle, or first launch on Android 13+ |
| Calendar access (iOS `NSCalendarsUsageDescription`) | Sync personal devotion events with the system calendar — only if you connect Google / Apple / Outlook | When you tap "Connect calendar" in Settings |
| File picker access | Restore an encrypted `.tmkbak` backup file from local storage | When you tap "Restore backup" |

You can revoke any of these at any time from your device settings — see **Your rights** below.

### From your device, locally (on-device only)

| What | Stored where |
|------|-------------|
| App settings — language, theme, font scale, Protestant tradition | Encrypted `TmkStorage` (AES-256-GCM) on-device |
| Bible bookmarks / favourites | Encrypted `TmkStorage` on-device |
| Devotion notes, sermon notes, prayer journal, memorised verses | Encrypted `TmkStorage` on-device |
| Streaks, daily activity log, reading-plan progress | Encrypted `TmkStorage` on-device |
| Cached hymn / sermon catalogue JSON | App documents folder — re-downloaded on demand |
| Premium IAP receipt flag | `shared_preferences` on-device |
| Encrypted backup snapshots (when you use **Profile → Backup**) | `.tmkbak` file under app Documents — AES-256-GCM, key derived from your passphrase via PBKDF2-SHA256 |

> **About backups.** When you tap **Profile → Backup → Export**, the app encrypts a copy of your data with your passphrase and writes a `.tmkbak` file. You control where it goes — the share sheet lets you keep it local, send it to yourself, or upload to your own cloud. TMK never sees the file or the passphrase. **If you lose the passphrase, the backup is unrecoverable** (this is intentional — we cannot reset it).

---

## Permissions explained

### Android

| Permission | Why the app needs it |
|------------|----------------------|
| `INTERNET` | Fetch the public hymn / sermon catalogue from `cal.tmkgroup.vn` and load AdMob ads |
| `ACCESS_NETWORK_STATE` | Detect offline mode and show the offline banner so you know which features still work |
| `POST_NOTIFICATIONS` *(Android 13+)* | Deliver the daily 7 AM devotion reminder, reading-plan nudges, prayer-intention alerts. Requested only when you enable a reminder toggle |
| `RECEIVE_BOOT_COMPLETED` | Re-schedule reminders after a device restart so the morning devotion still fires |

### iOS

| Permission key in `Info.plist` | Why the app needs it |
|--------------------------------|----------------------|
| `NSCalendarsUsageDescription` / `NSCalendarsFullAccessUsageDescription` | Sync personal devotion events with the system calendar — only triggered by your action |
| Notification authorisation (no plist key) | Daily / reading-plan / prayer reminders |

The Apple Privacy Manifest (`PrivacyInfo.xcprivacy`) declares the standard `UserDefaults`, `FileTimestamp`, `SystemBootTime`, and `DiskSpace` API reasons used by the Flutter framework and `tmk_storage_package`.

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Google AdMob** | Display banner ads on Home / Utilities screens, interstitial ads on hub entries, optional rewarded ads for premium content | Advertising ID, coarse location (country), device/OS, ad-unit ID. Non-personalised by default | [Google Privacy Policy](https://policies.google.com/privacy) · [AdMob data disclosure](https://support.google.com/admob/answer/7665968) |
| **Google Play Billing / App Store In-App Purchase** | Process the one-time `gospel_remove_ads` purchase | Transaction handled entirely by Google / Apple; TMK only receives a "purchased" flag from the OS | [Google](https://policies.google.com/privacy) · [Apple](https://www.apple.com/legal/privacy/) |
| **`cal.tmkgroup.vn`** Supabase storage | Serve the public hymn / sermon / radio media catalogue JSON | None — anonymous read-only HTTPS GET | TMK owns this endpoint; no logging beyond standard web access logs |
| **Apple / Google rating prompt** | Show the native "rate this app" dialog after a few days of use | Triggered locally; rating delivered through the OS native flow | — |
| **Google Calendar / Apple Calendar / Microsoft Outlook** *(optional)* | If you connect a provider in Settings, the app reads events into the calendar tab | OAuth token stored in `flutter_secure_storage`; calendars read with `calendar.readonly` scope | [Google](https://policies.google.com/privacy) · [Apple](https://www.apple.com/legal/privacy/) · [Microsoft](https://privacy.microsoft.com/) |
| **Google Gemini API** *(optional, BYOK)* | Powers the "Ask AI" Q&A button on the Daily Devotion screen. Disabled by default; only activates when you paste your own free [Google AI Studio](https://aistudio.google.com/app/apikey) key into Profile → AI assistant | Each question you type plus a Protestant-tradition system prompt; the API key is stored encrypted on-device via `tmk_storage_package`; TMK never sees your key or your questions | [Google AI Studio terms](https://ai.google.dev/terms) · [Gemini API privacy](https://ai.google.dev/gemini-api/terms) |

We do **not** integrate any analytics, crash reporting, or backend service for your account data. There is no account.

---

## In-app purchase

| Product | Type | Price | What it does |
|---------|------|-------|--------------|
| `gospel_remove_ads` | Non-consumable | \$1.99 USD (≈ 49.000 VND / 270 JPY / 2.500 KRW) | Permanently removes all banner, interstitial, and rewarded ads from this install. Restore Purchase is available on the Upgrade screen for re-installs / new devices on the same store account |

---

## Data retention

| Data | Retained |
|------|----------|
| Notes / favourites / streaks / preferences | Until you delete them or use **Profile → Delete local data** |
| Cached media catalogue JSON | Until you clear app storage or uninstall |
| Notification schedules | Re-applied on every cold start; cleared when you disable reminders |
| IAP premium flag | Until you uninstall (re-instate via Restore Purchase) |

Uninstalling the app removes everything stored on the device. There is nothing on TMK servers tied to you.

---

## Children's privacy

This app is rated **4+ / Everyone** and is intended for general audiences seeking Bible-reading and devotion tools. It does not knowingly collect personal information from children under 13. The Google AdMob integration is configured to serve **non-personalised, family-safe** ad content by default; if you would like to disable ads entirely, the **Remove Ads** in-app purchase eliminates them.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| Erase everything | **Profile → Privacy & Data → Delete local data** |
| Export your data | **Profile → Privacy & Data → Export data** (creates an encrypted `.tmkbak` file) |
| Revoke a permission | Device Settings → Apps → TMK Gospel → Permissions |
| Remove ads | Buy the one-time `gospel_remove_ads` upgrade on the Upgrade screen |
| Disconnect a calendar provider | Settings → Calendar sync → Disconnect (revokes OAuth token immediately) |
| Contact the developer | Use the developer email shown on the app's store listing |

---

## Changes to this policy

If we ever add a feature that changes what is collected (e.g. an account, personalised ads, telemetry), we will bump `last_updated` above and ship a new version of the app that surfaces the updated policy on first launch. Past versions of this policy are tracked in the public Git history of this privacy site.
