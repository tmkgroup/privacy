---
layout: app-policy
permalink: /tmk_japan_calendar/
title: "日本カレンダー — Privacy Policy"
description: "Privacy policy for 日本カレンダー (Japan Calendar), a Japanese calendar app with rokuyo, the old lunisolar date, national holidays, solar terms, auspicious day selection, diary, notes and household budget."
last_updated: 2026-11-06
app_name: 日本カレンダー (Japan Calendar)
app_subtitle: Rokuyō · 旧暦 · 祝日 · 択日 · Diary
app_id: com.tmkgroup.japancalendar
data_collected: "Nothing reaches TMK servers. Your events, diary, notes and budget stay on your device. The free tier shows Google AdMob ads; the optional subscription removes them."
order: 36
---

## Summary

日本カレンダー is a Japanese calendar app: month / week / agenda views, 六曜, 旧暦, 二十四節気, 雑節, 祝日, 和暦, events and reminders, countdowns, 日記, メモ, 家計簿, 択日, 九星気学, 八宅, 風水コンパス, 魯班尺, おみくじ, 夢占い, タロット, 12星座, 家系図, weather, home-screen widgets and mini games.

**TMK Group runs no server for this app and stores nothing of yours.** Almanac readings, 択日 calculations, compass measurements, events, diary entries, notes and budget records are computed and stored on **your device** — no TMK account, no TMK cloud, no sign-in. The things that *can* leave your device are:

1. **Anonymous ad-request signals** to Google AdMob — free tier only. The optional 「広告非表示」 subscription removes ads entirely.
2. **An encrypted backup file (`.tmkbak`) you choose to share** through the system share sheet (your own iCloud Drive, Google Drive, e-mail, USB). It is AES-256-GCM-encrypted with a passphrase you type; only you know it.
3. **Your own calendar accounts, only if you connect them** (Google Calendar / Microsoft Outlook / Apple Calendar) — read-only, to show those events beside your own.
4. **An approximate location and the weather request** to Open-Meteo when the weather card loads.
5. **Your prompt to Google Gemini, only if you turn the AI helper on and enter your own Gemini API key.** The app has no AI key of its own; without your key the AI features stay off.
6. **Purchase validation** through Apple's App Store (or Google Play) when you subscribe — handled by the store, not by us.

Apart from the above, the app works offline.

---

## Data we collect

### Automatically (no action required from you)

| What | Why | Who sees it |
|------|-----|-------------|
| **Ad-request signals — free tier only.** When a banner, interstitial or rewarded ad loads, Google AdMob receives the standard ad-request data (device language, coarse location derived from your IP address, app version, AdMob's advertising identifier where the OS provides it). | Serve the ads that keep the free tier free | Google AdMob |
| **No analytics, no crash reporting.** No Firebase Analytics, no Crashlytics, no Sentry, no Mixpanel, no AppsFlyer, no TMK account server. | — | — |

**Subscribers see no ads**, so no ad-request signal is sent at all.

### With your consent

| What | Why | When asked |
|------|-----|-----------|
| Notification permission (Android 13+ / iOS) | Deliver the daily reminder, anniversary / 法事 alerts and note reminders at your chosen time | When you enable notifications in 設定 |
| Approximate location (Android `ACCESS_COARSE_LOCATION`; iOS `NSLocationWhenInUseUsageDescription`) | Show the weather and sunrise / sunset for where you are. The app never asks for precise location. Deny it and the rest of the app works unchanged. | When the weather card first loads |
| Calendar read access (iOS `NSCalendarsUsageDescription` / `NSCalendarsFullAccessUsageDescription`) | Read your Apple / Google / Outlook calendar events **read-only** to list them beside your own events. Imported events are kept on the device. | When you connect a calendar in 設定 |
| Photo library (iOS `NSPhotoLibraryUsageDescription`; Android `READ_MEDIA_IMAGES`) | Attach a photo to a person in 家系図 | When you pick a photo |
| Camera (iOS `NSCameraUsageDescription`) | Only when you choose to take a photo inside the app | When you tap the camera |
| Microphone and speech recognition (iOS `NSMicrophoneUsageDescription` / `NSSpeechRecognitionUsageDescription`; Android `RECORD_AUDIO`) | Dictate an event title. Recognition is performed by the device's own speech recogniser. | When you tap the microphone on the event screen |
| Motion sensors (iOS `NSMotionUsageDescription`) | Drive the 風水コンパス and the 魯班尺 measuring tool | When you open the compass |
| Face ID / biometrics (iOS `NSFaceIDUsageDescription`) | Unlock the app when you switch app lock on | When you enable app lock |
| App Tracking Transparency (iOS `NSUserTrackingUsageDescription`) | Only to let AdMob show more relevant ads. Decline it and you still get ads, just non-personalised. | On a free-tier device, before personalised ads are requested |

You can revoke any of these at any time from your device settings — see **Your rights** below.

### From your device, locally (on-device only)

| What | Stored where |
|------|-------------|
| Events, anniversaries, countdowns and 法事 you create | `sqflite` database in app sandbox |
| Diary entries, notes and their reminder times | `sqflite` database in app sandbox |
| Household budget (家計簿) records | `sqflite` database in app sandbox |
| 家系図 people, relations and photos you add | `sqflite` database + app sandbox files |
| Birth date / sex you type for 択日 and 占い | `shared_preferences` / `sqflite` on-device |
| Events imported read-only from a calendar you connected, and the OAuth token for it | Events: app database. Token: Keychain (iOS) / EncryptedSharedPreferences (Android) |
| Your own Gemini API key, if you enter one | Encrypted on-device storage; never sent to TMK |
| Preferences (theme mode, accent colour, language, notification time) | `shared_preferences` on-device |
| Whether you bought the 「広告非表示」 subscription | Checked against the store at launch; cached in `shared_preferences` |
| Install date (used to time the rating prompt) | `shared_preferences` on-device |
| Encrypted backup snapshots (設定 → バックアップ) | `.tmkbak` file under app Documents — AES-256-GCM, key derived from your passphrase via PBKDF2-SHA256 |

> **About backups.** When you export a backup, the app encrypts a copy of your data with
> your passphrase and writes a `.tmkbak` file to your device. You control where it goes.
> TMK never sees the file or the passphrase. **If you lose the passphrase, the backup is
> unrecoverable** (this is intentional — we cannot reset it).

---

## Permissions explained

### Android

| Permission | Why the app needs it |
|------------|----------------------|
| `POST_NOTIFICATIONS` *(Android 13+)* | Deliver the daily notification, anniversary and note reminders. Requested only when you enable notifications. Denying it leaves the rest of the app fully functional. |
| `SCHEDULE_EXACT_ALARM` · `USE_EXACT_ALARM` *(Android 12+)* | Fire reminders at the precise time you set. Without them, notifications may be delayed by battery optimisation. |
| `RECEIVE_BOOT_COMPLETED` | Re-schedule reminders after a device restart. |
| `ACCESS_COARSE_LOCATION` | Weather and sunrise / sunset for your current area. Approximate only — the app does **not** request `ACCESS_FINE_LOCATION`. |
| `INTERNET` · `ACCESS_NETWORK_STATE` | Load ads on the free tier, fetch weather, connect a calendar you choose, and reach the AI helper with your own key. |
| `READ_MEDIA_IMAGES` | Pick a photo for a person in 家系図. |
| `RECORD_AUDIO` | Dictate an event title through the device speech recogniser. |
| `com.android.vending.BILLING` | Sell and restore the 「広告非表示」 subscription through Google Play. |
| `AD_ID` *(added by Google Mobile Ads)* | AdMob ad serving on the free tier. Revocable in Android Settings → Privacy → Ads. Subscribers get no ads. |

### iOS

| Permission | Why the app needs it |
|------------|----------------------|
| Notifications | Daily notification, anniversary / 法事 alerts and note reminders. |
| `NSLocationWhenInUseUsageDescription` | Weather and sunrise / sunset for your current area. |
| `NSCalendarsUsageDescription` · `NSCalendarsFullAccessUsageDescription` | Read-only import of calendar events when you connect an account. |
| `NSPhotoLibraryUsageDescription` · `NSCameraUsageDescription` | Photos for 家系図. |
| `NSMicrophoneUsageDescription` · `NSSpeechRecognitionUsageDescription` | Voice input of an event title. |
| `NSMotionUsageDescription` | 風水コンパス and 魯班尺. |
| `NSFaceIDUsageDescription` | App lock. |
| `NSUserTrackingUsageDescription` | Personalised AdMob ads on the free tier; declining keeps the app working. |

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Google AdMob** | Ads on the free tier | Standard ad-request signals: device language, coarse location from IP, app version, advertising identifier where the OS provides it. No events, diary, notes, budget, birth data or calendar content is ever sent. | [Google](https://policies.google.com/technologies/ads) |
| **Apple App Store / Google Play billing** | Sell and validate the optional 「広告非表示」 subscription | Handled entirely by the store. We never see your name, card or address — only whether a subscription is active. | [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy) |
| **Open-Meteo** (weather + reverse geocoding) | Show the weather card and the 7-day forecast | Approximate coordinates only — no identifier, no account | [Open-Meteo](https://open-meteo.com/en/terms) |
| **Google Calendar / Microsoft Outlook (only if you connect one)** | Read-only import of your own events | OAuth sign-in happens in the provider's own flow; the token stays in your device's secure storage. Events are read, never written or deleted. | [Google](https://policies.google.com/privacy) · [Microsoft](https://privacy.microsoft.com/privacystatement) |
| **Google Gemini (only if you enter your own API key)** | The optional AI helper that answers calendar questions and drafts events | Your prompt and the calendar context you ask about, sent under **your** key to Google. Leave the key empty and nothing is sent. | [Google](https://policies.google.com/privacy) |
| **Apple / Google rating prompt** | Show the native "rate this app" dialog some days after install | Triggered locally; the rating itself is delivered through Apple / Google's own flow | [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy) |

We do **not** integrate any analytics, crash reporting, or TMK backend service in this version.

---

## Data retention

| Data | Retained |
|------|----------|
| Events / diary / notes / budget / preferences | Until you delete them or reset the app data |
| Install date / onboarding flag | Until you uninstall the app or reset data |
| Notification schedules | Re-applied on every cold start; cleared when you disable notifications |

Uninstalling the app removes everything; there is nothing stored off-device.

---

## Children's privacy

This app is not directed at children. It shows ads on the free tier and offers one auto-renewing subscription, so it is rated for teens and older on the stores. We do not knowingly collect any data from anyone — adult or child — beyond what is documented above. There is no chat, no social feed and no sharing of your content with other users.

---

## In-app purchase

The app offers one optional auto-renewing subscription — **広告非表示** (`com.tmkgroup.japancalendar.remove_ads_1m`), US$1.00 per month — which removes all ads. Payment, renewal and cancellation are handled by Apple (App Store) or Google (Play Store); cancel any time in your store account settings. The app only asks the store whether an active subscription exists; it stores no payment data and has no account of its own. Restoring purchases re-checks the store when you change device.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| Erase everything | Delete your data in 設定, or uninstall the app |
| Revoke notification / location / photo permission | Device Settings → the app → the permission |
| Export your data | 設定 → encrypted backup, or the `.ics` export for events |
| Contact the developer | tmktechgroup@gmail.com |

---

## Changes to this policy

If we ever add a feature that changes what is collected, we will bump `last_updated` above and ship a new version of the app. Past versions of this policy are tracked in the public Git history of the privacy site.
