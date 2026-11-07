---
# Chinese Calendar dùng layout "default" (KHÔNG "app-policy") như Caribbean / Xiangqi Clash: master-policy ghi
# "never share it with advertisers", sai với app này (Google AdMob).
# Mẫu bê từ caribbean/index.md. Nguồn từng ý (2026-11-07, anh Truc "publish"):
#  - tmk_chinese_calendar/lib/src/screens/privacy_app_screen.dart (màn Quyền riêng tư trong app: hasAccount false,
#    hosts googleads / data.weather.gov.hk / 1823.gov.hk (chỉ vùng HK) / open-meteo.com, dữ liệu lưu máy, .tmkbak AES-256-GCM PBKDF2)
#  - lib/src/services/hko_warning_service.dart:51 (data.weather.gov.hk weatherAPI, sửa 2026-11-07 vì www.hko.gov.hk trả 404), hk_holidays_remote.dart:35 (www.1823.gov.hk ical)
#  - lib/src/services/location_service.dart:35-40 (thành phố dự phòng theo vùng), lib/src/screens/today_screen.dart:62,110
#  - lib/src/services/calendar_sync_service.dart:18,37-40 (chỉ Apple Calendar; Google chưa có client id nên không hiện)
#  - lib/src/monetization/app_ads.dart (UMP, AdMob banner + rewarded), remove_ads.dart (gói 3 tháng tự gia hạn)
#  - ios/Runner/Info.plist (purpose strings: calendar, location, camera, photo library, microphone, tracking)
#  - package/tmk_weather_package (api / air-quality-api / geocoding-api.open-meteo.com, api.bigdatacloud.net)
#  - package/tmk_spendly_package spendly_rates_service.dart (tỷ giá, hỏi trước khi kết nối — như Caribbean)
#  - package/games/tmk_games xep_hinh/jigsaw/Utils/jigsaw_url_helper.dart:3 (ảnh xếp hình từ cdn.jsdelivr.net)
layout: default
permalink: /chinesecalendar/
title: "Chinese Calendar — Privacy Policy"
description: "Privacy policy for Chinese Calendar."
last_updated: 2026-11-07
app_name: Chinese Calendar
app_subtitle: Lunar almanac for China, Hong Kong, Macao and Taiwan
app_id: com.tmkgroup.chinesecalendar
data_collected: "No account. Events, diary, notes, family tree and budget stay on your device. Weather and Hong Kong warnings are fetched online. Google AdMob ads collect device data."
order: 131
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Chinese Calendar — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.chinesecalendar</code></span>
      <span>Effective date: 2026-11-07</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Chinese Calendar** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.
- The App has no analytics, no telemetry and no crash reporting of its own.

## 2. Information stored only on your device

The App saves on your device: your region, language, script and display settings, anniversaries, birthdays and personal events, diary entries (with optional photos and voice notes), notes and reminders, family tree data, household budget entries, and whether you have removed ads. This information is not sent to us. Uninstalling the App removes it. You can delete it at any time in **Profile → Privacy**.

You can export an encrypted backup file (`.tmkbak`, AES-256-GCM, key derived from a passphrase you choose with PBKDF2-SHA256). The file goes only where you save or share it; we never receive it.

## 3. Almanac, holidays and tools

The almanac, solar terms, public holidays and the divination and feng-shui tools are calculated on your device. They do not send what you enter (for example birth dates or names) anywhere.

## 4. Hong Kong region only

When Hong Kong is the selected region, the App downloads:

- weather warnings from the Hong Kong Observatory open data service (data.weather.gov.hk);
- the public holiday calendar from 1823 of the Hong Kong Government (www.1823.gov.hk).

These requests contain only the language of the data. Like any internet service, those servers receive your IP address in order to deliver the data.

## 5. Weather and location

The Today screen shows the weather from Open-Meteo (open-meteo.com). If you allow location access, the App uses your device coordinates for local sunrise and sunset times and sends them to Open-Meteo to get the local forecast and to BigDataCloud (bigdatacloud.net) to show the name of your place. If you do not allow location access, the App uses Beijing, Hong Kong, Macao or Taipei, depending on the region you selected.

- Open-Meteo terms and privacy: <https://open-meteo.com/en/terms>
- BigDataCloud privacy policy: <https://www.bigdatacloud.com/privacy-policy>

## 6. Calendar connection (optional)

If you connect Apple Calendar, the App reads and adds events in the Calendar on your device. This data stays on your device.

## 7. Household budget: exchange rates

The household budget tool can show exchange rates and market prices. Before it connects, the App asks you. The requests go to public rate services (such as open.er-api.com, Frankfurter, the European Central Bank, Binance, CoinGecko and Yahoo Finance) and contain only the currencies or symbols requested, not your budget entries.

## 8. Games

The games run on your device. The jigsaw puzzle downloads its pictures from cdn.jsdelivr.net; the request contains only the picture requested.

## 9. Advertising (Google AdMob)

The free version shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address
- a device ID, such as the advertising identifier
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps)
- crash logs and performance data

This data is used by Google for advertising, analytics and to improve the SDK. Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset your advertising identifier in your device settings.

Some tools offer an optional rewarded ad (for example, to unlock a reading or get more game hints). Watching it is your choice.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 10. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renews automatically until you cancel). Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. While it is active, the App does not start the advertising SDK.

## 11. Notifications

The daily almanac reminder and the reminders you set for anniversaries, events and notes are scheduled on your device and are not sent to us. You can turn them off in the App or in your device settings.

## 12. Permissions

| Permission | Why |
|---|---|
| Location (when in use) | Local sunrise and sunset times and the local weather forecast. Optional. |
| Calendar | Read and add events after you connect Apple Calendar. Optional. |
| Camera | Taking a photo for a diary entry. Optional. |
| Photo library | Adding a photo to a diary entry. Optional. |
| Microphone | Recording a voice note in a diary entry. Optional. |
| Tracking (iOS) | Personalised ads, only if you tap "Allow". |
| Notifications | The daily almanac reminder and the reminders you set. |

## 13. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 14. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 15. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
