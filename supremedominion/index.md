---
# Supreme Dominion dùng layout "default" (KHÔNG "app-policy") như Xiangqi Clash: master-policy ghi "never share it with advertisers",
# sai với Supreme Dominion (AdMob). Mẫu bê từ xiangqiclash/index.md. Nguồn từng ý (code game, đọc 2026-11-06):
# E:/Onsite/game/000-unity/Supreme Dominion/Assets/SupremeDominion/Runtime/ — Campaign/Online.cs (Server game.tmkgroup.vn, InstallId,
# GiftCodes /v1/codes /v1/redeem, CloudSave /v1/save/put /v1/save/get, NewsUrl /news), Campaign/GameClock.cs (/v1/health),
# Campaign/Notify.cs (thông báo cục bộ), Ads/AdBridge.cs (chỉ quảng cáo có thưởng, UMP, Privacy options), Campaign/RemoveAds.cs,
# Campaign/Shop.cs (gói kim cương, thẻ tháng, Supporter Pack), Campaign/CampaignHud.Shop.cs (Restore purchases).
# Máy chủ: E:/Onsite/cloudflare/worker-game-giftcode/src/index.js (bảng saves giữ data + prev_data, owner = install ID, platform, build;
# đếm lần sai theo install ID + IP trong 1 giờ; không có lệnh xoá save tự động). ProjectSettings/UnityConnectSettings.asset:
# m_EngineDiagnosticsEnabled 1, Unity Analytics 0. Anh Truc 2026-11-06: "privacy.tmktechgroup.com/supremedominion/ mẹ mày đợi tao làm à?"
layout: default
permalink: /supremedominion/
title: "Supreme Dominion — Privacy Policy"
description: "Privacy policy for Supreme Dominion."
last_updated: 2026-11-06
app_name: Supreme Dominion
app_subtitle: Strategy game
app_id: com.tmkgroup.supremedominion
data_collected: "No account. Progress is saved on your device and backed up to our game server under a random backup code. Google AdMob ads and Unity crash diagnostics collect device data."
order: 150
---

<article class="app-policy">
  <p class="app-back"><a href="{{ '/' | relative_url }}">← All policies</a></p>
  <header class="app-header">
    <h1>Supreme Dominion — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.supremedominion</code></span>
      <span>Effective date: 2026-11-06</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile game **Supreme Dominion** ("the App"), published by **TMK Tech Group** ("we", "us"), handles information. The App is not directed to children under 13.

## 1. Information we do not collect

- The App has no user accounts and no sign-in.
- We do not ask for your name, email address, phone number, contacts, photos, or location.

## 2. Information stored on your device

The App saves your game progress and settings on your device: your base, troops, resources, missions, purchases made in the game, music and sound settings, notification setting, language, and a random install ID created on your device. Uninstalling the App removes this information from the device.

## 3. Our game server

The App connects to our game server at game.tmkgroup.vn, hosted on Cloudflare. Nothing on the server is needed to play: without a connection the game goes on.

- **Cloud save.** The App backs up your game progress to the server under a random backup code and password created on your device (shown in Settings → Cloud save). With each backup the App sends the save, the random install ID, the platform (Android or iOS), and the game version. The server keeps the latest backup and the one before it. Anyone who has your backup code and password can restore the save on another device, so keep them private.
- **Gift codes.** When you type a gift code, the App sends the code, the random install ID, the platform, and the game version, so that each code is given only once to each install.
- **Game clock.** The App reads the current time from the server when it opens and while it runs, so that timers and daily rewards follow the real time.
- **News.** The "News" button opens a web page from the same server in your browser.
- **Abuse protection.** To stop repeated wrong codes or passwords, the server counts failed attempts by install ID and by IP address within one hour.

Like any internet service, our hosting provider Cloudflare receives your IP address in order to deliver the connection and may keep technical logs. To have your cloud backup deleted, email us with your backup code (see section 10).

- Cloudflare's privacy policy: <https://www.cloudflare.com/privacypolicy/>

## 4. Advertising (Google AdMob)

The App offers optional rewarded ads: an ad is shown only when you tap a "Watch" button to get an in-game reward. The App uses the Google Mobile Ads SDK (Google AdMob). According to Google, the SDK automatically collects and shares the following data for advertising, analytics, and fraud prevention purposes:

- IP address (may be used to estimate the general location of the device)
- User product interactions (such as app launches, taps, and video views)
- Diagnostic information (performance of the App and the SDK)
- Device and account identifiers (such as the advertising ID and app set ID)

This data is encrypted in transit. Where required by law (for example in the EEA, the UK, and Switzerland), the App asks for your consent before personalised ads are shown, and you can change your choice at any time from the "Privacy options" button in Settings. On iPhone and iPad, the App asks for your permission before the advertising identifier is used for tracking. You can reset or delete your advertising ID in your device settings.

While a "Remove ads" subscription is active, the App does not start the advertising SDK.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 5. In-app purchases

The App offers optional purchases: gem packs, a monthly card, a supporter pack, and "Remove ads", a 3-month subscription that renews automatically until you cancel it. Payment is handled entirely by the Apple App Store or Google Play; we do not receive your payment details. The App records what you bought in your game save, and the "Restore purchases" button in the Shop asks the store to confirm earlier purchases.

## 6. Notifications

The App can schedule local notifications on your device, for example when a construction, research, or healing is finished or storage is full. They are created on your device and are not sent to us. The App asks for permission first, and you can turn them off in the App's Settings or in your device's notification settings.

## 7. Crash and diagnostic data (Unity)

The App is built with the Unity engine. Unity Technologies may collect diagnostic data at runtime, such as crash logs, "Application Not Responding" errors, and error traces, to keep the engine working correctly.

- Unity's privacy policy: <https://unity.com/legal/privacy-policy>

## 8. Children

The App is not directed to children under 13, and we do not knowingly collect personal information from children under 13.

## 9. Changes to this policy

If we change this policy, we will update the effective date above and publish the new version at the same address.

## 10. Contact

TMK Tech Group — [tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com)

</div>
</article>
