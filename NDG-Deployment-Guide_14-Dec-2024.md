# NDG Website Deployment Guide
## Simple Step-by-Step Instructions
## Created: 14-Dec-2024

---

# STEP 1: PREPARE YOUR FILES

You need these 10 files in a single folder:

```
ndg-website/
├── index.html          ← Main website
├── client-access.html  ← Client portal placeholder
├── styles.css          ← All styling
├── epichalo.png        ← Hero Socrates
├── logotablet.png      ← Floating tablet logo
├── writing.png         ← Philosophy section
├── reading.png         ← Philosophy section
├── orating.png         ← Philosophy section
├── herocontemplating.png ← Turning + Client Access
├── stmichael.png       ← Moral compass section
└── thumbsup.png        ← Footer
```

**Checklist:**
- [ ] All 10 files present
- [ ] File names match exactly (case-sensitive)
- [ ] All PNG files have transparent backgrounds

---

# STEP 2: PUSH TO GITHUB

## Option A: Using GitHub Desktop (Easier)

1. Open GitHub Desktop
2. Click **File → Add Local Repository**
3. Select your `ndg-website` folder
4. If it asks to create a repository, click **Create Repository**
5. Add commit message: `NDG Website v1.0 - Initial deployment`
6. Click **Commit to main**
7. Click **Push origin**

## Option B: Using Terminal

```bash
# Navigate to your folder
cd /path/to/ndg-website

# Initialize git if needed
git init

# Add all files
git add .

# Commit
git commit -m "NDG Website v1.0 - Initial deployment"

# Push to GitHub (assumes repo exists)
git push origin main
```

---

# STEP 3: DEPLOY ON VERCEL

1. Go to **https://vercel.com**
2. Sign in with your GitHub account
3. Click **Add New → Project**
4. Find and select your `ndg-website` repository
5. Leave all settings as default
6. Click **Deploy**
7. Wait 30-60 seconds for deployment
8. You'll get a URL like: `ndg-website-xyz.vercel.app`

---

# STEP 4: CONNECT YOUR DOMAIN

1. In Vercel, go to your project
2. Click **Settings → Domains**
3. Enter: `www.noeticdharma.com`
4. Click **Add**
5. Vercel will show DNS records to add

## Add DNS Records (in your domain registrar):

| Type | Name | Value |
|------|------|-------|
| A | @ | 76.76.21.21 |
| CNAME | www | cname.vercel-dns.com |

6. Wait 5-30 minutes for DNS propagation
7. Vercel will auto-configure SSL

---

# STEP 5: CONFIGURE CONTACT FORM

## Option A: Formspree (Free, Simple)

1. Go to **https://formspree.io**
2. Sign up / Sign in
3. Click **New Form**
4. Name it: `NDG Contact Form`
5. Copy your form endpoint (looks like: `https://formspree.io/f/xyzabc`)
6. Edit `index.html`:
   - Find: `action="https://formspree.io/f/YOUR_FORM_ID"`
   - Replace `YOUR_FORM_ID` with your actual form ID
7. Push changes to GitHub
8. Vercel will auto-redeploy

## Option B: Resend (More Control)

1. Go to **https://resend.com**
2. Set up API key
3. Create serverless function for form handling
4. (More complex - do this later if needed)

---

# STEP 6: TEST EVERYTHING

## Desktop Testing
- [ ] Hero loads with floating tablet and Socrates
- [ ] All images display correctly
- [ ] Navigation links work (smooth scroll)
- [ ] Contact form submits successfully
- [ ] Client Access page loads
- [ ] Footer links work

## Mobile Testing
- [ ] Responsive layout works
- [ ] Images scale properly
- [ ] Form is usable on mobile
- [ ] Navigation visible/functional

## Form Testing
- [ ] Submit test inquiry
- [ ] Check email delivery
- [ ] Verify all fields captured

---

# STEP 7: ONGOING UPDATES

## To Make Changes:

1. Edit files locally
2. Test in browser (open `index.html`)
3. When ready, commit and push:
```bash
git add .
git commit -m "Description of changes"
git push origin main
```
4. Vercel auto-deploys in ~30 seconds

---

# QUICK TROUBLESHOOTING

## Images Not Showing
- Check file names match exactly (case-sensitive)
- Ensure PNG files are in same folder as HTML
- Clear browser cache (Ctrl+Shift+R)

## Fonts Not Loading
- Check internet connection
- Google Fonts should load automatically
- Fallback fonts will display if blocked

## Form Not Working
- Verify Formspree form ID is correct
- Check Formspree dashboard for submissions
- Ensure form action URL is exact

## Domain Not Connecting
- DNS can take up to 48 hours (usually 5-30 min)
- Verify DNS records match Vercel's instructions
- Check in Vercel dashboard for status

---

# CONTACTS & RESOURCES

| Resource | URL |
|----------|-----|
| Vercel Dashboard | https://vercel.com/dashboard |
| GitHub Repo | https://github.com/YOUR_USERNAME/ndg-website |
| Formspree | https://formspree.io |
| Google Fonts | https://fonts.google.com |

---

# NEXT STEPS (After Deployment)

1. **Configure form endpoint** (Step 5)
2. **Test on multiple devices**
3. **Share Client Access spec** with developer for future build
4. **Set up analytics** (Plausible or Vercel Analytics)
5. **Monitor form submissions** via Formspree dashboard

---

## Need Help?

If any step fails, share the error message and I can help troubleshoot.

---

© 2025 Noetic Dharma Group, LLC | CONFIDENTIAL & PROPRIETARY
