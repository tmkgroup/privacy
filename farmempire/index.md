---
# Farm Empire dùng layout "default" (KHÔNG "app-policy") như Blockora / Xiangqi Clash: master-policy ghi "never share it with advertisers",
# sai với Farm Empire (AdMob). Mẫu bê từ blockora/index.md. Nguồn từng ý (code game, đọc 2026-11-17):
# E:/Onsite/game/000-unity/farm/FarmEmpire/ — Assets/_FarmEmpire/Scripts/Persistence/PlayerSave.cs + SaveService (lưu persistentDataPath),
# grep Assets/**/*.cs không có UnityWebRequest / HttpClient / Firebase / Analytics, Assets/_FarmEmpire/Scripts/Core/FarmAds.cs +
# Packages/com.tmkgroup.monetize (AdMob xen kẽ + tặng thưởng, KHÔNG banner, UMP, gói bỏ quảng cáo thuê bao 3 tháng, Restore),
# ProjectSettings/UnityConnectSettings.asset (m_EngineDiagnosticsEnabled 1). Anh Truc 2026-11-17: "kiểm rồi build ipa cho tao" → "xong rồi".
layout: default
permalink: /farmempire/
title: "Farm Empire — Privacy Policy"
description: "Privacy policy for Farm Empire."
last_updated: 2026-11-17
app_name: Farm Empire
app_subtitle: Farm building game
app_id: com.tmkgroup.farmempire
data_collected: "No account. Progress stays on your device. Google AdMob ads collect device data."
order: 180
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Farm Empire — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.farmempire</code></span>
      <span>Effective date: 2026-11-17</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile game **Farm Empire** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. Information we do not collect

- The App has no user accounts and no sign-in.
- We do not ask for your name, email address, phone number, contacts, photos, or location.

## 2. Information stored only on your device

The App saves your farm on your device: buildings, fields, animals, items, coins, levels, quests, mini-game progress, sound and language settings, and whether you have removed ads. This information stays on your device and is not sent to us. Uninstalling the App removes it.

## 3. Internet connections

The App does not send your game data to our servers. The Unity game engine's diagnostics feature is turned on and sends technical crash and performance data to Unity Technologies (<https://unity.com/legal/privacy-policy>).

## 4. Advertising (Google AdMob)

The App shows ads using the Google Mobile Ads SDK (Google AdMob): full-screen ads between mini games, and videos you choose to watch for a reward. According to Google, the SDK automatically collects and shares the following data for advertising, analytics, and fraud prevention purposes:

- IP address (may be used to estimate the general location of the device)
- User product interactions (such as app launches, taps, and video views)
- Diagnostic information (performance of the App and the SDK)
- Device and account identifiers (such as the advertising ID and app set ID)

This data is encrypted in transit. Where required by law (for example in the EEA, the UK, and Switzerland), the App asks for your consent before personalised ads are shown, and you can change your choice at any time from the "Privacy options" button in Settings. On iPhone and iPad, the App asks for permission before using your advertising identifier. You can reset or delete your advertising ID in your device settings.

If you buy "Remove ads", the App stops showing full-screen ads. Videos you choose to watch for a reward stay available.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 5. In-app purchase

The App offers one optional purchase, "Remove ads", a subscription that renews automatically every 3 months until you cancel. Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. The App only records on your device that ads have been removed, and the "Restore" button asks the store to confirm a previous purchase.

## 6. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 7. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 8. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
