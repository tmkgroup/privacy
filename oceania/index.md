---
# 2026-11-08 (anh Truc "publish"): bê nguyên south-east-europe/index.md (CÙNG vỏ
# tmk_country_calendar_shell, cùng bộ quyền, cùng layout "default"). Khác đúng 1 chỗ, đã đối chiếu code
# app này: app NÀY hỏi App Tracking Transparency và dùng IDFA (ios/Runner/Info.plist CÓ
# NSUserTrackingUsageDescription + thông báo IDFA "Oceania Calendar IDFA" đã xuất bản trên AdMob —
# tmk_oceania_calendar/cau_truc.md mục 3.Q) → mục Quảng cáo lấy lại câu của caribbean/index.md và
# bảng quyền có dòng "Tracking (iOS)".
# Nguồn từng ý (2026-11-08, anh Truc "publish"):
#  - tmk_oceania_calendar/lib/main.dart (ShellConfig: adBanner, rewardGate, gameHintReward,
#    removeAdsProductId; KHÔNG khai googleClientId* → chỉ nối Apple Calendar)
#  - tmk_oceania_calendar/lib/ads/app_ads.dart (UMP consent, AdMob banner + rewarded)
#  - tmk_oceania_calendar/ios/Runner/Info.plist (purpose strings: tracking, location, calendar, motion,
#    photo library)
#  - KHÔNG có Giờ cầu nguyện / Qibla: không module nước nào khai `prayer` (lib/countries/*/module.dart);
#    mục 'Motion' vẫn giữ vì la bàn nằm trong khung chung
#  - package/calendar/tmk_country_calendar_shell/lib/src/pages/profile_page.dart (Data & Privacy trong app)
#  - package/tmk_weather_package open_meteo_datasource.dart · package/tmk_spendly_package spendly_rates_service.dart
#  - developers.google.com/admob/ios/privacy/data-disclosure
layout: default
permalink: /oceania/
title: "Oceania Calendar — Privacy Policy"
description: "Privacy policy for Oceania Calendar."
last_updated: 2026-11-08
app_name: Oceania Calendar
app_subtitle: Public holidays of Oceania and the Pacific
app_id: com.tmkgroup.oceaniacalendar
data_collected: "No account. Notes, diary and budget stay on your device. Weather and holiday updates are fetched online. Google AdMob ads collect device data."
order: 135
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Oceania Calendar — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.oceaniacalendar</code></span>
      <span>Effective date: 2026-11-08</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Oceania Calendar** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.

## 2. Information stored only on your device

The App saves on your device: your country, language and display settings, personal events, diary entries, notes, reminders, household budget entries, and whether you have removed ads. This information is not sent to us. Uninstalling the App removes it.

You can export an encrypted backup file (`.tmkbak`, AES-256-GCM, protected by a passphrase you choose). The file goes only where you save or share it; we never receive it.

## 3. Holiday updates

To keep public-holiday dates current, the App downloads holiday correction files for the selected country from our server at world-calendar.tmkgroup.vn. The request contains only the country and year. Like any internet service, the server receives your IP address in order to deliver the file.

## 4. Weather and location

The weather tool gets forecasts and air quality from Open-Meteo (open-meteo.com). If you allow location access, the App sends your device coordinates to Open-Meteo to get the local forecast and to BigDataCloud (bigdatacloud.net) to show the name of your place. If you do not allow location access, the App uses the capital city of the selected country. Location is used only for the weather.

- Open-Meteo terms and privacy: <https://open-meteo.com/en/terms>
- BigDataCloud privacy policy: <https://www.bigdatacloud.com/privacy-policy>

## 5. Calendar connections (optional)

- **Apple Calendar:** if you connect it, the App reads and adds events in the Calendar on your device.

## 6. Household budget: exchange rates

The household budget tool can show exchange rates and market prices. Before it connects, the App asks you. The requests go to public rate services (such as open.er-api.com, Frankfurter, the European Central Bank, Binance, CoinGecko and Yahoo Finance) and contain only the currencies or symbols requested, not your budget entries.

## 7. Advertising (Google AdMob)

The free version shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address
- a device ID, such as the advertising identifier
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps)
- crash logs and performance data

This data is used by Google for advertising, analytics and to improve the SDK. Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised; you can change your answer later from the ad privacy settings inside the App.

On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset your advertising identifier in your device settings.

Some tools offer an optional rewarded ad (for example, to unlock a Tarot reading or get more game hints). Watching it is your choice.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 8. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renews automatically until you cancel). Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. While it is active, the App does not start the advertising SDK.

## 9. Notifications

Reminders you set are scheduled on your device and are not sent to us. You can turn them off in your device settings.

## 10. Permissions

| Permission | Why |
|---|---|
| Location (when in use) | Local weather forecast. Optional. |
| Calendar | Read and add events after you connect Apple Calendar. Optional. |
| Motion | Compass tool. |
| Photo library | Choosing a file in the household budget backup screen. |
| Tracking (iOS) | Personalised ads, only if you tap "Allow". |
| Notifications | Reminders you set. |

## 11. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 12. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 13. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
