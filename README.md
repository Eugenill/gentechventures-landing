# Gen Tech Ventures — Landing Page

A simple, single-page landing site for **Gen Tech Ventures**, the personal holding company of Eugeni Llagostera Saltor.

## Stack

- Plain HTML + CSS (no build step, no dependencies)
- Inline SVG logo + favicon
- Google Fonts (Inter)
- Fully responsive, mobile-first

## Project structure

```
.
├── index.html       # The landing page (all HTML + CSS inline)
├── favicon.svg      # Favicon (icon from the logo)
└── README.md        # This file
```

## Local preview

Just open `index.html` in your browser — there's no build step.

Or, from the folder:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

---

## Deployment — GitHub + Vercel (step-by-step)

### 1. Push the code to GitHub

From the project folder:

```bash
# 1. Initialize git
git init
git add .
git commit -m "Initial commit: Gen Tech Ventures landing page"

# 2. Create a new repo on GitHub
#    Go to https://github.com/new
#    Name it e.g. "gentechventures-landing"
#    Do NOT initialize with README/gitignore/license
#    (keep it empty so we can push)

# 3. Connect and push
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/gentechventures-landing.git
git push -u origin main
```

### 2. Deploy on Vercel

1. Go to https://vercel.com/new
2. Click **"Import Git Repository"** and authorize GitHub if needed.
3. Pick the `gentechventures-landing` repo you just pushed.
4. On the configuration screen:
   - **Framework Preset:** `Other` (it's a static site)
   - **Build Command:** leave empty
   - **Output Directory:** leave empty (root)
   - **Install Command:** leave empty
5. Click **"Deploy"**.
6. After ~20 seconds you'll get a live URL like `https://gentechventures-landing.vercel.app`.

### 3. Attach a custom domain (optional, recommended)

If you have a domain (e.g. `gentechventures.com`):

1. In your Vercel project → **Settings → Domains**.
2. Add your domain and follow Vercel's DNS instructions
   (typically an `A` record pointing to `76.76.21.21` or a `CNAME` to `cname.vercel-dns.com`).
3. DNS propagation usually takes a few minutes; SSL is automatic.

---

## Updating the site

Every push to the `main` branch on GitHub auto-deploys to Vercel:

```bash
# Make your edits, then:
git add .
git commit -m "Update copy"
git push
# Vercel deploys automatically in ~20 seconds
```

---

## What to customize later

- **LinkedIn page link:** when you create the company LinkedIn page, add it as a link in the footer or founder section (search for `linkedin.com` in `index.html`).
- **Tagline / About copy:** edit the `<h1>` and `.tagline` in `index.html`, and the About section paragraph.
- **Portfolio descriptions:** each card's `<p>` inside `#portfolio` is currently a placeholder — swap in real positioning lines for Enkitek and Colectin whenever you'd like.
- **Replace the SVG logo with your PNG:** if you prefer your original PNG logo, drop the file into this folder as `logo.png` and replace the `<svg class="hero-logo">...</svg>` block with `<img src="/logo.png" alt="Gen Tech Ventures" class="hero-logo" />`.

---

&copy; 2026 Gen Tech Ventures
