# Brand Globe — Claude Instructions

## Project Overview
Single-file app (`index.html`) — all HTML, CSS, and JavaScript in one file. No build step.

## Architecture
- **Globe**: Globe.gl v2.30.0 with `htmlElementsData` for brand markers
- **Markers**: `.brand-marker` divs with `dataset.lat` / `dataset.lng` for culling
- **Culling**: RAF loop in `cullBacksideMarkers()` hides markers behind the geometric limb using dot product: `dot < gr/dist + 0.06`
- **Popup**: CSS transition-based (`.visible` class toggle), no GSAP
- **Cloud layer**: Derived from Globe.gl's internal Three.js scene — no external Three.js CDN
- **Icons**: `https://cdn.simpleicons.org/{slug}` with `filter: brightness(0) invert(1)` on markers; colored in popup/search

## Key Constants
- Globe radius: 100 (Globe.gl default, via `world.getGlobeRadius()`)
- Camera altitude: 2.2 (set in `world.pointOfView`)
- `htmlAltitude`: 0 (markers sit on the surface)
- Auto-rotate speed: 0.5, resumes 2s after drag ends

## Brand Data
`const brands = [...]` — each entry has: `name, icon, lat, lng, country, flag, sector, hq, founded, revenue`

Icon slugs come from [simpleicons.org](https://simpleicons.org/). If no icon exists, the marker falls back to 2-letter initials.

## Dev Server
```bash
npx serve -p 3456 .
```
Preview at `http://localhost:3456`

## Things to Avoid
- Do NOT add an external Three.js CDN — conflicts with Globe.gl's bundled copy
- Do NOT use `globeBumpImageUrl` — not a valid Globe.gl method
- Do NOT use GSAP — was removed; use CSS transitions instead
- Do NOT add dark/light mode toggle — was removed at user request
