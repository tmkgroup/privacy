# tmkgroup-privacy

Privacy policies for every app published by **TMK Group**, served as a
static Jekyll site through GitHub Pages at **https://privacy.tmkgroup.vn**.

This repo's only job is to host the publisher-required privacy URL for
the Google Play Store and the Apple App Store. Each app has its own page
under its own permalink (`/taqwim/`, `/wallet/`, etc.), and they all
share a common "TMK Group" boilerplate via `_includes/master-policy.md`
so the per-app pages stay focused on what's actually different.

## Layout

```
.
├── _config.yml             ← Jekyll config + per-app defaults
├── CNAME                   ← privacy.tmkgroup.vn
├── _layouts/
│   ├── default.html        ← header / footer
│   └── app-policy.html     ← per-app layout (includes master policy at the bottom)
├── _includes/
│   └── master-policy.md    ← shared TMK Group statement (one source of truth)
├── _TEMPLATE_app/          ← copy this folder when launching a new app
│   └── index.md
├── taqwim/index.md         ← Taqwim privacy policy
├── index.md                ← landing page listing all app policies
├── assets/style.css        ← minimal CSS
└── README.md               ← this file
```

## Add a new app

1. Copy the template:
   ```sh
   cp -r _TEMPLATE_app newapp
   ```
2. Open `newapp/index.md`, set frontmatter (`title`, `description`,
   `permalink: /newapp/`, `last_updated`), and fill in the sections.
3. Add a defaults block to `_config.yml`:
   ```yaml
   - scope:
       path: "newapp"
     values:
       layout: app-policy
       app_name: NewApp
       app_subtitle: One-line tagline
       app_id: com.tmkgroup.newapp
       data_collected: "Short summary."
   ```
4. Add a `<li>` entry to `index.md`.
5. Commit and push. GitHub Pages rebuilds in 30-60 seconds.

The app-specific page automatically gets the TMK Group master statement
appended via the `app-policy` layout — no need to copy that text.

## Local preview (optional)

GitHub Pages auto-builds on push. To preview locally:

```sh
bundle exec jekyll serve     # requires Ruby + bundler + jekyll gem
```

Most edits don't require local preview — Jekyll's syntax is plain
Markdown plus a tiny bit of front matter, and any layout error shows
in the GitHub Actions log within a minute of pushing.

## DNS — one-time setup

To make `privacy.tmkgroup.vn` serve this repo:

1. **GitHub side**:
   - Push this repo to `github.com/tmkgroup/privacy` (public repo).
   - In repo Settings → Pages: Source = `Deploy from branch`, Branch =
     `main` (root). The `CNAME` file already has `privacy.tmkgroup.vn`,
     so GitHub will auto-configure the custom domain.
   - Enable "Enforce HTTPS" once the cert is provisioned (usually
     within ~10 minutes).

2. **DNS provider side** (where `tmkgroup.vn` is registered):
   - Add a `CNAME` record:
     ```
     Type:  CNAME
     Host:  privacy
     Value: tmkgroup.github.io
     TTL:   3600
     ```
   - Wait 5-30 minutes for propagation. Check with:
     ```sh
     dig privacy.tmkgroup.vn +short
     # → tmkgroup.github.io.
     ```

3. **Verify**:
   - Open `https://privacy.tmkgroup.vn/taqwim/` in a browser.
   - Submit this URL as the **Privacy Policy URL** in Google Play
     Console and App Store Connect when listing each app.

## Why this lives in its own repo

- **Reusable across all TMK Group apps** without coupling to any one
  app's release cycle.
- **Permanent URL** that survives any app being renamed, paused, or
  rebuilt.
- **Audit trail** — every wording change is a Git commit, which Apple
  and Google can verify if asked.
- **Zero maintenance** — GitHub Pages handles SSL, CDN, and uptime.

## License

Content (`*.md`) is © TMK Group, all rights reserved. The site
scaffolding (CSS / layouts) is MIT-licensed for anyone who wants to
copy this pattern for their own privacy site.
