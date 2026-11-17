---
# Isle Genesis dùng layout "default" (KHÔNG "app-policy") như Dream Haven: master-policy ghi "never share it with advertisers",
# sai với app có AdMob. Mẫu bê từ dreamhaven/index.md. Nguồn từng ý (code game, đọc 2026-11-17):
# E:/Onsite/game/000-unity/Isle Genesis/ — Assets/IsleGenesis/Scripts/Core/SaveSystem.cs:11 (lưu ở Application.persistentDataPath),
# Core/Ads.cs + Packages/com.tmkgroup.monetize (AdMob CHỈ quảng cáo tặng thưởng, KHÔNG banner; UMP; gói bỏ quảng cáo thuê bao 3 tháng; Khôi phục),
# Idle/IdleHost.cs (nút "x2 Watch ad" ở thưởng ngoại tuyến), Island/UI/ShopPanels.cs (Cài đặt: Remove ads / Restore purchases / Privacy Settings;
# hiện mã thiết bị trên màn Cài đặt, không gửi đi). Không có UnityWebRequest/HttpClient trong Assets/IsleGenesis/Scripts, không gọi ATT.
# Anh Truc 2026-11-17: "build ipa".
layout: default
permalink: /islegenesis/
title: "Isle Genesis — Privacy Policy"
description: "Privacy policy for Isle Genesis."
last_updated: 2026-11-17
app_name: "Isle Genesis"
app_subtitle: Island farming adventure
app_id: com.tmkgroup.islegenesis
data_collected: "No account. Progress stays on your device. Google AdMob ads collect device data."
order: 200
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Isle Genesis — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.islegenesis</code></span>
      <span>Effective date: 2026-11-17</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile game **Isle Genesis** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. Information we do not collect

- The App has no user accounts and no sign-in.
- We do not ask for your name, email address, phone number, contacts, photos, or location.

## 2. Information stored only on your device

The App saves your game progress on your device: your islands, buildings, items, resources, quests, settings, and whether you have removed ads. This information stays on your device and is not sent to us. Uninstalling the App removes it. The Settings screen shows your device's identifier for your own reference; the App does not send it anywhere.

## 3. Internet connections

The App does not send your game data to our servers. The App connects to the internet only to show ads and to handle a purchase, as described below.

## 4. Advertising (Google AdMob)

The App shows ads using the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK automatically collects and shares the following data for advertising, analytics, and fraud prevention purposes:

- IP address (may be used to estimate the general location of the device)
- User product interactions (such as app launches, taps, and video views)
- Diagnostic information (performance of the App and the SDK)
- Device and account identifiers (such as the advertising ID and app set ID)

This data is encrypted in transit. Where required by law (for example in the EEA, the UK, and Switzerland), the App asks for your consent before personalised ads are shown, and you can change your choice at any time from the "Privacy Settings" button in Settings. The App does not ask for permission to track you across other companies' apps and websites. You can reset or delete your advertising ID in your device settings.

The App does not show banner ads. It only shows a short video ad when you choose to watch one for a reward (for example, doubling the gold you earned while you were away).

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 5. In-app purchase

The App offers one optional purchase, "Remove ads", a subscription that renews automatically every 3 months until you cancel. With it, you get the rewards without watching the video ads. Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. The App only records on your device that ads have been removed, and the "Restore purchases" button asks the store to confirm a previous purchase.

## 6. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 7. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 8. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
