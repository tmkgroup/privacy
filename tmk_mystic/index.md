---
layout: app-policy
permalink: /tmk_mystic/
title: "Mystic — Privacy Policy"
description: "Privacy policy for Mystic, the western astrology & tarot app."
last_updated: 2026-11-13

app_name: Mystic
app_subtitle: Western Astrology & Tarot
app_id: com.tmkgroup.mystic
data_collected: "No account, no analytics. Charts, journals and readings stay encrypted on your device; AI answers use a Gemini key you supply yourself."
order: 160
---

## Summary

**Mystic has no account and no server of ours.**

Your profile, natal charts, journal entries, dream log, tarot history and
settings are written to encrypted storage on your own device. TMK Group
operates no backend for this app, so none of that content is uploaded to us
and we have no way to read it.

Three things do leave the device, and only when you choose them:

1. **AI interpretations** — sent to Google's Gemini API using **your own API
   key**, which you create yourself and paste into Settings.
2. **Purchases** — verified through RevenueCat and the store you bought from.
3. **Ads** — the free version shows banner ads and an optional rewarded ad
   through Google AdMob.

## Data we collect

### From you, automatically

**None.** Mystic has no analytics SDK, no crash reporter, no telemetry, and
no account system. We do not know who you are, how often you open the app, or
what you record in it.

### From you, with your consent

- **Gemini API key (BYOK)** — you create a free key at
  [aistudio.google.com](https://aistudio.google.com/app/apikey) and paste it
  into Settings. The key is stored in encrypted local storage on your device
  and is sent **only** to Google's `generativelanguage.googleapis.com` when
  you ask for an AI reading or chat. We never receive it.
- **What you send to the AI** — when you ask for an interpretation, the chart
  data or tarot spread involved in that question is included in the request to
  Google so it can be interpreted. Google processes it under your own API key
  and under Google's terms for that key. Do not type anything into the AI chat
  that you do not want sent to Google.
- **Health data (optional)** — if you enable it, the app reads today's steps,
  last night's sleep, resting heart rate and burned calories from Apple Health
  (HealthKit) or Android Health Connect, purely to draw the Biorhythm screen.
  The values are read on the device, shown on screen, and never uploaded,
  shared or sold. Deny the permission and every other screen still works.
- **Microphone (optional)** — voice input in the AI chat. Speech recognition is
  handled by your operating system's own service.
- **Notifications (optional)** — daily horoscope, moon-phase and transit
  alerts, streak reminders. All are scheduled locally on the device.
- **Photos / files (optional)** — only the single image you pick for Photo
  Reading, or the backup file you pick when restoring. The app cannot browse
  your library on its own.

### From your device, locally

Stored in encrypted on-device storage (`tmk_storage_package` — AES over
SQLite / SharedPreferences):

- Profile and natal chart data (name, date of birth, birth time and place)
- Personal events and countdowns you added
- Journal entries and dream log
- Tarot history and saved readings, including AI-generated interpretations
- App preferences (theme, language, notification toggles, AI tier) and your
  Gemini API key

This data is never uploaded to TMK Group.

## Permissions explained

| Permission | Why Mystic needs it |
|---|---|
| Notifications | Locally-scheduled horoscope, transit and streak reminders. Optional. |
| Exact alarm (Android 12+) | Makes those reminders fire at the exact scheduled minute. |
| Boot completed (Android) | Re-arms the scheduled reminders after a reboot. |
| Health Connect / HealthKit read (steps, sleep, heart rate, calories) | Draws the Biorhythm screen from your own activity data. Read-only, on-device, optional. |
| Microphone | Voice input in the AI chat. Optional. |
| Photos / files | The single photo you pick for Photo Reading, and backup import / export. Optional. |
| Internet | AI requests with your own key, purchase verification, and ads. |

You can revoke any of these in your device settings at any time; the app keeps
working with the matching feature switched off.

## Third-party services

- **Google Gemini API** (`generativelanguage.googleapis.com`) — AI readings and
  chat, called with **your** API key. Google's privacy policy applies to that
  traffic: <https://policies.google.com/privacy>
- **Google AdMob** — banner ads and the optional rewarded ad in the free
  version. In the EEA, the UK and Switzerland the app asks for your consent
  before any ad request, and you can reopen that choice any time from
  Settings → "Ad privacy options". Buying the ad-free entitlement, or watching
  the rewarded ad, hides the banner. Google's advertising policy:
  <https://policies.google.com/technologies/partner-sites>
- **RevenueCat** (`api.revenuecat.com`) — checks which subscription you own so
  the app can unlock paid features. It receives an anonymous purchase
  identifier, not your name or chart data:
  <https://www.revenuecat.com/privacy>
- **Apple App Store / Google Play** — handle the payment itself; we never see
  your card details.
- **raw.githubusercontent.com** — downloads the short, public "how to get an
  AI key" guide text. No data about you is sent.

Mystic does **not** contain Firebase Analytics, Crashlytics, Facebook SDK, or
any other telemetry.

## Backups (yours to save anywhere)

Settings → Backup produces a passphrase-encrypted file. The app hands it to
the system share sheet, and it goes only where **you** send it. TMK Group
never receives a copy, and a lost passphrase cannot be recovered by anyone.

## Data retention

- **On-device data**: kept until you delete it in the app or uninstall.
- **Off-device data**: we hold none. Requests you send to Google or RevenueCat
  are retained by those companies under their own policies.

## Children's privacy

Mystic is not directed at children under 13 (16 in the EU). We collect no
personal data and operate no server, so we cannot identify a user's age.

## Your rights

- **Access**: everything is visible inside the app.
- **Export**: Settings → Backup writes an encrypted file with all your data.
- **Delete**: Profile → Data & Privacy → "Delete all local data", or uninstall.
- **Correct**: edit any profile, event or journal entry in the app.
- **Object / restrict**: revoke a permission, withdraw ad consent in Settings,
  or remove your Gemini key — the rest of the app keeps working.

Questions: [dev@tmkgroup.vn](mailto:dev@tmkgroup.vn). We cannot delete data we
never had.

## Changes to this policy

We will update the "Last updated" date above and ship a new app version
whenever this policy changes.
