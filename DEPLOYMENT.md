# RAMD.ai Website - Deployment Guide

This guide covers all deployment options for your RAMD.ai website.

## Prerequisites

- Git installed on your computer
- GitHub account (for GitHub Pages deployment)
- Web browser for testing

## 🚀 Deployment Options

### Option 1: GitHub Pages (Recommended - Free & Easy)

#### Step 1: Create GitHub Repository
1. Go to [github.com/new](https://github.com/new)
2. Create a new repository named `ramd-ai-website` (or similar)
3. **Do NOT** initialize with README (we already have one)
4. Click **Create repository**

#### Step 2: Push Code to GitHub
```bash
# Navigate to your project folder
cd ramd-ai-website

# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit changes
git commit -m "Initial commit: RAMD.ai website launch"

# Rename branch to main (if needed)
git branch -M main

# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/ramd-ai-website.git

# Push to GitHub
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

#### Step 3: Enable GitHub Pages
1. Go to your repository on GitHub
2. Navigate to **Settings** (gear icon)
3. In the left sidebar, click **Pages**
4. Under "Build and deployment":
   - Source: Select **Deploy from a branch**
   - Branch: Select **main**
   - Folder: Select **/ (root)**
5. Click **Save**
6. GitHub will automatically deploy your site

#### Step 4: Access Your Website
After 1-2 minutes, your website will be live at:
```
https://YOUR_USERNAME.github.io/ramd-ai-website/
```

**Note**: To use your custom domain (ramd.ai):
1. In **Settings** → **Pages**
2. Under "Custom domain", enter your domain: `ramd.ai`
3. Update your domain's DNS settings with:
   - A record pointing to GitHub's IP: `185.199.108.153`
   - CNAME record pointing to: `YOUR_USERNAME.github.io`

---

### Option 2: Traditional Web Host (Bluehost, Hostinger, etc.)

#### Step 1: Upload Files
1. Log into your hosting provider's control panel
2. Use **File Manager** or **FTP** client
3. Navigate to **public_html** folder
4. Upload `index.html` to this folder

#### Step 2: Access Your Website
Visit your domain (e.g., `ramd.ai`)

**Popular Hosting Providers**:
- Bluehost
- Hostinger
- GoDaddy
- SiteGround
- A2 Hosting

---

### Option 3: Docker Deployment

Create a `Dockerfile` for containerized deployment:

```dockerfile
FROM nginx:alpine

# Copy website files
COPY index.html /usr/share/nginx/html/

# Expose port
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
```

Deploy with:
```bash
docker build -t ramd-ai-website .
docker run -p 80:80 ramd-ai-website
```

---

### Option 4: Netlify Deployment

#### Step 1: Connect GitHub
1. Go to [netlify.com](https://netlify.com)
2. Sign up with GitHub account
3. Click **Connect repository**
4. Select your RAMD repository

#### Step 2: Configure Build
- **Base directory**: `/` (leave blank)
- **Build command**: (leave blank - not needed)
- **Publish directory**: `.` (current directory)

#### Step 3: Deploy
Click **Deploy site**. Your site will be live in seconds!

**Advantages**:
- Automatic deploys on every push
- Free HTTPS
- Custom domain support
- Built-in analytics

---

### Option 5: Vercel Deployment

1. Go to [vercel.com](https://vercel.com)
2. Sign up with GitHub
3. Import your repository
4. Click **Deploy** - it works out of the box!

---

## 🔧 Local Testing Before Deployment

### Using Python 3 (Recommended)
```bash
cd ramd-ai-website
python3 -m http.server 8000
# Open browser to http://localhost:8000
```

### Using Node.js
```bash
npm install -g http-server
http-server
# Opens at http://localhost:8080
```

### Using Ruby
```bash
ruby -run -ehttpd . -p8000
# Open browser to http://localhost:8000
```

---

## 📊 SEO Configuration

To improve search engine visibility:

### Update Meta Tags in `index.html`
```html
<meta name="description" content="Your custom description">
<meta name="keywords" content="your, custom, keywords">
```

### Create `sitemap.xml`
Save as `sitemap.xml` in root folder:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://ramd.ai/</loc>
    <lastmod>2026-04-26</lastmod>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
</urlset>
```

### Create `robots.txt`
Save as `robots.txt` in root folder:
```
User-agent: *
Allow: /
Sitemap: https://ramd.ai/sitemap.xml
```

---

## 🔒 Security Best Practices

1. **HTTPS**: Ensure your domain uses HTTPS (automatic with GitHub Pages & Netlify)
2. **Email Privacy**: The contact form uses `mailto:` links - emails aren't processed server-side
3. **No Tracking**: By default, no analytics or tracking is enabled
4. **Regular Updates**: Keep your content current to maintain credibility

---

## 📈 Adding Analytics (Optional)

### Google Analytics
Add this before `</head>` tag:
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Replace `G-XXXXXXXXXX` with your Google Analytics ID.

---

## 🚨 Troubleshooting

### Site Not Loading on GitHub Pages
- **Solution**: Wait 5-10 minutes for GitHub Pages to rebuild
- Check Settings → Pages shows deployment status

### Custom Domain Not Working
- **Solution**: Verify DNS records are correctly configured
- Use [DNS Checker](https://dnschecker.org) to verify

### Email Links Not Working
- **Solution**: This is normal - `mailto:` links require email client
- Users' email applications must be configured on their device

### Website Looks Different Locally
- **Solution**: Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- Try different browser to isolate issue

---

## 🔄 Updating Your Website

### Update Content
1. Edit `index.html` locally
2. Save file
3. Commit and push:
```bash
git add index.html
git commit -m "Update website content"
git push
```

4. GitHub automatically redeploys (1-2 minutes)

### Update Email Address
Find and replace `info@ramdfz.com` with your email in `index.html`

---

## 📞 Support

For hosting-specific questions:
- **GitHub Pages**: [docs.github.com/pages](https://docs.github.com/en/pages)
- **Netlify**: [netlify.com/support](https://netlify.com/support)
- **Vercel**: [vercel.com/docs](https://vercel.com/docs)

---

## ✅ Deployment Checklist

- [ ] All files uploaded to repository
- [ ] `index.html` is in root directory
- [ ] Email address updated to `info@ramdfz.com` (or your email)
- [ ] GitHub Pages enabled in Settings
- [ ] Website tested in multiple browsers
- [ ] Mobile responsiveness verified
- [ ] Contact button opens email client
- [ ] All links work correctly
- [ ] Page loads quickly (< 3 seconds)
- [ ] SEO basics configured (meta tags, sitemap)

---

**RAMD.ai Website** - Enterprise AI Solutions
