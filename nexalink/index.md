---
# NexaLink = PC server (Windows, Microsoft Store) cho tinh nang "Dieu khien PC" cua app Edu.
# Nguon (2026-11-25): tmk_edu_server lib/core/constants/api_constants.dart (cong 2222 Socket.IO + 2224 HTTP),
# lib/core/network/secure/secure_channel.dart (X25519 + HKDF-SHA256 + ChaCha20-Poly1305, PIN 6 so),
# lib/core/constants/socket_constants.dart (su kien chuot / ban phim / file / thong tin may),
# lib/features/file_transfer/data/stores/upload_save_directory_store.dart (thu muc luu do nguoi dung chon),
# pubspec.yaml (khong co quang cao, khong tai khoan, khong analytics); lib/ khong goi HTTP ra Internet.
layout: default
permalink: /nexalink/
title: "NexaLink — Privacy Policy"
description: "Privacy policy for NexaLink, the PC companion that lets your phone control your computer over your local Wi-Fi network."
last_updated: 2026-11-25
app_name: NexaLink
app_subtitle: Control your PC from your phone over local Wi-Fi
app_id: TMKTECHGROUP.NexaLink
data_collected: "No account, no ads, no analytics. Mouse, keyboard and file data travel only between your phone and your PC on your local network, end-to-end encrypted."
order: 46
---

## Summary

NexaLink runs on your Windows PC and lets a phone on the **same Wi-Fi network** control that PC: move the mouse, click, scroll, type, and send files in both directions. The phone connects directly to the PC on your local network. Nothing is sent to TMK servers, there is no account, no advertising and no analytics.

Every session is paired with a QR code and a 6-digit PIN shown on the PC screen. After pairing, all traffic between the phone and the PC is **end-to-end encrypted** (X25519 key exchange, HKDF-SHA256, ChaCha20-Poly1305). A new key pair and PIN are created each time NexaLink starts.

---

## Data we collect

### Sent to TMK

None. NexaLink does not send any data to TMK Tech Group or to any other company.

### Exchanged between your phone and your PC (local network only)

| What | Direction | Why |
|------|-----------|-----|
| PC name, local IP address, operating system | PC → phone | Show which computer you are connected to |
| Mouse movements, clicks, scrolls, swipes | Phone → PC | Control the pointer |
| Text and key presses you type on the phone | Phone → PC | Type on the PC |
| Files you choose to send | Phone ↔ PC | File transfer you start yourself |

This data stays inside your local network, is encrypted end to end, and is not stored by NexaLink except for files you choose to receive.

### On your PC, locally

| What | Where |
|------|-------|
| Settings (language, start with Windows, close behaviour) | App's private settings storage |
| The folder you chose for received files | App's private settings storage |
| Files received from your phone | The folder you chose |

---

## Permissions explained

| Capability | Why NexaLink needs it |
|------------|-----------------------|
| Local network (listen for connections on ports 2222 and 2224) | Let your phone on the same Wi-Fi connect to the PC |
| Run as a full-trust desktop app | Move the mouse and send key presses to Windows |

Windows Firewall may ask you to allow NexaLink on private networks the first time it starts; the app does not work across the Internet.

---

## Third-party services

None. NexaLink does not use advertising, analytics, crash reporting or sign-in services.

---

## Data retention

| Data | Kept until |
|------|-----------|
| Settings | You uninstall NexaLink |
| Received files | You delete them from the folder you chose |

---

## Children's privacy

NexaLink does not collect personal data from anyone, including children under 13.

---

## Your rights

All data stays on your own devices, so you can view, change or delete it directly: change settings in the app, delete received files from your folder, or uninstall NexaLink to remove its settings. Questions: email **tmktechgroup@gmail.com**.

---

## Changes to this policy

When this policy changes we update the "Last updated" date above and ship a new app version.
