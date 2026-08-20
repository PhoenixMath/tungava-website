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

- [ ] Replace `YOUR_FORM_ID` in `index.html` with a real Formspree endpoint
- [ ] Add site photographs: `images/hero-quarry.jpg`, `images/site-1.jpg` … `site-6.jpg`
- [ ] Update the domain in `sitemap.xml`, `robots.txt`, and the `og:url` meta tag
- [ ] Fill GSTIN and Udyam number in the footer (currently "add here")
- [ ] Confirm the email address — currently still `svinfradevelopers8@gmail.com`
- [ ] Confirm written client consent before publishing the client names section
- [ ] Create `og-image.jpg` (1200×630) for social sharing previews

---

## Photographs

| File | Size | Notes |
|---|---|---|
| `hero-quarry.jpg` | 1920px wide | Landscape. Keep the left third uncluttered — text sits there |
| `site-1.jpg` … `site-6.jpg` | 1200×900 | Gallery |
| `og-image.jpg` | 1200×630 | Social sharing card |

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
| `logo-horizontal.svg` | Letterhead, invoices, documents (light backgrounds) |
| `logo-horizontal-light.svg` | Dark/navy backgrounds — used in the site footer |
| `logo-mark.svg` | Monogram alone, light backgrounds |
| `logo-mark-light.svg` | Monogram alone, dark backgrounds — used in the site header |
| `logo-favicon.svg` | Browser tab, app icons |

The wordmark uses live text with a font fallback. Before sending to any print or signage vendor, open the file in Inkscape and use **Path → Object to Path** to convert the letters to outlines.
