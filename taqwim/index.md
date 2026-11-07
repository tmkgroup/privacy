---
# Taqwim dùng layout "default" (KHÔNG "app-policy"): master-policy ghi
# "never share it with advertisers", sai với app này từ khi gắn Google AdMob (2026-11-07).
# Nguồn từng ý (2026-11-07, anh Truc "publish"):
#  - tmk_taqwim/lib/ads/app_ads.dart (UMP consent, MobileAds.initialize, banner + rewarded, mã AdMob thật)
#  - tmk_taqwim/lib/ads/banner_ad_widget.dart · lib/ads/rewarded_ad_free.dart (AdFreeWindow 24 giờ)
#  - tmk_taqwim/lib/services/remove_ads_service.dart:40 (com.tmkgroup.taqwim.remove_ads_3m)
#  - tmk_taqwim/lib/providers/purchase_provider.dart:13-22 (taqwim_tip_small/medium/large, taqwim_supporter cũ)
#  - tmk_taqwim/lib/providers/mosque_provider.dart:38,297 + halal_provider.dart:40,294
#    (cdn-taqwim.tmkgroup.vn, overpass-api.de)
#  - tmk_taqwim/lib/screens/mosque_map_screen.dart:20,24 + lib/utils/map_style.dart (tiles.openfreemap.org,
#    tile.openstreetmap.org); package/tmk_map_kit/lib/src/map_server.dart:27 (map.tmkgroup.vn — chỉ tile VN)
#  - tmk_taqwim/lib/services/quran_service.dart + lib/screens/credits_screen.dart (verses.quran.com, tanzil.net)
#  - tmk_taqwim/android/app/src/main/AndroidManifest.xml (quyền; ACCESS_FINE_LOCATION bỏ 2026-11-07)
#  - tmk_taqwim/ios/Runner/Info.plist (purpose strings + NSUserTrackingUsageDescription)
#  - developers.google.com/admob/ios/privacy/data-disclosure (đọc 2026-11-06, bản ghi ở caribbean/index.md)
layout: default
permalink: /taqwim/
title: "Taqwim — Privacy Policy"
description: "Privacy policy for Taqwim, the Islamic calendar, prayer times and Qibla app."
last_updated: 2026-11-07
app_name: Taqwim
app_subtitle: Islamic Calendar & Prayer Times
app_id: com.tmkgroup.taqwim
data_collected: "No account. Prayer logs, notes, diary and Quran progress stay on your device. Mosque and halal search and Quran audio are fetched online. Google AdMob ads collect device data."
order: 10
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Taqwim — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.taqwim</code></span>
      <span>Effective date: 2026-11-07</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Taqwim** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.

## 2. Information stored only on your device

The App saves on your device: your language, theme and calculation settings, saved locations, prayer log and sunnah rakat counts, notes, diary entries, bookmarks, dua wall entries, sadaqah ledger, habit and Hajj checklists, Hayd cycle log, Quran reading and hifz progress, and whether you have removed ads. This information is not sent to us. Uninstalling the App removes it.

You can export an encrypted backup file (`.tmkbak`, AES-256-GCM, protected by a passphrase you choose). The file goes only where you save or share it; we never receive it. If you lose the passphrase, nobody can open the backup, including us.

## 3. Location

If you allow location access, the App reads your **approximate** position (Android `ACCESS_COARSE_LOCATION`; iOS "when in use") to compute prayer times and the Qibla direction, and to search for mosques and halal places near you. The coordinates are not sent to us. You can refuse location access and enter coordinates or pick a city by hand instead.

## 4. Mosques and halal places

- The App first asks our server **cdn-taqwim.tmkgroup.vn** for the ready-made list of mosques or halal places of a country; that request contains only the country code.
- If no list exists for your country, the App queries the public **Overpass API** (overpass-api.de, OpenStreetMap data) with the map area around you.
- Map images come from **tiles.openfreemap.org** and **tile.openstreetmap.org**. Inside Vietnam, map tiles and driving directions come from our own server **map.tmkgroup.vn**.

Like any internet service, these servers receive your IP address in order to answer. No identifier of you is sent.

## 5. Quran text and audio

The Quran text and the bundled translations ship inside the App (source: the Tanzil Project, tanzil.net) and need no connection. When you tap **Play** on a verse, the App downloads that one audio file from the public CDN **verses.quran.com** run by quran.com, and caches it on your device for offline replay. If you never tap Play, no audio request is made.

## 6. Advertising (Google AdMob)

The free version shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address
- a device ID, such as the advertising identifier
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps)
- crash logs and performance data

This data is used by Google for advertising, analytics and to improve the SDK. Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before ads are personalised. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App Tracking Transparency prompt. You can reset your advertising identifier in your device settings.

The ad SDK cannot see what you write in the App — your prayer log, notes, diary, dua wall entries and Quran progress are never passed to it. **No feature of the App is locked behind an ad.** There is one optional rewarded ad: watching it hides the banners for 24 hours. Watching it is your choice.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 7. Remove ads subscription

"Remove ads" (`com.tmkgroup.taqwim.remove_ads_3m`) is an optional subscription (3 months, renews automatically until you cancel). Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details, billing address or real name. While it is active, the App does not start the advertising SDK.

## 8. Tips

The App also offers optional one-time tips. They unlock nothing — every feature is free whether you tip or not. A one-time "Supporter" purchase sold up to version 1.4.2 is still honoured for its thank-you state; the 30-day prayer log it used to unlock is now free for everyone.

Refunds, receipts and purchase history are handled by Apple or Google under their own terms: [Apple](https://www.apple.com/legal/privacy/) · [Google](https://policies.google.com/privacy).

## 9. Notifications

Adhan, pre-prayer and iqamah reminders, suhoor and iftar, Tahajjud, Jumu'ah, the daily verse and hadith and eclipse alerts are scheduled by your own phone and work offline. Nothing about them is sent to us. You can turn them off in your device settings.

## 10. Permissions

| Permission | Why |
|---|---|
| Location (approximate, when in use) | Prayer times, Qibla, nearby mosques and halal places. Optional — you can enter a place by hand. |
| Camera | AR Qibla screen only. No image, video or frame is saved or transmitted. Optional. |
| Notifications | The prayer and reminder alerts you set. |
| Exact alarm (Android 12+) | So prayer notifications fire at the exact minute. |
| Boot completed (Android) | Re-arms scheduled prayer notifications after a reboot. |
| Vibrate | Tasbih counter feedback. |
| Photo library (iOS) | Choosing a backup file to import. |
| Tracking (iOS) | Personalised ads, only if you tap "Allow". |

You can revoke any permission in your device settings at any time; the App keeps working with reduced features.

## 11. Data retention

- On-device data: kept until you delete it in **Settings → Reset all data** or uninstall the App.
- We hold no copy of your data, so there is nothing for us to retain or delete.

## 12. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 13. Your rights

- **Access**: open the App; the in-app data is the whole record.
- **Export**: the encrypted backup in Settings.
- **Delete**: "Reset all data" in Settings, or uninstall.
- **Correct**: edit any field on the relevant screen.
- **Object / restrict**: revoke permissions in your device settings; decline ad personalisation in the consent screen.

## 14. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 15. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
