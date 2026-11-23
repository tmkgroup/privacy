---
# Edu dung layout "default" (KHONG "app-policy") nhu india-calendar / caribbean:
# master-policy ghi "never share it with advertisers", sai voi app nay (Google AdMob).
# Nguon (2026-11-23, anh Truc "ok build ipa di"): tmk_edu ios/Runner/Info.plist (UsageDescription),
# android/app/src/main/AndroidManifest.xml, pubspec.yaml, lib/services/ai_config.dart (Gemini),
# lib/screens/profile/widgets/remove_ads_card.dart (goi 3 thang tu gia han).
layout: default
permalink: /edu/
title: "Edu: Học Tập Mầm Non – THPT — Privacy Policy"
description: "Privacy policy for Edu: Học Tập Mầm Non – THPT, the learning app from preschool to high school."
last_updated: 2026-11-23
app_name: "Edu: Học Tập Mầm Non – THPT"
app_subtitle: Learning from preschool to high school
app_id: com.tmkgroup.edu
data_collected: "Optional account (Supabase) for sync, classes and homework; ads via Google AdMob with consent; text you send to AI study features goes to Google Gemini; lessons and exams are downloaded from TMK's CDN."
order: 45
---

## Summary

Edu is a learning app with lessons, interactive exercises, mock exams, tools and classroom features for preschool through grade 12. You can use the learning content without creating an account. If you sign in, your account and the data you create for classes, homework, notes and progress are stored on TMK servers (Supabase) so they can sync and be shared with your teacher, students or parents. Lessons, exam papers and audio are downloaded from TMK's content server `cdn-edu.tmkgroup.vn`.

The app shows ads from Google AdMob. Before any ad is requested, the Google User Messaging Platform (UMP) consent form is shown where required by law. You can remove ads with an optional auto-renewing subscription.

---

## Data we collect

### Sent to TMK servers (Supabase) — only when you sign in

| What | Why |
|------|-----|
| Account: provider ID, display name, email, profile picture (from Google, Apple or Facebook sign-in, or email + password) | Sign in and sync |
| Grades / subjects you follow, learning progress, scores, notes | Keep your learning history across devices |
| Classes, homework, attachments, messages you create or receive in classroom features | Share them with the teacher, students and parents in the same class |

You start every one of these writes yourself; nothing is uploaded silently in the background.

### Sent to other services, only when you use the feature

| What | Sent to | When |
|------|---------|------|
| The text you type into AI study features (questions, topics for a mind map) | Google Gemini API | When you press the AI button |
| Voice audio while you read aloud in "Spelling with kids" | Your device's built-in speech-recognition service (Apple on iOS, Google on Android) | Only while the microphone button is on |
| Audio / video during a call | Jitsi Meet | Only during a call you join |
| Map area you are viewing | The map-tile provider | When you open a map screen |

### With your consent (device permissions)

| Permission | Why the app needs it |
|------------|----------------------|
| Microphone | Listen to the child reading aloud in the spelling exercise; voice in calls |
| Speech recognition (iOS) | Score the spelling exercise |
| Camera | Take a photo or scan a code when you choose to |
| Photo Library | Pick a picture from your library when you choose to |
| Location (when in use) | Only the location features you open in the app |
| Calendars (iOS) | Read and add events to the Calendar on your device, only after you allow it |
| Bluetooth (Android) | Audio devices during calls |

You can revoke any permission in your device settings; the related feature simply stops working.

### On your device, locally

App settings, favourites (for example the exams you pinned in the Exam tab), cached lessons, offline exercise progress and your sign-in session are stored in the app's private storage on your device.

---

## Third-party services

| Service | Purpose | Policy |
|---------|---------|--------|
| Supabase (TMK-hosted) | Accounts, database, file storage | [supabase.com/privacy](https://supabase.com/privacy) |
| Google Sign-In | Sign in with Google | [policies.google.com/privacy](https://policies.google.com/privacy) |
| Sign in with Apple | Sign in with Apple | [apple.com/legal/privacy](https://www.apple.com/legal/privacy/) |
| Facebook Login | Sign in with Facebook | [facebook.com/privacy/policy](https://www.facebook.com/privacy/policy/) |
| Google AdMob + User Messaging Platform | Ads and consent | [policies.google.com/technologies/ads](https://policies.google.com/technologies/ads) |
| Google Gemini API | AI study features | [policies.google.com/privacy](https://policies.google.com/privacy) |
| Jitsi Meet | In-app calls | [jitsi.org/meet-jit-si-privacy](https://jitsi.org/meet-jit-si-privacy/) |
| YouTube | Lesson videos played inside the app | [policies.google.com/privacy](https://policies.google.com/privacy) |
| Apple App Store / Google Play billing | Optional "Remove ads" subscription | Payments are handled by Apple or Google; the app never receives your card details |

---

## In-app purchases

"Remove ads" is an auto-renewing subscription billed by Apple or Google. It renews until you cancel it in your store account settings. Terms of Use: [Apple standard EULA](https://www.apple.com/legal/internet-services/itunes/dev/stdeula/).

---

## Data retention

| Data | Kept until |
|------|-----------|
| Account and the records you created | You delete them in the app or ask us to delete your account |
| Data on your device | You clear the app's data or uninstall the app |

---

## Children's privacy

The app contains learning content for young children. Children should use it with a parent, guardian or teacher, and an adult should create any account. We do not knowingly collect personal data from a child under 13 without the consent of a parent or guardian. If you believe a child has given us personal data without that consent, email us and we will delete it.

---

## Your rights

You can see and edit your data inside the app. To export or delete your account and all data tied to it, email **tmktechgroup@gmail.com** with the subject "Account Deletion Request" from the address linked to your account; we process requests within 30 days. You can revoke device permissions in your device settings, and change your ad consent by clearing the app's data so the consent form is shown again.

---

## Changes to this policy

When this policy changes we update the "Last updated" date above and ship a new app version.
