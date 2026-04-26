# Quick Start Guide

Get your RAMD.ai website live in minutes.

## ⚡ 60-Second Setup

### 1. Local Testing (Immediate)
```bash
# Navigate to project folder
cd ramd-ai-website

# Start local server
python3 -m http.server 8000

# Open browser
# Visit: http://localhost:8000
```

### 2. GitHub Pages (5 minutes)
```bash
# Setup git
git init
git add .
git commit -m "RAMD.ai website launch"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/ramd-ai-website.git
git push -u origin main
```

Then:
1. Go to repository Settings → Pages
2. Select "Deploy from a branch" → main → root
3. Wait 2 minutes, visit `https://YOUR_USERNAME.github.io/ramd-ai-website/`

### 3. Custom Domain (Bonus)
Edit these DNS records at your domain registrar:
```
A Record:     185.199.108.153
CNAME Record: YOUR_USERNAME.github.io
```

Then add your domain in GitHub Pages settings.

---

## 🔧 Quick Customization

### Change Email Address
**Find & Replace** in `index.html`:
- Search: `info@ramdfz.com`
- Replace with: `your-email@company.com`

### Change Colors
Edit CSS variables (~line 20):
```css
:root {
    --primary: #0F4C75;      /* Main blue */
    --accent: #FFB703;        /* Gold highlights */
    --secondary: #1B7BA6;     /* Light blue */
    --dark: #0A1E28;          /* Dark backgrounds */
}
```

### Update Content
All text is clearly labeled in HTML:
- Hero section: Search for `<h1>` and `<p class="tagline">`
- Solution cards: Find `<h3>` within `.solution-card` divs
- Benefits section: Look for `<h4>` in benefit items
- Footer: Find `<footer>` section

---

## 📁 File Structure

```
├── index.html          ← Everything is here!
├── README.md           ← Full documentation
├── DEPLOYMENT.md       ← Deployment instructions
├── BRAND_GUIDE.md      ← Brand guidelines
├── QUICK_START.md      ← This file
├── package.json        ← Node.js metadata
└── .gitignore          ← Git ignore rules
```

---

## ✅ Pre-Deployment Checklist

- [ ] Tested locally (works in Chrome, Firefox, Safari)
- [ ] Updated email address to your domain
- [ ] Updated any custom content/messaging
- [ ] Checked mobile view (looks good on iPhone)
- [ ] Verified all links work
- [ ] Contact button opens email correctly
- [ ] Committed to GitHub
- [ ] Enabled GitHub Pages
- [ ] Custom domain configured (if using)
- [ ] Site loads in < 3 seconds

---

## 🆘 Troubleshooting

| Issue | Solution |
|-------|----------|
| Site not live after push | Wait 5 minutes for rebuild |
| Custom domain not working | Verify DNS records with [dnschecker.org](https://dnschecker.org) |
| Site looks different locally | Clear browser cache (Ctrl+Shift+Delete) |
| Email button not working | Correct - opens user's email client only |
| Mobile looks squished | Zoom to 100% and refresh |

---

## 🚀 Next Steps

1. **Test Locally**: Run Python server and open in browser
2. **Customize**: Update email, colors, content as needed
3. **Commit**: Push to GitHub
4. **Deploy**: Enable GitHub Pages
5. **Monitor**: Check site loads correctly
6. **Iterate**: Update content as business evolves

---

## 📞 Support Resources

- **GitHub Pages Help**: [docs.github.com/pages](https://docs.github.com/en/pages)
- **DNS Configuration**: [dnschecker.org](https://dnschecker.org)
- **Browser Testing**: Test in Chrome, Firefox, Safari, Edge
- **Mobile Testing**: Use Chrome DevTools (F12 → Toggle Device Toolbar)

---

## 🎯 Key Features Recap

✅ Single HTML file (no build process needed)
✅ Mobile responsive (works on all devices)
✅ Email contact (opens user's email client)
✅ Smooth animations (professional look)
✅ Fast loading (optimized performance)
✅ SEO friendly (proper meta tags)
✅ Zero external dependencies (works offline)

---

## 💡 Pro Tips

1. **Search Engine Optimization**
   - Add your business info to meta tags
   - Create `sitemap.xml` and `robots.txt`
   - Submit to Google Search Console

2. **Analytics** (Optional)
   - Add Google Analytics ID
   - Track visitor behavior
   - Optimize based on data

3. **Performance**
   - Site loads in < 1 second
   - Uses system fonts (no slow font loading)
   - Minimal JavaScript

4. **Updates**
   - Make changes to `index.html`
   - Commit: `git add . && git commit -m "Update"`
   - Push: `git push`
   - Auto-deploys in 1-2 minutes

---

## 🎓 Learning Resources

- **CSS Grid**: [MDN Grid Guide](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- **Flexbox**: [CSS-Tricks Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- **Git Basics**: [GitHub Docs](https://docs.github.com/en/get-started)
- **HTML Structure**: [MDN HTML Guide](https://developer.mozilla.org/en-US/docs/Learn/HTML)

---

**You're all set!** 🎉

Your RAMD.ai website is production-ready. Deploy it, customize it, and start connecting with your customers.

Questions? Check the full documentation in README.md and DEPLOYMENT.md.
