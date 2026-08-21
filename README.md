# romankc.com.np

Personal site for Roman KC — full-stack product engineer, Kathmandu.

Static, hand-built, no framework and no build step. One `index.html` with
inlined CSS and ~40 lines of JS. Served by GitHub Pages behind Cloudflare.

## Structure

```
index.html            the whole site
assets/images/        profile photo + Open Graph cover
CNAME                 www.romankc.com.np
robots.txt
sitemap.xml
```

## Editing

Everything lives in `index.html`:

- **Colours** — the `:root` token block at the top of `<style>`. Change a token
  once and it updates light and dark together. Dark values are repeated in
  three places (`prefers-color-scheme`, the nesting fallback, and
  `[data-theme="dark"]`) so the manual toggle wins in both directions.
- **Projects** — the `<article class="card">` blocks under `#work`.
- **Earlier work** — the `.archive__row` blocks under `#archive`.
- **Social preview** — regenerate `assets/images/og-cover.png` if the tagline
  changes; it is referenced by the `og:image` and `twitter:image` meta tags.

## Deploy

Push to `master`. GitHub Pages rebuilds automatically; Cloudflare caches in
front of it, so purge the cache if a change does not appear within a few
minutes.
