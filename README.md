# Pico website

Astro static site. Splash page now; Menu and About are placeholder pages ready to fill in.

## Run locally

```bash
npm install
npm run dev        # http://localhost:4321
```

## Structure

```
src/
  layouts/Base.astro       <head>, fonts, header + footer wrapper (every page uses this)
  components/Header.astro  Spring Menu · tagline · About
  components/Footer.astro  email signup + copyright
  components/Logo.astro    PICO wordmark (SVG, color follows CSS)
  pages/index.astro        splash page
  pages/menu.astro         placeholder
  pages/about.astro        placeholder
  styles/global.css        colors, fonts, base styles
public/
  fonts/                   TT Commons Pro Condensed Bold (woff2, Latin subset)
  favicon.svg
```

Colors and fonts are CSS variables at the top of `src/styles/global.css`.

## Deploy (Netlify)

1. Push this folder to a GitHub repo.
2. Netlify → Add new site → Import from GitHub → pick the repo.
   Build command `npm run build`, publish directory `dist` (auto-detected).
3. Email signups appear under **Forms** in the Netlify dashboard.
   (Enable form detection in Site settings → Forms if it isn't on.)
4. Domain: Site settings → Domain management → add your domain and follow the DNS steps.

On Cloudflare Pages or Vercel the site works the same, but the email form needs
a different backend (e.g. Buttondown, Mailchimp, Formspree) — change the form's `action`.

## Before launch

- **Font license:** `public/fonts/` currently holds the *trial* TT Commons Pro.
  Replace it with the licensed web font (convert to woff2, same filename) and
  make sure the license covers web embedding.
- Footer body text uses Barlow as a stand-in; swap `--font-body` in
  `global.css` if you license regular TT Commons.
- Logo is from the original vector (pico-logo.pdf).
