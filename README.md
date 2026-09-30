# Ember & Oak Coffee Roasters — Website

A single-page marketing site for **Ember & Oak Coffee Roasters**, a small-batch roastery at 14 Kiln Yard, Marlow Street, Portland, OR 97209.
The core message: coffee roasted in small batches every week and shipped within 48 hours of roasting.

Built with **plain HTML5 and CSS3 only**: no JavaScript, no frameworks, no npm, and no build step.
Open `index.html` in a browser and it works.

---

## File structure

```
index.html            → All page content (one page, anchored sections)
favicon.ico           → Browser tab icon (16/32/48px)
style.css             → All styling, organised into numbered sections
vercel.json           → Optional static-hosting config (caching + security headers)
README.md             → This file
assets/
└── images/
    ├── hero-roaster-drum-ember.jpg            Hero visual
    ├── about-roaster-hands-beans.jpg          About section
    ├── service-small-batch-roasting.jpg       Service card 01
    ├── service-single-origin-subscription.jpg Service card 02
    ├── service-wholesale-cafe-supply.jpg      Service card 03
    ├── service-barista-training.jpg           Service card 04
    ├── why-fresh-roast-beans-cooling.jpg      Why Us: Day 0
    ├── why-packing-shipping.jpg               Why Us: within 48 hours
    ├── why-cupping-table.jpg                  Why Us: on arrival
    ├── texture-roasted-beans-dark.jpg         Background texture (Why Us)
    ├── cta-pour-over-steam.jpg                CTA band background
    ├── og-share-roaster.jpg                   Social share image (1200×630)
    ├── logo-mark.png                          Logo for light backgrounds (transparent)
    ├── logo-mark-light.png                    Logo for dark backgrounds (header/footer)
    ├── favicon-32.png                         Browser icon (plus /favicon.ico at root)
    ├── apple-touch-icon.png                   iOS home-screen icon (180×180)
    └── avatar-placeholder-01..03.jpg          Placeholder portraits for testimonials
```

## Page sections

1. Sticky navigation (the mobile menu is a CSS-only checkbox toggle)
2. Hero with a "roast log" ticket
3. About / our story
4. Coffee & services: small-batch roasting, subscriptions, wholesale, barista training
5. Why choose us: a roast → ship → cup timeline and a comparison table
6. Social proof (**placeholder** testimonials, stats and partner logo slots)
7. Call-to-action band
8. Contact form (UI only)
9. Footer

---

## Editing content

- **Text:** open `index.html`. Each section starts with a comment banner like `<!-- 4. SERVICES / PRODUCTS -->`.
- **Placeholders:** search `index.html` for `[`. Values in square brackets are placeholders you need to replace: email, phone, hours, prices, workshop dates, stats, testimonial names, and this week's roast log.
- **Testimonials:** the quotes are examples written for layout. **Replace them with real, verified reviews** before launch, then remove the "Placeholder" tags and the placeholder note.
- **Colours, fonts, spacing:** change the CSS variables at the top of `style.css` (section 01, "Design tokens"). The whole site updates from there.
- **Images:** put a new file in `assets/images/` with the same filename, or update the `src` in `index.html`. Keep the `width` and `height` attributes in line with the new image's real proportions.
- **Social links:** the footer social links point to `#`. Swap in your real profile URLs.

### Making the contact form send email

The form is UI only, because a static site has no backend. To receive messages, sign up for a form service such as Formspree, Basin or Getform. Then change the opening form tag:

```html
<form class="contact-form" action="https://formspree.io/f/YOUR_ID" method="post">
```

No JavaScript is needed.

### Before going live

- Change `https://www.example.com/` in the `<link rel="canonical">` tag to your real domain.
- Social platforms need absolute URLs for share images. Change `og:image` and `twitter:image` to full URLs, e.g. `https://yourdomain.com/assets/images/og-share-roaster.jpg`.

---

## Running locally

Double-click `index.html`. That's all.
(If you'd like a local server anyway: `python3 -m http.server` and visit http://localhost:8000.)

## Deploying to Vercel

**Option A: dashboard**
1. Push this folder to a GitHub, GitLab or Bitbucket repository.
2. In Vercel, click **Add New → Project** and import the repository.
3. Framework preset: **Other**. Leave the Build Command and Output Directory **empty**.
4. Click **Deploy**.

**Option B: drag & drop / CLI**
- Run `vercel` from this folder with the Vercel CLI and accept the defaults. No build settings are required.

There is no `package.json`, no install step, no build step and no environment variables. Vercel serves the files as they are.
