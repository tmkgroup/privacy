---
# Medimo dùng layout "default" như Fincore / Scan Doc: app có Google AdMob nên KHÔNG dùng master-policy ("never share it with advertisers").
# Tạo 2026-11-12 (anh Truc "Tạo GDPR 5 app" — ô GDPR trên AdMob bắt buộc URL chính sách, Medimo chưa có trang).
# Nguồn từng ý:
#  - mục 3, 4 (HealthKit), 6 (chia sẻ gia đình), 7 (sao lưu), BLE, Children, Your rights, email liên hệ:
#    bê ý bản trong app tmk_medimo/lib/features/legal/data/legal_content.dart:109-175 (en)
#  - bảng Permissions: tmk_medimo/android/app/src/main/AndroidManifest.xml + ios/Runner/Info.plist (các khoá NS*UsageDescription)
#  - mục 5 (tìm nơi gần + bản đồ): tmk_medimo/lib/features/find_nearby/services/overpass_service.dart:47-55,
#    package/tmk_map_kit/lib/src/map_server.dart:27-69, find_nearby/models/nearby_place_model.dart:27 (link Google Maps)
#  - OCR phiếu xét nghiệm trên máy: tmk_medimo/pubspec.yaml (google_mlkit_text_recognition, ghi chú "offline")
#  - mục 8 + 9 (quảng cáo, gói Bỏ quảng cáo): tmk_medimo/lib/ads/*.dart, lib/core/services/remove_ads_service.dart:37
#    (com.tmkgroup.medimo.remove_ads_3m), rewarded_ad_free.dart:33 (24 giờ); câu chữ danh sách dữ liệu SDK bê từ fincore/index.md mục 5
layout: default
permalink: /medimo/
title: "Medimo — Privacy Policy"
description: "Privacy policy for Medimo, the local-first family health record."
last_updated: 2026-11-12
app_name: Medimo
app_subtitle: Family Health Records
app_id: com.tmkgroup.medimo
data_collected: "No account. Your health records stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 31
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Medimo — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.medimo</code></span>
      <span>Effective date: 2026-11-12</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Medimo** ("the App"), published by **TMK Tech Group**
("we", "us"), handles information.

## 1. In short

**Your health data is sensitive. Medimo is built local-first: your records stay on your device unless you
choose to back them up.** Medimo does not send your health data to our servers.

Four things use the network, and none of them carries a health record of yours: **Google's advertising SDK**
(section 8), the **store** when you buy or restore the Remove ads subscription (section 9), the **find
nearby** search and its map (section 5), and links you tap that open Google Maps or another app.

## 2. No account

- The App has no account and no sign-in to our servers.
- There is no server account to delete.

## 3. What is stored on your device

Profiles (name, date of birth, contact, optional photo), medical records, vaccines, vitals, medications,
wellness logs (activity, water, sleep, nutrition, mood, cycle, growth), appointments, documents, allergies
and settings. All of this lives in an encrypted Hive store on your device.

Text recognition of a lab report you photograph runs on your device (Google ML Kit text recognition); the
photo is not uploaded by the App.

### Permissions

| Permission | Why Medimo needs it |
|---|---|
| Notifications, exact alarm, boot completed, vibrate, wake lock (Android) | Locally-scheduled medication and appointment reminders, re-armed after a reboot. |
| Camera | Scanning a family-sharing QR code and photographing a lab report or document. |
| Photo library (iPhone and iPad) | Picking a profile photo or a document image you choose. |
| Location (while in use) | Finding hospitals, pharmacies and clinics near you, and filling a clinic's position. |
| Bluetooth | Reading a blood pressure monitor, glucometer or scale you pair. |
| Health (Apple HealthKit / Health Connect) | Reading and writing the health data types you allow. |
| Face ID | Locking the App with your device's biometrics. |
| Tracking (iPhone and iPad) | Personalised ads, only if you tap "Allow" on Apple's prompt. |

You can revoke any permission in your device settings at any time. The App keeps working with fewer features.

## 4. Health platform integration (optional)

If you enable Apple HealthKit, Google Fit or Health Connect, Medimo reads/writes data only with your explicit
permission per data type. You can revoke this in your device settings at any time. Data syncs directly
between your device and the platform — never through Medimo servers. Health platform data is never used for
advertising and is never shared with the advertising SDK.

## 5. Find nearby and maps

When you search for hospitals, pharmacies or clinics nearby, the App sends the map position of the search
(latitude, longitude and radius) — no name, profile or health record — to these services, in this order until
one answers: overpass.tmkgroup.vn (our relay of OpenStreetMap data), overpass-api.de and
overpass.kumi.systems. Results are cached on your device.

The map is drawn from map.tmkgroup.vn inside Vietnam and tiles.openfreemap.org elsewhere. Directions and
clinic links open Google Maps in your browser or the Google Maps app. Each of these services sees an ordinary
web request (including your IP address) under its own privacy policy.

## 6. Family sharing (optional)

You can export profiles to a QR code or file and share them with family members. The transfer happens
device-to-device or via a channel you choose (email, messaging). Medimo is not in the middle.

## 7. Backups and Bluetooth devices

When you create a backup, the file is saved to your device storage or a location you pick (cloud drive, USB,
share sheet). Protecting that backup is your responsibility.

When you connect a BLE device (blood pressure monitor, glucometer, scale), readings are stored locally as vital
records. The pairing data stays on your device.

## 8. Advertising (Google AdMob)

The free version shows a banner and offers an optional rewarded ad, using the Google Mobile Ads SDK (Google
AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your
profiles, medical records, vitals, medications or any other health record** — those are not available to the
SDK.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before
ads are personalised, and you can change your choice at any time with the "Ad privacy options" button in
the Profile tab. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's
App Tracking Transparency prompt. You can reset or delete your advertising ID in your device settings.

The **rewarded ad** is never forced: you tap it yourself in the Profile tab to turn ads off for 24 hours.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 9. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renewing automatically until you cancel it in your store
account settings). Payment is handled entirely by the Apple App Store or Google Play; **we never receive your
payment details**. While the subscription is active the App does not start the advertising SDK at all, so none
of the data in section 8 is collected.

## 10. Children

Profiles for minors are managed by you, the parent or guardian. Medimo does not knowingly collect information
from children — all data is entered by you on your device.

## 11. Your rights (GDPR / CCPA / LGPD)

You have the right to access, correct, export and delete your data. Because data is on your device, you can do
all of this yourself: export from Backup, delete profiles or uninstall the app. There is no server account to
delete.

Questions about privacy: [trucmn@gmail.com](mailto:trucmn@gmail.com)

## 12. Changes to this policy

We will update the "Effective date" above and ship a new app version whenever this policy changes.

</div>
</article>
