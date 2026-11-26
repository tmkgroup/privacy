---
# Food: Easy Recipes dùng layout "default" (KHÔNG "app-policy") như Garden Log / Scan Doc:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app có Google AdMob.
# Nguồn từng ý (2026-11-26, đọc code thật của E:\Onsite\flutter\tmk_food):
#  - lib/ads/app_ads.dart (UMP consent, showPrivacyOptionsForm, banner + quảng cáo có thưởng)
#  - lib/ads/rewarded_ad_free.dart:31 (xem quảng cáo có thưởng → tắt quảng cáo 24 giờ)
#  - lib/services/remove_ads_service.dart:39 (gói com.tmkgroup.food.remove_ads_3m, 3 tháng)
#  - lib/services/backup_service.dart:120 (file sao lưu JSON do người dùng tự xuất)
#  - lib/main.dart:38 (ảnh món từ cdn-food.tmkgroup.vn)
#  - lib/services/nearby_food_service.dart:192 (Overpass: quán ăn quanh vị trí)
#  - lib/pages/nearby_food_map.dart:126 (LocationAccuracy.medium), :238 (OSRM map.tmkgroup.vn), :259 (Google Maps)
#  - package/tmk_map_kit/lib/src/map_server.dart (tile map.tmkgroup.vn / openfreemap / openstreetmap)
#  - package/tmk_weather_package/.../open_meteo_datasource.dart:551,627 (open-meteo, bigdatacloud)
#  - ios/Runner/Info.plist (NSLocationWhenInUse, NSPhotoLibrary; KHÔNG NSUserTrackingUsageDescription)
#  - android/app/src/main/AndroidManifest.xml (quyền)
layout: default
permalink: /food/
title: "Food: Easy Recipes — Privacy Policy"
description: "Privacy policy for Food: Easy Recipes: Vietnamese recipes, meal plans, food journal, vegetarian days and nearby restaurants."
last_updated: 2026-11-26
app_name: "Food: Easy Recipes"
app_subtitle: "Recipes & Meal Plans"
app_id: com.tmkgroup.tmkFood
data_collected: "No account. Your meal plans, food journal, diary, notes and health records stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off. Weather and the restaurant map use your approximate location."
order: 51
---

<article class="app-policy">
  <header class="app-header">
    <h1>Food: Easy Recipes — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.tmkFood</code> (iOS) · <code>com.tmkgroup.tmk_food</code> (Android)</span>
      <span>Effective date: 2026-11-26</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Food: Easy Recipes** ("the App"), published by
**TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Your records stay on your phone. We run no account server for this App and we collect nothing about you.**

There is no account and no sign-in. Your saved recipes, meal plans, food journal, meal reminders,
calendar events, vegetarian-day settings, diary entries, notes, water and weight records are written
to storage inside the App on your device. If you uninstall the App, all of it goes with it; we cannot
recover anything for you, because no copy ever reached us.

Things that use the network, none of which carries your records:

1. **Dish photos** — downloaded from our image server (section 4).
2. **Weather** — your approximate position goes to the weather service (section 4).
3. **Nearby restaurants map** — your approximate position goes to the map services (section 4).
4. **Google AdMob ads** — free tier only (section 5).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We never ask for your name, email address or phone number.
- We have no way to identify you or to see what you record in the App.

## 3. What stays on your device

| What | Where it lives |
|------|----------------|
| Saved recipes, meal plans, shopping list | The App's own storage on your device |
| Food journal, meal reminders, calendar events | Same |
| Vegetarian-day settings (1st / 15th lunar day, custom days) | Same |
| Diary entries and notes | Same |
| Water intake, weight and BMI records, health conditions you pick | Same |
| Saved weather places, theme, colour | Your device's app preferences |
| Backup files (`.json`) you export yourself | Where you choose to put them |

Reminders (meals, vegetarian days, notes) are scheduled **by your own phone**. There is no push
server, so no reminder of yours passes through us.

A backup is a plain `.json` file that **you** create and share from **Backup** in the App. It is not
encrypted: keep it somewhere you trust. We never receive it.

## 4. What leaves your device, and why

| Service | What it receives | Why |
|---------|------------------|-----|
| **Our image server** (`cdn-food.tmkgroup.vn`) | The name of the dish photo being shown | Show dish photos |
| **Open-Meteo** (`api.open-meteo.com`, `air-quality-api.open-meteo.com`, `geocoding-api.open-meteo.com`) | Your approximate latitude and longitude, or the place name you search for | Local forecast and air quality |
| **BigDataCloud** (`api.bigdatacloud.net`) | Your approximate latitude and longitude | Turn those coordinates into a place name to show you |
| **Overpass / OpenStreetMap** (`overpass-api.de`, `overpass.kumi.systems`) | Your approximate latitude and longitude and the search radius | Find restaurants and food stalls around you |
| **Map tiles** (`map.tmkgroup.vn`, `tiles.openfreemap.org`, `tile.openstreetmap.org`) | The map area you are looking at | Draw the map |
| **Route service** (`map.tmkgroup.vn`, Vietnam only) | The start and end points of a route you ask for | Draw directions on the map |
| **Google Maps** (outside Vietnam) | The destination you tap, opened in Google Maps under Google's policy | Directions |
| **Google AdMob** | Standard ad-request data (section 5) | Serve the ads that keep the free tier free |
| **Apple App Store / Google Play** | Your purchase of the subscription | Take the payment and tell the App whether the subscription is active |

Location is requested as **"while using the app"** and at **medium accuracy** — street or district
level. It is used only on the weather screen and the nearby restaurants map. You can refuse it: the
rest of the App works without it.

## 5. Ads (free tier)

The free tier shows **Google AdMob** banners, and a **rewarded** ad you can choose to watch to turn
ads off for 24 hours. When an ad loads, Google AdMob receives the standard ad-request data: device
language, coarse location derived from your IP address, device model, app version, and the
advertising identifier where the operating system provides one.

- In the EEA, the UK and Switzerland the App shows **Google's consent form (UMP)** before any ad
  loads, and **Ad privacy options** on the Profile screen lets you change your answer at any time.
- This version **does not ask for App Tracking Transparency permission on iOS**, so iOS does not
  hand your advertising identifier (IDFA) to AdMob, and the App does not track you.
- Google's own list of what its advertising SDK collects:
  <https://developers.google.com/admob/ios/privacy/data-disclosure>

**Subscribers see no ads at all**, so no ad request is sent.

## 6. No analytics, no tracking, no profiling

The App contains **no** analytics SDK, **no** crash reporter and **no** attribution SDK. We do not
build a profile of you, we do not track you across apps or websites, and we sell nothing to anybody —
we hold nothing to sell.

## 7. Photos, files and sharing

The photo library / file picker is used only when **you** choose a backup file to restore. The App
shares something only when **you** tap share (a backup file, the App's store link). It then goes
wherever you send it, under that app's own policy.

## 8. Health information

Health conditions you pick, water and weight records stay on your device and are never sent anywhere.
Health-related content in the App is general reference only and does not replace a doctor.

## 9. In-app purchase

One auto-renewing subscription, **Remove ads** (`com.tmkgroup.food.remove_ads_3m`), billed every
3 months, turns off all ads. It is handled entirely by Apple or Google: we never see your payment
details. Manage or cancel it in your App Store or Google Play subscription settings; cancelling takes
effect at the end of the paid period. Terms of Use: Apple's standard EULA,
<https://www.apple.com/legal/internet-services/itunes/dev/stdeula/>.

## 10. Children

The App is a cooking tool for general audiences and is not directed to children under 13. We do not
knowingly collect anything from a child — in fact we collect nothing from anybody.

## 11. Your rights

Because we hold no data about you, there is nothing for us to export, correct or delete on your
behalf. You are in full control:

- **Delete everything** — uninstall the App, or delete individual entries in the App.
- **Take your data with you** — export a backup file from **Backup**.
- **Turn off location** — in your device's system settings, at any time.
- **Change your ad consent** — Profile → Ad privacy options (where the law requires the form).
- **Turn off ads** — subscribe to Remove ads, or watch a rewarded ad for 24 ad-free hours.

For the services in section 4, their own policies apply:
[Google](https://policies.google.com/privacy) ·
[Open-Meteo](https://open-meteo.com/en/terms) ·
[BigDataCloud](https://www.bigdatacloud.com/privacy-and-cookie-policy) ·
[OpenStreetMap](https://osmfoundation.org/wiki/Privacy_Policy) ·
[Apple](https://www.apple.com/legal/privacy/)

## 12. Changes

If this policy changes, the date at the top of this page changes with it and the new text appears
here.

## 13. Contact

**TMK Tech Group** — <contact@tmktechgroup.com>

Support page: [Food: Easy Recipes — Support](/food/support/)

</div>
</article>
