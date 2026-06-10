---
layout: app-policy
permalink: /calendar/
title: "TMK Lịch Vạn Niên — Privacy Policy"
description: "Privacy policy for TMK Lịch Vạn Niên — Vietnamese lunisolar calendar with astrology, feng shui, palm/face reading, family tree, and auspicious-day picker."
last_updated: 2026-06-10
app_name: TMK Lịch Vạn Niên
app_subtitle: Vietnamese Lunisolar Calendar · Astrology · Feng Shui
app_id: com.tmkgroup.tmkcalendar
data_collected: "Account, personal events, family-tree records and wallet transactions are stored on TMK servers (Supabase). Birth-time inputs used for astrology are sent with consent and never sold."
order: 30
---

## Summary

TMK Lịch Vạn Niên ("the app") is a Vietnamese lunisolar calendar that bundles astrology (tử vi), feng shui (phong thủy), palm-reading (xem chỉ tay), face-reading (xem tướng), family tree (gia phả), an auspicious-day picker, weather forecast, and a small in-app wallet for paid features.

Because the wallet, family tree, friend chat and subscription history must follow you across devices, the app **does** operate a backend — your account profile, wallet ledger, family-tree records, chat threads, subscription state and feedback messages are stored on TMK-operated Supabase + Cloudflare infrastructure. Pure-local content (theme, ngày tốt xấu cached, draft inputs) stays on your device.

The app shows AdMob ads to free-tier users. In the EU/UK/Brazil/Switzerland it asks for ad-personalisation consent first (UMP). You can replay that consent screen any time from Profile → "Quyền riêng tư quảng cáo".

---

## Data we collect

### Sent to TMK servers (Supabase, Cloudflare Workers)

| What | Why | Stored in |
|------|-----|-----------|
| Account: Supabase user ID, email or phone (from sign-in), display name, optional avatar URL, referral code | Authentication and referrals | Supabase `profiles` |
| Optional birth info you type into Profile: date of birth (solar / lunar), birth hour, gender, place of birth | Power the personalised tử vi (astrology) chart, ngày hợp/khắc, and feng-shui suggestions | Supabase `profiles` |
| Wallet ledger: gold (in-app currency) balance and transaction history | Show your balance, accept tips, unlock paid features | Supabase wallet tables |
| Subscription state: current tier, expiry date, purchase token from Apple/Google | Enable premium features, restore purchases on a new device | Supabase `subscriptions` |
| Family-tree records (relative name, relationship, birth/death dates, notes, optional photos) | Show, edit and share your tree across devices | Supabase + Supabase Storage |
| Personal events / countdowns (title, date, repetition rule, optional notes) | Sync your reminders across devices and surface upcoming countdowns | Supabase + local SQLite mirror via `tmk_events_package` |
| Friend / call / chat data (peer ID, timestamps, messages, optional attachments) | Power the in-app messaging tab via `chat-calendar.tmkgroup.vn` | Cloudflare D1 + R2 (TMK-operated) |
| Feedback messages you send via Profile → Góp ý (text, optional screenshot, app version, OS, device model, current screen name, optional email) | Triage bug reports and route to the admin via Telegram | Cloudflare D1 + R2 (TMK-operated) at `feedback-api.tmkgroup.vn` |
| Firebase Cloud Messaging registration token | Deliver push notifications (event reminders, chat pings) | Google FCM |

You initiate every one of these writes — the app does not silently upload data in the background.

### With your consent (device permissions)

| What | Why | When asked |
|------|-----|-----------|
| Location (when in use) | Show local weather (Open-Meteo) and feng-shui orientation on the in-app compass | First time you open the weather card or feng-shui compass |
| Camera | Take a photo of your palm (xem chỉ tay) or face (xem tướng) for the reading sheet, scan a QR code, attach an image to chat | First time you tap the camera icon |
| Photo Library / Gallery (`READ_MEDIA_IMAGES` on Android 13+, `NSPhotoLibraryUsageDescription` on iOS) | Pick an existing photo for palm/face reading, profile avatar, or chat attachment | First time you tap "Pick from gallery" |
| Save to Photo Library | Save reading results / shared images back to your device | First time you tap "Save image" |
| Microphone | Voice and video calls inside the messaging tab | First time you join a call |
| Notifications | Send event reminders, chat notifications, daily horoscope nudges | First time the relevant feature opts in |

You can revoke any of these in your OS settings at any time; the corresponding feature degrades gracefully (you can type a city instead of using GPS, pick a photo instead of taking one, attend a call muted, etc.).

### On your device, locally

| What | Stored where |
|------|-------------|
| Cached events / countdowns mirror (`tmk_events_package`) | App sandbox SQLite |
| HydratedBloc state — theme, locale, last-used filters, UMP consent state | App sandbox |
| Ad session counter (anti-spam ad logic) | App sandbox |
| Supabase OAuth session token | Encrypted on-device, used to authenticate API calls |
| `.env` config (Supabase URL + anon key, AdMob ad-unit IDs, wallet endpoint) | Bundled asset, public values intended for client distribution |

---

## Permissions explained

### Android

| Permission | Why TMK Lịch Vạn Niên needs it | Fallback if denied |
|------------|---------------------------------|--------------------|
| `INTERNET` | Talk to Supabase, Cloudflare Workers (chat / feedback), Open-Meteo, AdMob, Firebase | App cannot function — every cross-device feature is online |
| `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` | Weather forecast for your area, feng-shui compass orientation | Type a city name manually; compass still works without precise lat/lon |
| `CAMERA` | Take a palm / face photo for the reading sheets, scan a QR code, capture chat attachments | Pick a photo from the gallery instead |
| `READ_MEDIA_IMAGES` (Android 13+) / `READ_EXTERNAL_STORAGE` (≤ Android 12) | Pick an avatar / chat / reading photo from gallery | Take a fresh photo with the camera |
| `com.android.vending.BILLING` | In-app purchases (subscription / supporter tip via Google Play Billing) | You can still use free features |
| `POST_NOTIFICATIONS` (Android 13+) | Deliver reminders set by the user and chat pings | Reminders fire silently in-app only |

### iOS

| Key (Info.plist) | Why TMK Lịch Vạn Niên needs it |
|------------------|----------------------|
| `NSCameraUsageDescription` | Palm / face reading photo, QR scan, chat attachments |
| `NSPhotoLibraryUsageDescription` | Pick photos for readings, avatar, chat |
| `NSPhotoLibraryAddUsageDescription` | Save reading results to Photos |
| `NSMicrophoneUsageDescription` | Voice and video calls inside the messaging tab |
| `NSLocationWhenInUseUsageDescription` / `NSLocationAlwaysAndWhenInUseUsageDescription` | Local weather + feng-shui compass orientation |

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Supabase** (TMK-hosted) | Authentication, database, file storage, real-time wallet ledger | Everything in the "Sent to TMK servers" table above | [Supabase privacy](https://supabase.com/privacy) |
| **Google Sign-In / Apple Sign-In** | Account login | Your provider UID + the public profile fields you approve (name, email, picture) | [Google](https://policies.google.com/privacy) · [Apple](https://www.apple.com/legal/privacy/) |
| **Cloudflare Workers** (TMK-operated: `chat-calendar.tmkgroup.vn`, `social-calendar.tmkgroup.vn`, `feedback-api.tmkgroup.vn`, `feedback.tmkgroup.vn`) | Friend chat / call signalling, in-app feedback intake | Chat messages, call signalling payloads, feedback text + optional screenshot | [Cloudflare privacy](https://www.cloudflare.com/privacypolicy/) |
| **Google Play Billing / Apple StoreKit** | Process in-app purchases (subscription, supporter tip) | Receipt token; we never see card numbers | [Google](https://policies.google.com/privacy) · [Apple](https://www.apple.com/legal/privacy/) |
| **Google AdMob SDK** | Show banner, interstitial, and rewarded ads to free-tier users; UMP consent collected in EU/UK/Brazil/Switzerland before any personalised ad request | Standard AdMob signals (anonymised device identifier, ad-unit ID, app version, locale); contents of your account, events, family tree, chat, palm/face photos are **never** sent to AdMob | [Google privacy](https://policies.google.com/privacy) · [AdMob technologies](https://support.google.com/admob/answer/9012903) |
| **Firebase Cloud Messaging (FCM)** | Deliver push notifications | FCM registration token, notification payload we send | [Firebase privacy](https://firebase.google.com/support/privacy) |
| **Open-Meteo** (`api.open-meteo.com`) | Weather forecast | Your latitude/longitude (or the city you typed); no account or device identifier | [Open-Meteo privacy](https://open-meteo.com/en/terms#privacy) |
| **MapLibre GL** | Render the in-app map for feng-shui / location pickers | Map-tile requests (your viewport coordinates) go to the configured tile provider | Provider's own policy |
| **Google ML Kit** (`google_ml_kit`) | On-device image processing helpers (e.g. text recognition, image labelling) used inside reading flows | Image bytes are processed **on-device only**; ML Kit does not upload them | [ML Kit terms](https://developers.google.com/ml-kit/terms) |

TMK Lịch Vạn Niên **does not** integrate any third-party analytics SDK or crash-reporting SDK.

---

## In-app purchases

The app sells subscription tiers (Cơ bản / Nâng cao / Premium) and supporter top-ups for the in-app wallet. Billing is handled by **Google Play Billing** on Android and **Apple StoreKit** on iOS — TMK never sees your card number, billing address or full purchase token. The store-issued receipt token is forwarded to Supabase only to record the entitlement against your account.

Restore purchases is available from Profile → Nâng cấp tài khoản → "Restore" (iOS) or by re-installing on a Google account that owns the entitlement.

---

## Data retention

| Data | Retained until |
|------|---------------|
| Account profile, wallet ledger, subscription state, family-tree records, personal events, chat messages | Until you delete the record inside the app or request account deletion (see "Your rights") |
| Supabase Storage files (avatar, family-tree photos, chat attachments) | Until the parent record is deleted; orphan files are pruned periodically |
| Feedback messages + screenshots in `feedback.tmkgroup.vn` (R2) | Retained for triage; you can request deletion by emailing the address below |
| OAuth session token on-device | Until you sign out or uninstall the app |
| On-device caches (events SQLite mirror, HydratedBloc, ad session counter, draft forms) | Until you tap "Logout" (clears PII) or uninstall |
| Backend access logs | Up to 30 days for security and abuse-prevention, then aggregated or deleted |

---

## Children's privacy

TMK Lịch Vạn Niên is **not directed to children**. The astrology / palm-reading / face-reading features touch on adult topics (relationships, career, health) and the in-app wallet processes real-money transactions, so the app is intended for users aged 13 and above (16+ in the EU). We do not knowingly collect personal data from anyone under that age; if we learn that we have, the account and its data will be deleted.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| **Access** | Open Profile to see your account, wallet, subscription, family tree, events and birth info tied to your account |
| **Correct** | Edit any record directly from its detail page; edit your profile in Profile → "Sửa hồ sơ" |
| **Export** | Email `trucmn@gmail.com` from the address tied to your account; we will return a JSON dump within 30 days |
| **Delete a single record** | Open the record → Delete (events, family-tree entries, chat messages, feedback) |
| **Delete your account** | Email `trucmn@gmail.com` with subject "Delete my TMK Calendar account". We remove your `profiles` row, your Supabase Storage files, your wallet ledger and any chat / feedback records you authored. |
| **Withdraw ad-personalisation consent** | Profile → "Quyền riêng tư quảng cáo" (visible in regions where consent is required) |
| **Revoke OAuth** | Sign out, then revoke the app at [myaccount.google.com/permissions](https://myaccount.google.com/permissions) or, on iOS, **Settings → Apple ID → Sign in with Apple** |
| **Revoke a device permission** | OS Settings → Apps → TMK Lịch Vạn Niên → Permissions |

---

## Changes to this policy

When we make material changes, we update the `last_updated` date at the top and ship a new app version. Continued use after an update constitutes acceptance. Updates will clarify or expand your rights — never restrict them silently.

Questions or requests? Email `trucmn@gmail.com`.
