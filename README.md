# tmkgroup-privacy

Privacy policies for every app published by **TMK Group**, served as a
static Jekyll site through **GitHub Pages** at
**https://privacy.tmkgroup.vn**.

This repo's only job is to host the publisher-required privacy URL for
the Google Play Store and the Apple App Store. Each app has its own page
under its own permalink (`/taqwim/`, `/wallet/`, etc.), and they all
share a common "TMK Group" boilerplate via `_includes/master-policy.md`
so the per-app pages stay focused on what's actually different.

## Layout

```
.
├── _config.yml             ← Jekyll config (small, doesn't grow per app)
├── Gemfile                 ← Jekyll gem pin (GitHub Pages-compatible)
├── CNAME                   ← custom domain — DO NOT delete; GitHub Pages reads it
├── .ruby-version           ← Ruby pin for reproducible builds
├── _layouts/
│   ├── default.html        ← header / footer
│   └── app-policy.html     ← per-app layout (includes master policy at the bottom)
├── _includes/
│   └── master-policy.md    ← shared TMK Group statement (one source of truth)
├── _TEMPLATE_app/          ← copy this folder when launching a new app
│   └── index.md
├── <app>/index.md          ← one folder per app — the only file you create
├── index.md                ← landing page (auto-lists every app)
├── assets/style.css        ← minimal CSS
└── README.md               ← this file
```

## Add a new app — one file, one push

The whole workflow scales to dozens of apps without the config bloating:

```sh
cp -r _TEMPLATE_app <appname>
# edit <appname>/index.md only
git add <appname> && git commit -m "Add <AppName> privacy policy" && git push
```

That is it. Concretely:

1. Copy the template directory: `cp -r _TEMPLATE_app <appname>`.
2. Open `<appname>/index.md`, replace every placeholder in the frontmatter
   (`permalink`, `app_name`, `app_subtitle`, `app_id`,
   `data_collected`, `order`), and write the policy body.
3. Commit and push. GitHub Pages rebuilds in 30–60 seconds.

### Naming convention — folder name = technical app name

The folder name (and `permalink`) must match the **last segment of the
bundle ID**, not the display name. Examples:

| App display name | Bundle ID | Folder / permalink |
|---|---|---|
| Taqwim | `com.tmkgroup.taqwim` | `taqwim/` |
| Shubh Calendar | `com.tmkgroup.shubhcalendar` | `shubh-calendar/` |
| Vintana | `com.tmkgroup.vintana` | `vintana/` |
| Sổ Thu Chi | `com.tmkgroup.fincore` | `fincore/` |

Use the Flutter project name / Android `namespace` if the bundle ID
segment is ambiguous. Never use the localised display name as the folder
name — it changes across languages and makes URLs fragile.

The landing page (`/`) reads `app_name` from each page's frontmatter
and automatically lists the new app — no need to edit `index.md`. The
shared layout automatically appends the TMK Group master statement to
the bottom of every app page — no need to copy boilerplate. `_config.yml`
holds only one default (the layout for plain pages) and never grows.

## Local preview (optional)

GitHub Pages auto-builds on push. To preview locally:

```sh
bundle exec jekyll serve     # requires Ruby + bundler + jekyll gem
```

Most edits don't require local preview — Jekyll's syntax is plain
Markdown plus a tiny bit of front matter, and any layout error shows
in the GitHub Actions log within a minute of pushing.

## Hosting — GitHub Pages, one-time setup

> **Prerequisite:** the repo MUST be **public**. GitHub Pages on the
> free tier does not host private repos — you'll see "Upgrade or make
> this repository public to enable Pages" if it's private. Privacy
> policies are public information anyway (you submit the URL to Apple
> and Google), so this is the right default.

To make `privacy.tmkgroup.vn` serve this repo:

1. **Make the repo public**
   - `tmkgroup/privacy` → **Settings → General** → scroll to **Danger
     Zone** → **Change repository visibility** → **Make public** →
     confirm by typing the repo name.

2. **Enable GitHub Pages**
   - **Settings → Pages**.
   - **Source**: *Deploy from a branch*.
   - **Branch**: `main`, folder `/ (root)` → **Save**.
   - GitHub builds the Jekyll site automatically on every push to
     `main`. First build ~1 minute; subsequent builds ~30–60 seconds.
     Build logs live under the repo's **Actions** tab.

3. **Add the custom domain**
   - Same page, **Custom domain** field → type `privacy.tmkgroup.vn`
     → **Save**.
   - GitHub commits a `CNAME` file to `main` containing that hostname.
     **Don't delete it** — GitHub Pages reads it on every build to know
     which domain to serve.
   - GitHub then requests a free Let's Encrypt certificate. SSL
     provisioning takes 1–10 minutes; the page shows a green "Your
     site is published at https://privacy.tmkgroup.vn/" when ready.
   - Once the cert is live, tick **Enforce HTTPS**.

4. **DNS (one-time, at your domain registrar)**
   - Add a `CNAME` record at the registrar's DNS panel:
     ```
     Type:  CNAME
     Host:  privacy
     Value: tmkgroup.github.io
     TTL:   3600
     ```
   - GitHub Pages serves from four anycast IPs
     (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
     `185.199.111.153`) — using `CNAME` is preferred so GitHub can
     change IPs without breaking you.

5. **Verify**
   - Open `https://privacy.tmkgroup.vn/taqwim/`. The Taqwim privacy
     policy should render with a valid green-padlock cert.
   - Submit this URL as the **Privacy Policy URL** in Google Play
     Console and App Store Connect when listing each app.

### Troubleshooting

| Symptom | Cause | Fix |
|---|---|---|
| "Upgrade or make this repository public to enable Pages" | Repo is private | Step 1 — make public |
| `NET::ERR_CERT_COMMON_NAME_INVALID` | Custom domain not configured in Pages settings, GitHub serving default cert | Step 3 — add custom domain, wait for Let's Encrypt |
| 404 from GitHub Pages | `CNAME` file missing or branch source wrong | Re-do Step 3; check `main/` has a `CNAME` file at root |
| Site shows old content | Jekyll build failed | Check **Actions** tab for the failing build log |

## Why this lives in its own repo

- **Reusable across all TMK Group apps** without coupling to any one
  app's release cycle.
- **Permanent URL** that survives any app being renamed, paused, or
  rebuilt.
- **Audit trail** — every wording change is a Git commit, which Apple
  and Google can verify if asked.
- **Zero maintenance** — GitHub Pages handles SSL (Let's Encrypt),
  CDN, and uptime for free.

## License

Content (`*.md`) is © TMK Group, all rights reserved. The site
scaffolding (CSS / layouts) is MIT-licensed for anyone who wants to
copy this pattern for their own privacy site.
