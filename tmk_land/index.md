---
# TMK Land dùng layout "default" (KHÔNG "app-policy") từ 2026-11-07 như Scan Doc / Caribbean Calendar:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app này từ 2026-11-07 (gắn Google AdMob thật).
# Nguồn từng ý thêm 2026-11-07:
#  - tmk_land/lib/ads/app_ads.dart (UMP consent rồi mới khởi động SDK; mã AdMob thật)
#  - tmk_land/lib/presentation/pages/main/utility_page.dart (banner TmkBannerAdWidget sau lưới Tiện ích)
#  - package/tmk_wallet_package/lib/src/presentation/screens/missions_page.dart:62 (quảng cáo có thưởng nhận xu,
#    gửi ssvUserId = mã tài khoản + ssvCustomData = mã lượt cho kiểm tra phía máy chủ)
#  - tmk_land/lib/services/remove_ads_service.dart (gói com.tmkgroup.tmkland.remove_ads_3m, 3 tháng)
#  - tmk_land/ios/Runner/Info.plist (NSUserTrackingUsageDescription, GADApplicationIdentifier thật)
#  - danh sách dữ liệu SDK quảng cáo: bê scandoc/index.md mục 5 (developers.google.com/admob/ios/privacy/data-disclosure)
layout: default
permalink: /tmk_land/
title: "TMK Land — Privacy Policy"
description: "Privacy policy for TMK Land, the real-estate management and shared-investment platform."
last_updated: 2026-11-07
app_name: TMK Land
app_subtitle: Real-Estate Management & Shared Investment
app_id: com.tmkgroup.tmkland
data_collected: "Account, property, rental and investment data are stored on TMK servers (Supabase) because the app is collaborative. National-ID (CCCD) number is collected with consent for tenant identification; CCCD photos are never stored or uploaded — they are processed on-device only by an OCR helper that discards them after extracting text. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 40
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>TMK Land — Privacy Policy</h1>
    <p class="app-subtitle">Real-Estate Management &amp; Shared Investment</p>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.tmkland</code></span>
      <span>Last updated: 2026-11-07</span>
    </p>
  </header>

  <aside class="data-summary">
    <strong>Data we collect:</strong> Account, property, rental and investment data are stored on TMK servers (Supabase) because the app is collaborative. National-ID (CCCD) number is collected with consent for tenant identification; CCCD photos are never stored or uploaded — they are processed on-device only by an OCR helper that discards them after extracting text. Google AdMob ads collect device data; the Remove ads subscription turns them off.
  </aside>

<div markdown="1">

## Summary

TMK Land is a collaborative real-estate platform: you create property listings, manage rental contracts, raise or join shared-investment opportunities, and message other users. Because every one of these features requires sharing data with other accounts (co-owners, tenants, investors, friends), TMK Land **does** operate a backend — your account profile, listings, rooms, contracts, payments and investment records are stored on TMK servers (Supabase, hosted at `api.tmkgroup.vn`). Anything that does **not** need to be shared — draft form state, app preferences, call history — stays on your device.

**National-ID (CCCD/CMND) handling — in line with Vietnamese personal-data regulations:**

- The CCCD **number** is collected only when you (the tenant or landlord) choose to enter it for tenant identification within a rental contract. You are never required to provide it to use the app.
- An **on-device OCR helper** (Google ML Kit Text Recognition) lets you photograph a CCCD so the app can auto-fill the number, name, date of birth, etc. into the form. **The photo itself is never uploaded to TMK servers and is never stored in the app** — it lives only in the OS temp directory for the few seconds the OCR runs, and is discarded as soon as you close the scanner sheet.
- **No CCCD images are stored** in our database or storage buckets. Older builds offered "Upload CCCD front/back photo"; this feature has been removed.

The app ships **without** analytics and **without** crash reporting. Since 2026-11-07 the free version shows ads from **Google AdMob** (a banner on the Utilities screen and an optional rewarded video in Wallet → Missions); see [Advertising](#advertising-google-admob). The optional **Remove ads** subscription turns them off.

---

## Data we collect

### Sent to TMK servers (Supabase, `api.tmkgroup.vn`)

| What | Why | Stored in |
|------|-----|-----------|
| Account: provider UID, display name, email (from Google / Apple) | Authentication | `profiles` |
| Optional tenant identity fields: name on ID, CCCD/CMND number, issue date, issuing authority, date of expiry, nationality, place of origin | Tenant identification for rental contracts (only fields the user types or auto-fills via on-device OCR) | `profiles`, `tenants` |
| Avatar image | Show your face to other users you interact with | Supabase Storage `avatars/` |
| Property listings (title, description, price, address, photos, location) | Display the listing to other users | `properties` + Supabase Storage |
| Rental rooms and contracts (room details, tenant name & contact, term, rent amount) | Manage rentals between landlord and tenant accounts | `rooms`, `contracts` |
| Rental payment & expense records | Track who paid what, when | `payments`, income/expense receipt tables |
| Shared investment opportunities (amount, term, interest, participants) | Match investors with property owners | `opportunities`, interest-rate tables |
| Friend / follow relationships | Display your social graph inside the app | `profiles` relationships, follow tables |
| Friend chat messages | Deliver messages between accounts | TMK chat tables |
| Call log entries (peer ID, timestamp, duration) | Show your meeting history | `call_logs` |

You initiate every one of these writes — the app does not silently upload anything in the background.

### With your consent (device permissions)

| What | Why | When asked |
|------|-----|-----------|
| Camera | Take photos of properties, scan QR codes, take a short-lived photo of a CCCD that is processed on-device by OCR and **discarded** (never uploaded) | First time you tap the camera icon |
| Photo Library / Gallery | Pick existing photos for property listings, avatars, attachments | First time you tap the gallery icon |
| Save to Photo Library | Save shared receipts / generated PDFs back to your device | First time you tap "Save image" |
| Location | Centre the map on your area, suggest nearby properties, fill the address field of a new listing | First time you open the map or tap "Use my location" |
| Microphone | Join Jitsi-powered video meetings inside the app | First time you join a call |
| Face ID / Touch ID (iOS) | Optional biometric unlock for the app session | When you enable biometric lock in Profile |
| Notifications | Deliver reminders (e.g. upcoming rent due date) | First time the relevant feature opts in |

You can revoke any of these in your OS settings at any time; the corresponding feature degrades gracefully (you can still type an address manually, paste a photo URL, attend a call without microphone, etc.).

### On your device, locally

| What | Stored where |
|------|-------------|
| Drift / SQLite cache (call history, draft forms, ephemeral lookups) | App sandbox, `app_database.dart` |
| `shared_preferences` (theme, language, last-used filters) | App sandbox |
| Supabase OAuth session token | Encrypted on-device, used to authenticate API calls |
| `.env` config (Supabase URL + anon key, Google web client ID) | Bundled asset, public values |

---

## Permissions explained

### Android

| Permission | Why TMK Land needs it | Fallback if denied |
|------------|----------------------|--------------------|
| `INTERNET` | Talk to Supabase, Maplibre tile server, Jitsi meeting server, ML Kit model download (one-time) | App cannot function — every collaborative feature is online |
| `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` | Centre the map, pre-fill address field on a new listing | You can type the address by hand |
| `CAMERA` | Property photos, QR scan, transient CCCD photo for on-device OCR (discarded immediately) | Pick from gallery instead |
| `READ_MEDIA_IMAGES` (Android 13+) / `READ_EXTERNAL_STORAGE` (≤ 12) | Pick a photo from gallery for listings / avatar | You can still take a fresh photo with the camera |
| `RECORD_AUDIO` | Jitsi voice/video meetings | Join muted / skip meetings |
| `WRITE_EXTERNAL_STORAGE` (Android ≤ 9 only) | Save generated PDFs / shared receipts to public Downloads | Save inside app sandbox only |

### iOS

| Key (Info.plist) | Why TMK Land needs it |
|------------------|----------------------|
| `NSCameraUsageDescription` | Property photos, QR scan, transient CCCD photo for on-device OCR (discarded immediately) |
| `NSPhotoLibraryUsageDescription` | Pick photos for listings / avatar |
| `NSPhotoLibraryAddUsageDescription` | Save generated receipts / PDFs back to Photos |
| `NSMicrophoneUsageDescription` | Jitsi voice/video meetings |
| `NSLocationWhenInUseUsageDescription` / `NSLocationAlwaysAndWhenInUseUsageDescription` | Map centring, address pre-fill |
| `NSFaceIDUsageDescription` | Optional biometric session unlock |

---

## Third-party services

| Service | Purpose | Data sent | Link |
|---------|---------|-----------|------|
| **Supabase** (TMK-hosted at `api.tmkgroup.vn`) | Authentication, database, file storage | Everything in the "Sent to TMK servers" table above | [Supabase privacy](https://supabase.com/privacy) |
| **Google Sign-In** | Sign in with Google | Your Google provider UID + the public profile fields you approve (name, email, picture) | [Google privacy](https://policies.google.com/privacy) |
| **Apple Sign-In** | Sign in with Apple (iOS) | Your Apple provider UID + optionally a relay email | [Apple privacy](https://www.apple.com/legal/privacy/) |
| **Google ML Kit — Text Recognition** | On-device OCR for the CCCD scanner (auto-fill tenant identity form) | The photo bytes are processed **on-device only**; nothing is uploaded by ML Kit | [ML Kit terms](https://developers.google.com/ml-kit/terms) |
| **Maplibre GL** | Render the map | Map-tile requests (your viewport coordinates) go to the configured tile provider | Provider's own policy |
| **Jitsi Meet** | In-app video meetings | Audio/video stream + room name during the call | [Jitsi privacy](https://jitsi.org/meet-jit-si-privacy/) |
| **Google AdMob SDK** | Banner ad and optional rewarded video (see [Advertising](#advertising-google-admob)) | Device data listed in the Advertising section; for the rewarded video also your TMK account ID and a one-time session code so the coin reward can be verified | [Google privacy](https://policies.google.com/privacy) |

TMK Land **does not** integrate any third-party analytics, crash reporting or advertising attribution SDK. The only advertising SDK is Google AdMob, described below.

---

## Advertising (Google AdMob)

The free version shows a banner below the Utilities grid and offers an optional rewarded video in Wallet → Missions, using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your listings, contracts, messages, payments or CCCD data** — those are not available to the SDK. When you choose to watch the rewarded video, your TMK account ID and a one-time session code are attached to that ad so the coin reward can be verified.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset or delete your advertising ID in your device settings.

The rewarded video is never forced: you start it yourself to earn coins. Nothing else in the App is locked behind an ad.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

---

## Remove ads subscription

"Remove ads" (Settings → Ads) is an optional subscription (3 months, renewing automatically until you cancel it in your App Store / Google Play account settings). Payment is handled entirely by Apple or Google; **we never receive your payment details**. While the subscription is active the App does not start the advertising SDK, so none of the advertising data above is collected, and no banner is shown.

---

## In-app purchases

TMK Land offers optional VIP subscriptions and one-time purchases through Apple App Store / Google Play billing. All payment transactions are processed entirely by Apple or Google — TMK Land never receives or stores your payment card information. Purchases are subject to the respective platform's terms of service.

---

## Data retention

| Data | Retained until |
|------|---------------|
| Account profile, properties, contracts, payments, opportunities | Until you delete the record inside the app, or request account deletion (see "Your rights") |
| Supabase Storage files (avatars, property images) | Until the parent record is deleted; orphan files are pruned during periodic clean-up |
| OAuth session token on-device | Until you sign out or uninstall the app |
| On-device caches (Drift / SQLite / shared_preferences / OCR form state) | Until you tap "Clear Data" in Profile, sign out, or uninstall |
| Backend access logs | Up to 30 days for security and abuse-prevention, then aggregated or deleted |

---

## Children's privacy

TMK Land is **not directed to children**. Renting property and joining a shared-investment opportunity create legal and financial obligations, and the platform requires an adult account. You must be at least 18 years old (or the age of legal majority where you live) to use TMK Land. We do not knowingly collect personal data from anyone under that age; if we learn that we have, the account and its data will be deleted.

---

## Your rights

| Right | How to exercise it |
|-------|--------------------|
| **Access** | Open Profile → My Listings / My Opportunities / My Contracts to see every record tied to your account |
| **Correct** | Edit any record directly from its detail page; edit your profile in Profile → Edit Profile |
| **Export** | Email `trucmn@gmail.com` from the address tied to your account; we will return a JSON dump within 30 days |
| **Delete a single record** | Open the record → Delete |
| **Delete your account** | Profile → Settings → Delete Account, or email `trucmn@gmail.com`. We remove your `profiles` row, your Supabase Storage files, and anonymise any records that other accounts still depend on (e.g. a contract you signed with another user). |
| **Revoke OAuth** | Sign out, then revoke the app at [myaccount.google.com/permissions](https://myaccount.google.com/permissions) or, on iOS, **Settings → Apple ID → Sign in with Apple** |
| **Revoke a device permission** | OS Settings → Apps → TMK Land → Permissions |

---

## Account Deletion

You can delete your TMK Land account and all associated data at any time using either of the following methods:

**Option 1 — In-app (recommended):**
Open the app → Profile → Settings → Delete Account → confirm deletion.

**Option 2 — Email request:**
Send an email to **tmktechgroup@gmail.com** with the subject line "Account Deletion Request" and include the email address associated with your TMK Land account. We will process your request within 30 days.

Upon deletion, we will permanently remove:
- Your account profile and authentication record
- All property listings, rental contracts, and investment records you created
- Your uploaded photos and files
- On-device data is cleared when you uninstall the app

Records that other accounts depend on (e.g., a rental contract co-signed with a tenant) will be anonymised rather than deleted, so those users are not affected.

---

## Changes to this policy

When we make material changes, we update the `last_updated` date at the top and ship a new app version. Continued use after an update constitutes acceptance. Updates will clarify or expand your rights — never restrict them silently.

</div>
</article>
