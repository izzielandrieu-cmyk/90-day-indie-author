# The Self-Editing Field Guide — Izzie Writes

Sales page for *The Self-Editing Field Guide* by Izzie Writes.

## File structure

```
izzie-writes-site/
├── index.html        ← Main page (hero + guide previews + outcome messaging + CTA)
├── css/
│   └── styles.css    ← All styles
├── js/
│   └── main.js       ← Scroll reveal animations
└── README.md
```

## Deploy to GitHub Pages

1. **Create a new repo** on GitHub (e.g. `izzie-writes-site` or your username.github.io)
2. **Upload these files** — drag and drop into the repo, or push via git:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```
3. **Enable GitHub Pages**
   - Go to your repo → Settings → Pages
   - Source: **Deploy from a branch**
   - Branch: `main` / `root`
   - Save — your site will be live at `https://YOUR_USERNAME.github.io/YOUR_REPO/`

## Before you publish

- **Update the buy link** — find `href="#"` on the CTA button in `index.html` and replace `#` with your Gumroad, Payhip, or Shopify link.
- **Custom domain** (optional) — add a `CNAME` file to the repo root containing your domain (e.g. `store.izziewrites.com`), then point your DNS to GitHub Pages.

## Fonts

The page loads Cormorant Garamond, DM Sans, and DM Mono from Google Fonts. All three have graceful system-font fallbacks (Georgia, Helvetica Neue, Courier New) if Google Fonts is unavailable.

## Editing the page

| What you want to change | Where to look |
|---|---|
| Buy button link | `index.html` — search for `href="#"` near "Get the Field Guide" |
| Headline / body copy | `index.html` — each section is clearly commented |
| Colours | `css/styles.css` — `:root` block at the top |
| Guide preview content | `index.html` — each guide preview is wrapped in `<!-- 01 DEVELOPMENTAL -->` etc. |
| Animations / timing | `js/main.js` and `transition-delay` attributes in `index.html` |
