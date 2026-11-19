---
# Tank Legion dùng layout "default" (KHÔNG "app-policy") như Farm Empire / Blockora: master-policy ghi "never share it with advertisers",
# sai với Tank Legion (AdMob). Mẫu bê từ farmempire/index.md. Nguồn từng ý (code game, đọc 2026-11-18):
# E:/Onsite/game/000-unity/Tank Legion/ — Assets/TankLegion/Scripts/Core/SaveData.cs (PlayerPrefs trên máy), grep Assets/**/*.cs chỉ có
# UnityWebRequest ở OpenRA/Host/OpenRAData.cs đọc file streamingAssets trên máy (file://), không Firebase / Analytics / ATT;
# Assets/TankLegion/Scripts/Monetization/TLAds.cs + TLShop.cs + Packages/com.tmkgroup.monetize (AdMob xen kẽ + tặng thưởng, KHÔNG banner,
# UMP, gói ngọc, gói kịch bản Hex Command, bỏ quảng cáo thuê bao 3 tháng, Restore), ProjectSettings/UnityConnectSettings.asset
# (m_EngineDiagnosticsEnabled 1). Anh Truc 2026-11-18: "tạo gói quảng cáo cho nó".
layout: default
permalink: /tanklegion/
title: "Tank Legion — Privacy Policy"
description: "Privacy policy for Tank Legion."
last_updated: 2026-11-18
app_name: Tank Legion
app_subtitle: Tank battle game
app_id: com.tmkgroup.tanklegion
data_collected: "No account. Progress stays on your device. Google AdMob ads collect device data."
order: 190
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Tank Legion — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.tanklegion</code></span>
      <span>Effective date: 2026-11-18</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile game **Tank Legion** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. Information we do not collect

- The App has no user accounts and no sign-in.
- We do not ask for your name, email address, phone number, contacts, photos, or location.

## 2. Information stored only on your device

The App saves your progress on your device: your chosen tank and its upgrades, coins and gems, records, unlocked levels and scenarios, sound settings, and whether you have removed ads. This information stays on your device and is not sent to us. Uninstalling the App removes it.

## 3. Internet connections

The App does not send your game data to our servers. The Unity game engine's diagnostics feature is turned on and sends technical crash and performance data to Unity Technologies (<https://unity.com/legal/privacy-policy>).

## 4. Advertising (Google AdMob)

The App shows ads using the Google Mobile Ads SDK (Google AdMob): full-screen ads at the end of some battles, and videos you choose to watch for a reward. According to Google, the SDK automatically collects and shares the following data for advertising, analytics, and fraud prevention purposes:

- IP address (may be used to estimate the general location of the device)
- User product interactions (such as app launches, taps, and video views)
- Diagnostic information (performance of the App and the SDK)
- Device and account identifiers (such as the advertising ID and app set ID)

This data is encrypted in transit. Where required by law (for example in the EEA, the UK, and Switzerland), the App asks for your consent before personalised ads are shown, and you can change your choice at any time from the "Privacy options" button in Settings. You can reset or delete your advertising ID in your device settings.

If you buy "Remove ads", the App stops showing full-screen ads. Videos you choose to watch for a reward stay available.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 5. In-app purchases

The App offers optional purchases: gem packs, extra scenario packs, and "Remove ads", a subscription that renews automatically every 3 months until you cancel. Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. The App only records on your device what you have bought, and the "Restore purchases" button asks the store to confirm previous purchases.

## 6. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 7. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 8. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
