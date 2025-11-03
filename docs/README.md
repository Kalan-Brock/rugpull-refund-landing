# Rug Pull Refund - Landing Page

This folder contains the GitHub Pages site for **Rug Pull Refund**, a free Android app that helps Solana users recover SOL rent from empty token accounts.

## 🌐 Live Site

- **Production:** https://rugpullrefund.app
- **GitHub Pages:** https://YOUR_USERNAME.github.io/rugpull-refund-landing/

## 📁 Structure

```
docs/
├── index.html           # Homepage with features, FAQ, screenshots
├── download.html        # APK download page with QR code
├── privacy.html         # Privacy policy (required for app stores)
├── download-qr.png      # QR code for mobile downloads
├── robots.txt           # SEO crawler instructions
└── sitemap.xml          # Search engine sitemap
```

## 🚀 Features

- **SEO Optimized:** Comprehensive meta tags, Open Graph, Twitter Cards, Schema.org structured data
- **Mobile Responsive:** Works perfectly on all devices
- **Fast Loading:** Pure HTML/CSS, no frameworks, no build step required
- **Privacy-Focused:** No tracking, no cookies, no analytics by default
- **Accessibility:** Semantic HTML, ARIA labels, keyboard navigation

## 🎯 SEO Keywords Targeted

- Solana wallet cleaner
- Recover SOL rent
- Empty token accounts
- Phantom wallet tools
- Solflare optimization
- Solana Mobile apps
- SPL token cleanup
- Blockchain wallet utilities

## 📱 APK Download

The APK is served from `../release-package/artifacts/RugpullRefund-release.apk` (28.8 MB). Users can:

1. **Scan QR code** on mobile devices to download directly
2. **Click download button** to get the APK file
3. **Follow installation instructions** for side-loading on Android

## 🔧 Local Development

Test the site locally before deploying:

```bash
cd docs/
python3 -m http.server 8000
# Visit http://localhost:8000
```

## 🌍 Deployment

See `../GITHUB_PAGES_SETUP.md` for complete deployment instructions.

Quick deploy:

```bash
git add docs/
git commit -m "Update landing page"
git push pages main
```

## 📊 Analytics (Optional)

To add analytics, insert tracking code in the `<head>` of each HTML file. Privacy-friendly options:

- **Plausible Analytics** - Privacy-focused, GDPR compliant
- **Simple Analytics** - No cookies, minimal footprint  
- **Fathom Analytics** - Privacy-first, fast loading

## 🔗 Important Links to Update

When deploying to production, update these URLs:

1. **QR Code:** Regenerate with production URL
2. **Canonical URLs:** Update in meta tags
3. **Sitemap:** Change domain from rugpullrefund.app to your domain
4. **Robots.txt:** Update sitemap URL
5. **GitHub link:** Replace "yourusername" with your actual GitHub username

## 📈 SEO Checklist

- [x] Title tags under 60 characters
- [x] Meta descriptions under 160 characters
- [x] Open Graph tags for social sharing
- [x] Twitter Card tags
- [x] Schema.org structured data
- [x] Semantic HTML (h1, h2, h3 hierarchy)
- [x] Alt text for all images
- [x] Mobile responsive design
- [x] Fast loading (no heavy frameworks)
- [x] HTTPS enforced (via GitHub Pages)
- [x] Sitemap.xml
- [x] Robots.txt

## 🎨 Branding

- **App Name:** Rug Pull Refund (two words - "Rug Pull" is two separate words)
- **Tagline:** "Reclaim SOL from empty Solana token accounts in one secure tap"
- **Primary Color:** `#667eea` (purple)
- **Accent Color:** `#14F195` (Solana green)
- **Font:** System fonts for fast loading

## 📞 Support

- **Email:** support@rugpullrefund.app
- **GitHub Issues:** https://github.com/yourusername/rugpull-refund-mobile/issues
- **Privacy Policy:** https://rugpullrefund.app/privacy.html

## 📝 License

Open source and community-driven. See main repository for license details.

---

Built with ❤️ for the Solana community 🌞
