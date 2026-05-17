---
layout: app-policy
permalink: /cambodia/
title: "ប្រតិទិនខ្មែរ (Khmer Calendar) — Privacy Policy"
description: "Privacy policy for ប្រតិទិនខ្មែរ (Khmer Calendar), a privacy-first Cambodian calendar with Buddhist Era, lunar dates, Theravada Uposatha, Tevoda, Khmer New Year and public holidays."
last_updated: 2026-05-17
app_name: ប្រតិទិនខ្មែរ (Khmer Calendar)
app_subtitle: Buddhist Era · Uposatha · Tevoda · Khmer New Year · public holidays
app_id: com.tmkgroup.cambodia
data_collected: "Nothing reaches our servers. Everything (anniversaries, Uposatha streak, settings) is stored on your device only."
order: 38
---

## Summary

ប្រតិទិនខ្មែរ is a privacy-first Cambodian calendar. All Buddhist-Era and lunar conversions, Uposatha tracking, Tevoda-of-the-year readings, daily Buddha / Pali word / Dhammapada content, anniversary reminders, and personal events are computed and stored on **your device** — no account, no cloud, no TMK servers. The app works **fully offline**; an internet connection is only used when you open this privacy policy in your browser, or — if you enable the weather card — to fetch the public Open-Meteo forecast.

---

## Data we collect

### Automatically (no action required from you)

| What | Why | Who sees it |
|------|-----|-------------|
| **Nothing.** No analytics SDK, no crash reporter, no telemetry, no ads. | — | — |

### With your consent

| What | Why | When asked |
|------|-----|-----------|
| Notification permission (Android 13+ / iOS) | Deliver the daily Khmer-calendar reminder (date, lunar day, Uposatha flag, next holiday) and any anniversary alerts at your chosen time | When you enable the daily reminder in Me → Daily Reminder |
| Approximate location (Android / iOS) | Show the local sunrise / noon / sunset time and, if enabled, the local weather forecast on the Today screen. If permission is denied we fall back to Phnom Penh coordinates. | When you first open the Today screen with weather/location enabled |

You can revoke either of these at any time from your device settings — see **Your rights** below.

### From your device, locally (on-device only)

| What | Stored where |
|------|-------------|
| Anniversaries / birthday / memorial events you create | Encrypted SQLite via `tmk_storage_package` (AES-256) |
| Profile (name, birth year, gender for horoscope features) | Encrypted SQLite via `tmk_storage_package` |
| Uposatha observance log and streak counter | Encrypted SQLite via `tmk_storage_package` |
| Preferences (theme, language, notification toggle) | `shared_preferences` on-device |
| Cached daily push payloads (next 30 days) | `flutter_local_notifications` scheduling store |
| Encrypted backup snapshots (when you use Me → Backup) | `.tmkbak` file under app Documents — AES-256-GCM, key derived from your passphrase via PBKDF2-SHA256 |
| Last-known coarse location (when weather card is enabled) | `shared_preferences` on-device, cleared when you disable the weather card |

> **About backups.** When you tap **Me → Export Backup**, the app encrypts a copy of your events,
> profile, and Uposatha log with your passphrase and writes a `.tmkbak` file to your device. You
> control where it goes — the share sheet lets you keep it locally, send it to yourself, or upload
> to your own cloud. TMK never sees the file or the passphrase. **If you lose the passphrase, the
> backup is unrecoverable** (this is intentional — we cannot reset it).

---

## Permissions explained

### Android

| Permission | Why the app needs it |
|------------|----------------------|
| `POST_NOTIFICATIONS` *(Android 13+)* | Deliver the daily Khmer-calendar reminder and anniversary alerts. Requested only when you enable the toggle in Me → Daily Reminder. Denying it leaves the rest of the app fully functional. |
| `SCHEDULE_EXACT_ALARM` / `USE_EXACT_ALARM` *(Android 12+ / 14+)* | Fire reminders at the precise time you set. Without it, notifications may be delayed by battery optimisation. |
| `RECEIVE_BOOT_COMPLETED` | Re-schedule reminders after a device restart so the next daily notification still fires. |
| `ACCESS_COARSE_LOCATION` / `ACCESS_FINE_LOCATION` | Only when you enable the weather card or local sunrise/sunset display. The location is used solely to look up the forecast and sun times — it is never sent to TMK. |
| `INTERNET` | Only used to (a) open this privacy policy or the Play Store rating page in your browser, and (b) fetch the Open-Meteo forecast if you enable the weather card. |

### iOS

| Permission | Why the app needs it |
|------------|----------------------|
| Notifications usage description | Deliver the daily Khmer-calendar notification. |
| `NSLocationWhenInUseUsageDescription` | Same as Android location above — only when weather / sun-time is enabled. |

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Open-Meteo** *(optional — only if you enable the weather card)* | Provide the local weather forecast on the Today screen | Approximate latitude / longitude, rounded to ~1 km | [open-meteo.com/en/terms](https://open-meteo.com/en/terms) |
| **Apple / Google rating prompt** | Show the native "rate this app" dialog ~3 days after install | Triggered locally; rating itself is delivered through Apple / Google's own flow | [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy) |

We do **not** integrate any analytics, crash reporting, advertising SDK, or backend service in this version.

---

## Data retention

| Data | Retained |
|------|----------|
| Events / anniversaries / profile / Uposatha log / preferences | Until you delete them or use Me → Delete Local Data |
| Cached reminder push payloads | Rolling 30 days; cleared when you disable notifications |
| Last-known coarse location | Until you disable the weather card or revoke location permission |
| Notification schedules | Re-applied on every cold start; cleared when you disable notifications |

Uninstalling the app removes everything; there is nothing stored off-device.

---

## Children's privacy

This app is rated **4+ / Everyone** and does not target children specifically. We do not knowingly collect any data from anyone — adult or child — beyond what is documented above. The app contains no in-app purchases, no ads, no chat, and no user-generated content.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| Erase everything | Me → Delete Local Data (also clears scheduled notifications) |
| Revoke notification permission | Device Settings → Apps → ប្រតិទិនខ្មែរ → Notifications |
| Revoke location permission | Device Settings → Apps → ប្រតិទិនខ្មែរ → Permissions → Location |
| Export your data | Me → Export Backup (encrypted `.tmkbak` — only you can decrypt it) |
| Contact the developer | Use the developer email shown on the app's store listing |

---

## Changes to this policy

If we ever add a feature that changes what is collected (e.g. calendar sync, ads, premium tier), we will bump `last_updated` above and ship a new version of the app. Past versions of this policy are tracked in the public Git history of the privacy site.
