---
# Chính sách quyền riêng tư Scan Doc (Privacy Policy URL cho App Store + Play).
# Mọi ý dưới đây lấy từ code THẬT đã Read: E:/Onsite/flutter/tmk_scan_doc/cau_truc.md mục 0-10, 19-21,
# pubspec.yaml (không có http/dio/analytics/ads/IAP), ios/Runner/Info.plist (2 quyền), AndroidManifest
# (không khai uses-permission nào). Layout app-policy như /fincore/ vì app KHÔNG có quảng cáo.
layout: app-policy
permalink: /scandoc/
title: "Scan Doc — Privacy Policy"
description: "Privacy policy for Scan Doc: document scanner, OCR and PDF toolkit."
last_updated: 2026-11-06

app_name: Scan Doc
app_subtitle: PDF Scanner & OCR
app_id: com.tmkgroup.scandoc
data_collected: "None. Scanning, text recognition and every PDF job run on your device; nothing you scan is uploaded."
order: 45
---

## Summary

**Scan Doc works on your device. We collect nothing.**

There is no account, no sign-in, no analytics SDK, no advertising SDK,
no crash reporter and no backend of ours. Pages you scan, the text that
recognition produces, the PDF, Word and Markdown files the app writes,
your signature and your watermarks all stay in Scan Doc's own folder on
your phone.

If you uninstall Scan Doc, every byte of that is gone with it. We cannot
recover anything for you, and neither can anyone else, because no copy
ever left your device.

The one time Scan Doc uses the network is when **you** translate text:
Google's on-device translation needs a language pack, and the app asks
Google to download it the first time you pick that language. The text you
are translating is **not** sent anywhere — the translation itself runs on
your phone, with the pack already downloaded.

## Data we collect

### From you, automatically

**None.** Scan Doc has no telemetry, no analytics, no crash reporting and
no server of ours. We have no way to identify you, see what you scan, or
know that you exist as a user.

### From you, with your consent

- **Camera** — used only while you are scanning a document or an ID card,
  to photograph the pages in front of you. Deny it and the rest of the app
  (history, importing pictures, every PDF job) still works.
- **Photo library** — read only when you tap **Import images** and pick
  pictures yourself. The app receives the pictures you selected and nothing
  else.
- **Files you pick** — when you choose a PDF or an image for the PDF tools,
  the system file picker hands the app that one file. The app never browses
  your storage on its own.

### From your device, locally

Stored inside Scan Doc's own application folder and settings:

- The page images the scanner produced, and pictures you imported
- Recognised text for each document
- Document records in a local SQLite database `history.db` (name, page list,
  recognised text, creation date)
- Files the app writes for you: exported PDF, Word (`.docx`), Markdown
  (`.md`), page images, your signature (PNG) and watermarked pages
- Settings (light/dark mode, accent colour, app language, writing system for
  text recognition)

This data is **never** uploaded anywhere. It is yours, and only yours.

## Permissions explained

| Permission | Why Scan Doc needs it |
|---|---|
| Camera | Photographing the pages while you scan a document or an ID card. Optional — everything except scanning works without it. |
| Photo library | Reading the pictures **you** select with "Import images". The app sees only what you picked. |
| Internet | One purpose only: downloading a Google translation language pack the first time you translate into that language. Scanning, text recognition and all PDF jobs need no connection. |

You can revoke any permission in your device settings at any time. The app
keeps working with fewer features (for example, no camera scanning).

## Third-party services

**Google ML Kit** (on-device) — three parts of the app use it:

- the document scanner that finds the edges of the page,
- text recognition (OCR) for Latin, Chinese, Devanagari, Japanese and Korean
  script,
- translation of the recognised text.

ML Kit does its work **on your device**: the page images and the recognised
text are not sent to Google for processing. Two things do travel over the
network, both triggered by you:

- the **translation language pack** download (once per language), and
- on Android, the scanning and recognition components themselves, which
  Google Play services fetches onto the phone the first time they are used.

Those requests go to Google, under
[Google's privacy policy](https://policies.google.com/privacy). They carry no
document of yours.

There is no Google Analytics, Firebase Analytics, Crashlytics, Sentry, AdMob,
Facebook SDK, or any other telemetry or advertising endpoint in Scan Doc.

When you tap **Share**, the app opens the standard OS share sheet. Whatever
you send goes where **you** direct it — not to TMK Group.

## Data retention

- **On-device data**: kept until you delete the document in the app or
  uninstall Scan Doc.
- **Off-device data**: there is none held by us. A file you shared or saved
  elsewhere stays wherever you put it, for as long as you keep it. Delete it
  from that location to remove it. We never had a copy.

## Children's privacy

Scan Doc is suitable for all ages. Because we collect no personal data and
operate no server, the app cannot tell the age of any user. We do not
knowingly collect data from children under 13 (or 16 in the EU); we do not
collect data from anyone.

## Your rights

You have full control because the data lives on your device:

- **Access**: every document, page and recognised text is visible inside the
  app.
- **Export**: use Export PDF, Export Word, To Markdown or Share to take any
  document out of the app.
- **Delete**: delete a document from its detail screen, or uninstall the app
  to remove everything.
- **Correct**: edit the recognised text, rename, rotate, reorder, add and
  remove pages directly inside the app.
- **Object / restrict**: revoke any permission in your device settings; the
  app continues to work with reduced features.

You may also contact
[tmktechgroup@gmail.com](mailto:tmktechgroup@gmail.com) with any question —
but we cannot delete what we never had.

## Changes to this policy

We will update the "Last updated" date above and ship a new app version
whenever this policy changes.
