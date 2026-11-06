---
# Catholic Calendar dùng layout "default" (KHÔNG "app-policy") như Caribbean Calendar / Xiangqi Clash:
# master-policy ghi "never share it with advertisers", sai với app này (Google AdMob).
# Nguồn từng ý (2026-11-06, anh Truc "làm đi để publish" → "Làm hồ sơ store"), đọc trong code thật:
#  - tmk_catholic_calendar/lib/ads/app_ads.dart (UMP consent, AdMob banner + rewarded, tắt khi đã mua)
#  - tmk_catholic_calendar/lib/premium/remove_ads.dart:33 (com.tmkgroup.catholic.remove_ads_3m, 3 tháng)
#  - tmk_catholic_calendar/lib/services/nearby_church_service.dart:350-359 (overpass-api.de,
#    overpass.kumi.systems, User-Agent tmk-catholic-calendar)
#  - tmk_catholic_calendar/lib/services/{bible_service,saints_service,media_service,church_teaching_service}.dart
#    (cdn-catholic.tmkgroup.vn — chỉ tải xuống)
#  - package/tmk_map_kit/lib/src/map_server.dart:28,54,58 (map.tmkgroup.vn trong VN,
#    tiles.openfreemap.org ngoài VN, tile.openstreetmap.org dự phòng)
#  - package/calendar/tmk_universal_calendar_sync/lib/src/providers/{google,outlook}_calendar_provider.dart
#    (scope ĐỌC + GHI, không phải read-only)
#  - package/tmk_spendly_package (open.er-api.com, api.frankfurter.dev, data-api.ecb.europa.eu,
#    api.binance.com, api.coingecko.com, query1.finance.yahoo.com, api.fiscaldata.treasury.gov,
#    sjc.com.vn, techcombank.com)
#  - tmk_catholic_calendar/ios/Runner/Info.plist (purpose strings: location, camera, photo library,
#    calendar, tracking)
#  - tmk_catholic_calendar/lib/pages/mass_time_contribute_screen.dart (đóng góp giờ lễ: lưu máy +
#    người dùng tự gửi qua email / share sheet, app không tự upload)
#  - developers.google.com/admob/flutter/privacy/data-disclosure (đọc 2026-11-06)
layout: default
permalink: /catholic-calendar/
title: "Catholic Calendar — Privacy Policy"
description: "Privacy policy for Catholic Calendar."
last_updated: 2026-11-06
app_name: Catholic Calendar
app_subtitle: Liturgical calendar, prayers and nearby churches
app_id: com.tmkgroup.catholic
data_collected: "No account. Prayer journal, notes, reminders and budget stay on your device. Catholic content and nearby-church searches are fetched online. Google AdMob ads collect device data."
order: 140
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Catholic Calendar — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.catholic</code></span>
      <span>Effective date: 2026-11-06</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Catholic Calendar** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.

## 2. Information stored only on your device

The App saves on your device: your language, theme and display settings, prayer journal entries, notes, reminders, countdown events, sacrament and confession records, reading-plan progress, favourites, household budget entries, downloaded content for offline reading, and whether you have removed ads. This information is not sent to us. Uninstalling the App removes it.

You can export an encrypted backup file (`.tmkbak`, AES-256-GCM, protected by a passphrase you choose). The file goes only where you save or share it; we never receive it. If you lose the passphrase, the file cannot be opened.

## 3. Catholic content

Scripture texts, saints, church teaching and media lists are downloaded from our content server at `cdn-catholic.tmkgroup.vn`. These requests only ask for a file by language and name; they carry no personal data. Like any internet service, the server receives your IP address in order to deliver the file.

## 4. Nearby churches and maps

The "Nearby Church" feature and the church map search OpenStreetMap data:

- Church data comes from the public Overpass API (`overpass-api.de`, with `overpass.kumi.systems` as a fallback). If you allow location access, the App sends the coordinates of your search area to that public service to list churches around you. If you do not allow location access, the feature does not use your position.
- Map tiles come from our map server (`map.tmkgroup.vn`) inside Vietnam, from OpenFreeMap (`tiles.openfreemap.org`) elsewhere, and from OpenStreetMap tiles (`tile.openstreetmap.org`) as a last resort. Driving directions inside Vietnam are calculated on our map server.
- Your location is not stored on our servers and is not used for anything other than finding churches near you and showing directions.

Links: [OpenStreetMap privacy policy](https://osmfoundation.org/wiki/Privacy_Policy) · [OpenFreeMap](https://openfreemap.org/)

## 5. Calendar connections (optional)

- **Apple Calendar:** if you connect it, the App reads and adds events in the Calendar on your device.
- **Google Calendar / Outlook Calendar:** if you connect one, you sign in with that provider and the App can read and write events in your calendar. The data goes directly between your device and that provider; it does not pass through our servers. You can remove the App's access at any time in your Google or Microsoft account settings.

Links: [Google privacy policy](https://policies.google.com/privacy) · [Microsoft privacy statement](https://privacy.microsoft.com/privacystatement)

## 6. Household budget: exchange rates

The household budget tool can show exchange rates and market prices. Before it connects, the App asks you. The requests go to public rate services (such as open.er-api.com, Frankfurter, the European Central Bank, Binance, CoinGecko, Yahoo Finance, the US Treasury fiscal data service, and Vietnamese bank and gold price pages) and contain only the currencies or symbols requested, never your budget entries.

## 7. Mass time contributions

If you fill in the "contribute Mass times" form, what you type and the photo you attach are saved on your device and then handed to your own email app or to the system share sheet, with you choosing where to send it. The App does not upload the form by itself.

## 8. Advertising (Google AdMob)

The free version shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address
- a device ID, such as the advertising identifier
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps)
- crash logs and performance data

This data is used by Google for advertising, analytics and to improve the SDK. Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset your advertising identifier in your device settings.

Some tools and games offer an optional rewarded ad (for example, to get extra hints). Watching it is your choice.

Links: [Google privacy policy](https://policies.google.com/privacy) · [How Google uses data from partner apps](https://policies.google.com/technologies/partner-sites)

## 9. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renews automatically until you cancel). Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. While it is active, the App does not start the advertising SDK and shows no ads.

## 10. Notifications

Reminders you set — daily prayer times, solemnities, the saint of the day — are scheduled on your device and are not sent to us. You can turn them off in your device settings.

## 11. Permissions

| Permission | Why |
|---|---|
| Location (when in use) | Finding churches near you and showing directions. Optional. |
| Calendar | Read and add events after you connect a calendar. Optional. |
| Camera | Taking a photo of a Mass-time board for a contribution. Optional. |
| Photo library | Choosing or saving an image, and picking a backup file. Optional. |
| Tracking (iOS) | Personalised ads, only if you tap "Allow". |
| Notifications | Reminders you set. |

## 12. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 13. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 14. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
