---
# Garden Log dùng layout "default" (KHÔNG "app-policy") như Scan Doc / Caribbean Calendar:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app có Google AdMob.
# Nguồn từng ý (2026-11-07, đọc code thật của tmk_garden_log):
#  - lib/core/ads/ad_banner.dart (UMP consent, banner, ad unit thật, quảng cáo có thưởng)
#  - lib/core/ads/ad_free_window.dart (xem quảng cáo có thưởng → tắt quảng cáo 24 giờ)
#  - lib/core/iap/remove_ads_service.dart (gói com.tmkgroup.gardenlog.remove_ads_3m, 3 tháng)
#  - lib/core/storage/garden_storage.dart + TmkStorage.free(appId:) (CHỈ lưu trên máy, không CDN)
#  - package/tmk_storage_package/lib/src/models/backup_header.dart:7 (PBKDF2-SHA256 → AES-256-GCM)
#  - package/tmk_weather_package/.../open_meteo_datasource.dart (open-meteo + LocationAccuracy.medium:550)
#  - lib/features/wiki/data/wiki_api.dart:28 (wikipedia REST)
#  - package/tmk_ai_kit (khoá Gemini của chính người dùng — BYOK)
#  - lib/core/review/review_service.dart (hộp đánh giá của cửa hàng)
#  - ios/Runner/Info.plist + android/app/src/main/AndroidManifest.xml (quyền)
#  - lib/core/iap/iap_service.dart:16 (RevenueCat còn khoá mẫu → KHÔNG khởi tạo, không gửi gì)
layout: default
permalink: /gardenlog/
title: "Garden Log — Privacy Policy"
description: "Privacy policy for Garden Log: plant care diary, watering reminders, harvest log and garden journal."
last_updated: 2026-11-07
app_name: "Garden Log"
app_subtitle: "Plant Care Diary"
app_id: com.tmkgroup.gardenlog
data_collected: "No account. Your plants, photos, diary and records stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off. Weather and maps use your approximate location."
order: 50
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Garden Log — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.gardenlog</code></span>
      <span>Effective date: 2026-11-07</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Garden Log** ("the App"), published by
**TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Your garden stays on your phone. We run no server for this App and we collect nothing.**

There is no account and no sign-in. Your plants, photos, care log, schedules, harvest records, diary
entries, notes, expenses and saved places are written to a database inside the App's own folder on
your device. If you uninstall the App, all of it goes with it; we cannot recover anything for you,
because no copy ever reached us.

Four things do use the network, and none of them carries your garden records:

1. **Google AdMob ads** — free tier only (section 5).
2. **Weather and maps** — your approximate position goes to the weather and map services so the App
   can show the local forecast and the map around you (section 4).
3. **Plant articles** — the plant name you open goes to Wikipedia (section 4).
4. **Plant identification with AI** — only if you choose to turn it on with **your own** Google
   Gemini API key (section 6).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We never ask for your name, email address or phone number.
- We have no way to identify you, to see your garden, or to know that you exist as a user.

## 3. What stays on your device

Everything you create in the App:

| What | Where it lives |
|------|----------------|
| Plants, species, locations, photos | The App's own database and media folder on your device |
| Care schedules, watering / fertilising / pruning log | Same |
| Harvests, expenses, insights | Same |
| Diary entries, notes, reminders | Same |
| Settings, theme, language, units | Your device's app preferences |
| Backup files (`.tmkbak`) you export yourself | Where you choose to put them |

Reminders are scheduled **by your own phone**. There is no push server, so no reminder of yours
passes through us.

Backups are encrypted on your device with a passphrase **you** type (PBKDF2-SHA256 for the key,
AES-256-GCM for the data). We never see the passphrase or the file. If you lose the passphrase, the
backup cannot be opened — not by you and not by us.

## 4. What leaves your device, and why

| Service | What it receives | Why |
|---------|------------------|-----|
| **Open-Meteo** (`api.open-meteo.com`, `air-quality-api.open-meteo.com`, `archive-api.open-meteo.com`, `geocoding-api.open-meteo.com`) | Your approximate latitude and longitude | Local forecast, rain forecast used to skip a watering, air quality, climate history for your climate zone |
| **BigDataCloud** (`api.bigdatacloud.net`) | Your approximate latitude and longitude | Turn those coordinates into a place name to show you |
| **Map tiles** (`map.tmkgroup.vn`, `tiles.openfreemap.org`, `tile.openstreetmap.org`) | The map area you are looking at | Draw the map |
| **Nominatim / OpenStreetMap** (`nominatim.openstreetmap.org`) | The text you type into the map search box | Find the place you searched for |
| **Wikipedia** (`<language>.wikipedia.org`) | The title of the plant article you open | Show the plant article in the Wiki tab |
| **Google AdMob** | Standard ad-request data (section 5) | Serve the ads that keep the free tier free |
| **Apple App Store / Google Play** | Your purchase of the subscription | Take the payment and tell the App whether the subscription is active |

Location is requested as **"while using the app"** and at **medium (coarse) accuracy** — street or
district level, never a precise fix. You can refuse it: the App then asks you to pick a place on the
map instead, and the weather card tells you location is off. On Android the App declares only
`ACCESS_COARSE_LOCATION`.

## 5. Ads (free tier)

The free tier shows **Google AdMob** banners, and a **rewarded** ad you can choose to watch to turn
ads off for 24 hours. When an ad loads, Google AdMob receives the standard ad-request data: device
language, coarse location derived from your IP address, device model, app version, and the
advertising identifier where the operating system provides one.

- In the EEA, the UK and Switzerland the App shows **Google's consent form (UMP)** before any ad
  loads, and **Ad privacy options** in Settings lets you change your answer at any time.
- This version **does not ask for App Tracking Transparency permission on iOS**, so iOS does not
  hand your advertising identifier (IDFA) to AdMob.
- Google's own list of what its advertising SDK collects:
  <https://developers.google.com/admob/ios/privacy/data-disclosure>

**Subscribers see no ads at all**, so no ad request is sent.

## 6. Plant identification and diagnosis with AI (optional, your own key)

The AI screen is **off until you set it up yourself**. To use it you paste **your own** Google Gemini
API key, which the App stores on your device only. When you then send a photo of a leaf or a plant:

- the photo and your question go **from your device to Google** (`generativelanguage.googleapis.com`)
  **under your own API key**, governed by your own agreement with Google;
- they do **not** pass through any TMK server, and we never see them;
- nothing is sent at all while the AI screen is unused or has no key.

Remove the key in Settings and the feature stops sending anything.

## 7. No analytics, no tracking, no profiling

The App contains **no** analytics SDK, **no** crash reporter and **no** attribution SDK: no Firebase
Analytics, no Crashlytics, no Sentry, no Mixpanel, no AppsFlyer, no Facebook SDK. We do not build a
profile of you, we do not track you across apps or websites, and we sell nothing to anybody —
we hold nothing to sell.

The App ships with a purchase library (RevenueCat) that is **not configured and never starts**, so
nothing is sent to it.

## 8. Photos, camera and sharing

The camera and photo library are used only when you add a photo to a plant, a diary entry or the AI
screen. Photos you add are copied into the App's own folder; the App never scans your library and
never uploads a photo on its own.

The App shares a file only when **you** tap share or export (a `.tmkbak` backup, a CSV export, a
report). It then goes wherever you send it, under that app's own policy.

## 9. In-app purchase

One auto-renewing subscription, **Remove ads** (`com.tmkgroup.gardenlog.remove_ads_3m`), US$1.00 per
3 months, turns off all ads. It is handled entirely by Apple or Google: we never see your payment
details. Manage or cancel it in your App Store or Google Play subscription settings; cancelling takes
effect at the end of the paid period. Terms of Use: Apple's standard EULA,
<https://www.apple.com/legal/internet-services/itunes/dev/stdeula/>.

## 10. Children

The App is a gardening tool for general audiences and is not directed to children under 13. We do not
knowingly collect anything from a child — in fact we collect nothing from anybody.

## 11. Your rights

Because we hold no data about you, there is nothing for us to export, correct or delete on your
behalf. You are in full control:

- **Delete everything** — uninstall the App, or delete individual plants, entries and records in the App.
- **Take your data with you** — export an encrypted `.tmkbak` backup, or a CSV export, from Settings.
- **Turn off location** — in your device's system settings, at any time.
- **Change your ad consent** — Settings → Ad privacy options (where the law requires the form).
- **Turn off ads** — subscribe to Remove ads, or watch a rewarded ad for 24 ad-free hours.

For the services in section 4, their own policies apply:
[Google](https://policies.google.com/privacy) ·
[Open-Meteo](https://open-meteo.com/en/terms) ·
[BigDataCloud](https://www.bigdatacloud.com/privacy-and-cookie-policy) ·
[OpenStreetMap](https://osmfoundation.org/wiki/Privacy_Policy) ·
[Wikimedia](https://foundation.wikimedia.org/wiki/Policy:Privacy_policy) ·
[Apple](https://www.apple.com/legal/privacy/)

## 12. Changes

If this policy changes, the date at the top of this page changes with it and the new text appears
here. Material changes will also be noted in the App's release notes.

## 13. Contact

**TMK Tech Group** — <tmktechgroup@gmail.com>

Support page: [Garden Log — Support](/gardenlog/support/)

</div>
</article>
