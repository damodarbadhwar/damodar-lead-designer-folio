# Damodar Badhwar — Folio

Personal portfolio site. Built with **Astro 5 + Tailwind CSS v4**, deployed on **Netlify**.

## Run locally

```bash
npm install
npm run dev
```

Open http://localhost:4321 in your browser. Hot reload is on — every save shows up live.

## Stack

- **Astro 5** — static site generator, ships near-zero JS by default.
- **Tailwind CSS v4** — design tokens defined in `src/styles/global.css` via `@theme`.
- **No external animation library** — fades use IntersectionObserver + CSS transitions, hovers use Tailwind variants.
- **Inter** (UI) + **Noto Serif** (display) loaded from Google Fonts.

## Project structure

```
src/
├── pages/
│   └── index.astro            ← Phase 0 foundation preview (replaced in Phase 1)
├── layouts/
│   └── BaseLayout.astro       ← <head>, fonts, meta, OG tags
├── components/
│   ├── Nav.astro              ← Sticky pill nav (Home / About)
│   ├── FadeIn.astro           ← Scroll-fade wrapper (IntersectionObserver)
│   └── Swatch.astro           ← Token preview swatch (Phase 0 only)
└── styles/
    └── global.css             ← Tailwind import + design tokens (@theme)
public/
└── favicon.svg
```

## Design tokens

All colors, fonts, and type sizes live in `src/styles/global.css` under `@theme`. Edit there, restart dev, everything updates.

## Deploy

Push to GitHub → Netlify auto-builds. (Wired up in Phase 5.)
