---
layout: app-policy
permalink: /homecare/
title: "Home Care: Warranty & Repairs — Privacy Policy"
description: "Privacy policy for Home Care: Warranty & Repairs."
last_updated: 2026-11-07

app_name: "Home Care: Warranty & Repairs"
app_subtitle: Keep track of your household devices, warranties and repairs
app_id: com.tmkgroup.homecare
data_collected: "Nothing leaves your phone. No account, no analytics, no profile."
order: 60
---

## Summary

Home Care is an offline notebook for the things you own at home: devices,
warranty dates, repair jobs, maintenance schedules, spending, a diary and
notes. **Everything you type stays on your phone.** There is no account to
create, no sign-in, no server of ours that your data is sent to, and we do
not run analytics or collect a profile about you.

The app does reach the internet for four optional things: map tiles when you
pick a repair shop on the map, your own smart-home hub if you connect one,
advertisements, and the store when you buy the ad-free subscription. Each of
those is described below.

## Data we collect

### From you, automatically

**None.** We do not collect, transmit or store any personal data on our own
servers. There is no analytics SDK, no crash-reporting SDK and no advertising
identifier read by us.

### From you, with your consent

Only what you type or pick yourself, and it is written to your phone's own
storage:

- devices, brands, serial numbers, purchase dates and warranty dates you enter;
- repair jobs, maintenance schedules, technicians and repair shops you enter;
- photos you take or choose for a device, receipt or warranty card;
- income and expense entries, diary entries and notes you write;
- the location you pick on the map for a repair shop, and (if you grant the
  permission) your current position used only to centre that map;
- the address and access token of your own Home Assistant hub, if you choose
  to connect one.

### From your device, locally

The app keeps all of the above on the device: a key-value store for settings,
SQLite databases for the diary and notes, and image files in the app's own
documents folder. Backups you create with the backup feature are files you
choose where to put — we never receive them.

## Permissions explained

| Permission | Why Home Care needs it |
|---|---|
| Internet | Map tiles, your own smart-home hub, advertisements, the app store for the ad-free subscription, and the optional Google-hosted font. |
| Camera | Scan a device QR code; take a photo of a device, receipt or warranty card. |
| Photo library | Pick an existing photo of a device, receipt or warranty card. |
| Location (while using the app) | Centre the map on where you are when you pick a repair shop. The app works without it; it is never stored or sent anywhere except to the map tile server as the map view you are looking at. |
| Local network (iOS) | Reach your Home Assistant hub on your own Wi-Fi. |
| Notifications | Remind you before a warranty expires, a maintenance job is due, or a repair is ready for pickup. Reminders are built on your phone. |
| Run after restart | Re-arm those reminders after the phone reboots. |
| Tracking (iOS) | Only asked so advertisements can be personalised. Say no and you still get ads, just non-personalised ones. |

## Third-party services

- **Google AdMob** shows the banner and the optional rewarded advertisement.
  Google receives the data described in its own policy
  (<https://policies.google.com/technologies/ads>). Before any ad request the
  app shows Google's consent form where it is legally required (EEA, UK,
  Switzerland), and on iOS the system tracking prompt. You can reopen the
  consent choices from **Settings → Ads → Ad privacy options**.
- **Apple App Store / Google Play** handle the "Remove ads" subscription. We
  never see your payment details; the app only asks the store whether the
  subscription is active.
- **Map tiles and search**: `map.tmkgroup.vn` (our own tile server, inside
  Vietnam) and, outside Vietnam, `tiles.openfreemap.org` and
  `tile.openstreetmap.org`. Place search uses
  `nominatim.openstreetmap.org`. These servers see the map area you are
  looking at and the words you search for, as any map does.
- **Your own Home Assistant hub**, only if you enter its address. The app
  talks to it directly on your network; nothing passes through us.
- **Google Fonts** is contacted only when you choose the optional
  "Plus Jakarta Sans" font in Settings; the default font is already on your
  phone and needs no download.
- **Opening another app**: tapping a repair shop's route hands the
  coordinates to Google Maps, and recording a repair cost can hand the amount
  to our TMK Fincore app if you have it installed. Both are ordinary app
  links you trigger yourself.

We do **not** sell or share your data with data brokers, and no advertising
network receives the contents of your devices, repairs, notes or diary.

## Data retention

On-device until you delete the entry or uninstall the app. Uninstalling
removes the databases and photos the app created. Backup files you exported
stay wherever you put them until you delete them. We hold nothing, so there
is nothing for us to retain.

## Children's privacy

Home Care is not directed at children under 13 (under 16 in the EEA). We do
not knowingly collect anything from children — in fact we do not collect
anything from anyone. If advertisements are a concern, the "Remove ads"
subscription turns them off entirely.

## Your rights

Because your data never leaves your phone, you exercise every right directly
in the app:

- **Access / export** — Settings → Backup creates a file with your data, and
  the device list exports to CSV and PDF.
- **Correct** — edit any device, repair, entry or note.
- **Delete** — delete the item, or uninstall the app to remove everything.
- **Object to advertising** — buy "Remove ads", or change your consent under
  Settings → Ads → Ad privacy options.

If you have a question, email TMK Tech Group at <tmktechgroup@gmail.com> — the same address as the app's support page.

## Changes to this policy

We will update the "Last updated" date above and ship a new app
version whenever this policy changes.
