# Complete Deployment Guide for Microtech Beavers Website

## 📋 What You Need

1. Your website files (all ready in this folder!)
2. A domain name (microtechbeavers.com)
3. A hosting platform (choose one below)

---

## 🎯 RECOMMENDED: Netlify (Easiest & Free)

### Why Netlify?
- ✅ 100% Free for basic sites
- ✅ Automatic HTTPS/SSL
- ✅ Global CDN (fast worldwide)
- ✅ No coding required
- ✅ Deploy in 60 seconds

### Steps:

#### Part 1: Deploy Website (2 minutes)

1. **Go to Netlify Drop**
   - Visit: https://app.netlify.com/drop
   - No account needed initially

2. **Upload Your Files**
   - Drag the entire `OurWebsite` folder onto the webpage
   - Wait 30 seconds for deployment
   - Your site is now live at: `random-name-12345.netlify.app`

3. **Create Account** (to manage your site)
   - Click "Claim this site"
   - Sign up with email or GitHub
   - Free forever for this type of site

#### Part 2: Purchase Domain (10 minutes)

**Option A: Namecheap (Recommended)**
1. Go to: https://www.namecheap.com
2. Search: "microtechbeavers.com"
3. Add to cart
4. Checkout (cost: ~$10-15/year)
5. Choose "Namecheap BasicDNS" when prompted

**Option B: GoDaddy**
1. Go to: https://www.godaddy.com
2. Search and purchase domain (~$12-20/year)

**Option C: Google Domains**
1. Go to: https://domains.google.com
2. Search and purchase (~$12/year)

#### Part 3: Connect Domain to Netlify (5 minutes)

1. **In Netlify Dashboard**
   - Click your site name
   - Go to "Domain settings"
   - Click "Add custom domain"
   - Enter: `microtechbeavers.com`
   - Click "Verify"

2. **Netlify Will Show You DNS Records**
   - Copy these records (you'll need them next)

#### Part 4: Configure DNS (5 minutes)

**If using Namecheap:**
1. Log into Namecheap
2. Go to "Domain List" → Click "Manage" next to your domain
3. Go to "Advanced DNS" tab
4. Delete any existing A or CNAME records
5. Add these records:
   ```
   Type: A Record
   Host: @
   Value: 75.2.60.5
   TTL: Automatic

   Type: CNAME Record
   Host: www
   Value: [your-netlify-site].netlify.app
   TTL: Automatic
   ```

**If using GoDaddy:**
1. Log into GoDaddy
2. My Products → Domains → DNS
3. Add same records as above

**If using Google Domains:**
1. Log into Google Domains
2. Click your domain → DNS
3. Add same records as above

#### Part 5: Wait & Verify (1-24 hours)

1. DNS propagation takes 1-24 hours (usually 2-6 hours)
2. Check status at: https://www.whatsmydns.net
3. Enter your domain and check A and CNAME records
4. When green checkmarks appear worldwide, you're live!

**DONE! Your website is now at www.microtechbeavers.com**

---

## 🐙 ALTERNATIVE 1: GitHub Pages (Free)

### Why GitHub Pages?
- ✅ Free
- ✅ Good for developers
- ✅ Version control included
- ❌ Requires basic Git knowledge

### Steps:

1. **Create GitHub Account**
   - Go to: https://github.com
   - Sign up for free

2. **Create New Repository**
   - Click "+" → "New repository"
   - Name: `microtechbeavers-website`
   - Make it Public
   - Click "Create repository"

3. **Upload Files via Command Line**
   ```bash
   cd /home/almamargaret/OurWebsite
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/microtechbeavers-website.git
   git push -u origin main
   ```

   **OR Upload via Web Interface:**
   - Click "uploading an existing file"
   - Drag all files from OurWebsite folder
   - Click "Commit changes"

4. **Enable GitHub Pages**
   - Go to repository Settings
   - Scroll to "Pages" section
   - Source: Select "main" branch
   - Click Save
   - Your site is now at: `username.github.io/microtechbeavers-website`

5. **Add Custom Domain**
   - In Pages settings, add: `www.microtechbeavers.com`
   - GitHub will show you DNS records

6. **Configure DNS** (same as Netlify above, but use these values)
   ```
   Type: A Record
   Host: @
   Value: 185.199.108.153

   Type: A Record
   Host: @
   Value: 185.199.109.153

   Type: A Record
   Host: @
   Value: 185.199.110.153

   Type: A Record
   Host: @
   Value: 185.199.111.153

   Type: CNAME
   Host: www
   Value: YOUR-USERNAME.github.io
   ```

---

## 💼 ALTERNATIVE 2: Traditional Hosting (Paid)

### Hosting Providers (includes domain):

**Hostinger** - Best Value
- Cost: $2.99/month
- Link: https://www.hostinger.com
- Includes: Free domain, email, cPanel

**Bluehost** - Most Popular
- Cost: $2.95/month
- Link: https://www.bluehost.com
- Includes: Free domain, WordPress support

**SiteGround** - Best Performance
- Cost: $3.99/month
- Link: https://www.siteground.com
- Includes: Free SSL, daily backups

### Steps:

1. **Purchase Hosting Package**
   - Choose provider above
   - Select basic shared hosting plan
   - Choose domain: microtechbeavers.com
   - Complete purchase

2. **Access cPanel**
   - Check email for login credentials
   - Login to your hosting account
   - Open cPanel

3. **Upload Files**

   **Method A: File Manager (Easy)**
   - In cPanel, click "File Manager"
   - Navigate to `public_html` folder
   - Click "Upload"
   - Upload all files from OurWebsite folder
   - Extract if zipped

   **Method B: FTP (Better for large sites)**
   - Download FileZilla: https://filezilla-project.org
   - Get FTP credentials from hosting provider
   - Connect to your server
   - Upload all files to `public_html` folder

4. **Verify**
   - Visit: www.microtechbeavers.com
   - Your site should be live within 1-2 hours

---

## 🔧 Troubleshooting

### "Site not loading after 24 hours"
- Check DNS propagation: https://www.whatsmydns.net
- Verify DNS records are correct
- Clear your browser cache (Ctrl + Shift + Delete)

### "SSL/HTTPS not working"
- Netlify: Automatic after DNS is set
- GitHub Pages: Enable in settings
- cPanel: Install Let's Encrypt certificate

### "Images not showing"
- Check file names match exactly (case-sensitive)
- Verify all files uploaded correctly

### "Form not submitting"
- The form currently shows an alert
- To receive actual emails, add backend service:
  - Formspree: https://formspree.io (free)
  - Netlify Forms: Built-in (free)

---

## 📧 Need Help?

1. **Netlify Support**: https://answers.netlify.com
2. **GitHub Pages Docs**: https://docs.github.com/pages
3. **Your Hosting Provider's Support Chat**

---

## ✅ Post-Launch Checklist

- [ ] Website loads at www.microtechbeavers.com
- [ ] Website loads at microtechbeavers.com (without www)
- [ ] SSL certificate is active (shows padlock in browser)
- [ ] Mobile version works correctly
- [ ] All links work
- [ ] Contact form works
- [ ] Update email/phone in index.html to your actual contact info
- [ ] Test on different browsers (Chrome, Firefox, Safari)
- [ ] Add Google Analytics (optional)
- [ ] Submit to Google Search Console (optional)

---

**Congratulations! Your website is now live! 🎉**
