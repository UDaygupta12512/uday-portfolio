# Uday Gupta — Portfolio

Single-file static site. Everything (HTML, CSS, JS) lives in `index.html` — no build
step, no dependencies, no `node_modules`. Just upload and go.

## Files in this folder

| File | Purpose |
|---|---|
| `index.html` | The entire site. This is the only file that matters. |
| `robots.txt` | Tells search engines to index everything. |
| `sitemap.xml` | Single-page sitemap for SEO. |
| `README.md` | This file. |

## Deploy — pick one

### Vercel (recommended, free)
1. Go to [vercel.com/new](https://vercel.com/new)
2. Drag this folder onto the page, or connect a GitHub repo containing it
3. Framework preset: **Other** — no build command needed
4. Deploy

### Netlify (free)
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag this folder directly onto the page
3. Done — live instantly, no config

### GitHub Pages (free)
1. Push these files to a repo (e.g. `uday-gupta-portfolio`)
2. Repo Settings → Pages → Source: `main` branch, root folder
3. Site goes live at `https://<username>.github.io/<repo-name>/`
4. Optional: add a `CNAME` file with your custom domain

### Lovable (already set up)
Upload `index.html` through the Lovable project editor and republish —
this is the same host referenced throughout the site's own links
(`uday-gupta-portfolio.lovable.app`).

## Before you go live — update these

- **Domain**: `robots.txt`, `sitemap.xml`, and the `og:url` / `canonical` /
  JSON-LD tags inside `index.html` all currently point to
  `uday-gupta-portfolio.lovable.app`. If you deploy elsewhere, update those.
- **Contact form**: the form currently opens the visitor's email client with
  a pre-filled message (`mailto:`). If you want it to submit silently in the
  background instead, wire it up to a service like Formspree or EmailJS —
  search `submitForm` inside `index.html` to find the spot.

## Good to know

- **GitHub API rate limit**: the Live Build Log and Open Source stats pull
  live data from `api.github.com` without authentication, which is capped
  at 60 requests/hour per visitor IP. The site caches results in
  `sessionStorage` for 10 minutes to stay well under that. If the feed
  ever fails to load, it just hides itself — no broken error text.
- **No backend required**: there is no server, database, or API key
  anywhere in this project. Everything either runs client-side or calls
  public, unauthenticated third-party APIs (GitHub, GitHub stats/streak
  image generators).
- **Zero build step**: don't run this through webpack/vite/etc. — it's
  meant to be served as-is.
