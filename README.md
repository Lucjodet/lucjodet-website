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
