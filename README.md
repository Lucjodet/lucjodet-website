# lucjodet.com

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

### Custom domain (lucjodet.com)

In Settings → Pages, add `lucjodet.com` as the custom domain (GitHub creates a `CNAME` file), then point the domain's DNS: an `A`/`ALIAS` record to GitHub Pages, or a `CNAME` record from `www` to `<your-username>.github.io`.
