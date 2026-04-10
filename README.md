# Brand Globe 🌍

An interactive 3D globe showcasing 150+ world-famous brands placed on their home countries.

## Features

- **3D Photorealistic Earth** — Blue marble texture with cloud layer and atmosphere glow
- **150+ Brands** across 100+ countries — each pinned to their exact home country
- **Hover Popups** — Brand logo, country, sector, HQ, founded year, and revenue
- **Search** — Find any brand or country instantly
- **Auto + Manual Rotation** — Globe auto-spins; drag to rotate manually, auto-resumes after 2s
- **Smart Culling** — Markers only appear on the visible hemisphere, fade near the limb
- **Country Labels** — Major countries labeled on the globe surface

## Tech Stack

- [Globe.gl](https://globe.gl/) — WebGL 3D globe rendering
- [Three.js](https://threejs.org/) — 3D scene (bundled inside Globe.gl)
- [Simple Icons CDN](https://simpleicons.org/) — Brand SVG logos
- [Google Fonts — Outfit](https://fonts.google.com/specimen/Outfit) — Typography
- Pure HTML / CSS / JavaScript — No build tools, no frameworks

## Live Demo

[brand-globe.vercel.app](https://brand-globe.vercel.app)

## Local Setup

Just open `index.html` in a browser, or serve with any static server:

```bash
npx serve .
```

## Adding a New Brand

In `index.html`, find the `const brands = [...]` array and add an entry:

```js
{
  name: "Brand Name",
  icon: "simpleicons-slug",   // from simpleicons.org
  lat: 37.09,                  // country latitude
  lng: -95.71,                 // country longitude
  country: "USA",
  flag: "🇺🇸",
  sector: "Technology",
  hq: "Cupertino, CA",
  founded: 1976,
  revenue: "$394B"
}
```

Find the icon slug at [simpleicons.org](https://simpleicons.org/).

## Author

Built by [@aamir-16](https://github.com/aamir-16)
