---
# Copy this whole _TEMPLATE_app/ directory to <appname>/ when launching
# a new app. Edit the frontmatter below + write the policy content.
# Do NOT touch _config.yml or index.md — the landing page picks the
# new app up automatically once you push.

layout: app-policy
permalink: /<appname>/                # ← change to /myapp/, must end with /
title: "<App Name> — Privacy Policy"
description: "Privacy policy for <App Name>."
last_updated: 2026-01-01

# Per-app metadata read by the layout + the landing page loop.
app_name: <App Name>                  # ← what users see
app_subtitle: One-line tagline        # ← optional
app_id: com.tmkgroup.<appname>        # ← bundle ID
data_collected: "Short one-line summary."   # ← shown on landing page
order: 100                            # ← lower numbers appear first; pick any
---

## Summary

<!-- One-paragraph plain-language summary of what data the app deals with. -->
<App Name> ...

## Data we collect

### From you, automatically

<!-- e.g. "None.", "Anonymous crash reports.", "Account email + hashed password." -->

### From you, with your consent

<!-- List every permission the app requests and what it's used for. -->

### From your device, locally

<!-- Anything the app stores on-device. -->

## Permissions explained

| Permission | Why <App Name> needs it |
|---|---|
| | |

## Third-party services

<!-- Every external service the app talks to, even optionally. -->

## Data retention

<!-- How long we keep what. "On-device until uninstall" if local-only. -->

## Children's privacy

<!-- Standard COPPA / GDPR-K language unless app is specifically for kids. -->

## Your rights

<!-- Access / Export / Delete / Correct / Object — how the user exercises each. -->

## Changes to this policy

We will update the "Last updated" date above and ship a new app
version whenever this policy changes.
