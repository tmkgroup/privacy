---
layout: app-policy
permalink: /tmk_land/
title: "TMK Land — Privacy Policy"
description: "Privacy policy for TMK Land, the real-estate management and shared-investment platform."
last_updated: 2026-05-14
app_name: TMK Land
app_subtitle: Real-Estate Management & Shared Investment
app_id: com.tmkgroup.tmkland
data_collected: "Account, property, rental and investment data are stored on TMK servers (Supabase) because the app is collaborative. National-ID (CCCD) number is collected with consent for tenant identification; CCCD photos are never stored or uploaded — they are processed on-device only by an OCR helper that discards them after extracting text."
order: 40
---

## Summary

TMK Land is a collaborative real-estate platform: you create property listings, manage rental contracts, raise or join shared-investment opportunities, and message other users. Because every one of these features requires sharing data with other accounts (co-owners, tenants, investors, friends), TMK Land **does** operate a backend — your account profile, listings, rooms, contracts, payments and investment records are stored on TMK servers (Supabase, hosted at `api.tmkgroup.vn`). Anything that does **not** need to be shared — draft form state, app preferences, call history — stays on your device.

**National-ID (CCCD/CMND) handling — in line with Vietnamese personal-data regulations:**

- The CCCD **number** is collected only when you (the tenant or landlord) choose to enter it for tenant identification within a rental contract. You are never required to provide it to use the app.
- An **on-device OCR helper** (Google ML Kit Text Recognition) lets you photograph a CCCD so the app can auto-fill the number, name, date of birth, etc. into the form. **The photo itself is never uploaded to TMK servers and is never stored in the app** — it lives only in the OS temp directory for the few seconds the OCR runs, and is discarded as soon as you close the scanner sheet.
- **No CCCD images are stored** in our database or storage buckets. Older builds offered "Upload CCCD front/back photo"; this feature has been removed.

The app currently ships **without** analytics, **without** crash reporting, and **without** advertising. AdMob is declared in the Android manifest only because a shared TMK package (`tmk_wallet_package`) pulls in `play-services-ads`; the AdMob App ID is Google's official **test** ID and no real ads are requested.

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
| **Google AdMob SDK** | **Currently not serving ads.** The SDK is pulled in by a shared TMK package; the App ID configured is Google's official test ID (`ca-app-pub-3940256099942544~3347511713`). | Nothing — no `AdRequest` is ever made by TMK Land | [Google privacy](https://policies.google.com/privacy) |

TMK Land **does not** integrate any third-party analytics, crash reporting or advertising attribution SDK.

---

## In-app purchases

TMK Land does not sell anything in-app today. If we add paid features in a future version, billing will go through Apple / Google and this policy will be updated before that build ships.

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

## Changes to this policy

When we make material changes, we update the `last_updated` date at the top and ship a new app version. Continued use after an update constitutes acceptance. Updates will clarify or expand your rights — never restrict them silently.
