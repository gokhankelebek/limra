# Limra Mediterranean Restaurant — Coming Soon

A warm, refined "opening soon" landing page for **Limra Mediterranean Restaurant & Café**, opening July 2026 in Holly Springs, NC.

> An elevated Mediterranean bistro by chefs Mehmetcan & Elif — döner and gyro from the spit, a fresh daily buffet, pastries and baklava, and a proper espresso bar.

## What's inside

```
.
├── index.html          # Entire site — single self-contained file
├── assets/
│   ├── limra-emblem-brown.jpg    # Used as og:image for social sharing
│   ├── limra-emblem-cream.jpg    # Alternate brand mark (cream variant)
│   └── limra-horizontal.jpg      # Horizontal lockup
└── README.md
```

The hero emblem is **embedded directly into `index.html` as base64**, so the page renders correctly even when previewed without the assets folder. The `assets/` folder is kept for proper Open Graph social-sharing previews when the site is deployed.

## Tech

- **Plain HTML, CSS, vanilla JS.** No build step, no framework, no dependencies.
- Google Fonts: Cormorant Garamond, EB Garamond, Italiana.
- Mailchimp integration via JSONP (no backend required).
- ~120 KB total, mostly the embedded emblem.

## Brand colors

| | Hex | Use |
|---|---|---|
| Cream | `#F2E5C9` | Background |
| Forest green | `#1F4A2E` | Primary text, accents |
| Bronze | `#A6713B` | Italic emphasis, hover states |
| Cream-light | `#FBF4DF` | Notify section background |

## Mailchimp setup

The signup form needs three values from your Mailchimp embedded-form code. Open `index.html`, search for `MAILCHIMP_CONFIG`, and replace:

```js
const MAILCHIMP_CONFIG = {
  url: 'https://YOURNAME.us21.list-manage.com/subscribe/post-json',
  u:   'YOUR_USER_ID',
  id:  'YOUR_AUDIENCE_ID',
};
```

**To find these:** Mailchimp → Audience → Signup forms → Embedded forms. The `<form action="...">` URL contains everything you need. The `u` and `id` are query-string parameters in that URL. Important: write `/post-json`, not `/post`.

The honeypot field name auto-syncs from the config — no separate step.

## Deploying

This is a static site. Easiest options, ranked:

1. **Netlify** — Drag `index.html` + `assets/` into [app.netlify.com/drop](https://app.netlify.com/drop). Done in 30 seconds. Or connect this GitHub repo for auto-deploy on every push.
2. **Vercel** — Connect the GitHub repo at [vercel.com/new](https://vercel.com/new). Same auto-deploy flow.
3. **Cloudflare Pages** — Connect the GitHub repo at [pages.cloudflare.com](https://pages.cloudflare.com). Free SSL, fast CDN.
4. **GitHub Pages** — In this repo's Settings → Pages → set source to `main` branch. Free, but no custom domain SSL without a few extra DNS steps.

For a custom domain (e.g. `limrarestaurant.com`), Netlify or Cloudflare Pages handle SSL automatically once you point your DNS at them.

## Local preview

Just open `index.html` in a browser. No server needed.

For nicer dev workflow:

```bash
npx serve .
```

## License

Brand assets © Limra Mediterranean Restaurant. Code released for the project.
