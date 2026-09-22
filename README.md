# fol.kz — Folkz Studio

Static one-page site for Folkz Studio. No build step, no dependencies.

## Structure

```
index.html          Home page
404.html            Not-found page (Cloudflare Pages serves it automatically)
_headers            Security headers + long cache for /assets
robots.txt, sitemap.xml
assets/
  folkz-wordmark.svg, folkz-wordmark-light.svg
  favicon.svg, favicon-32.png, apple-touch-icon.png, og-image.png
  icons/untime.png, opened.png, camperbase.png
```

## Deploy on Cloudflare Pages

1. Push this folder to a GitHub repo (repo root = this folder).
2. Cloudflare dashboard → Workers & Pages → Create → Pages → Connect to Git → pick the repo.
3. Build settings: Framework preset **None**, Build command **empty**, Build output directory **/**.
4. Deploy. Every push to `main` redeploys.
5. Custom domains → add `fol.kz` (and `www.fol.kz`). For the apex domain, fol.kz's nameservers must point to Cloudflare.

## Editing

- App cards live in `index.html` under `<section id="apps">`.
- Assets in `/assets` are cached for a year. When you replace a file, rename it (e.g. `untime-v2.png`) and update the reference so visitors get the new one.
