# Rohan Paliwal — Personal Portfolio

A single-file, zero-build-step portfolio site for Rohan Paliwal, Manager of Product Management at Western Union. Designed to be shared with recruiters and hiring managers immediately.

---

## 1. Positioning Summary

**Rohan Paliwal is a B2B2C product leader who ships self-serve software where the stakes are real** — fintech at Western Union, QSR kiosks at GRUBBRR, financial trading workflows at BlackRock. The portfolio is positioned around one differentiated thesis: he does his best work in multi-sided markets where user, partner, and business each need to win in the same transaction.

Headline credibility markers the site leads with:
- **O-1A Extraordinary Ability Visa** recipient
- **Manager, Product Management at Western Union** — Miami, FL
- Grew **WU Rewards from $1M to $7M ARR in 12 months**, scaled to **10+ markets**
- Published by **Product-Led Alliance** (2 articles + 1 framework template)
- **Top 5% PM expert on TopMate**, PM Coach at **Leland**, member of **Supra**
- **Udemy instructor** — "B2B2C PM 101" with 620+ enrollments across 81 countries
- **Carnegie Mellon University** — M.S. ISM (STEM, GPA 3.80), Product Management concentration

---

## 2. Site Architecture

Single-page scrollable site with anchored sections. No build step. No framework. No external runtime dependencies beyond Google Fonts.

```
index.html          ← the entire site (HTML + inline CSS + inline JS), ~64 KB
resume.pdf          ← the resume linked from the Contact section
README.md           ← this file
DEPLOY.md           ← deployment instructions (Vercel / Netlify / GitHub Pages / Cloudflare Pages)
```

Sections in reading order:
1. **Hero** — positioning statement, O-1A badge, "currently" card, headline impact strip (4 metrics), company marquee
2. **About** — personal philosophy, career throughline, pull quote from PLA article
3. **Experience** — three roles (WU → GRUBBRR → BlackRock) with verified, quantified impact bullets
4. **Selected Work** — four case studies with Context / Problem / Role / Strategy / Execution / Outcome / Lessons structure (expandable)
5. **Skills & Expertise** — 6 organizing buckets + "Toolbelt" row for day-to-day tools
6. **Signal** — two verified LinkedIn testimonials
7. **Writing, Teaching & Credentials** — 4 publications/courses + 8-card credentials grid (Leland, TopMate, Supra, Judging, CMU, MIT Manipal, O-1A, Certifications)
8. **Contact** — email, LinkedIn, published work, resume download + recruiter "what I'm looking for" card

---

## 3. Design System

**Aesthetic direction:** Refined editorial. Warm paper-cream base rather than stark black-white. Fraunces serif display paired with Inter body and JetBrains Mono for metadata. One signal color (burnt orange, `#c2410c`). Paper-grain overlay. Asymmetric hero with "currently" side-card bordered in a Pentagram-style color stripe.

**Tokens** (all defined as CSS variables at the top of the file):
- `--bg` `#f4f1ea` — warm paper
- `--bg-panel` `#ece7dc` — subtle contrast panel
- `--ink` `#16171a` — near-black
- `--ink-soft` `#2b2d31` — body copy
- `--muted` `#6b6a63` — warm grey (metadata)
- `--accent` `#c2410c` — burnt orange
- `--accent-soft` `#f0d7c5` — accent background (used on the O-1A badge)
- `--rule` `#2322201a` — hairline dividers

**Type:**
- Display: **Fraunces** (variable, opsz 9–144) — used with italic for accents
- Body: **Inter** 400/500/600
- Metadata: **JetBrains Mono** 400/500
- All loaded from Google Fonts over HTTPS with `preconnect` for fast boot

**Motion:** Reveal-on-scroll via IntersectionObserver, a single marquee animation, hover micro-interactions on nav links and contact rows. All motion respects `prefers-reduced-motion`.

**Accessibility:** Semantic HTML (`<nav>`, `<section>`, `<article>`, `<aside>`, `<figure>`, `<blockquote>`, `<details>`/`<summary>`), AA-contrast color pairings, keyboard-navigable, ARIA labels on the nav and hero, focus states inherited from browser defaults.

**SEO:** Page title, meta description, Open Graph + Twitter cards, canonical URL, JSON-LD `Person` schema with `jobTitle`, `alumniOf`, `sameAs`, `knowsAbout`, and `worksFor`. Favicon is an inline SVG (no separate file needed).

---

## 4. Tone of Voice

- Executive, thoughtful, concrete
- Leads with the *decision* and the *metric*, not the feature list
- No buzzwords ("results-driven", "passionate about innovation", "team player" — all banned)
- Serif italics used sparingly on accent words to create a deliberate editorial voice
- Recruiter-readable in under 30 seconds above the fold

---

## 5. Editing the Site

The whole site is one HTML file. To edit any content, open `index.html` in a text editor — every section is clearly commented (`<!-- ============ EXPERIENCE ============ -->`, etc.).

Common edits and where to find them:

| What you want to change | Where it lives |
|---|---|
| Your name / hero tagline | `<header class="hero">` — near the top |
| Current role / side card | `<aside class="hero-side">` |
| The 4 headline metrics | `<div class="impact-strip">` |
| Company marquee | `<div class="marquee-track">` (remember to update both copies — the second one is a duplicate for seamless scrolling) |
| Experience bullets | `<section id="experience">` |
| A case study | Find the `<article class="case">` for that case |
| Skills | `<section id="skills">` |
| Testimonials | `<section id="voices">` |
| Writing / publications | `<section id="writing">` — first `.writing-list`, then `.creds-grid` for the credential cards |
| Contact links | `<section id="contact">` |
| Resume download | Replace `resume.pdf` in the folder; the link already points to `resume.pdf` |
| Colors / fonts / spacing | `:root { ... }` at the top of the `<style>` block |

There is no build step. Save the file and refresh the browser.

---

## 6. Running Locally

You need zero dependencies. Any of these will work:

```bash
# Python (pre-installed on macOS and most Linux)
cd rohan-portfolio
python3 -m http.server 8000
# Then open http://localhost:8000

# OR — Node (if you have it)
npx serve .

# OR — just double-click index.html in Finder/Explorer
#     (some browsers limit local file permissions but the site will render)
```

---

## 7. Deploying

See `DEPLOY.md` for complete step-by-step instructions on Vercel, Netlify, Cloudflare Pages, and GitHub Pages. Short version: drag the `rohan-portfolio/` folder onto **https://vercel.com/new** and you'll have a live URL in about 60 seconds.

---

## 8. Content Sourcing

Every claim on the site is grounded in one of three sources:
1. The Notion portfolio PDF export (provided)
2. The resume PDF (provided) — `RohanPaliwal_PM_Apr2026.pdf`
3. Public, verifiable third-party sources: Product-Led Alliance articles (Nov 2025 + Mar 2026), LinkedIn endorsement excerpts surfaced in search snippets, ZoomInfo profile, Udemy course listing

Nothing was fabricated. A few copy choices worth flagging:
- The two testimonials are real LinkedIn recommendations I saw in search snippets. Attribution is conservative ("Hiring Manager — Western Union", "Colleague — GRUBBRR") because I couldn't verify the full names of the endorsers from snippets alone. If you have their permission, adding names and companies would make these testimonials stronger.
- Rohan's phone number is in the resume PDF but is **deliberately not on the public site** for privacy. The site funnels recruiters to email / LinkedIn / resume download instead.
- The "Let's Cook" blog post link currently points to Rohan's LinkedIn profile — if the post has a direct LinkedIn article URL, swap it in.

---

## 9. Placeholders / Nice-to-haves for a Future Pass

- **Custom domain** (e.g., `rohanpaliwal.com`) — 5-minute setup on any host, see `DEPLOY.md`
- **OG image** — right now OG tags use the site URL; adding a 1200×630 preview image (e.g., Rohan's headshot + name + tagline) would make LinkedIn/Twitter shares look branded. Generate at Canva or Figma, save as `og.jpg`, then add `<meta property="og:image" content="/og.jpg" />` to `<head>`.
- **Personal photo in the hero** — the current hero is typographic; if you want a portrait, drop a square image into the hero-side card.
- **Case study artifacts** — if any of the Notion project portfolio items (IntelliSight, Muse, Doolingo, Spotify Social, Disney+ Deloitte, Happiness Indicator, PM School Twitch) have PDF write-ups you'd like linked, we can add a second "Earlier work" sub-section.
- **Analytics** — Plausible, Fathom, or GA4. One `<script>` in `<head>`.
- **Scheduling** — a Calendly / Cal.com link could be added to the Contact section as a fifth link.

---

## 10. File Inventory

```
rohan-portfolio/
├── index.html       64 KB   — the whole site
├── resume.pdf      179 KB   — Rohan Paliwal, PM, April 2026
├── README.md        (this file)
└── DEPLOY.md        (deployment instructions)
```

No build step. No `node_modules`. No secrets. No environment variables. Portable to any static host on earth.
