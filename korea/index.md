---
layout: app-policy
permalink: /korea/
title: "한국 만세력 — Privacy Policy"
description: "Privacy policy for 한국 만세력 (Korea Almanac), a Korean calendar app with lunar dates, 24 solar terms, Saju, feng-shui tools, diary, notes and household budget."
last_updated: 2026-11-06
app_name: 한국 만세력 (Korea Almanac)
app_subtitle: Korean Almanac · Saju · 풍수 · Diary
app_id: com.tmkgroup.korea
data_collected: "Nothing reaches TMK servers. Your events, diary, notes and budget stay on your device. The free tier shows Google AdMob ads; the optional subscription removes them."
order: 35
---

## Summary

한국 만세력 is a Korean calendar app: solar/lunar dates, 24 solar terms, 간지, holidays, 제사 reminders, Saju charts, Tarot, feng-shui compass, 노반척, diary, notes, household budget (가계부), 바둑 and mini games.

**TMK Group runs no server for this app and stores nothing of yours.** All almanac readings, Saju calculations, Tarot draws, compass measurements, events, diary entries, notes and budget records are computed and stored on **your device** — no TMK account, no TMK cloud, no sign-in. The things that *can* leave your device are:

1. **Anonymous ad-request signals** to Google AdMob — free tier only. The optional "광고 제거" subscription removes ads entirely.
2. **An encrypted backup file (`.tmkbak`) you choose to share** through the system share sheet (your own iCloud Drive, Google Drive, email, USB). It is AES-256-GCM-encrypted with a passphrase you type; only you know it.
3. **Your own calendar accounts, only if you connect them** (Google Calendar / Microsoft Outlook / Apple Calendar) — read-only, to show those events on the 오늘 screen.
4. **Purchase validation** through Apple's App Store (or Google Play) when you subscribe — handled by the store, not by us.

Apart from the above, the app works offline.

---

## Data we collect

### Automatically (no action required from you)

| What | Why | Who sees it |
|------|-----|-------------|
| **Ad-request signals — free tier only.** When a banner, interstitial or rewarded ad loads, Google AdMob receives the standard ad-request data (device language, coarse location derived from your IP address, app version, AdMob's advertising identifier where the OS provides it). | Serve the ads that keep the free tier free | Google AdMob |
| **No analytics, no crash reporting.** No Firebase Analytics, no Crashlytics, no Sentry, no Mixpanel, no AppsFlyer, no Facebook SDK, no TMK account server. | — | — |

**Subscribers see no ads**, so no ad-request signal is sent at all.

On iOS this version does **not** ask for App Tracking Transparency permission, so iOS does not hand your advertising identifier (IDFA) to AdMob.

### With your consent

| What | Why | When asked |
|------|-----|-----------|
| Notification permission (Android 13+ / iOS) | Deliver the daily 운세 reminder, 제사 / anniversary alerts and note reminders at your chosen time | When you enable "알림 사용" in Settings |
| Approximate location (Android `ACCESS_COARSE_LOCATION`; iOS `NSLocationWhenInUseUsageDescription`) | Show the weather for where you are on the 오늘 screen. Coordinates stay on the device. Deny it and the rest of the app works unchanged. | When the weather card first loads |
| Calendar read access (iOS `NSCalendarsUsageDescription` / `NSCalendarsFullAccessUsageDescription`; Android per-account) | Read your Apple / Google / Outlook calendar events **read-only** to list them beside your own events. Imported events are kept on the device. | When you connect a calendar in 설정 → 외부 캘린더 |
| Photo library (iOS `NSPhotoLibraryUsageDescription`) | Attach a photo to a family member in the family-tree tool | When you pick a photo |
| Camera (iOS `NSCameraUsageDescription`) | Only when you choose to take a photo inside the app | When you tap the camera |
| Motion sensors (iOS `NSMotionUsageDescription`) | Drive the feng-shui compass (나경) and measuring tools | When you open the compass |

You can revoke any of these at any time from your device settings — see **Your rights** below. Connected calendars can be disconnected in 설정 → 외부 캘린더.

### From your device, locally (on-device only)

| What | Stored where |
|------|-------------|
| Anniversaries / D-day / birthday / 제사 / memo events you create | `sqflite` database in app sandbox |
| Diary entries, notes and their reminder times | `sqflite` database in app sandbox |
| Household budget (가계부) records | `sqflite` database in app sandbox |
| Family-tree (가계도) people, relations and photos you add | `sqflite` database + app sandbox files |
| Birth date / time you type for Saju, and Tarot draw history | `shared_preferences` / `sqflite` on-device |
| Events imported read-only from a calendar you connected, and the OAuth token for it | Events: app database. Token: Keychain (iOS) / EncryptedSharedPreferences (Android) |
| Preferences (theme, colour, language, text scale, notification toggle) | `shared_preferences` on-device |
| Whether you bought the "광고 제거" subscription | Checked against the store at launch; cached in `shared_preferences` |
| Install date (used to time the rating prompt) | `shared_preferences` on-device |
| Whether you have completed onboarding | `shared_preferences` on-device |
| Encrypted backup snapshots (when you use Settings → 백업) | `.tmkbak` file under app Documents — AES-256-GCM, key derived from your passphrase via PBKDF2-SHA256 |

> **About backups.** When you tap **Settings → 백업 내보내기**, the app encrypts a copy
> of your events with your passphrase and writes a `.tmkbak` file to your device. You
> control where it goes — the share sheet lets you keep it locally, send it to yourself,
> or upload to your own cloud. TMK never sees the file or the passphrase. **If you lose
> the passphrase, the backup is unrecoverable** (this is intentional — we cannot reset it).

---

## Permissions explained

### Android

| Permission | Why the app needs it |
|------------|----------------------|
| `POST_NOTIFICATIONS` *(Android 13+)* | Deliver the daily 운세 notification and anniversary alerts. Requested only when you enable the toggle in Settings. Denying it leaves the rest of the app fully functional. |
| `SCHEDULE_EXACT_ALARM` *(Android 12+)* | Fire reminders at the precise time you set. Without it, notifications may be delayed by battery optimisation. |
| `RECEIVE_BOOT_COMPLETED` | Re-schedule reminders after a device restart so the next 운세 notification still fires. |
| `ACCESS_COARSE_LOCATION` | Weather for your current area on the 오늘 screen. Approximate only — the app never asks for precise location. |
| `INTERNET` | Load ads on the free tier, fetch weather, connect a calendar you choose, and open this policy or the store rating page. |
| `AD_ID` *(added by Google Mobile Ads)* | AdMob ad serving on the free tier. Revocable in Android Settings → Privacy → Ads. Subscribers get no ads. |

### iOS

| Permission | Why the app needs it |
|------------|----------------------|
| Notifications | Deliver the daily 운세 notification, 제사 / anniversary alerts and note reminders. |
| `NSLocationWhenInUseUsageDescription` | Weather for your current area. |
| `NSCalendarsUsageDescription` · `NSCalendarsFullAccessUsageDescription` | Read-only import of Apple Calendar events when you connect it. |
| `NSPhotoLibraryUsageDescription` | Attach a photo to a person in 가계도. |
| `NSCameraUsageDescription` | Take a photo inside the app when you choose to. |
| `NSMotionUsageDescription` | Feng-shui compass (나경) and measuring tools. |

The app does **not** request App Tracking Transparency permission, so no IDFA is shared with AdMob.

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Apple / Google rating prompt** | Show the native "rate this app" dialog ~3 days after install | Triggered locally; rating itself is delivered through Apple/Google's own flow | [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy) |
| **Google AdMob** | Ads on the free tier | Standard ad-request signals: device language, coarse location from IP, app version, advertising identifier where the OS provides it. No events, diary, notes, budget, birth data or calendar content is ever sent. | [Google](https://policies.google.com/technologies/ads) |
| **Apple App Store / Google Play billing** | Sell and validate the optional "광고 제거" subscription | Handled entirely by the store. We never see your name, card or address — only whether a subscription is active. | [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy) |
| **Google Calendar / Microsoft Outlook (only if you connect one)** | Read-only import of your own events into the 오늘 screen | OAuth sign-in happens in the provider's own flow; the token stays in your device's secure storage. Events are read, never written or deleted. | [Google](https://policies.google.com/privacy) · [Microsoft](https://privacy.microsoft.com/privacystatement) |
| **Open-Meteo** (weather + reverse geocoding) | Show the weather card for your area | Approximate coordinates only — no identifier, no account | [Open-Meteo](https://open-meteo.com/en/terms) |

We do **not** integrate any analytics, crash reporting, or TMK backend service in this version.

---

## Data retention

| Data | Retained |
|------|----------|
| Events / anniversaries / preferences | Until you delete them or use **Settings → 데이터 초기화** |
| Install date / onboarding flag | Until you uninstall the app or reset data |
| Notification schedules | Re-applied on every cold start; cleared when you disable notifications |

Uninstalling the app removes everything; there is nothing stored off-device.

---

## Children's privacy

This app is not directed at children. It shows ads on the free tier and offers one auto-renewing subscription, so it is rated for teens and older on the stores. We do not knowingly collect any data from anyone — adult or child — beyond what is documented above. There is no chat, no social feed and no sharing of your content with other users.

---

## In-app purchase

The app offers one optional auto-renewing subscription — **광고 제거** (`com.tmkgroup.korea.remove_ads_1m`), US$1.00 per month — which removes all ads. Payment, renewal and cancellation are handled by Apple (App Store) or Google (Play Store); cancel any time in your store account settings. The app only asks the store whether an active subscription exists; it stores no payment data and has no account of its own. "구매 내역 복원" re-checks the store when you change device.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| Erase everything | Settings → 데이터 초기화 (also clears scheduled notifications) |
| Revoke notification permission | Device Settings → Apps → 한국 만세력 → Notifications |
| Export your data | Not applicable — there is nothing to export beyond what is already on your device |
| Contact the developer | Use the developer email shown on the app's store listing |

---

## Changes to this policy

If we ever add a feature that changes what is collected (e.g. calendar sync, ads, premium tier), we will bump `last_updated` above and ship a new version of the app. Past versions of this policy are tracked in the public Git history of the privacy site.
