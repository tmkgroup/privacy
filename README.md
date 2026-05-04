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
├── _config.yml             ← Jekyll config (small, doesn't grow per app)
├── CNAME                   ← privacy.tmkgroup.vn
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
cp -r _TEMPLATE_app newapp
# edit newapp/index.md only
git add newapp && git commit -m "Add NewApp privacy policy" && git push
```

That is it. Concretely:

1. Copy the template directory: `cp -r _TEMPLATE_app newapp`.
2. Open `newapp/index.md`, replace every placeholder in the frontmatter
   (`permalink`, `app_name`, `app_subtitle`, `app_id`,
   `data_collected`, `order`), and write the policy body.
3. Commit and push. GitHub Pages rebuilds in 30–60 seconds.

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
