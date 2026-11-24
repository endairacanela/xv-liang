# AGENTS.md

## Architecture
A single static page (a XV años / quinceañera invitation) with no framework, no package.json and no build.
Netlify publishes `public/` as-is (see `netlify.toml`). There is no server code, database or form handling.

## Key files
- `public/index.html` — all markup, CSS and JS inline (~77 KB). Flow: envelope "gate" → invitation card → detail blocks (date, venue/map, dress code, gallery) → RSVP.
- `public/_headers` — Netlify headers: `X-Robots-Tag: noindex`, long-lived caching for `/images/*`.
- `public/images/` — gallery photos, map, logo.
- `public/og-image.jpg` + Open Graph meta tags in `<head>` — link preview for WhatsApp sharing.

## Conventions / non-obvious decisions
- Content is in Spanish (es-MX). Keep it that way.
- The page is intentionally hidden from search engines (meta robots + header). Don't remove that.
- Open Graph URLs are absolute and point at `https://website-e44492.netlify.app`; update them if the domain changes. WhatsApp caches previews — test with `?v=N`.
- RSVP is done via `wa.me` deep links (confirm / decline), not a form. If a form is ever needed, use Netlify Forms.
- `<audio id="bgm" src="">` is deliberately empty; the music button stays hidden until a source is set.
- Edit the HTML in place; don't introduce a framework or build step.
