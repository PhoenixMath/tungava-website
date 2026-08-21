# Tungava Constructions — Website

Static single-page site. No build step, no dependencies, no framework.
Open `index.html` in a browser to preview locally.

---

## Structure

```
index.html      the entire site (HTML + CSS + JS in one file)
404.html        not-found page
robots.txt      search engine directives
sitemap.xml     update the domain before going live
images/         logo files + site photographs
```

---

## Before going live — checklist

- [x] Replace `YOUR_FORM_ID` in `index.html` with a real Formspree endpoint
- [x] Add site photographs — `images/site-1.jpg` … `site-7.jpg` (7 real project photos)
- [x] Domain already set correctly in `sitemap.xml`, `robots.txt`, and the `og:url` meta tag (`tungavaconstructions.in`)
- [ ] Add `images/hero-quarry.jpg` (1920px wide) — the homepage hero background is still blank
- [ ] Create `images/og-image.jpg` (1200×630) for social sharing previews
- [ ] Fill GSTIN and Udyam number in the footer (currently "add here")
- [ ] Confirm the public contact email — currently `svinfradevelopers8@gmail.com` (note: the Formspree account itself is registered under a different address)
- [ ] Confirm written client consent before publishing the client names section
- [ ] Point the `tungavaconstructions.in` domain at the Cloudflare Pages deployment, if not done already

---

## Photographs

| File | Size | Status |
|---|---|---|
| `hero-quarry.jpg` | 1920px wide, landscape | **Missing** — keep the left third uncluttered, text sits there |
| `site-1.jpg` … `site-7.jpg` | as-is | Done — 7 real project photos in the gallery |
| `og-image.jpg` | 1200×630 | **Missing** — social sharing card |

Compress every image to under 250 KB before committing — use [squoosh.app](https://squoosh.app), free and browser-based. Uncompressed phone photos are 4–8 MB each and will make the site painfully slow on site-office connections.

---

## Editing

Everything lives in `index.html`.

**Colours** — the CSS variables at the top of the `<style>` block. Change once, applies everywhere:

```css
--navy-900:#04162E;   /* header, hero, contact */
--navy-800:#00264D;   /* stats strip */
--navy-700:#03386E;   /* headings, card accents */
--gold:#C6902F;       /* all gold accents */
```

**Content** — each section is marked with an HTML comment (`<!-- ========== SERVICES ========== -->`). Find the section, edit the text.

**Adding a service** — copy any `<article class="card">` block and change the text inside. The grid reflows automatically.

---

## Deploying — Cloudflare Pages (recommended)

1. Push this repo to GitHub
2. [dash.cloudflare.com](https://dash.cloudflare.com) → Workers & Pages → Create → Pages → Connect to Git
3. Select the repo
4. Build settings: **leave the build command empty**, set output directory to `/`
5. Deploy
6. Custom domains → add your domain

Every `git push` to `main` redeploys automatically.

---

## Deploying — GitHub Pages (alternative)

1. Repo → Settings → Pages
2. Source: Deploy from a branch → `main` → `/ (root)`
3. For a custom domain, add a file named `CNAME` containing just your domain, e.g. `tungavaconstructions.in`

GitHub Pages requires a public repo on the free plan. Cloudflare Pages works with private repos.

---

## Logo files

| File | Use |
|---|---|
| `logo-mark.png` | Full-color crest/monogram, navy+gold — light backgrounds only (letterhead, documents) |
| `logo-mark-light.png` | Reversed white+gold crest — used in the site header, footer, and 404 page, all on the dark navy background |
| `logo-full.png` | Full-color stacked lockup with wordmark and tagline, navy+gold — light backgrounds only |
| `logo-horizontal.png` | Full-color wide wordmark with tagline, no crest — for letterhead/document headers where a stacked lockup is too tall |
| `favicon-32.png` | Browser tab icon, cropped from the crest |
| `apple-touch-icon.png` | iOS home-screen icon, 180×180, crest on a solid `--bone` background |

All rebuilt from `Tungava_Master_Logo_Sheet.pptx` (2026-08-21) — treat that file as the source of truth for any future re-export.

These are raster PNGs with transparent backgrounds (source: brand logo sheet). Ask the designer for a vector (AI/EPS/SVG) version before sending to any print or signage vendor.
