# www.lucjodet.com

Personal website of Luc Jodet — entrepreneur, investor, and PhD candidate at EPFL researching AI and job displacement.

A single self-contained HTML file (`index.html`): no build step, no dependencies.

## Local preview

Open `index.html` in a browser.

## Deploy on GitHub Pages

1. Create a repo on GitHub (e.g. `lucjodet-website`) and push this folder:
   ```
   git remote add origin https://github.com/<your-username>/lucjodet-website.git
   git push -u origin main
   ```
2. On GitHub: Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)` → Save.
3. The site goes live at `https://<your-username>.github.io/lucjodet-website/` a minute later.

### Custom domain (www.lucjodet.com)

In Settings → Pages, add `www.lucjodet.com` as the custom domain (GitHub writes it to the `CNAME` file), then set the domain's DNS at the registrar:

- `CNAME` record: `www` → `lucjodet.github.io.`
- Four `A` records on the apex (`lucjodet.com`) → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`, so the bare domain redirects to `www`.

Once the DNS check passes, tick **Enforce HTTPS**.

## SEO housekeeping

- `.github/workflows/stamp-and-ping.yml` runs on every content push to `main`: it stamps `<lastmod>` in `sitemap.xml` and `dateModified` in `index.html` with the current date, commits the stamp, and pings IndexNow once Pages has deployed. Nothing to do by hand.
- `llms.txt` is a plain-text summary for AI crawlers. Keep its dates and facts in sync with `index.html` when the biography changes.
- The Person schema in `index.html` lists every public profile under `sameAs`. When a new profile exists (ORCID, Wikidata, Google Scholar), add it there and add the site URL on the profile too, so the links are reciprocal.

### Known gap: apex HTTPS

GitHub Pages issues a TLS certificate only for the configured custom domain (`www`). `https://lucjodet.com` therefore serves GitHub's wildcard certificate and browsers warn. Two fixes:

1. Set the custom domain to the apex `lucjodet.com` in Settings → Pages (GitHub then issues one certificate for both hosts and redirects `www` → apex). Update the canonical URL, `og:url`, sitemap, JSON-LD `@id`s, `SITE_URL` in the workflow, and the Gandi redirect for `lucopedia.com` to match.
2. Or keep `www` canonical and put DNS behind Cloudflare with a redirect rule from the apex.

Until one of these is done, make sure `lucopedia.com` redirects to `https://www.lucjodet.com/`, not the apex.
