---
# Fincore dùng layout "default" (KHÔNG "app-policy") như Scan Doc / Caribbean Calendar / Xiangqi Clash:
# _includes/master-policy.md ghi "never share it with advertisers", sai với app này từ 2026-11-11
# (app đã gắn Google AdMob — anh Truc "Gắn Fincore đi").
# Nguồn từng ý (2026-11-11):
#  - tmk_fincore/lib/ads/app_ads.dart (UMP consent, khởi động SDK sau khi đồng ý)
#  - tmk_fincore/lib/ads/banner_host.dart + banner_ad_widget.dart (banner dưới mọi màn), rewarded_ad_free.dart (24 giờ tắt quảng cáo)
#  - tmk_fincore/lib/ads/remove_ads_service.dart (gói com.tmkgroup.fincore.remove_ads_3m, 3 tháng)
#  - tmk_fincore/ios/Runner/Info.plist (NSUserTrackingUsageDescription, GADApplicationIdentifier)
#  - bảng Permissions, mục Backups, email liên hệ: giữ nguyên ý bản 2026-05-12 (chỉ thêm dòng Tracking)
#  - package/tmk_spendly_package/lib/src/services/spendly_rates_service.dart (10 máy chủ tỉ giá / giá thị trường, chỉ GET)
#  - các mục Permissions / Backups / Data retention / Children / Your rights giữ ý của bản 2026-05-12
#  - developers.google.com/admob/ios/privacy/data-disclosure (danh sách dữ liệu SDK quảng cáo thu,
#    bê nguyên câu chữ của scandoc/index.md mục 5)
layout: default
permalink: /fincore/
title: "Fincore — Privacy Policy"
description: "Privacy policy for Fincore, the offline personal finance tracker."
last_updated: 2026-11-11
app_name: Fincore
app_subtitle: Personal Income & Expense Tracker
app_id: com.tmkgroup.fincore
data_collected: "No account. Your transactions stay on your device. Google AdMob ads collect device data; the Remove ads subscription turns them off."
order: 30
---

<article class="app-policy">
  <p class="app-back"><a href="/">← All policies</a></p>
  <header class="app-header">
    <h1>Fincore — Privacy Policy</h1>
    <p class="app-meta">
      <span>Bundle ID: <code>com.tmkgroup.fincore</code></span>
      <span>Effective date: 2026-11-11</span>
    </p>
  </header>

<div markdown="1">

This Privacy Policy explains how the mobile app **Fincore** ("the App"), published by **TMK Tech Group**
("we", "us"), handles information. The App is not directed to children under 13.

## 1. In short

**Every transaction you record stays on your device. We run no server and we collect nothing.**

There is no account, no sign-in, no analytics SDK, no crash reporter and no backend of ours. Every
transaction, category, note and recurring payment you record lives in encrypted local storage on your
device, and nowhere else. If you uninstall Fincore, every byte of that is gone with it; we cannot recover
anything for you, because no copy ever left your phone.

Three things do use the network, and none of them carries a record of yours: **Google's advertising SDK**
(section 5), the **store** when you buy or restore the Remove ads subscription (section 6), and the
**exchange-rate and market-price lookups** of the currency converter and market screens (section 4).

## 2. No account

- The App has no TMK account and no sign-in to our servers.
- We do not ask for your name, email address or phone number.
- We have no way to identify you, see what you record in the App, or know that you exist as a user.

## 3. What is stored on your device

Stored in encrypted on-device storage:

- income and expense transactions (amount, date, category, notes you typed);
- categories, accounts, budgets and saving goals you created;
- recurring payment rules and their due dates, and the scheduled reminder triggers;
- your settings: language, theme, accent colour, currency format, notification toggles, and the end time of
  a 24-hour ad-free window if you watched a rewarded ad.

This data is never uploaded to us.

### Permissions

| Permission | Why Fincore needs it |
|---|---|
| Notifications | Locally-scheduled payment-due reminders. Never sent to a server. Optional — the App works without it. |
| Exact alarm (Android 12+) | Required by Android so payment reminders fire at the exact scheduled minute, not "approximately". |
| Boot completed (Android) | Re-arms scheduled payment reminders after a phone reboot. No network access. |
| Read / write external storage (Android < 13 / < 10) | Required by older Android versions when you open the system file picker or share sheet for a backup file. The App only reads files you explicitly pick. |
| Tracking (iPhone and iPad) | Personalised ads, only if you tap "Allow" on Apple's prompt. |

You can revoke any permission in your device settings at any time. The App keeps working with fewer features.

## 4. Exchange rates and market prices

The currency converter and the market screens download public exchange rates and prices (currencies, gold,
crypto, stocks) from these services: open.er-api.com, api.frankfurter.dev, sjc.com.vn, api.binance.com,
api.coingecko.com, query1.finance.yahoo.com, api.fiscaldata.treasury.gov, data-api.ecb.europa.eu and
techcombank.com. These are plain downloads of public data: **no transaction, amount or note of yours is
sent**. Each service sees an ordinary web request (including your IP address) under its own privacy policy.

## 5. Advertising (Google AdMob)

The free version shows a banner at the bottom of the screen and offers an optional rewarded ad, using the
Google Mobile Ads SDK (Google AdMob). According to Google, the SDK may collect:

- coarse location, including location derived from the IP address;
- a device ID, such as the advertising identifier;
- advertising data (for example, ads you have seen) and product interactions (such as app launches and taps);
- crash logs and performance data.

This data is used by Google for advertising, analytics and to improve the SDK. **It never includes your
transactions, amounts, categories or notes** — those are not available to the SDK.

Where required by law (for example in the EEA, the UK and Switzerland), the App asks for your consent before
ads are personalised, and you can change your choice at any time with the "Ad privacy options" button in
the More tab. On iPhone and iPad, the advertising identifier is shared only if you tap "Allow" on Apple's App
Tracking Transparency prompt. You can reset or delete your advertising ID in your device settings.

The **rewarded ad** is never forced: you tap it yourself in the More tab to turn ads off for 24 hours. Nothing
in the App is locked behind it — recording, reports, budgets, saving goals, reminders, the currency converter
and backups are free whether or not you watch an ad.

- Google's privacy policy: <https://policies.google.com/privacy>
- How Google uses data from partner apps: <https://policies.google.com/technologies/partner-sites>

## 6. Remove ads subscription

"Remove ads" is an optional subscription (3 months, renewing automatically until you cancel it in your store
account settings). Payment is handled entirely by the Apple App Store or Google Play; **we never receive your
payment details**. While the subscription is active the App does not start the advertising SDK at all, so none
of the data in section 5 is collected.

## 7. Backups (yours to save anywhere)

Fincore includes a **passphrase-encrypted backup feature**. When you create a backup:

- A `.tmkbak` file is produced, encrypted with AES using the passphrase **you** type. We do not see, store,
  or transmit your passphrase.
- The App opens the **system share sheet**. From there *you* choose where the file goes (Files, iCloud Drive,
  Google Drive, an email attachment, and so on). TMK Tech Group never receives a copy.
- To restore, pick the file from wherever you saved it and re-enter the same passphrase.
- If you lose the passphrase, **no one** — not us, not anyone — can recover the backup. That is by design.

## 8. Data retention

On-device data is kept until you delete it in the App or uninstall Fincore. There is no off-device data held
by us. Any `.tmkbak` file you saved elsewhere stays wherever you put it, for as long as you keep it; delete
the file from that location to remove it.

## 9. Children

Fincore is suitable for all ages and is not directed to children under 13. Because we collect no personal
data and operate no server, the App cannot tell the age of any user. We do not knowingly collect data from
children under 13, or 16 in the EU; we do not collect data from anyone.

## 10. Your rights

You have full control because the data lives on your device. Every transaction and record is visible inside
the App. The backup feature exports all of it in one `.tmkbak` file. You can edit any transaction or category
directly in the App, delete records, or uninstall the App to remove everything. Revoking a permission in your
device settings leaves the App working with reduced features (for example, no reminders).

You may also contact [dev@tmkgroup.vn](mailto:dev@tmkgroup.vn) with any question, but we cannot delete what
we never had.

## 11. Changes to this policy

We will update the "Effective date" above and ship a new app version whenever this policy changes.

</div>
</article>
