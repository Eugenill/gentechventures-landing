# Gen Tech Ventures — Landing Page

A premium single-page site for **Gen Tech Ventures**, the personal holding company of Eugeni Llagostera Saltor. Dark, editorial styling inspired by modern VC sites (e.g. type1ventures.com).

## Stack

- Plain HTML + CSS (no build step, no dependencies)
- Google Fonts: Instrument Serif (display) + Inter (body)
- Inline SVG favicon
- Intersection Observer scroll reveals
- Fully responsive, mobile-first

## Project structure

```
.
├── index.html           # The landing page (all HTML + CSS + JS inline)
├── favicon.svg          # Favicon
├── enkitek-logo.png     # ← YOU add this (see below)
├── colectin-logo.png    # ← YOU add this (see below)
├── eugeni.jpg           # ← YOU add this (see below)
├── vercel.json          # Vercel config
└── README.md            # This file
```

## ⚠ Before you deploy — save the 3 images

The page references three image files that need to live next to `index.html`. Save the attachments you shared in the chat into this folder, using these exact filenames:

| File name            | What it is              |
| -------------------- | ----------------------- |
| `enkitek-logo.png`   | The Enkitek logo        |
| `colectin-logo.png`  | The Colectin logo       |
| `eugeni.jpg`         | Your black & white photo (it'll be auto-converted to grayscale by CSS, so colour is fine too) |

If you prefer `.jpg` or different filenames, just update the `src="..."` paths in `index.html` accordingly.

## Local preview

Open `index.html` directly, or run a quick server:

```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

---

## Deployment — GitHub + Vercel (step-by-step)

### 1. Push the code to GitHub

From the project folder:

```bash
git init
git add .
git commit -m "Initial commit: Gen Tech Ventures landing page"

# Create a new empty repo on https://github.com/new
# (name it e.g. gentechventures-landing — no README/gitignore/license)

git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/gentechventures-landing.git
git push -u origin main
```

### 2. Deploy on Vercel

1. Go to https://vercel.com/new
2. **Import Git Repository** → pick the repo you just pushed.
3. Configuration:
   - **Framework Preset:** `Other`
   - **Build Command:** _(leave empty)_
   - **Output Directory:** _(leave empty — root)_
   - **Install Command:** _(leave empty)_
4. Click **Deploy**. ~20 seconds later you'll get a live URL.

### 3. Custom domain (optional)

Vercel project → **Settings → Domains** → add your domain and follow the DNS instructions (usually an `A` record → `76.76.21.21`, or `CNAME` → `cname.vercel-dns.com`). SSL is automatic.

---

## Auto-deploys

Every push to `main` triggers a redeploy on Vercel.

```bash
git add .
git commit -m "Update copy"
git push
```

---

## Easy customization

- **Hero headline + tagline:** `<h1>` + `.hero-sub` inside `index.html`
- **Thesis copy (About section):** `.about-body` paragraphs
- **Portfolio descriptions + tags:** inside each `.portfolio-card` block
- **Founder bio:** inside the `#founder` section
- **Accent color:** change `--accent: #5b9dff;` in the `:root` block (top of `<style>`)
- **LinkedIn page link:** once your company LinkedIn exists, add another `.founder-link` block, or put it in the footer.

---

&copy; 2026 Gen Tech Ventures · Barcelona
