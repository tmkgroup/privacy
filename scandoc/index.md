---
# Scan Doc dùng layout "default" (KHÔNG "app-policy") như Caribbean Calendar / Xiangqi Clash:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app này từ 2026-11-07
# (app đã gắn Google AdMob).
# Nguồn từng ý (2026-11-07):
#  - tmk_scan_doc/lib/ads/app_ads.dart (UMP consent, khởi động SDK sau khi đồng ý)
#  - tmk_scan_doc/lib/ads/banner_ad_widget.dart (banner), lib/ads/rewarded_ad_free.dart (quảng cáo có thưởng)
#  - tmk_scan_doc/lib/services/remove_ads_service.dart (gói com.tmkgroup.scandoc.remove_ads_3m, 3 tháng)
#  - tmk_scan_doc/ios/Runner/Info.plist (NSCameraUsageDescription, NSPhotoLibraryUsageDescription,
#    NSUserTrackingUsageDescription, GADApplicationIdentifier)
#  - tmk_scan_doc/android/app/src/main/AndroidManifest.xml (không khai uses-permission nào)
#  - tmk_scan_doc/pubspec.yaml (không có http / dio / firebase / analytics / crash reporter)
#  - package/tmk_scan_doc_package/lib/tmk_scan_doc_package.dart (ML Kit trên máy: quét, OCR)
#  - developers.google.com/admob/ios/privacy/data-disclosure (danh sách dữ liệu SDK quảng cáo thu,
#    bê qua caribbean/index.md mục 7 của repo này)
layout: default
permalink: /scandoc/
title: "Scan Doc — Privacy Policy"
description: "Privacy policy for Scan Doc: document scanner, OCR and PDF toolkit."
last_updated: 2026-11-07
app_name: "Scan Doc"
app_subtitle: "PDF Scanner and OCR"
app_id: com.tmkgroup.scandoc
data_collected: "No account. Scans, text and PDF files stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 45
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Scan Doc — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.scandoc</code></span>
      <span>Effective date: 2026-11-07</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Scan Doc** ("the App"), published by **TMK Tech Group**
("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Everything you scan stays on your device. We run no server and we collect nothing.**

There is no account, no sign-in, no analytics SDK, no crash reporter and no backend of ours. Pages you scan,
the text that recognition produces, the PDF, Word and Markdown files the App writes, your signature and your
watermarks all stay in Scan Doc's own folder on your phone. If you uninstall the App, every byte of that is
gone with it; we cannot recover anything for you, because no copy ever left your device.

Two things do use the network, and neither carries a document of yours: **Google's advertising SDK**
(section 5), and the **translation language pack** Google downloads the first time you translate into a
language (section 4).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.
- We have no way to identify you, see what you scan, or know that you exist as a user.

## 3. What is stored on your device

Inside Scan Doc's own application folder and settings:

- the page images the scanner produced, and pictures you imported;
- the recognised text for each document;
- document records in a local database (name, date, page list);
- files the App writes for you: PDF, Word, Markdown, page images, your signature, watermarked pages;
- your settings: light or dark mode, accent colour, app language, writing system for text recognition, and
  the end time of a 24-hour ad-free window if you watched a rewarded ad.

This data is never uploaded to us.

### Permissions

| Permission | Why |
|---|---|
| Camera | Only while you are scanning a document or an ID card. Deny it and the rest of the App still works. |
| Photo library | Only when you tap Import images and pick pictures yourself. |
| Files you pick | One at a time through the system file picker, when you choose a PDF or image for the PDF tools. The App never browses your storage on its own. |
| Tracking (iPhone and iPad) | Personalised ads, only if you tap "Allow" on Apple's prompt. |

You can revoke any permission in your device settings at any time. The App keeps working with fewer features.

## 4. Text recognition and translation (Google ML Kit, on your device)

**Google ML Kit** does three jobs in the App: the document scanner that finds the edges of the page on
Android, text recognition for Latin, Chinese, Devanagari, Japanese and Korean script, and translation of the
recognised text. On iPhone and iPad the scanner is Apple's own document camera (VisionKit), which runs on the
device.

ML Kit does its work on your device: page images and recognised text are **not** sent to Google for
processing. Two things travel over the network, both triggered by you — the translation language pack
download, once per language, and on Android the scanning and recognition components themselves, which Google
Play services fetches onto the phone the first time they are used. Those requests go to Google under Google's
own privacy policy. They carry no document of yours.

- Google's privacy policy: <https://policies.google.com/privacy>

## 5. Advertising (Google AdMob)

The free version shows a banner at the bottom of the screen and offers an optional rewarded ad, using the
Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your
documents, your scans or the recognised text** — those are not available to the SDK.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before
ads are personalised, and you can change your choice at any time with the "Ad privacy options" button in
Settings. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App
Tracking Transparency prompt. You can reset or delete your advertising ID in your device settings.

The **rewarded ad** is never forced: you tap it yourself in Settings to turn ads off for 24 hours. Nothing in
the App is locked behind it — scanning, text recognition, translation, export and every PDF tool are free
whether or not you watch an ad.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 6. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renewing automatically until you cancel it in your store
account settings). Payment is handled entirely by the Apple App Store or Google Play; **we never receive your
payment details**. While the subscription is active the App does not start the advertising SDK at all, so none
of the data in section 5 is collected.

## 7. Sharing

When you tap Share, the App opens the standard system share sheet. Whatever you send goes where you direct
it, not to us. A file you saved or shared elsewhere stays wherever you put it, for as long as you keep it;
delete it from that location to remove it. We never had a copy.

## 8. Data retention

On-device data is kept until you delete the document in the App or uninstall Scan Doc. There is no
off-device data held by us.

## 9. Children

Scan Doc is suitable for all ages and is not directed to children under 13. Because we collect no personal
data and operate no server, the App cannot tell the age of any user. We do not knowingly collect data from
children under 13, or 16 in the EU; we do not collect data from anyone.

## 10. Your rights

You have full control because the data lives on your device. Every document, page and recognised text is
visible inside the App. Export PDF, Export Word, To Markdown and Share take any document out of it. Deleting
a document from its detail screen removes it, and uninstalling the App removes everything. You can edit the
recognised text, rename, rotate, reorder, add and remove pages directly inside the App. Revoking a permission
in your device settings leaves the App working with reduced features.

You may also contact tmktechgroup@gmail.com with any question, but we cannot delete what we never had.

## 11. Changes to this policy

We will update the "Effective date" above and ship a new app version whenever this policy changes.

</div>
</article>
