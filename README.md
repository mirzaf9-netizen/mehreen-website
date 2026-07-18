# Dr. Mehreen Fatima — Academic Portfolio Website

Academic portfolio website for Dr. Mehreen Fatima, Developmental Psychologist and Assistant Professor at Azim Premji University, Bhopal.

## Project Structure

```
mehreen-website/
├── index.html          ← Single-page website (all CSS/JS inline)
├── images/
│   └── mehreen-hero.png  ← Hero portrait photo
├── vercel.json         ← Vercel hosting config (caching, headers)
└── README.md
```

## Deployment: GitHub → Vercel → GoDaddy

### Step 1: Push to GitHub

1. Go to [github.com/new](https://github.com/new)
2. Create a new repository (e.g., `mehreen-website`)
3. Set it to **Private** (or Public — your choice)
4. Do NOT initialize with README (we already have one)
5. Push this folder:

```bash
cd mehreen-website
git init
git add .
git commit -m "Initial commit — Mehreen Fatima portfolio website"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/mehreen-website.git
git push -u origin main
```

### Step 2: Deploy on Vercel (Free)

1. Go to [vercel.com](https://vercel.com) and sign in with your GitHub account
2. Click **"Add New → Project"**
3. Select the `mehreen-website` repository
4. Framework Preset: select **"Other"** (it's a static site)
5. Leave all other settings as default
6. Click **Deploy**
7. Vercel will give you a URL like `mehreen-website-xyz.vercel.app` — test it

### Step 3: Connect GoDaddy Domain to Vercel

**In Vercel:**
1. Go to your project → **Settings → Domains**
2. Add your domain (e.g., `mehreenfatima.com`)
3. Also add `www.mehreenfatima.com`
4. Vercel will show you the DNS records you need to set

**In GoDaddy:**
1. Log in to [GoDaddy DNS Management](https://dcc.godaddy.com/)
2. Select your domain → **DNS → DNS Records**
3. Set the following records:

| Type  | Name  | Value                   | TTL    |
|-------|-------|-------------------------|--------|
| A     | @     | 76.76.21.21             | 600    |
| CNAME | www   | cname.vercel-dns.com    | 600    |

> Note: The A record IP (`76.76.21.21`) is Vercel's standard. If Vercel shows different values in your dashboard, use those instead.

4. Delete any conflicting A or CNAME records for `@` or `www`
5. Wait 5–30 minutes for DNS propagation
6. Back in Vercel, the domain status should turn green ✓
7. Vercel automatically provisions a free SSL certificate (HTTPS)

### Step 4: Update OG Image URL

After deployment, update the `<meta property="og:image">` tag in `index.html` with the full URL:
```html
<meta property="og:image" content="https://mehreenfatima.com/images/mehreen-hero.png">
```

## To Update Content

1. Edit `index.html` locally
2. Push to GitHub: `git add . && git commit -m "Update content" && git push`
3. Vercel auto-deploys within ~30 seconds

## Before Going Live — Checklist

- [ ] Confirm Fulbright status (semifinalist vs. confirmed fellow)
- [ ] Update ResearchGate profile URL
- [ ] Update Google Scholar profile URL  
- [ ] Set up Topmate.io account and link booking URLs
- [ ] Update canonical URL in `<head>` with actual domain
- [ ] Update OG image URL with full domain path
- [ ] Replace CV download link with actual PDF URL
- [ ] Test on mobile devices
- [ ] Test all navigation links
- [ ] Verify booking buttons link to correct Topmate sessions

## Tech Stack

- Pure HTML/CSS/JS — no framework, no build step
- Google Fonts: Cormorant Garamond + Plus Jakarta Sans
- Hosted on Vercel (free tier)
- Domain via GoDaddy
