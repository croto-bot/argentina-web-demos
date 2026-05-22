---
name: static-landing-page-design
description: "Build a fast, beautiful, conversion-focused static (HTML/CSS) business website and deploy it to GitHub Pages or Cloudflare Pages. Use when redesigning a small/medium business site to pitch a rebuild."
---

# Static Landing Page Design

Build a fast, beautiful, conversion-focused **static** website (HTML + CSS + assets only — no backend, no build step required) and deploy it to GitHub Pages or Cloudflare Pages. Use this when redesigning a small/medium business website to pitch the owner a rebuild.

## Goal of the page

This is a **demo built to sell a rebuild**. The owner should open it and feel "this is so much better than what I have now." Optimize for that emotional reaction and for the actions a real customer would take (call, WhatsApp, book, get directions, see the menu/services).

## Hard rules

- Output is static only: `index.html`, a `styles.css` (or inline `<style>`), and an `assets/` folder. No frameworks that need a build, no server code. A single self-contained `index.html` is acceptable and often best for a demo.
- Mobile-first and fully responsive. Most LATAM local-business traffic is mobile.
- Must load fast: optimized/compressed images, system fonts or one webfont max, no heavy libraries.
- Real, specific content for the business (name, services, hours, location, real-sounding copy in the business's language — Spanish/Portuguese as appropriate). Never leave "Lorem ipsum" or placeholder brackets in a demo you ship.
- Accessible: semantic HTML, alt text, sufficient color contrast, tap targets >= 44px.

## Page structure (default)

1. **Hero**: business name, one-line value prop, primary CTA (Call / WhatsApp / Reservar), background image or color.
2. **Services / menu / offerings**: clear cards or list with prices if relevant.
3. **Why us / trust**: 3 short benefits, years in business, certifications.
4. **Social proof**: 2-4 testimonials or star rating (use real Google reviews if found during research).
5. **Gallery**: 3-6 images of the place/work.
6. **Location & hours**: address, embedded map (static image or simple iframe), opening hours.
7. **Contact / footer**: phone, WhatsApp link (`https://wa.me/<number>`), email, social links, sticky mobile call/WhatsApp button.

## Visual quality

- Pick a small, tasteful palette derived from the business's brand or vertical. Define CSS custom properties for colors and spacing.
- Generous whitespace, clear type scale, consistent rounded corners and shadows.
- One clear primary CTA color used consistently.
- Use modern CSS (flexbox/grid, clamp() for fluid type). Avoid clutter.

## Images

- Use royalty-free or generated placeholder imagery that fits the vertical when real photos aren't available, but prefer real photos found during prospecting.
- Always compress. Lazy-load below-the-fold images (`loading="lazy"`).

## Deploy

Deploy the finished site and return a **public live URL**. Two supported paths:

### GitHub Pages
1. `git init`, commit the static files at repo root (or `/docs`).
2. Create a repo via `gh repo create <name> --public --source . --push` (if `gh` is available) or push to a new remote.
3. Enable Pages on the `main` branch root (`gh api` or repo settings). The site serves at `https://<user>.github.io/<repo>/`.

### Cloudflare Pages
1. `wrangler pages deploy <dir> --project-name <name>` (requires `wrangler` + `CLOUDFLARE_API_TOKEN`).
2. The site serves at `https://<project>.pages.dev`.

Pick whichever has working credentials in the environment. If neither is configured, report exactly which credential/secret is missing so the owner can provision it — do not silently skip deploy. Always verify the live URL returns HTTP 200 before reporting it as done.

## Definition of done

- Live, public URL that loads correctly on mobile and desktop.
- All business details correct, no placeholders.
- A primary CTA that works (tel:, wa.me, or booking link).
- Reported URL verified reachable.