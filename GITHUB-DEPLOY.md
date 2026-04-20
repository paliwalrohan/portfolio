# GitHub + Vercel Deployment Guide

You've created the repo at https://github.com/paliwalrohan/portfolio and given Vercel access. Here's what to do next:

## Step 1: Push your portfolio to GitHub

### Option A: Using Terminal (Mac/Linux)

```bash
# 1. Download your portfolio folder to your computer
# (Download the folder from Claude's file output)

# 2. Navigate to the folder
cd ~/Downloads/rohan-portfolio

# 3. Initialize git and push
git init
git add .
git commit -m "Initial portfolio commit"
git branch -M main
git remote add origin https://github.com/paliwalrohan/portfolio.git
git push -u origin main
```

### Option B: Using GitHub Desktop (Easiest)

1. Download [GitHub Desktop](https://desktop.github.com/)
2. Open GitHub Desktop
3. Click "Add" → "Add Existing Repository"
4. Select your downloaded `rohan-portfolio` folder
5. Click "Publish repository"
6. Choose `paliwalrohan/portfolio`
7. Click "Publish"

### Option C: Upload via GitHub.com

1. Go to https://github.com/paliwalrohan/portfolio
2. Click "uploading an existing file"
3. Drag ALL files from your portfolio folder:
   - `index.html`
   - `headshot.jpg`
   - `resume.pdf`
   - `README.md`
   - `DEPLOY.md`
4. Click "Commit changes"

---

## Step 2: Deploy on Vercel

1. Go to https://vercel.com/new
2. You should see `paliwalrohan/portfolio` in the list
3. Click "Import" next to it
4. Click "Deploy" (no configuration needed)
5. ✅ Wait ~30 seconds → Your site is live!

Vercel will give you a URL like: `portfolio-rohan.vercel.app`

---

## Step 3: Get a Custom Domain (Optional)

### Buy the domain
1. Go to [Namecheap](https://www.namecheap.com) or [Google Domains](https://domains.google)
2. Search for `rohanpaliwal.com` (~$10-15/year)
3. Purchase it

### Connect to Vercel
1. In Vercel, go to your project → Settings → Domains
2. Add `rohanpaliwal.com`
3. Vercel will show you DNS records to add
4. Go to your domain registrar's DNS settings
5. Add the records Vercel provided
6. Wait ~1 hour → Your custom domain is live with HTTPS!

---

## Making Updates Later

After initial deployment, to update your portfolio:

1. Edit files in the `rohan-portfolio` folder
2. Push to GitHub:
   ```bash
   git add .
   git commit -m "Updated experience section"
   git push
   ```
3. Vercel auto-deploys in ~30 seconds ✅

---

## Need Help?

**Common issues:**

- **"Repository not showing in Vercel"**: Make sure the repo is public, or reconnect Vercel to GitHub in Settings
- **"Deploy failed"**: Check that `index.html` is in the root folder (not in a subfolder)
- **"Headshot not showing"**: Make sure `headshot.jpg` is uploaded with exact filename

Email me at paliwalrohan39@gmail.com if stuck!
