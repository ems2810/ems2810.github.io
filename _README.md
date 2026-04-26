# achim.dev — iOS App Portfolio Site

Static website for Track Tailor, Folio Home, and Sketchline.  
Hosted on GitHub Pages — no build step, no dependencies.

## File structure

```
index.html                  — Homepage / app showcase
shared.css                  — Shared styles for all subpages

legal/
  playlistgenerator-privacy.html
  playlistgenerator-terms.html
  foliohome-privacy.html
  foliohome-terms.html
  sketchline-privacy.html
  sketchline-terms.html

beta/
  foliohome.html            — TestFlight beta info + link
  sketchline.html           — Waitlist signup form
```

## Setup

### 1. Create GitHub repository

Name it `ems2810.github.io` for a root Pages site,  
or any name (e.g. `apps-website`) for a project Pages site at `ems2810.github.io/apps-website`.

### 2. Push files

```bash
git init
git add .
git commit -m "Initial site"
git remote add origin https://github.com/ems2810/ems2810.github.io
git push -u origin main
```

### 3. Enable GitHub Pages

Repository → Settings → Pages → Source: Deploy from branch → Branch: main → / (root)

Your site will be live at `https://ems2810.github.io` within a few minutes.

### 4. Custom domain (optional)

Buy a domain (e.g. Namecheap, Hover, Cloudflare Registrar).  
Add a `CNAME` file to the repo root containing your domain:

```
yourdomain.com
```

Then add a DNS A record pointing to GitHub Pages IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

## Things to update before going live

### index.html
- [ ] Replace `mailto:hello@example.com` with your real email
- [ ] Add your real GitHub profile URL
- [ ] Add real App Store link for Track Tailor
- [ ] Add support page URL for Track Tailor

### beta/foliohome.html
- [ ] Replace `YOUR_TESTFLIGHT_LINK_HERE` with your TestFlight public link
  (App Store Connect → TestFlight → Public Links → Create link)
- [ ] Replace beta feedback email

### beta/sketchline.html
- [ ] Set up a form backend and replace `YOUR_FORM_ID`:
  - **Tally** (recommended, free): create form at tally.so, use their embed
  - **Formspree** (free tier 50 submissions/mo): sign up at formspree.io, replace the form action URL
  - **Google Forms**: embed or link to your form

### legal/*.html
- [ ] Replace placeholder email addresses
- [ ] Replace `April 2026` with actual effective date
- [ ] Add a real Imprint page (Impressum) — required for German sites

### App Store links (Track Tailor)
Current link format: `https://apps.apple.com/app/idXXXXXXXXXX`

## Hosting legal docs for App Store

App Store Connect requires:
- **Privacy Policy URL**: use `https://yourdomain.com/legal/playlistgenerator-privacy.html`
- **Terms of Use / EULA URL**: use `https://yourdomain.com/legal/playlistgenerator-terms.html`
- **Support URL**: can point to `index.html#apps` or create a dedicated support page

## AdMob privacy requirement

AdMob requires a publicly reachable privacy policy that mentions AdMob/Google.  
The policies in `legal/` already include this section.  
In AdMob dashboard: Apps → [App] → App settings → Privacy Policy URL → paste the URL.
