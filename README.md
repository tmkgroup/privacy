# tmkgroup-privacy

Privacy policies for every app published by **TMK Group**, served as a
static Jekyll site through **Cloudflare Pages** at
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
├── Gemfile                 ← Jekyll gem pin for Cloudflare's build
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

## Hosting — Cloudflare Pages, one-time setup

To make `privacy.tmkgroup.vn` serve this repo via Cloudflare Pages:

1. **Cloudflare account** (if not already)
   - Sign up at https://dash.cloudflare.com/sign-up (free tier is enough).
   - Add the site `tmkgroup.vn` to Cloudflare and switch the registrar's
     nameservers to the two Cloudflare gives you. Cloudflare now manages
     DNS for the whole domain — that step is what makes everything else
     trivial later.

2. **Connect Cloudflare Pages to this GitHub repo**
   - Cloudflare dashboard → **Workers & Pages** → **Create application**
     → **Pages** → **Connect to Git**.
   - Authorize Cloudflare to read the `tmkgroup` GitHub org (one-time).
   - Select repo `tmkgroup/privacy`, branch `main`.
   - Build settings:
     - **Framework preset**: `Jekyll`
     - **Build command**: `jekyll build`
     - **Build output directory**: `_site`
     - **Root directory**: `/`
     - **Environment variables**: leave empty
   - **Save and Deploy**. First build runs in ~1 minute; subsequent
     builds (one per push) usually take ~30 seconds.

3. **Add custom domain inside Cloudflare Pages**
   - Project → **Custom domains** → **Set up a custom domain** →
     `privacy.tmkgroup.vn` → **Activate domain**.
   - Cloudflare automatically creates the matching `CNAME` record
     because the domain is on the same Cloudflare account. SSL is
     auto-issued in ~1 minute.

4. **Verify**
   - Open `https://privacy.tmkgroup.vn/taqwim/` in a browser. The
     Taqwim privacy policy should render.
   - Submit this URL as the **Privacy Policy URL** in Google Play
     Console and App Store Connect when listing each app.

### Alternative: DNS not on Cloudflare

If you keep DNS at another provider (e.g. the registrar's panel),
Cloudflare Pages still works — you just have to add the CNAME yourself:

```
Type:  CNAME
Host:  privacy
Value: <project-name>.pages.dev
TTL:   3600
```

Cloudflare Pages tells you the exact `pages.dev` hostname under
Custom domains. SSL still auto-provisions.

## Why this lives in its own repo

- **Reusable across all TMK Group apps** without coupling to any one
  app's release cycle.
- **Permanent URL** that survives any app being renamed, paused, or
  rebuilt.
- **Audit trail** — every wording change is a Git commit, which Apple
  and Google can verify if asked.
- **Zero maintenance** — Cloudflare Pages handles SSL, CDN, and uptime.

## License

Content (`*.md`) is © TMK Group, all rights reserved. The site
scaffolding (CSS / layouts) is MIT-licensed for anyone who wants to
copy this pattern for their own privacy site.
