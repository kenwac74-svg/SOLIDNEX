# Solidnex — publishable site

Static, dependency-free. `index.html` is the whole site; drop this folder on any host.

## Deploy

**GitHub Pages** — push the contents of this folder to the repo, then Settings → Pages → Branch: `main`, Folder: `/ (root)`. `.nojekyll` is included so underscore-prefixed paths are served as-is.

**Netlify / Vercel / Cloudflare Pages** — no build command, publish directory = this folder.

**Existing web host** — upload the folder contents to the document root over FTP.

## What is local vs remote

Local (in `assets/`): the logo, as SVG (`logo-solidnex-navy.svg`, `logo-solidnex-white.svg`) with the original PNGs kept for the Apple touch icon.

Remote: the five member portraits, five role badges and the advisory placeholder load from `https://www.solidnex.net/assets/imgs/`. **This deploys to solidnex.net, so those are same-origin and work as-is** — no copying needed. If the site ever moves to another domain, copy those 11 images into `assets/imgs/` and swap the URL prefix for `./assets/imgs/`.

Fonts load from CDN (Pretendard via jsDelivr, IBM Plex Mono via Google Fonts). The hero animation is drawn in canvas — there is no video file to host.

## Before going live

- [ ] Replace the traced SVG logos with the real vector master if one exists (see readme.md, Known substitutions).
- [ ] Add a real `og.png` social card at `assets/imgs/og.png` (1200×630); the `og:image` tag already points there.
- [ ] Confirm `og:url` and `<link rel="canonical">` match the final domain.
- [ ] Add analytics if wanted — nothing is tracked at present.
- [ ] Decide what the 상담 문의 buttons should do; they currently jump to the contact section, which offers `mailto:info@solidnex.net`.

## Accessibility and behaviour

KO/EN toggle swaps every string on the page. Header collapses to a ☰ menu under 860px. Portraits are colour, settling to full saturation on hover; on touch devices they stay full colour. Career panels open on hover, tap, or keyboard focus. `prefers-reduced-motion` stops the hero animation and all transitions.
