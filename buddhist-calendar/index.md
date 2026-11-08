---
# Buddhist Calendar+ dùng layout "default" (KHÔNG "app-policy") như Caribbean Calendar:
# master-policy ghi "never share it with advertisers", sai với app này (Google AdMob).
# Nguồn từng ý (2026-11-08, anh Truc "publish"):
#  - tmk_buddhist_calendar/lib/app/ads/app_ads.dart (UMP consent, AdMob banner + rewarded)
#  - tmk_buddhist_calendar/lib/app/premium/remove_ads.dart (com.tmkgroup.buddhistcalendar.remove_ads_3m)
#  - tmk_buddhist_calendar/ios/Runner/Info.plist (purpose strings: location, calendar, photo library, tracking)
#  - tmk_buddhist_calendar/lib/app/spendly_host.dart (TmkStorage 'tmk_buddhist_calendar', sổ Thu chi của cả app)
#  - tmk_buddhist_calendar/lib/countries/nepal/src/services/calendar_sync_service.dart +
#    sync_oauth_config.dart (Google/Outlook còn placeholder → chỉ Apple Calendar trên iOS)
#  - package/tmk_weather_package (api/air-quality-api/geocoding-api.open-meteo.com, api.bigdatacloud.net)
#  - package/tmk_spendly_package spendly_rates_service.dart (open.er-api.com, Frankfurter, ECB, Binance,
#    CoinGecko, fiscaldata.treasury.gov — hỏi trước khi nối mạng)
#  - package/tmk_giapha_offline (ảnh thành viên gia phả qua image_picker)
#  - developers.google.com/admob/ios/privacy/data-disclosure (đọc 2026-11-06)
layout: default
permalink: /buddhist-calendar/
title: "Buddhist Calendar+ — Privacy Policy"
description: "Privacy policy for Buddhist Calendar+."
last_updated: 2026-11-08
app_name: Buddhist Calendar+
app_subtitle: Buddhist calendars of seven countries
app_id: com.tmkgroup.buddhistcalendar
data_collected: "No account. Diary, notes, events, budget and family tree stay on your device. Weather and exchange rates are fetched online when you ask. Google AdMob ads collect device data."
order: 140
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Buddhist Calendar+ — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.buddhistcalendar</code></span>
      <span>Effective date: 2026-11-08</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Buddhist Calendar+** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App covers the Buddhist calendars of Thailand, Laos, Myanmar, Cambodia, Bhutan, Mongolia and Nepal. The App is not directed to children under 13.

## 1. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.

## 2. Information stored only on your device

The App saves on your device: the country you chose, your language, theme and text-size settings, personal events, diary entries, notes, reminders, household budget entries, family tree entries (names, dates and any photo you pick) and whether you have removed ads. This information is not sent to us. Uninstalling the App removes it.

You can export an encrypted backup file (`.tmkbak`, AES-256-GCM, protected by a passphrase you choose). The file goes only where you save or share it; we never receive it.

## 3. Calendar data

Lunar dates, Buddhist holy days, public holidays and almanac data for the seven countries are built into the App. Opening the calendar does not contact us.

## 4. Weather and location

The weather tool gets forecasts and air quality from Open-Meteo (open-meteo.com). If you allow location access, the App sends your device coordinates to Open-Meteo to get the local forecast and to BigDataCloud (bigdatacloud.net) to show the name of your place. If you do not allow location access, the App uses a default city for the country you chose. Location is used only for the weather and for sunrise and sunset times.

- Open-Meteo terms and privacy: <https://open-meteo.com/en/terms>
- BigDataCloud privacy policy: <https://www.bigdatacloud.com/privacy-policy>

## 5. Device calendar (optional)

On iPhone and iPad, the Nepal calendar can show events from the Calendar app and add events to it, after you allow calendar access. This happens on your device; the events are not sent to us.

## 6. Household budget: exchange rates

The household budget tool can show exchange rates and market prices. Before it connects, the App asks you. The requests go to public rate services (open.er-api.com, Frankfurter, the European Central Bank, the US Treasury fiscal data service, Binance and CoinGecko) and contain only the currencies or symbols requested, never your budget entries.

## 7. Advertising (Google AdMob)

The free version shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address
- a device ID, such as the advertising identifier
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps)
- crash logs and performance data

This data is used by Google for advertising, analytics and to improve the SDK. Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset your advertising identifier in your device settings.

Ads appear on the Tools and Games tabs and on screens opened from them. A game can offer you an optional rewarded ad for extra hints; watching it is your choice. No calendar feature is locked behind an ad.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 8. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renews automatically until you cancel). Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. While it is active, the App does not start the advertising SDK.

## 9. Notifications

Reminders you set — notes, personal events, holy-day and holiday alerts — are scheduled on your device and are not sent to us. You can turn them off in your device settings.

## 10. Permissions

| Permission | Why |
|---|---|
| Location (when in use) | Local weather, sunrise and sunset. Optional. |
| Calendar | Show and add events in the device Calendar, after you connect it. Optional. |
| Photo library | Choosing a photo for a family tree member, or a backup file. Optional. |
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
