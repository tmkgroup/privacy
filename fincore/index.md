---
layout: app-policy
permalink: /fincore/
title: "Fincore — Privacy Policy"
description: "Privacy policy for Fincore, the offline personal finance tracker."
last_updated: 2026-05-12

app_name: Fincore
app_subtitle: Personal Income & Expense Tracker
app_id: com.tmkgroup.fincore
data_collected: "None — Fincore is fully offline and stores all data on your device only."
order: 30
---

## Summary

**Fincore is fully offline. We collect nothing.**

There is no account, no sign-in, no analytics SDK, no advertising SDK,
no crash reporter, and no remote backend. Every transaction, category,
note, and recurring payment you record lives in encrypted local storage
on your device — and nowhere else.

If you uninstall Fincore, every byte of data the app ever had is
gone with it. We cannot recover anything for you, and neither can anyone
else, because no copy ever left your phone.

## Data we collect

### From you, automatically

**None.** Fincore has no telemetry, no analytics, no crash
reporting, and no remote backend. We have no way to identify you, see
what you record in the app, or know that you exist as a user.

### From you, with your consent

- **Notification permission** (Android 13+: `POST_NOTIFICATIONS`; iOS:
  standard permission) — used **only** to send locally-scheduled
  reminders when a recurring payment is coming due. No notification
  content is uploaded or sent off-device. You can deny this permission
  and the rest of the app works normally.

### From your device, locally

Stored in encrypted on-device storage (`tmk_storage_package` — AES on
top of SQLite / SharedPreferences):

- Income and expense transactions (amount, date, category, notes you typed)
- Categories and tags you created
- Recurring payment rules and their due dates
- Settings (language, theme, currency format, notification toggles)
- Scheduled notification triggers (stored locally to fire reminders)

This data is **never** uploaded anywhere. It is yours, and only yours.

## Permissions explained

| Permission | Why Fincore needs it |
|---|---|
| Notifications | Locally-scheduled payment-due reminders. Never sent to a server. Optional — the app works without it. |
| Exact alarm (Android 12+) | Required by Android so payment reminders fire at the exact scheduled minute, not "approximately". |
| Boot completed (Android) | Re-arms scheduled payment reminders after a phone reboot. No network access. |
| Read / write external storage (Android < 13 / < 10) | Required by older Android versions when you open the system file-picker or share sheet to export a backup file. The app only reads files you explicitly pick. |

You can revoke any permission in your device settings at any time.
The app continues to work with reduced features (e.g. no reminders) when a permission is denied.

## Third-party services

**None.** Fincore does not connect to any external service. There is
no Google Analytics, Firebase Analytics, Crashlytics, Sentry, AdMob,
Facebook SDK, or any other telemetry or advertising endpoint.

You can verify this by inspecting network traffic — there is none.

The only optional file-sharing activity is the standard OS-level share
sheet (Android / iOS) which your device OS controls when you choose to
export a backup. That transfer goes to wherever *you* direct it — not
to TMK Group.

## Backups (yours to save anywhere)

Fincore includes a **passphrase-encrypted backup feature**
(Settings → Backup & Restore → Export Backup).

When you create a backup:

- A `.tmkbak` file is produced, encrypted with AES using the passphrase
  **you** type. We do not see, store, or transmit your passphrase.
- The app opens the **system share sheet**. From there *you* choose
  where the file goes — for example:
  - **iOS**: "Save to Files" → iCloud Drive, On My iPhone, or any
    Files-provider app you have installed (Dropbox, OneDrive, etc.).
  - **Android**: "Save to Drive", "Save to Files", or any app that can
    receive a file (Gmail attachment, Telegram, etc.).
- TMK Group never receives a copy. The file goes only where you send it.
- To restore, tap Import Backup, pick the file from wherever you saved
  it, and re-enter the same passphrase.
- If you lose the passphrase, **no one** — not us, not anyone — can
  recover the backup. That is by design.

## Data retention

- **On-device data**: kept until you delete it in the app or uninstall.
- **Off-device data**: there is no off-device data held by us. Any
  `.tmkbak` file you saved elsewhere stays wherever you put it, for as
  long as you keep it. Delete the file from that location to remove it.
  We never had a copy.

## Children's privacy

Fincore is suitable for all ages. Because we collect no personal data
and operate no server, the app cannot identify the age of any user. We
do not knowingly collect data from children under 13 (or 16 in the EU);
we do not collect data from anyone.

## Your rights

You have full control because the data lives on your device:

- **Access**: every transaction and record is visible inside the app.
- **Export**: use the in-app backup feature to produce a `.tmkbak` file
  containing all your data.
- **Delete**: use "Reset all data" in Settings, or uninstall the app.
- **Correct**: edit any transaction or category directly inside the app.
- **Object / restrict**: revoke any permission in your device settings;
  the app continues to work with reduced features (e.g. no reminders).

You may also contact [dev@tmkgroup.vn](mailto:dev@tmkgroup.vn) for any
question — but we cannot delete what we never had.

## Changes to this policy

We will update the "Last updated" date above and ship a new app version
whenever this policy changes.
