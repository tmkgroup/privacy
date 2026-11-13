---
layout: app-policy
permalink: /medimo/
title: Medimo — Privacy Policy
description: Privacy policy for Medimo, the offline-first family health record app.
last_updated: 2026-11-13

# Per-app metadata read by _layouts/app-policy.html and the landing page loop.
app_name: Medimo
app_subtitle: Family health records, vaccines, vitals and reminders
app_id: vn.tmkgroup.tmk_medimo
data_collected: "No health data reaches our servers. Everything stays in encrypted on-device storage. The free tier shows AdMob ads."
order: 40
---

## Summary

**Medimo stores your family's health records on your device only.**

There is no account, no sign-in, no TMK Group server holding your data,
no analytics SDK and no crash reporter. Medical records, vaccination
schedules, vital-sign readings, medication reminders, symptoms,
pregnancy entries and the emergency medical ID all live in encrypted
on-device storage (Hive) and nowhere else.

Three things can leave your device, and only when you act or when the
free tier shows an ad:

1. **A backup file you choose to save or share** through the system
   share sheet — to your own Drive, Files app, email or a cable.
2. **Anonymous ad-serving signals** to Google AdMob (free tier only; the
   "Remove ads" subscription turns these off).
3. **A search for clinics near you** (only when you open *Find nearby*),
   sent to an OpenStreetMap Overpass endpoint as coordinates and a
   radius — never with any of your health data attached.

## Data we collect

### From you, automatically

- **Anonymous ad signals (free tier only).** When the app shows a banner
  or a rewarded ad, Google AdMob receives the standard ad-request
  signals (device language, coarse location derived from IP, the
  Advertising ID, app version). In the EU/UK Google's UMP consent form
  is shown before any ad loads. **Subscribers see no ads, and no ad
  signals are sent for them.**
- **No analytics, no crash reporting, no Firebase Analytics, no
  Crashlytics, no Mixpanel, no AppsFlyer, no Sentry, no Facebook SDK,
  no TMK account server, no sign-in.** We do not measure your in-app
  behaviour and we do not host an account or a sync server. There is
  nothing to sign up for.
- **Your health data is never used for advertising.** Nothing you record
  in Medimo is sent to AdMob or to any other third party.

### From you, with your consent

- **Notifications** (Android 13+: `POST_NOTIFICATIONS`; iOS: standard
  permission) — for medication reminders, vaccine due dates and
  appointment alerts you set up. All scheduled on-device.
- **Exact alarms** (Android 12+: `SCHEDULE_EXACT_ALARM` /
  `USE_EXACT_ALARM`) — so a medication reminder fires at the minute you
  chose instead of being batched by the system.
- **Camera** (Android: `CAMERA`; iOS: `NSCameraUsageDescription`) — to
  scan a QR code and to photograph a lab result or prescription. Text
  recognition runs **on the device** with Google ML Kit's on-device
  model; the picture is not uploaded.
- **Bluetooth** (Android: `BLUETOOTH_SCAN` with `neverForLocation`,
  `BLUETOOTH_CONNECT`, plus `BLUETOOTH`, `BLUETOOTH_ADMIN` and
  `ACCESS_FINE_LOCATION` on Android 11 and older, where the system
  requires it for any BLE scan) — to read measurements from a blood
  pressure monitor, glucometer or smart scale over standard GATT. The
  readings go straight into your on-device store.
- **Location** (Android: `ACCESS_FINE_LOCATION`; iOS:
  `NSLocationWhenInUseUsageDescription`) — used **only** when you open
  *Find nearby* or set the address of a clinic, to search for places
  around you. The coordinates are used for that one request and are not
  stored by us.
- **Health Connect (Android) / Apple HealthKit (iOS)** — read-only
  access to the metrics you tick in the system dialog (steps, distance,
  calories, exercise, sleep, heart rate, resting heart rate, blood
  pressure, blood glucose, oxygen saturation, body temperature,
  respiratory rate, weight, height, body fat, hydration). The data is
  copied into Medimo's on-device store so it can appear next to your
  own entries. It is never uploaded, never shared, and never used for
  advertising. You can revoke the access at any time in Health Connect
  or in the iOS Health app.

### From your device, locally

Stored in encrypted on-device storage:

- Family member profiles you create (name, date of birth, blood type,
  allergies, chronic conditions — only what you type)
- Medical records, visits, prescriptions, documents and photos you add
- Vaccination schedules and doses given
- Vital-sign readings (blood pressure, glucose, weight, temperature,
  SpO2, heart rate) typed by you or read from a device
- Medication reminders and adherence history
- Symptoms, pain-map entries, wellness, nutrition, sleep, mood, cycle
  and growth entries
- Pregnancy entries
- The emergency medical ID card
- Settings (language, theme, notification toggles)

This data is **never** uploaded to TMK Group.

## Permissions explained

| Permission | Why Medimo needs it |
|---|---|
| Notifications | Medication reminders, vaccine due dates, appointment alerts you set up. Generated on-device. |
| Exact alarm (Android 12+) | Required by Android so a medication reminder fires at the exact minute. |
| Camera | Scan a QR code; photograph a lab result or prescription for on-device text recognition. |
| Bluetooth (scan / connect) | Read measurements from a blood pressure monitor, glucometer or smart scale. |
| Location | Only for *Find nearby* and clinic addresses; on Android 11 and older it is also what the system demands before any Bluetooth scan. |
| Health Connect / HealthKit (read) | Show steps, sleep, heart rate and other metrics you tick, beside your own entries. |
| Internet | Ads (free tier only), the in-store purchase, and the *Find nearby* clinic search. |
| Receive boot completed | Re-schedule your reminders after the phone restarts. |
| Vibrate | Tactile feedback for reminders. |
| Advertising ID (Android `AD_ID`) | AdMob ad personalisation on the free tier. Not used for subscribers; revocable in Android settings → Privacy → Ads. |

You can revoke any permission in your device settings at any time. The
app keeps working with the matching feature switched off.

## No accounts, no TMK servers

**Medimo has no sign-in.** We do not run an auth server, a profile
server or a sync server for this app. We cannot identify you, cannot see
what you record, and cannot recover anything for you.

When you move to a new phone, you bring your data with you using the
backup feature below.

## Backups (yours to save anywhere)

Medimo can export your data to a backup file (Settings → Backup). The
app opens the **system share sheet** and *you* choose where the file
goes — your Files app, your own Drive, an email to yourself, a cable.
TMK Group never receives a copy. To restore, import the file on the new
device.

If you delete every copy you saved, the data is gone: we never had one.

## Third-party services

Medimo talks to the following external services. **None of them is a TMK
Group data server.**

- **Google AdMob** (`*.googleadservices.com`, `*.doubleclick.net`,
  `*.googlesyndication.com`) — free tier only, after the EU/UK consent
  prompt. Sends the standard ad request (Advertising ID, language, app
  version, approximate location from IP). Never your health data.
  Privacy: <https://policies.google.com/privacy>.
- **Google Play Billing** (Android) / **Apple StoreKit** (iOS) — for the
  "Remove ads" subscription. Payment details never reach us. Privacy:
  [Google](https://policies.google.com/privacy) ·
  [Apple](https://www.apple.com/legal/privacy/).
- **OpenStreetMap Overpass** (`overpass.tmkgroup.vn`,
  `overpass-api.de`, `overpass.kumi.systems`) — only when you open *Find
  nearby*. Sends a coordinate and a radius to look up clinics,
  pharmacies and hospitals. No health data, no identifier.
  Privacy: <https://osmfoundation.org/wiki/Privacy_Policy>.
- **Google ML Kit text recognition** — runs **on the device**. The photo
  of your lab result or prescription is not uploaded.
- **Health Connect (Android) / HealthKit (iOS)** — the platform's own
  health store on your device. Medimo reads only what you tick.

We do **not** use Firebase Analytics, Crashlytics, Mixpanel, AppsFlyer,
Branch, Adjust, Sentry or the Facebook SDK.

## In-app purchases

Medimo offers **one optional in-app purchase**:

- **Remove ads** (`com.tmkgroup.medimo.remove_ads_3m`), an
  auto-renewing subscription that hides every ad in the app. It renews
  until you cancel it in the Google Play or App Store subscription
  settings.
- The transaction is processed **entirely by Google Play Billing** on
  Android or **Apple StoreKit** on iOS. Medimo never sees, receives or
  stores your payment details, billing address or real name.
- The app keeps a single flag on your device ("ads removed = yes/no").
  Restoring on a new device works through Google's / Apple's own
  "Restore purchases" mechanism.

## Data retention

- **On-device data**: kept until you delete it in the app or uninstall
  the app.
- **Backup files you saved elsewhere**: kept wherever you put them,
  until you delete them there. We never had a copy.
- **Ad-network data** (free tier only): retained by Google AdMob under
  their own policy:
  <https://policies.google.com/technologies/ads>.

## Children's privacy

Medimo is made for a whole household, and a parent may keep a child's
vaccination record in it. That record stays on the parent's device; it
is not transmitted to us and is not used for advertising. Because we
operate no account and no server, we cannot identify any user. We do not
knowingly collect data from children under 13 (or under 16 in the EU) —
the only data leaving the device on the free tier is the anonymous
AdMob ad request, which the "Remove ads" subscription turns off.

## Medical disclaimer

Medimo helps you organise health information. It is **not a medical
device**, it does not diagnose, and it does not replace professional
care. Always consult a licensed doctor for medical advice.

## Your rights

- **Access**: every record is visible inside the app.
- **Export**: Settings → Backup produces a file containing your data.
- **Delete (local)**: delete the record in the app, or uninstall the app
  to remove everything.
- **Delete (any copy you saved elsewhere)**: open the place you saved
  the backup file and delete it there. We never had a copy.
- **Correct**: edit any field directly inside the app.
- **Object / restrict**: revoke any permission in your device settings.
  Free-tier ad personalisation can be turned off in Android settings →
  Privacy → Ads, in iOS Settings → Privacy → Tracking, or by taking the
  "Remove ads" subscription.

You can also email <dev@tmkgroup.vn> with any question — but we have
nothing of yours to delete server-side, because we do not run a server
for this app.

## Changes to this policy

We will update the "Last updated" date above whenever this policy
changes. Material changes (a new third-party service, or a new category
of data) will be highlighted in the app on the next update.
