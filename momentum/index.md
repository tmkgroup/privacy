---
# Momentum dùng layout "default" (KHÔNG "app-policy") như Garden Log / Scan Doc:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app có Google AdMob.
# Nguồn từng ý (2026-11-16, đọc code thật của tmk_momentum):
#  - android/app/src/main/AndroidManifest.xml + ios/Runner/Info.plist (quyền)
#  - lib/ads/app_ads.dart:48-49 (ad unit thật AdMob Android), main.dart:127 (gói remove_ads_3m)
#  - lib/features/capture/data/verify/capture_verifier.dart:38-100 (worker verify-momentum.tmkgroup.vn,
#    POST /v1/captures lấy mã + PUT /v1/captures/<mã> gửi SHA-256, fail soft)
#  - lib/features/capture/data/datasources/weather_datasource.dart:22 (api.open-meteo.com)
#  - lib/core/storage/storage_bootstrap.dart (TmkStorage.withUserCloud + GoogleDriveProvider, đăng nhập lười)
#  - lib/features/settings/presentation/cubit/backup_cubit.dart (export/restore có mật khẩu)
#  - package/tmk_storage_package/lib/src/models/backup_header.dart (PBKDF2-SHA256 -> AES-256-GCM)
#  - package/tmk_map_kit (map.tmkgroup.vn, tiles.openfreemap.org, tile.openstreetmap.org, nominatim)
#  - package/tmk_ai_kit (generativelanguage.googleapis.com — khoá Gemini của chính người dùng, BYOK)
#  - lib/core/observability/analytics.dart (AppAnalytics -> AppLogger trên máy, KHÔNG có SDK phân tích)
layout: default
permalink: /momentum/
title: "Momentum — Privacy Policy"
description: "Privacy policy for Momentum: Timestamp Camera — GPS, time, weather and project stamps on photos and videos."
last_updated: 2026-11-16
app_name: "Momentum"
app_subtitle: "Timestamp Camera"
app_id: com.tmkgroup.tmk_momentum
data_collected: "No account. Photos, videos and projects stay on your device. GPS and weather stamps send your coordinates to the weather and map services. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 100
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Momentum — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.tmk_momentum</code></span>
      <span>Effective date: 2026-11-16</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Momentum — Timestamp Camera** ("the App"),
published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to
children under 13.

## 1. In short

**Your photos, videos and projects stay on your phone. There is no TMK account and we never receive
a picture you take.**

Everything you shoot, every project, every stamp preset, every note and every report is written to
the App's own folder on your device. If you uninstall the App, all of it goes with it; we cannot
recover anything for you, because no copy ever reached us.

Five things use the network, and none of them carries your picture:

1. **Google AdMob ads** — free tier only (section 6).
2. **Location and weather stamps** — your coordinates go to the weather and map services so the
   stamp can show where and in what weather the shot was taken (section 4).
3. **Capture verification** — a code and the **SHA-256 fingerprint** of the file, never the file
   itself (section 5).
4. **Backup to your own Google Drive** — only after you sign in yourself (section 7).
5. **AI photo analysis** — only if you turn it on with **your own** Google Gemini API key (section 8).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We never ask for your name, email address or phone number.
- We have no way to identify you, to see your shots, or to know that you exist as a user.

## 3. What stays on your device

| What | Where it lives |
|------|----------------|
| Photos and videos you capture, originals and stamped copies | The App's own folder on your device |
| Projects, project folders, titles and descriptions | The App's own database |
| Stamp presets, logo image, colours, date formats | Same |
| Notes, tags, PDF and CSV reports you build | Same |
| Settings, theme, language, units | Your device's app preferences |
| Backup files (`.tmkbak`) you export yourself | Where you choose to put them |

Backups are encrypted on your device with a passphrase **you** type (PBKDF2-SHA256 for the key,
AES-256-GCM for the data). We never see the passphrase or the file. If you lose the passphrase, the
backup cannot be opened — not by you and not by us.

## 4. What leaves your device, and why

| Service | What it receives | Why |
|---------|------------------|-----|
| **Open-Meteo** (`api.open-meteo.com`) | Your latitude and longitude | The temperature and conditions printed in the weather stamp |
| **Map tiles** (`map.tmkgroup.vn`, `tiles.openfreemap.org`, `tile.openstreetmap.org`) | The map area you are looking at | Draw the map and the small map stamp |
| **Nominatim / OpenStreetMap** (`nominatim.openstreetmap.org`) | The text you type into the map search box | Find the place you searched for |
| **Momentum verification** (`verify-momentum.tmkgroup.vn`) | A one-time code and the SHA-256 fingerprint of the file (section 5) | Prove a shot has not been edited since it was taken |
| **Google Drive** (`www.googleapis.com`) | The encrypted backup you choose to upload | Keep your own backup in your own Drive (section 7) |
| **Google Gemini** (`generativelanguage.googleapis.com`) | The photo you send, under your own API key | Optional AI analysis (section 8) |
| **Google AdMob** | Standard ad-request data (section 6) | Serve the ads that keep the free tier free |
| **Apple App Store / Google Play** | Your purchase of the subscription | Take the payment and tell the App whether the subscription is active |

Location is used while you are shooting, so the stamp can print coordinates and the place name. The
App asks for **precise** location because a jobsite stamp with a street-level error is worthless; on
Android it declares `ACCESS_FINE_LOCATION` and `ACCESS_COARSE_LOCATION`. Turning the place name into
text is done by your own device's geocoder. You can refuse location: the App then stamps time only,
and the weather field stays empty.

## 5. Capture verification

When verification is on, the App asks `verify-momentum.tmkgroup.vn` for a short code before the
shot, prints that code in the stamp, and afterwards sends the **SHA-256 fingerprint** of the
finished file so the code and the fingerprint are stored together. Anyone you give the code to can
open the public check page and confirm that a file they hold is byte-for-byte the one you took.

- **The photo or video itself is never uploaded.** A fingerprint cannot be turned back into a picture.
- An unclaimed code is purged after 24 hours.
- The call fails soft: with no network the shot is simply stamped with the device time and no code.

## 6. Ads (free tier)

The free tier shows **Google AdMob** banners, and a **rewarded** ad you can choose to watch. When an
ad loads, Google AdMob receives the standard ad-request data: device language, coarse location
derived from your IP address, device model, app version, and the advertising identifier where the
operating system provides one.

- In the EEA, the UK and Switzerland the App shows **Google's consent form (UMP)** before any ad
  loads, and **Ad privacy options** in Settings lets you change your answer at any time.
- Google's own list of what its advertising SDK collects:
  <https://developers.google.com/admob/android/privacy/play-data-disclosure>

**Subscribers see no ads at all**, so no ad request is sent.

## 7. Backup to your own Google Drive (optional)

The App can keep your encrypted `.tmkbak` backup in **your own** Google Drive. Nothing happens until
you tap **Connect to Drive** and sign in to Google yourself. From then on:

- the backup goes **from your device to your Drive**, under your own Google account;
- it is encrypted with your passphrase **before** it leaves the device, so Google stores a file
  neither Google nor we can read;
- it does **not** pass through any TMK server.

Disconnect in Settings and the App stops talking to Drive. Local export to a file of your own needs
no sign-in at all.

## 8. AI photo analysis (optional, your own key)

The AI screen is **off until you set it up yourself**. To use it you paste **your own** Google Gemini
API key, which the App stores on your device only. When you then send a photo:

- the photo and your question go **from your device to Google**
  (`generativelanguage.googleapis.com`) **under your own API key**, governed by your own agreement
  with Google;
- they do **not** pass through any TMK server, and we never see them;
- nothing is sent at all while the AI screen is unused or has no key.

Remove the key in Settings and the feature stops sending anything.

## 9. No analytics, no tracking, no profiling

The App contains **no** analytics SDK, **no** crash reporter and **no** attribution SDK: no Firebase
Analytics, no Crashlytics, no Sentry, no Mixpanel, no AppsFlyer, no Facebook SDK. Its internal event
log is written to a buffer **on your device** and is never sent anywhere. We do not build a profile
of you, we do not track you across apps or websites, and we sell nothing to anybody — we hold
nothing to sell.

## 10. Permissions explained

| Permission | Why Momentum needs it |
|---|---|
| Camera | Take the photos and videos you stamp |
| Microphone | Record sound with a video; not used for photos |
| Photo library | Pick an existing photo to stamp, pick your logo, and save stamped copies back to your gallery |
| Location (precise) | Print coordinates, place name, altitude and bearing in the stamp, and fetch the weather for that spot |
| Motion / compass | Print the direction the camera was pointing |
| Calendar | Only used by the in-app calendar and reminder tools; refuse it and the camera still works |
| Internet | The services listed in section 4 |

Every one of them can be refused in your device settings. The App keeps working with time-only
stamps.

## 11. Sharing and export

The App shares a file only when **you** tap share or export — a stamped photo or video, a PDF or CSV
report, a `.tmkbak` backup. It then goes wherever you send it, under that app's own policy. The App
never scans your photo library and never uploads a file on its own.

## 12. In-app purchase

One auto-renewing subscription, **Remove ads** (`com.tmkgroup.tmk_momentum.remove_ads_3m`), US$1.00
per 3 months, turns off all ads. It is handled entirely by Apple or Google: we never see your
payment details. Manage or cancel it in your App Store or Google Play subscription settings;
cancelling takes effect at the end of the paid period. Terms of Use: Apple's standard EULA,
<https://www.apple.com/legal/internet-services/itunes/dev/stdeula/>.

## 13. Children

The App is a work and documentation camera for general audiences and is not directed to children
under 13. We do not knowingly collect anything from a child — in fact we collect nothing from
anybody.

## 14. Your rights

Because we hold no data about you, there is nothing for us to export, correct or delete on your
behalf. You are in full control:

- **Delete everything** — uninstall the App, or delete individual shots and projects in the App.
- **Take your data with you** — export an encrypted `.tmkbak` backup, or a PDF / CSV report, from
  the App.
- **Turn off location** — in your device's system settings, at any time.
- **Turn off verification, Drive backup or AI** — each one is a switch in Settings.
- **Change your ad consent** — Settings → Ad privacy options (where the law requires the form).
- **Turn off ads** — subscribe to Remove ads.

For the services in section 4, their own policies apply:
[Google](https://policies.google.com/privacy) ·
[Open-Meteo](https://open-meteo.com/en/terms) ·
[OpenStreetMap](https://osmfoundation.org/wiki/Privacy_Policy) ·
[Apple](https://www.apple.com/legal/privacy/)

## 15. Changes

If this policy changes, the date at the top of this page changes with it and the new text appears
here. Material changes will also be noted in the App's release notes.

## 16. Contact

**TMK Tech Group** — <tmktechgroup@gmail.com>

</div>
</article>
