# Stephen Mimi — Portfolio Site

A static, dependency-free portfolio (plain HTML/CSS/JS — no build step) designed
for recruiter visibility in Data, SAP, Cloud and AI roles.

## What's in here

```
index.html    → the whole site (single page, anchored sections)
styles.css    → design system (navy / accent blue / gray, Space Grotesk + Inter + IBM Plex Mono)
script.js     → mobile nav, scroll reveal, active-link highlight, stat count-up
assets/
  Stephen_Mimi_CV.pdf → generated from your uploaded CV, wired to the "Download CV" button
```

No npm install, no framework, no build step. It's ready to deploy as-is.

## Deploy to GitHub Pages (2 options)

### Option A — user site at `mimi-dotcom.github.io` (recommended)
This gives you the cleanest possible URL for a CV: `https://mimi-dotcom.github.io/`

1. On GitHub, create a **new repository** named exactly `mimi-dotcom.github.io`
   (must match your username exactly — this is what makes it a "user site").
2. Upload `index.html`, `styles.css`, `script.js`, and the `assets/` folder to the
   root of that repo (drag-and-drop on github.com works, or use git — see below).
3. GitHub Pages publishes user sites automatically from the `main` branch root —
   no extra settings needed. Give it 1–2 minutes, then visit
   `https://mimi-dotcom.github.io/`.

### Option B — project page inside an existing repo (e.g. `portfolio`)
Your URL will be `https://mimi-dotcom.github.io/portfolio/`.

1. Create or reuse a repo, e.g. `portfolio`, and push these files to its root
   (or to a `docs/` folder).
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from
   a branch**. Pick `main` and `/ (root)` (or `/docs` if you used that folder).
3. Save. GitHub gives you the live URL once it finishes building.

### Using git from the command line (either option)
```bash
git init
git add .
git commit -m "Launch portfolio"
git branch -M main
git remote add origin https://github.com/mimi-dotcom/<repo-name>.git
git push -u origin main
```

## Before you go live — quick checklist

- [ ] **Canonical URL**: `index.html` has `og:url` and a `<link rel="canonical">`
      pointing to `https://mimi-dotcom.github.io/`. If you go with Option B,
      update those two to `https://mimi-dotcom.github.io/<repo-name>/`.
- [ ] **CV file**: `assets/Stephen_Mimi_CV.pdf` was generated from your uploaded
      Word doc. Swap in a newer export any time — just keep the same filename,
      or update the `href` in the "Download CV" button in `index.html`.
- [ ] **LinkedIn/GitHub links**: confirm `linkedin.com/in/stephenmimi` is still
      correct — it's used in the header, contact section, and the page's
      structured data (JSON-LD).
- [ ] **Custom domain (optional)**: if you ever point a domain (e.g.
      `stephenmimi.com`) at this, add a `CNAME` file at the repo root containing
      just the domain name, and update the canonical/OG URLs to match.
- [ ] **Social preview image (optional)**: add a 1200×630 image at
      `assets/og-cover.png` and uncomment/add an `og:image` meta tag in
      `index.html` so LinkedIn/Twitter shares show a card image instead of a
      plain link.

## Why it's built this way (recruiter visibility)

- **Fast & static** — no framework, nothing to build, loads instantly. Search
  engines and recruiters both reward that.
- **SEO metadata** — title, description, Open Graph, Twitter Card, and a
  `Person` JSON-LD block so Google can understand who you are and what you do
  when someone searches your name.
- **One-click CV download** — the PDF is bundled in `assets/`, no redirect to
  Google Drive or LinkedIn required.
- **Keyword-rich structure** — the capability matrix and project tags surface
  SAP / Cloud / AI / Data terms the way a recruiter or ATS skims a page,
  without turning the copy into a keyword dump.
- **Accessible by default** — semantic HTML, visible keyboard focus states,
  skip-to-content link, and `prefers-reduced-motion` support.

## Updating content later

Everything is in `index.html` as plain markup — experience bullets, project
cards, certifications, etc. are each their own block, so you can edit text
directly without touching `styles.css` or `script.js`. If you add or remove a
section, just make sure the `id` on the `<section>` still matches the matching
link in the `<nav>`.
