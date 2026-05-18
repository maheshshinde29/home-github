# Home Visit Dental Treatment — Pune (Static Site)

This is the **production-ready static build** of the website — pure HTML / CSS / JS, no backend needed.

## What's inside

```
build/
├── index.html
├── static/
│   ├── css/main.<hash>.css
│   └── js/main.<hash>.js
├── logo.png
├── hero-home-visit.png
├── service-*.{jpg,png,webp}
└── why-blessing.jpg
```

## How the booking form works

Since this is a static build, the booking form does **not** save to a database. Instead, when a patient submits the form it:

1. Collects all their details (name, phone, area, service, preferred date, message)
2. Opens **WhatsApp** in a new tab with a pre-filled formatted message
3. The patient just hits "Send" on WhatsApp and you get the booking on **+91 91563 91377**

No server, no API key, no monthly cost.

## Deployment options

### Option A — GitHub Pages (free)
1. Create a new public/private repository, e.g. `homevisitdentaltreatment-site`.
2. Push the contents of the `build/` folder to the `main` branch:
   ```bash
   cd build
   git init
   git add .
   git commit -m "Initial static site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo>.git
   git push -u origin main
   ```
3. Repo → **Settings → Pages** → Source: `main` → `/ (root)` → Save.
4. Wait 1–2 minutes. Your site goes live at `https://<your-username>.github.io/<repo>/`.
5. To use your own domain (`homevisitdentaltreatment.in`):
   - GitHub Pages → Custom domain → enter `homevisitdentaltreatment.in` → Save.
   - At your domain registrar add **4 A records** for the apex `@`:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - And a **CNAME** `www → <your-username>.github.io`
   - Wait 1–2 hours → HTTPS auto-issued.

### Option B — Netlify (drag & drop, free)
1. Go to https://app.netlify.com/drop
2. Drag the entire `build/` folder onto the page.
3. Done — your site is live within seconds. You can plug in `homevisitdentaltreatment.in` from Netlify's **Domain settings**.

### Option C — Hostinger / cPanel
1. Open File Manager → `public_html/`
2. Upload every file from `build/` into `public_html/`.
3. Done. The site is live at your domain.

## Important

- All images are served as **relative paths** (e.g. `./logo.png`), so the site works at the root of a domain *and* inside a subfolder like `username.github.io/repo/`.
- The site is a **single page** (`index.html`) with smooth scroll anchors — no routing required.
- The booking form uses `https://wa.me/919156391377?text=...` — works on mobile (opens WhatsApp app) and desktop (opens WhatsApp Web).
