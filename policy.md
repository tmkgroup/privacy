# How to add a privacy policy for a new TMK Group app

Per-app cheat sheet. The full architecture lives in [README.md](README.md);
this file is the **5-minute checklist** every new app follows.

URL pattern: `https://privacy.tmkgroup.vn/<appname>/`

---

## Step 1 — Create the per-app folder

```sh
cp -r _TEMPLATE_app <appname>
```

Then edit `<appname>/index.md` only. **Never** touch `_layouts/`,
`_includes/`, `_config.yml`, or the root `index.md` — they are shared
infrastructure and pick up the new app automatically.

### Frontmatter (all fields required)

```yaml
---
layout: app-policy
permalink: /<appname>/                    # MUST end with /
title: <App Name> — Privacy Policy
description: Privacy policy for <App Name>.
last_updated: YYYY-MM-DD                  # bump every content change

app_name: <App Name>
app_subtitle: One-line tagline shown on landing page
app_id: com.tmkgroup.<appname>            # exact bundle ID
data_collected: "Short one-line summary." # ≤ 90 chars, shown on landing
order: 100                                # lower = appears earlier in list
---
```

### Required sections (in this order)

| Section | What goes in it |
|---|---|
| `## Summary` | 1 paragraph, plain language — what data the app deals with |
| `## Data we collect` | Subsections: *automatically*, *with consent*, *on-device locally* |
| `## Permissions explained` | Table: every OS permission + 1-line justification |
| `## Third-party services` | Every URL the app contacts (CDNs, APIs). If offline, say so. |
| `## In-app purchases` | **Only if app has IAP.** Mention Apple/Google handles billing. |
| `## Backups` | Only if app exports/imports data |
| `## Data retention` | How long data is kept |
| `## Children's privacy` | Standard COPPA/GDPR-K paragraph |
| `## Your rights` | Access / export / delete / correct / object |
| `## Changes to this policy` | Standard "we bump last_updated and ship a new version" |

Reference implementation: [`taqwim/index.md`](taqwim/index.md).

---

## Step 2 — Push, GitHub Pages auto-deploys

```sh
git add <appname>/
git commit -m "Add <AppName> privacy policy"
git push
```

GitHub Pages rebuilds on every push to `main` in ~30–60 seconds.
Build status is visible under the repo's **Actions** tab. Verify
by opening `https://privacy.tmkgroup.vn/<appname>/` in a browser.

> **Prerequisite (one-time, already done):** the repo must be public
> and GitHub Pages must be configured (Settings → Pages → Source:
> `main`/root + Custom domain `privacy.tmkgroup.vn`). See
> [README.md](README.md) for the full one-time hosting setup.

---

## Step 3 — Wire up the Flutter app

**Pattern: single source of truth = the public site.** The in-app screen
shows a short summary + a button that opens the public URL. Policy edits
never require an app release.

### a. Dependency

```yaml
# pubspec.yaml
dependencies:
  url_launcher: ^6.3.1
```

### b. Minimal in-app screen

```dart
import 'package:url_launcher/url_launcher.dart';

class PrivacyPolicyScreen extends StatelessWidget {
  static const _publicUrl = 'https://privacy.tmkgroup.vn/<appname>/';

  Future<void> _open(BuildContext context) async {
    final ok = await launchUrl(Uri.parse(_publicUrl),
        mode: LaunchMode.externalApplication);
    if (!ok && context.mounted) {
      ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Could not open browser')),
      );
    }
  }

  // Body:
  //   - 6–8 bullets summarizing the policy
  //   - FilledButton.icon → onPressed: () => _open(context)
  //   - SelectableText showing the URL in case the button fails
}
```

Full reference: `tmk_taqwim/lib/screens/privacy_policy_screen.dart`.

### c. Onboarding Terms (if app has one)

If the onboarding screen has a "Terms of Use" block, keep it short
(4–5 bullets) and mention IAP if present, e.g.:

```
• Runs entirely on your device.
• <App-specific accuracy disclaimer if relevant>
• <Third-party data source disclaimer if relevant>
• No ads. No tracking. <Subscription / one-time IAP note if present>
```

---

## Step 4 — Submit URL to stores

Use **`https://privacy.tmkgroup.vn/<appname>/`** (with trailing slash) as:

- **Google Play Console** → App content → Privacy policy → URL
- **App Store Connect** → App Information → Privacy Policy URL

For Data Safety / App Privacy questionnaires: answer based on the
public policy you just wrote, not from memory. If the policy says
"no data collected", select "No data collected" on both stores.

---

## Per-app content checklist

What you MUST customize for each app (don't copy blindly from another):

- [ ] `permalink` and `app_id` — exact, never reused
- [ ] Permissions list — match `Info.plist` + `AndroidManifest.xml` 1:1
- [ ] On-device data list — every feature that persists user data
- [ ] Third-party services — every URL the app contacts
- [ ] In-app purchases — list product IDs and what they unlock
- [ ] `data_collected` frontmatter — ≤ 90 chars
- [ ] `last_updated` — bump on every content change

---

## Common pitfalls

- **Permissions mismatch.** Listing permissions you don't request, or
  requesting permissions you don't list, both trigger store rejection.
- **Wishy-washy language.** Say "we collect X" or "we don't collect X".
  Never "we may collect". Reviewers reject vague language.
- **Forgotten IAP disclosure.** Apple requires explicit mention of IAP
  and that Apple/Google handles billing — even for one-time tips.
- **Stale `last_updated`.** Bump the date in the same commit as content
  changes, otherwise the audit trail breaks.
- **Renaming `permalink` after launch.** It becomes the store's privacy
  URL forever. Renaming breaks every published listing.
- **Submitting before push lands.** The public URL must be reachable
  when reviewers click it. Push and verify before submitting.
