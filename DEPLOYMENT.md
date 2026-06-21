# 🚀 Deployment Guide

Complete guide to deploy your portfolio to various hosting platforms.

---

## 📋 Pre-Deployment Checklist

Before deploying, ensure:
- [ ] All content is customized
- [ ] All links are correct
- [ ] Tested on multiple browsers
- [ ] Mobile responsive verified
- [ ] Contact form backend ready (if needed)
- [ ] Analytics set up (optional)
- [ ] SEO optimized

---

## 🌐 Hosting Options

### **1. GitHub Pages (Free, Recommended)**

**Best for:** GitHub users, simple hosting, free domain

#### **Setup:**
```bash
# 1. Create new repository
# Repository name: your-username.github.io
# OR: moe-kyaw-aung-portfolio-v129

# 2. Clone repository
git clone https://github.com/YOUR_USERNAME/moe-kyaw-aung-portfolio-v129.git
cd moe-kyaw-aung-portfolio-v129

# 3. Add your HTML file
cp moe-kyaw-aung-portfolio-v129.html index.html

# 4. Commit and push
git add .
git commit -m "Deploy portfolio"
git push origin main

# 5. Enable Pages
# Go to: Settings → Pages
# Branch: main
# Folder: / (root)

# 6. Access at:
# https://username.github.io/
# https://username.github.io/repo-name/
```

#### **Custom Domain:**
```bash
# 1. Buy domain (GoDaddy, Namecheap, etc.)

# 2. Add CNAME file to repo:
# Content: your-domain.com

# 3. Configure DNS:
# Type: A
# Host: @
# Points to: 185.199.108.153

# 4. GitHub settings:
# Custom domain: your-domain.com
# Enforce HTTPS: Check
```

---

### **2. Netlify (Free, With Extras)**

**Best for:** Advanced features, continuous deployment, free SSL

#### **Setup Option A: Git Integration**
```bash
# 1. Go to: netlify.com
# 2. Click: New site from Git
# 3. Choose: GitHub
# 4. Select: Your repository
# 5. Build settings:
#    - Build command: (leave blank)
#    - Publish directory: /

# 6. Deploy!
# Access at: your-site.netlify.app
```

#### **Setup Option B: Direct Upload**
```bash
# 1. Go to: netlify.com/drop
# 2. Drag and drop HTML file
# 3. Uploaded automatically
# 4. Get random URL
# 5. (Optional) Claim site and customize
```

#### **Custom Domain:**
```bash
# 1. Domain settings → Custom domain
# 2. Add your domain
# 3. Netlify provides nameservers
# 4. Update domain registrar DNS
# 5. Wait 24-48 hours for propagation
```

#### **HTTPS (Automatic):**
- Netlify provides free SSL certificate
- Automatically renewed
- No additional configuration needed

---

### **3. Vercel (Free, For Developers)**

**Best for:** Developers, serverless hosting, analytics included

#### **Setup:**
```bash
# 1. Go to: vercel.com
# 2. Sign in with GitHub
# 3. New Project
# 4. Import Git repository
# 5. Framework: Other
# 6. Deploy!
# 7. Access at: project-name.vercel.app
```

#### **Custom Domain:**
```bash
# 1. Project settings → Domains
# 2. Add domain
# 3. Configure DNS pointing to Vercel
# 4. Verify ownership
# 5. Done!
```

---

### **4. Traditional Hosting (Shared/VPS)**

**Best for:** Control, custom setup, existing hosting

#### **FTP Upload:**
```bash
# 1. Get hosting account
# 2. Download FileZilla (free FTP client)
# 3. Connect with FTP credentials
# 4. Upload HTML file to: public_html/
# 5. Rename to: index.html
# 6. Access via domain
```

#### **SSH/SFTP:**
```bash
# Connect to server
sftp username@your-host.com

# Navigate to public directory
cd public_html

# Upload file
put moe-kyaw-aung-portfolio-v129.html index.html

# Set permissions
chmod 644 index.html

# Verify upload
ls -la
```

#### **Via Control Panel (cPanel):**
```
1. Login to cPanel
2. File Manager
3. Navigate to public_html
4. Upload HTML file
5. Rename to index.html
6. Set permissions to 644
```

---

### **5. Firebase Hosting (Google, Free)**

**Best for:** Google projects, analytics integration

#### **Setup:**
```bash
# 1. Install Firebase CLI
npm install -g firebase-tools

# 2. Login
firebase login

# 3. Initialize project
firebase init hosting

# 4. Deploy
firebase deploy

# Access at: project-name.firebaseapp.com
```

#### **Configuration:**
```bash
# firebase.json
{
  "hosting": {
    "public": ".",
    "cleanUrls": true,
    "redirects": [{
      "source": "/",
      "destination": "/index.html",
      "type": 200
    }]
  }
}
```

---

### **6. AWS S3 + CloudFront**

**Best for:** AWS ecosystem, high traffic, advanced features

#### **Setup:**
```bash
# 1. Create S3 bucket
# 2. Enable static website hosting
# 3. Upload HTML file
# 4. Create CloudFront distribution
# 5. Configure custom domain
# 6. Request SSL certificate
```

---

## 🔒 Security Configuration

### **HTTPS (Essential)**
```bash
# Most platforms provide free SSL
# Enable in hosting settings:
# - Netlify: Automatic
# - Vercel: Automatic
# - GitHub Pages: Automatic
# - Firebase: Automatic
```

### **Security Headers:**
```bash
# Add to .htaccess or hosting config:
Header set X-Content-Type-Options "nosniff"
Header set X-Frame-Options "SAMEORIGIN"
Header set X-XSS-Protection "1; mode=block"
Header set Referrer-Policy "strict-origin-when-cross-origin"
```

### **CSP (Content Security Policy):**
```bash
# Add to HTML head:
<meta http-equiv="Content-Security-Policy" 
      content="default-src 'self'; 
               script-src 'self' 'unsafe-inline' cdn.jsdelivr.net;
               style-src 'self' 'unsafe-inline' fonts.googleapis.com;
               font-src fonts.gstatic.com;
               img-src 'self' data: https:;">
```

---

## 📊 Analytics Setup

### **Google Analytics:**
```html
<!-- Add to HTML head -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_ID');
</script>
```

### **Netlify Analytics:**
```bash
# 1. Netlify dashboard
# 2. Analytics
# 3. Enable analytics
# 4. Automatic tracking (no code needed)
```

### **Vercel Analytics:**
```bash
# 1. Project settings
# 2. Analytics
# 3. Enable Web Vitals
# 4. Automatic setup
```

---

## 🔄 Continuous Deployment

### **GitHub Pages (Automatic):**
```bash
# Every push to main branch automatically deploys
git add .
git commit -m "Update portfolio"
git push origin main
# ✨ Deployed automatically!
```

### **Netlify (Git Integration):**
```bash
# 1. Connect repository
# 2. Push to GitHub
# 3. Netlify automatically builds and deploys
# 4. No additional steps needed
```

### **Vercel (Git Integration):**
```bash
# 1. Import from GitHub
# 2. Push to repository
# 3. Vercel auto-deploys
# 4. Preview URLs for PRs
```

---

## 🌍 DNS & Domain Setup

### **Point Domain to Hosting:**

#### **Netlify:**
```
Type: CNAME
Name: your-domain.com
Value: your-site.netlify.app
OR
Type: A
Name: @
Value: 75.2.60.5
```

#### **Vercel:**
```
Type: A
Name: @
Value: 76.76.19.165
OR
Type: CNAME
Name: www
Value: cname.vercel-dns.com
```

#### **GitHub Pages:**
```
Type: A
Name: @
Value: 185.199.108.153
       185.199.109.153
       185.199.110.153
       185.199.111.153
Type: CNAME
Name: www
Value: username.github.io
```

---

## ✅ Post-Deployment Testing

### **Functionality Tests:**
- [ ] Website loads correctly
- [ ] All links work
- [ ] Dark mode toggles
- [ ] Contact form functions
- [ ] Animations smooth
- [ ] Mobile responsive
- [ ] Images load properly

### **Performance Tests:**
```bash
# Use Lighthouse:
# 1. Open Chrome DevTools (F12)
# 2. Lighthouse tab
# 3. Generate report
# 4. Target scores: 90+
```

### **SEO Tests:**
```bash
# 1. Google Search Console
# 2. Submit sitemap
# 3. Request indexing
# 4. Monitor performance

# 2. Check meta tags:
# title ✓
# description ✓
# og:image ✓
# robots ✓
```

### **Security Tests:**
```bash
# 1. SSL Labs: ssllabs.com
# 2. Check certificate validity
# 3. Verify HTTPS works
# 4. Test mixed content (none allowed)

# 2. Mozilla Observatory:
# observatory.mozilla.org
# Check security headers
```

---

## 🐛 Troubleshooting

### **Site Not Loading:**
- [ ] Check DNS propagation (24-48 hours)
- [ ] Verify file uploaded correctly
- [ ] Clear browser cache
- [ ] Check hosting status page

### **HTTPS Not Working:**
- [ ] Wait for certificate generation
- [ ] Check force HTTPS setting
- [ ] Verify domain is correctly configured
- [ ] Try different browser

### **Styles Not Appearing:**
- [ ] Ensure HTML file is complete
- [ ] CSS is inline (not external)
- [ ] Clear browser cache
- [ ] Check browser console errors

### **Animations Not Working:**
- [ ] Check browser support
- [ ] Verify JavaScript enabled
- [ ] Check console for errors
- [ ] Try different browser

---

## 📈 Monitoring

### **Track Performance:**
- **Uptime**: UptimeRobot (free)
- **Speed**: Pingdom, GTmetrix
- **Analytics**: Google Analytics, Vercel Analytics
- **SEO**: Google Search Console, Bing Webmaster

### **Setup Alerts:**
```bash
# UptimeRobot:
# 1. Create account
# 2. Add monitoring
# 3. Set email alerts
# 4. Monitor uptime
```

---

## 🔄 Updates & Maintenance

### **Keeping Updated:**
```bash
# 1. Regular content updates
# 2. Test new features
# 3. Check broken links
# 4. Update certificates
# 5. Monitor analytics

# Update process:
git add .
git commit -m "Update: description"
git push origin main
# ✨ Auto-deployed!
```

---

## 🎯 Performance Optimization

### **Image Optimization:**
```bash
# Use tools:
# - TinyPNG: tinypng.com
# - ImageOptim: imageoptim.com
# - Compressor: compressor.io
```

### **Caching:**
```bash
# Netlify/Vercel: Automatic
# GitHub Pages: Configure via _headers
# AWS: CloudFront caching
# Traditional: Set .htaccess cache headers
```

### **CDN (Content Delivery Network):**
- Netlify: Built-in
- Vercel: Built-in
- GitHub Pages: Cloudflare free tier
- Traditional: Cloudflare, Bunny CDN

---

## 📞 Support

**Issues with deployment?**
- Check platform documentation
- Search GitHub issues
- Ask in discussions
- Email: hello@moekyawaung.dev

---

<div align="center">

**Your portfolio is live! 🚀**

[Back to README](README.md) | [Quick Start](QUICKSTART.md) | [Get Help](README.md#-contact--support)

</div>
