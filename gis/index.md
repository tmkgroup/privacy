---
# GIS dùng layout "default" (KHÔNG "app-policy") như Scan Doc: _includes/master-policy.md ghi
# "never share it with advertisers", sai với app có Google AdMob (gắn 2026-11-24).
# Nguồn từng ý (2026-11-24):
#  - tmk_gis/cau_truc.md mục 2.2 (quyền), 2.3 (kết nối ra ngoài), 2.4 (dữ liệu Hive trên máy)
#  - tmk_gis/ios/Runner/Info.plist (purpose string: Bluetooth, vị trí, camera, thư viện ảnh đọc + ghi,
#    micro đo decibel, cảm biến chuyển động, NSUserTrackingUsageDescription, GADApplicationIdentifier)
#  - tmk_gis/lib/ads/*.dart + lib/core/services/remove_ads_service.dart (bê tmk_scan_doc: UMP, banner,
#    quảng cáo có thưởng 24 giờ, gói com.tmkgroup.gis.remove_ads_3m 3 tháng)
#  - tmk_gis/lib/core/services/fire_service.dart + fire_watch_service.dart (tải CSV NASA FIRMS)
#  - package/tmk_map_kit/lib/src/map_server.dart (map.tmkgroup.vn, tiles.openfreemap.org,
#    tile.openstreetmap.org), nominatim.openstreetmap.org/search, google.com/maps/dir
#  - Mục 5 (dữ liệu SDK quảng cáo thu) bê nguyên scandoc/index.md của repo này
#    (nguồn developers.google.com/admob/ios/privacy/data-disclosure)
layout: default
permalink: /gis/
title: "GIS — Privacy Policy"
description: "Privacy policy for GIS: field survey and mapping."
last_updated: 2026-11-24
app_name: "GIS"
app_subtitle: "Field Survey & Mapping"
app_id: com.tmkgroup.gis
data_collected: "No account. Survey points, lines, areas, photos and notes stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 46
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>GIS — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.gis</code></span>
      <span>Effective date: 2026-11-24</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **GIS: Field Survey & Mapping** ("the App"), published by
**TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Your survey data stays on your device.** There is no account and no sign-in. Points, lines, areas, projects,
photos, journal entries, calendar items and notes are stored in the App's own database on your phone. If you
uninstall the App, that data is gone with it; we keep no copy.

The App uses the network for maps, address search, fire alerts, map layers and files you add yourself, the DJI
drone SDK, and Google's advertising SDK. Sections 4 to 6 list each one.

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.
- A surveyor name or project member you type in the App is stored only on your device, with your records.

## 3. What is stored on your device

- survey points, lines and areas with their coordinates and the form fields you fill in;
- projects, project forms and project members;
- photos you take or attach, and labelled photos you create;
- journal entries, work calendar items and quick notes;
- drone flight logs;
- downloaded offline map files and the map layers you added;
- your settings, and the end time of a 24-hour ad-free window if you watched a rewarded ad.

This data is never uploaded to us. It leaves your device only when you export or share it yourself.

### Permissions

| Permission | Why |
|---|---|
| Location | To show your position on the map, record the coordinates of what you survey, and control the drone. |
| Camera | Field photos, scanning land certificates, and AR measuring. |
| Photo library | To pick a photo you choose, and to save labelled photos you create. |
| Microphone | Only for the sound level meter (decibels). |
| Motion sensors | Only for the compass and measuring tools. |
| Bluetooth | To connect to the drone remote controller. |
| Tracking (iPhone and iPad) | Personalised ads, only if you tap "Allow" on Apple's prompt. |

You can revoke any permission in your device settings at any time. The App keeps working with fewer features.

## 4. Network services the App uses

- **Map tiles and routes** come from our map server (map.tmkgroup.vn). Outside Vietnam the App may load map
  tiles from OpenFreeMap (tiles.openfreemap.org) or OpenStreetMap (tile.openstreetmap.org). These requests
  ask for the map area on screen or the route you request; they do not carry your saved survey data.
- **Address search** sends the text you type to OpenStreetMap Nominatim (nominatim.openstreetmap.org).
- **Directions** open Google Maps when you choose it.
- **Fire alerts** download public fire data files from NASA FIRMS (firms.modaps.eosdis.nasa.gov). Checking
  those fires against your saved areas is done on your device.
- **Offline maps and map layers** (MBTiles, WMS, TMS, XYZ) are downloaded from the addresses you enter.
- **Drone control** uses the DJI Mobile SDK, operated by DJI under DJI's own privacy policy.
- **Text recognition** of land certificates uses Google ML Kit on your device; the images are not sent to
  Google for processing. **AR measuring** uses ARCore (Android) or ARKit (iPhone and iPad) on your device.

## 5. Advertising (Google AdMob)

The free version shows a banner above the tab bar (not on the Map tab) and offers an optional rewarded ad,
using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your survey
data, photos or notes** — those are not available to the SDK.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before
ads are personalised, and you can change your choice at any time with the "Ad privacy options" button in
Settings. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App
Tracking Transparency prompt. You can reset or delete your advertising ID in your device settings.

The **rewarded ad** is never forced: you tap it yourself in Settings to turn ads off for 24 hours. Nothing in
the App is locked behind it.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 6. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renewing automatically until you cancel it in your store
account settings). Payment is handled entirely by the Apple App Store or Google Play; **we never receive your
payment details**. While the subscription is active the App does not start the advertising SDK at all, so none
of the data in section 5 is collected.

## 7. Sharing and export

When you export or share (for example a GeoJSON file or a photo), the App opens the standard system share
sheet or file picker. Whatever you send goes where you direct it, not to us.

## 8. Data retention

On-device data is kept until you delete it in the App (Settings also has "Delete all data") or uninstall the
App. There is no off-device survey data held by us.

## 9. Children

The App is not directed to children under 13. We do not knowingly collect data from children under 13, or 16
in the EU.

## 10. Your rights

Your survey data lives on your device: you can view, edit, export and delete it inside the App. You may also
contact tmktechgroup@gmail.com with any question.

## 11. Changes to this policy

We will update the "Effective date" above and ship a new app version whenever this policy changes.

</div>
</article>
