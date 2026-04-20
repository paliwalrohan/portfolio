# Deployment Guide

The site is a static folder (`index.html` + `resume.pdf`). You can deploy it to any static host. Here are four options, in order of speed.

---

## Option 1 — Vercel (recommended, ~60 seconds)

Vercel is the fastest path to a live URL with free HTTPS and a custom domain.

### Drag-and-drop (no CLI needed)

1. Go to **https://vercel.com/new**
2. Sign up / sign in (GitHub or email)
3. Click **"Create a New Project" → "Deploy"** (or use the import-from-local flow — on the Vercel dashboard there's a "Drop" zone)
4. Drag the `rohan-portfolio/` folder onto the page
5. Accept the defaults — Framework Preset: **Other**, no build command, output directory: `.`
6. Click **Deploy**

In about 30 seconds you'll get a URL like `https://rohan-portfolio-abcd.vercel.app`. Test it.

### CLI (if you prefer terminal)

```bash
npm install -g vercel
cd rohan-portfolio
vercel            # follow prompts — accept defaults
vercel --prod     # promote to production when you're happy
```

### Add a custom domain (`rohanpaliwal.com` or similar)

1. Buy the domain at Namecheap, Porkbun, or Google Domains (~$10–15/yr)
2. In the Vercel dashboard, open your project → **Settings → Domains**
3. Enter `rohanpaliwal.com` → Vercel shows you the DNS records to add
4. In your domain registrar, add those DNS records (usually one `A` record pointing to `76.76.21.21` plus a `CNAME` for `www`)
5. HTTPS provisioning is automatic. Live within 5–30 minutes.

### Updating the site later

- **If you deployed from a folder via drag-and-drop:** re-drag to re-deploy. Each deploy gets a new preview URL; promote to production via the dashboard.
- **If you used GitHub:** push to `main` and Vercel auto-redeploys.

---

## Option 2 — Netlify (equally good)

1. Go to **https://app.netlify.com/drop**
2. Drag the `rohan-portfolio/` folder onto the drop zone
3. You immediately get a URL like `https://whimsical-panda-abc123.netlify.app`
4. Click the URL, rename it from the dashboard (Site settings → Change site name), or add a custom domain (Domain management → Add custom domain)

Free HTTPS. Free bandwidth (100 GB/mo). No CLI required.

---

## Option 3 — Cloudflare Pages

Best if you want Cloudflare's edge network for speed and free unlimited bandwidth.

### Via GitHub

1. Push `rohan-portfolio/` to a GitHub repo (say `rohan-portfolio`)
2. Go to **https://pages.cloudflare.com** → **Create a project** → **Connect to Git**
3. Pick the repo, accept defaults (no build command, output dir `/`)
4. Deploy. You get a `*.pages.dev` URL

### Direct Upload

1. **Cloudflare Dashboard → Pages → Create → Direct Upload**
2. Drag the `rohan-portfolio/` folder

Custom domain same as Vercel/Netlify — add DNS records, HTTPS is automatic.

---

## Option 4 — GitHub Pages (free, slower setup)

1. Create a new GitHub repo called `yourusername.github.io`
2. Upload `index.html` and `resume.pdf` to the root of the repo
3. In the repo's **Settings → Pages**, select **Branch: main, folder: / (root)**
4. Save. Live at `https://yourusername.github.io` in 1–5 minutes

Good if you already live in GitHub. Custom domains supported; HTTPS is automatic via Let's Encrypt.

---

## Updating content later

The edit loop is always the same:

1. Open `index.html` in VS Code, Sublime, or any text editor
2. Find the section by searching for the comment (e.g. `<!-- ============ EXPERIENCE ============ -->`)
3. Edit the text
4. Save the file
5. Re-deploy:
   - **Vercel/Netlify via drag-drop:** re-drag the folder
   - **Vercel/Netlify/Cloudflare via GitHub:** `git commit && git push`
   - **GitHub Pages:** commit and push; rebuild is automatic

No build step. No cache invalidation to worry about. Changes are live as soon as the host picks them up (usually under 30 seconds).

---

## Troubleshooting

**The resume download doesn't work.** Make sure `resume.pdf` is in the same folder as `index.html` when you deploy. Both need to be at the root of the deployed folder.

**The Google Fonts aren't loading.** Requires HTTPS (which all four hosts above provide automatically). If you open `index.html` by double-clicking locally, some browsers will block the font load over `file://` — use `python3 -m http.server 8000` instead for local testing.

**The social preview image isn't showing when I share the URL on LinkedIn.** You need to add an OG image. Create a 1200×630 JPG, save it as `og.jpg` in the folder, and add this line to `<head>`:

```html
<meta property="og:image" content="https://yourdomain.com/og.jpg" />
```

**I want analytics.** Add one line before `</head>`:

```html
<!-- Plausible (privacy-friendly, paid) -->
<script defer data-domain="rohanpaliwal.com" src="https://plausible.io/js/script.js"></script>
```

Or Google Analytics 4 — paste the GA4 snippet right before `</head>`.

---

## Cost

Every option above has a generous free tier. Expected monthly cost: **$0**. The only money you'd spend is ~$12/year for a custom domain (optional).
