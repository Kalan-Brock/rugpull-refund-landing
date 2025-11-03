# GitHub Pages Setup Guide for Rug Pull Refund

## 🚀 Quick Start - Deploy Your Landing Page

Follow these steps to create a new GitHub repository and deploy the Rug Pull Refund landing page with GitHub Pages.

---

## Step 1: Create New GitHub Repository

1. **Go to GitHub** and log in to your account
2. **Click the "+" icon** in the top-right corner and select "New repository"
3. **Repository Settings:**
   - **Name:** `rugpull-refund-landing` (or `rugpullrefund.app` if you own the domain)
   - **Description:** "Official landing page for Rug Pull Refund - Solana wallet cleaner Android app"
   - **Visibility:** Public (required for free GitHub Pages)
   - **Initialize:** Do NOT add README, .gitignore, or license (we'll add from local)
4. **Click "Create repository"**

---

## Step 2: Initialize Git and Push Files

Open your terminal in the project root and run:

```bash
# Navigate to the project directory
cd /home/kalan/projects/rugpull-refund-mobile

# Initialize git if not already initialized
git init

# Add the GitHub remote (replace YOUR_USERNAME with your GitHub username)
git remote add pages https://github.com/YOUR_USERNAME/rugpull-refund-landing.git

# Create .gitignore for the landing page repo
cat > .gitignore << 'EOF'
# Android build artifacts (not needed for landing page)
*.apk
*.aab
android/build/
android/app/build/
node_modules/
.gradle/

# Keep only docs folder and release package for download
EOF

# Stage only the docs folder and release artifacts
git add docs/
git add release-package/artifacts/
git add release-package/assets/

# Create initial commit
git commit -m "Initial commit: GitHub Pages landing site for Rug Pull Refund"

# Push to GitHub
git branch -M main
git push -u pages main
```

---

## Step 3: Enable GitHub Pages

1. **Go to your repository** on GitHub (https://github.com/YOUR_USERNAME/rugpull-refund-landing)
2. **Click "Settings"** tab
3. **Scroll to "Pages"** in the left sidebar (under "Code and automation")
4. **Configure GitHub Pages:**
   - **Source:** Deploy from a branch
   - **Branch:** `main`
   - **Folder:** `/docs` (very important!)
   - Click **"Save"**
5. **Wait 2-3 minutes** for deployment
6. **Your site will be live at:** `https://YOUR_USERNAME.github.io/rugpull-refund-landing/`

---

## Step 4: Custom Domain Setup (Optional but Recommended)

If you own `rugpullrefund.app`:

### 4a. Configure DNS (at your domain registrar)

Add these DNS records:

```
Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io

Type: A (add all 4 records)
Name: @
Value: 185.199.108.153
Value: 185.199.109.153
Value: 185.199.110.153
Value: 185.199.111.153
```

### 4b. Configure Custom Domain in GitHub

1. In **Settings > Pages**, scroll to **"Custom domain"**
2. Enter: `rugpullrefund.app`
3. Click **"Save"**
4. Wait for DNS check (can take up to 24 hours)
5. Once verified, **check "Enforce HTTPS"**

---

## Step 5: Update Download Links

After your site is live, update the QR code to point to the correct URL:

```bash
cd /home/kalan/projects/rugpull-refund-mobile/docs

# If using GitHub Pages default URL:
qrencode -o download-qr.png -s 10 -m 2 "https://YOUR_USERNAME.github.io/rugpull-refund-landing/release-package/artifacts/RugpullRefund-release.apk"

# If using custom domain:
qrencode -o download-qr.png -s 10 -m 2 "https://rugpullrefund.app/release-package/artifacts/RugpullRefund-release.apk"

# Commit and push the updated QR code
git add docs/download-qr.png
git commit -m "Update QR code with production URL"
git push pages main
```

---

## Step 6: SEO Optimization & Social Sharing

### 6a. Create Social Preview Image

Create a 1200x630px image with:
- App icon
- "Rug Pull Refund" text
- "Reclaim SOL from Empty Solana Token Accounts"
- Solana logo/branding

Save as `docs/assets/social-preview.png` and update meta tags in HTML files.

### 6b. Submit to Search Engines

**Google Search Console:**
1. Go to https://search.google.com/search-console
2. Add property: `rugpullrefund.app` or your GitHub Pages URL
3. Verify ownership (DNS or HTML file method)
4. Submit sitemap: Create `docs/sitemap.xml` (see example below)

**Bing Webmaster Tools:**
1. Go to https://www.bing.com/webmasters
2. Add site and verify
3. Import from Google Search Console (faster)

### 6c. Create sitemap.xml

```bash
cat > docs/sitemap.xml << 'EOF'
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://rugpullrefund.app/</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://rugpullrefund.app/download.html</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
  <url>
    <loc>https://rugpullrefund.app/privacy.html</loc>
    <lastmod>2025-01-15</lastmod>
    <changefreq>monthly</changefreq>
    <priority>0.5</priority>
  </url>
</urlset>
EOF

git add docs/sitemap.xml
git commit -m "Add sitemap for SEO"
git push pages main
```

---

## Step 7: Marketing & Traffic Generation

### Organic SEO Keywords (already optimized in HTML):
- Solana wallet cleaner
- Recover SOL rent
- Empty token accounts
- Phantom wallet tools
- Solflare optimization
- Solana Mobile apps

### Share on Social Media:
1. **Twitter/X:** Tag @solana, mention Phantom, Solflare
2. **Reddit:** r/solana, r/SolanaMobile, r/CryptoCurrency
3. **Discord:** Solana Discord, Phantom Discord, crypto communities
4. **Telegram:** Solana groups, crypto trading groups

### Content Marketing Ideas:
- Write Medium article: "How to Recover Hidden SOL from Your Phantom Wallet"
- Create YouTube tutorial video
- Share on Product Hunt
- Submit to crypto app directories (DappRadar, CoinGecko, etc.)

---

## Step 8: Analytics (Optional)

Add Google Analytics or privacy-friendly analytics:

```html
<!-- Add to <head> in all HTML files -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Or use privacy-friendly alternatives:
- Plausible Analytics
- Simple Analytics
- Fathom Analytics

---

## Troubleshooting

### Site not loading after 5 minutes?
- Check Settings > Pages shows "Your site is live at..."
- Ensure `/docs` folder is selected as source
- Try clearing browser cache
- Check browser console for errors

### APK download not working?
- Make sure `release-package/artifacts/RugpullRefund-release.apk` is committed to git
- Check file size isn't exceeding GitHub's 100MB limit (yours is 28.8 MB, so OK)
- Verify download link paths in HTML match repository structure

### Custom domain not working?
- DNS propagation can take 24-48 hours
- Verify DNS records with `dig rugpullrefund.app` or `nslookup rugpullrefund.app`
- Ensure "Enforce HTTPS" is checked after DNS verification

### QR code not scanning?
- Test QR code with multiple apps (built-in camera, QR scanner apps)
- Regenerate with higher error correction: add `-l H` flag to qrencode command
- Ensure URL in QR code is correct (no typos)

---

## Maintenance Checklist

**Weekly:**
- [ ] Check Google Search Console for indexing issues
- [ ] Monitor download counts (if analytics enabled)
- [ ] Respond to GitHub issues/questions

**Monthly:**
- [ ] Update sitemap if content changes
- [ ] Check for broken links
- [ ] Review SEO rankings for target keywords

**Per App Update:**
- [ ] Update APK file in `release-package/artifacts/`
- [ ] Update version numbers in download.html
- [ ] Regenerate QR code if download URL changes
- [ ] Update "Last Updated" date in privacy.html
- [ ] Commit and push changes

---

## Next Steps

1. **Create GitHub repository** and push code (Steps 1-2)
2. **Enable GitHub Pages** (Step 3)
3. **Update QR code** with production URL (Step 5)
4. **Create social preview image** for better sharing (Step 6a)
5. **Submit to search engines** (Step 6b)
6. **Share on social media** to drive initial traffic (Step 7)
7. **Monitor and optimize** based on analytics (Step 8)

---

## Support

If you run into issues:
- Check GitHub Pages documentation: https://docs.github.com/en/pages
- Review GitHub Actions logs if using custom workflows
- Test locally with: `python3 -m http.server 8000` in the docs/ folder

Good luck with your launch! 🚀🌞
