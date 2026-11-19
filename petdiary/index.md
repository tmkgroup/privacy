---
# Pet Diary dung layout "default" nhu Garden Log / Scan Doc: app co Google AdMob.
# Nguon tung y (2026-11-16, doc code that cua E:/Onsite/flutter/tmk_pet):
#  - lib/ads/app_ads.dart (UMP consent, banner + quang cao co thuong, ma AdMob that)
#  - lib/ads/rewarded_ad_free.dart (xem quang cao co thuong -> tat quang cao 24 gio)
#  - lib/core/services/remove_ads_service.dart (goi com.tmkgroup.pet.remove_ads_1m, 1 thang)
#  - lib/core/storage/hive_service.dart (hop Hive ma hoa AES-256, khoa trong Keystore / Keychain; CHI tren may)
#  - lib/core/services/backup_service.dart:6-7,85 (PBKDF2-HMAC-SHA256 100 000 vong -> AES-256-CBC)
#  - lib/core/services/notification_service.dart (nhac do chinh may hen gio)
#  - lib/features/clinics|shops/screens/*.dart (geo: / tel: / website mo ra app khac)
#  - lib/features/pets/screens/pet_detail_screen.dart (Chia se so suc khoe = share sheet he thong)
#  - ios/Runner/Info.plist + android/app/src/main/AndroidManifest.xml (quyen)
# 2026-11-20 (Claude, anh "nop duyet di" Apple): them CDN (lib/features/breed_ai/breed_model_store.dart,
#  lib/features/learn/learn_content_store.dart), micro (lib/features/learn/emotion_screen.dart: startStream PCM,
#  khong ghi file), thoi tiet (tmk_weather_package open_meteo_datasource.dart: api.open-meteo.com,
#  geocoding-api.open-meteo.com, du phong api.bigdatacloud.net; LocationAccuracy.medium).
layout: default
permalink: /petdiary/
title: "Pet Diary — Privacy Policy"
description: "Privacy policy for Pet Diary: pet records, feeding, weight, vaccinations, vet visits, reminders and expenses."
last_updated: 2026-11-20
app_name: "Pet Diary"
app_subtitle: "Pet Care Records"
app_id: com.tmkgroup.pet
data_collected: "No account. Your pets, photos, sounds and records stay on your device. Weather uses approximate location only when you open it. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 141
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Pet Diary — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.pet</code></span>
      <span>Effective date: 2026-11-20</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Pet Diary** ("the App"), published by
**TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Your pets' records stay on your phone. We run no server for this App and we collect nothing.**

There is no account and no sign-in. Pet profiles, photos, meals, food stock, weights, vaccinations,
vet visits, appointments, care logs, breeding records, litters, purchases, transfers, expenses and
reminders are written to an encrypted database inside the App's own folder on your device. If you
uninstall the App, all of it goes with it; we cannot recover anything for you, because no copy ever
reached us.

These things use the network, and none of them carries your pet records:

1. **Google AdMob ads** — free tier only (section 5).
2. **Apple App Store / Google Play** — only when you buy or restore the Remove ads subscription.
3. **Our download server** (`cdn-pet.tmkgroup.vn`) — recognition models and the lessons, body-language
   guide and cat pain scale are downloaded the first time you open those features (section 7a).
4. **Weather** — only when you open the Weather screen (section 7b).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We never ask for your name, email address or phone number.
- We have no way to identify you, to see your records, or to know that you exist as a user.

## 3. What stays on your device

| What | Where it lives |
|------|----------------|
| Pet profiles and photos | The App's encrypted database and folder on your device |
| Meals, food stock, weights | Same |
| Vaccinations, deworming, vet visits, medicines and other health notes you type in | Same |
| Clinics, shops, appointments, purchases | Same |
| Breeding records, litters, sale / adoption records | Same |
| Expenses and reminders | Same |
| Settings, theme, language, weight unit | Your device's app preferences |
| Backup files (`.tmkbak`) you export yourself | Where you choose to put them |

The database is encrypted with AES-256; its key is kept in your phone's secure key store (Android
Keystore / iOS Keychain).

Reminders are scheduled **by your own phone**. There is no push server, so no reminder of yours
passes through us.

Backups are encrypted on your device with a password **you** type (PBKDF2-HMAC-SHA256 with 100,000
rounds for the key, AES-256-CBC for the data). We never see the password or the file. If you lose the
password, the backup cannot be opened — not by you and not by us.

Health entries (vaccines, medicines, diagnoses, due dates) are **copied by you** from what your
veterinarian tells you. The App does not suggest medicines, doses, vaccine schedules or diagnoses.

## 4. Opening other apps

Buttons on a clinic or a shop hand the address, phone number or website **you entered** to another
app on your phone — your map app, your phone dialer or your browser. That app's own policy applies
from then on. Pet Diary itself does not contact any map, phone or web service.

## 5. Ads (free tier)

The free tier shows **Google AdMob** banners, and a **rewarded** ad you can choose to watch to turn
ads off for 24 hours. When an ad loads, Google AdMob receives the standard ad-request data: device
language, coarse location derived from your IP address, device model, app version, and the
advertising identifier where the operating system provides one.

- Before any ad loads, the App shows **Google's consent message (UMP)** where the law requires it
  (EEA, UK, Switzerland), and **Ad privacy options** in Settings lets you change your answer at any
  time.
- On iOS, the same Google consent flow may ask for **App Tracking Transparency** permission. If you
  decline, iOS does not hand your advertising identifier (IDFA) to AdMob.
- Google's own list of what its advertising SDK collects:
  <https://developers.google.com/admob/ios/privacy/data-disclosure>

**Subscribers see no ads at all**, so no ad request is sent.

## 6. No analytics, no tracking, no profiling

The App contains **no** analytics SDK, **no** crash reporter and **no** attribution SDK: no Firebase
Analytics, no Crashlytics, no Sentry, no Mixpanel, no AppsFlyer, no Facebook SDK. We do not build a
profile of you, we do not track you across apps or websites, and we sell nothing to anybody —
we hold nothing to sell.

## 7. Photos and sharing

The photo library is used only when you choose a picture for a pet, a vaccination, a vet visit or a
care log. The picture you pick is copied into the App's own folder; the App never scans your library
and never uploads a photo on its own.

The App shares something only when **you** tap share or export (a `.tmkbak` backup or the pet health
card as text). It then goes wherever you send it, under that app's own policy.

## 7a. Downloads, photo and sound recognition

The first time you open breed recognition, mood recognition from a photo or a sound, lessons, the
body-language guide or the cat pain scale, the App downloads the files it needs from
`cdn-pet.tmkgroup.vn`. The request carries nothing about you or your pets; like any web request, our
CDN (Cloudflare) sees your IP address to send the file back. After that, these features work offline.

- **Photos** you pick for recognition are analysed **on your phone**; they are never uploaded.
- **Sound** recognition uses the microphone **only while you tap Record** (at most a few seconds). The
  sound is analysed on your phone in memory, is not saved to a file and is never uploaded.

## 7b. Weather and approximate location

The Weather screen shows the forecast for your current area or for places you add. When you choose
"My location", the App asks for **approximate location** (it never asks for precise location) and
sends the coordinates to **Open-Meteo** (`api.open-meteo.com`) to get the forecast and the place name
(`geocoding-api.open-meteo.com`; if that fails, `api.bigdatacloud.net`). Places you add are searched
by the name you type. Nothing else about you is sent, and we do not receive or store your location.
Saved places, the daily weather reminder and units stay in the App on your device.
Their policies: [Open-Meteo](https://open-meteo.com/en/terms) ·
[BigDataCloud](https://www.bigdatacloud.com/privacy-policy)

You can deny location access and still use Weather by adding a place by name.

## 8. Subscription

One auto-renewing subscription, **Remove ads** (`com.tmkgroup.pet.remove_ads_1m`), billed monthly,
turns off all ads. It is handled entirely by Apple or Google: we never see your payment details.
Manage or cancel it in your App Store or Google Play subscription settings; cancelling takes effect at
the end of the paid period. Terms of Use: Apple's standard EULA,
<https://www.apple.com/legal/internet-services/itunes/dev/stdeula/>.

## 9. Children

The App is a pet-care record book for general audiences and is not directed to children under 13. We
do not knowingly collect anything from a child — in fact we collect nothing from anybody.

## 10. Your rights

Because we hold no data about you, there is nothing for us to export, correct or delete on your
behalf. You are in full control:

- **Delete everything** — uninstall the App, or delete individual pets and records in the App.
- **Take your data with you** — export an encrypted `.tmkbak` backup from Settings.
- **Change your ad consent** — Settings → Ad privacy options (where the law requires the form).
- **Turn off ads** — subscribe to Remove ads, or watch a rewarded ad for 24 ad-free hours.

Their own policies apply to: [Google](https://policies.google.com/privacy) ·
[Apple](https://www.apple.com/legal/privacy/)

## 11. Changes

If this policy changes, the date at the top of this page changes with it and the new text appears
here. Material changes will also be noted in the App's release notes.

## 12. Contact

**TMK Tech Group** — <tmktechgroup@gmail.com>

Support page: [Pet Diary — Support](/petdiary/support/)

</div>
</article>
