---
# Photo Editor Pro (tmk_photo) — layout "default" như scandoc/index.md (app có Google AdMob).
# Khung + mục 5, 6 chép scandoc/index.md của repo này (2026-11-27). Nguồn từng ý:
#  - tmk_photo/lib/ads/app_ads.dart (UMP consent, khởi động SDK sau khi đồng ý; KHÔNG ATT)
#  - tmk_photo/lib/ads/banner_ad_widget.dart (banner đáy trang chủ), lib/ads/rewarded_ad_free.dart (quảng cáo có thưởng)
#  - tmk_photo/lib/services/remove_ads_service.dart (gói com.tmkgroup.tmkphoto.remove_ads_3m, 3 tháng)
#  - tmk_photo/ios/Runner/Info.plist (NSCameraUsageDescription, NSPhotoLibraryUsageDescription,
#    NSPhotoLibraryAddUsageDescription; không NSUserTrackingUsageDescription)
#  - tmk_photo/android/app/src/main/AndroidManifest.xml (CAMERA, READ_MEDIA_IMAGES, READ/WRITE_EXTERNAL_STORAGE cũ)
#  - tmk_photo/pubspec.yaml (không có http / dio / firebase / analytics / crash reporter)
layout: default
permalink: /photoeditor/
title: "Photo Editor Pro — Privacy Policy"
description: "Privacy policy for Photo Editor Pro: photo editor, collage maker and image converter."
last_updated: 2026-11-27
app_name: "Photo Editor Pro"
app_subtitle: "Photo editor and collage maker"
app_id: com.tmkgroup.tmkPhoto
data_collected: "No account. Your photos stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 46
---

<article class="app-policy">
  <header class="app-header">
    <h1>Photo Editor Pro — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.tmkPhoto</code> (iOS) · <code>com.tmkgroup.tmk_photo</code> (Android)</span>
      <span>Effective date: 2026-11-27</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Photo Editor Pro** ("the App"), published by **TMK Tech Group**
("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Your photos stay on your device. We run no server and we collect nothing.**

There is no account, no sign-in, no analytics SDK, no crash reporter and no backend of ours. Photos you open,
edit, combine into a collage or convert are processed on your phone. The only network use is **Google's
advertising SDK** (section 4), and it never receives your photos.

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.
- We have no way to identify you or see your photos.

## 3. What is stored on your device

- edited photos, collages and converted images are saved to your photo library only when you tap Save;
- temporary files the App needs while editing, kept in the App's own folder;
- your settings, including the end time of a 24-hour ad-free window if you watched a rewarded ad, and whether
  the Remove ads subscription is active.

This data is never uploaded to us.

### Permissions

| Permission | Why |
|---|---|
| Camera | Only when you tap Take photo to capture a picture to edit. |
| Photo library (read) | To show your recent photos on the home screen and to open the pictures you choose. |
| Photo library (add) | Only when you tap Save to put an edited photo into your library. |

You can revoke any permission in your device settings at any time. The App keeps working with fewer features.

## 4. Advertising (Google AdMob)

The free version shows a banner at the bottom of the home screen and offers an optional rewarded ad, using the
Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your
photos** — they are not available to the SDK. The App does not ask for Apple's App Tracking Transparency
permission and does not track you across other companies' apps.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before
ads are personalised, and you can change your choice at any time with the "Ad privacy options" button in
Settings. You can reset or delete your advertising ID in your device settings.

The **rewarded ad** is never forced: you tap it yourself in Settings to turn ads off for 24 hours. Nothing in
the App is locked behind it — every editing, collage and conversion tool is free whether or not you watch an ad.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 5. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renewing automatically until you cancel it in your store
account settings). Payment is handled entirely by the Apple App Store or Google Play; **we never receive your
payment details**. While the subscription is active the App does not start the advertising SDK at all, so none
of the data in section 4 is collected.

## 6. Sharing

When you tap Share, the App opens the standard system share sheet. Whatever you send goes where you direct
it, not to us.

## 7. Data retention

Photos you saved stay in your photo library until you delete them. Temporary files and settings are removed
when you uninstall the App. There is no off-device data held by us.

## 8. Children

Photo Editor Pro is not directed to children under 13. Because we collect no personal data and operate no
server, we do not knowingly collect data from children under 13, or 16 in the EU.

## 9. Your rights

Your photos and settings live on your device, so you control them directly: delete photos in your library,
revoke permissions in your device settings, or uninstall the App to remove everything it stored.

You may also contact tmktechgroup@gmail.com with any question.

## 10. Changes to this policy

We will update the "Effective date" above and ship a new app version whenever this policy changes.

</div>
</article>
