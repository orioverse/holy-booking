# Holy Booking

**The Holy Family's Journey in Egypt** — a trilingual (English / العربية / Deutsch) scrollytelling site that follows the Holy Family's route through Egypt on an interactive 3D map, with booking for hotels, transport, restaurants and experiences near each site.

This is the **initial version (v0.1.0)**: a single self-contained page.

## Features

- **i18n:** EN, AR (full RTL) and DE with instant switching; language chosen from `?lang=`, saved preference, or browser language. Numbers, years and units are formatted per locale at runtime.
- **3D journey map:** Three.js map of Egypt with camera moves driven by GSAP ScrollTrigger as you scroll through the stops.
- **7 featured stops:** Wadi El-Natroun, Matariya, Old Cairo (Abu Serga & the Hanging Church), Maadi, Gabal El-Teir, Al-Muharraq and Mount Dranka, each with a story, highlights, access info and an illustrated image card.
- **Partner listings:** hotels, restaurants, transport and experiences per stop (sample data), plus a ride deep-link.
- **Design:** dark background, warm gold accents, editorial typography (Bodoni Moda / Hanken Grotesk; Amiri / IBM Plex Sans Arabic), glassmorphism panels.
- Accessibility: skip link, focus styles, live-region announcements, `prefers-reduced-motion` support.

## Run locally

No build step. Serve the folder with any static server:

```bash
python3 -m http.server 8080
# open http://localhost:8080/?lang=ar
```

Dependencies load from CDNs: Three.js r128, GSAP 3.12.5 + ScrollTrigger (cdnjs), and Google Fonts.

## Project structure

```
index.html   # markup, styles, content data (DATA object) and app script
```

All translatable content lives in the `DATA` object inside `index.html` (`meta`, `journey`, `locales.{en,ar,de}`, `stops[]`, `partners[]`). Coordinates are `[lat, lng]` and never translated.

## Notes

- Photo upload on the image cards uses the Claude artifact runtime (`window.claude`) and is disabled automatically when the page is hosted elsewhere; the built-in illustrations are shown instead.
- Partner entries marked `sample: true` are placeholders. Partner fees and contracts are intentionally not part of the public data.

## Roadmap

- Split into modules (`/src`, `/locales/*.json`, `/data/stops.json`)
- Real partner onboarding and booking flow
- Photography for each site
