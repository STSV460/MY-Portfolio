# My Portfolio — CLAUDE.md

## Project Overview

Single-file React portfolio website. Everything (HTML, CSS, JS, React components) lives in
`Portfolio.html`. There is no build step, no package.json, and no server — just open the
file directly in Chrome.

## Tech Stack

| Technology | Version | How loaded |
|---|---|---|
| React | 18.3.1 | CDN (unpkg) |
| React DOM | 18.3.1 | CDN (unpkg) |
| Babel Standalone | 7.29.0 | CDN (unpkg) — transpiles JSX in-browser |
| EmailJS | v1.0 REST API | direct fetch call |
| Google Fonts (Inter) | — | CDN |

## How to Run / Test

Just open `Portfolio.html` in Chrome. No server, no `npm install`, no build.

To test the contact form:
1. Open `Portfolio.html` in Chrome
2. Press F12 → open **Console** and **Network** tabs
3. Fill in the contact form and click **Send Message**
4. Check the Network tab for the POST to `api.emailjs.com` — inspect the response body
5. Check inbox at `pvshariharan324@gmail.com` (also check Spam)

## Files

```
My Portfolio/
├── Portfolio.html      ← entire app (HTML + CSS + React components)
├── photo_data.js       ← base64-encoded profile photo (window.PHOTO_DATA)
├── photo.jpeg          ← source photo
└── uploads/            ← screenshot assets
```

## Key Component Locations (all in Portfolio.html)

| Component | Approx. line |
|---|---|
| CSS variables / global styles | 12–300 |
| `Nav` | ~650 |
| `Hero` | ~720 |
| `About` | ~790 |
| `Skills` | ~850 |
| `Projects` | ~890 |
| `Contact` | 928–1069 |
| `Footer` | 1071–1090 |
| `App` (root) | ~1142 |

## EmailJS Configuration

Located at lines 944–946 in `Portfolio.html`:

```js
const EMAILJS_SERVICE_ID  = 'service_x7g0qh7';
const EMAILJS_TEMPLATE_ID = 'template_wqke4qx';
const EMAILJS_PUBLIC_KEY  = 'WMIE-TQ3P9tB0rwGU';
```

EmailJS dashboard: https://dashboard.emailjs.com

The contact form sends these `template_params`:
- `to_email` — recipient (`pvshariharan324@gmail.com`)
- `from_name` / `name` — sender name
- `from_email` / `email` — sender email
- `reply_to` — sender email (for easy reply)
- `message` — message body
- `title` — subject line
- `time` — timestamp

## Owner Contact

- Email: pvshariharan324@gmail.com
- GitHub: https://github.com/STSV460
