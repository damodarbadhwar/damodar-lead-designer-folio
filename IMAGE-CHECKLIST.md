# Image export checklist

Drop these into `public/` exactly with these filenames. The site is wired up — once a file is in the right place it'll show up immediately.

## Hero section

| File | Path | Source in Figma | Recommended export |
|---|---|---|---|
| Hero image | `public/hero-image.jpg` | The "PLAY × LINE FRIENDS" image at the top of home | JPG @ 1624×960 (2× for retina), 80% quality |
| Gradient background | `public/gradient-bg.png` *(optional)* | The soft pastel backdrop behind the hero | PNG @ 1280×1055. **Site has a CSS fallback** — only export if the CSS approximation doesn't match closely enough. |

## Case study thumbnails

| File | Path | Recommended export |
|---|---|---|
| Smart start banking | `public/projects/smart-start-banking.jpg` | JPG @ 1224×712, aspect 612:356 |
| Flipkart UPI | `public/projects/flipkart-upi.jpg` | JPG @ 1224×712, aspect 612:356 |

## Article thumbnails

| File | Path | Recommended export |
|---|---|---|
| Progress tracker | `public/articles/progress-tracker.jpg` | JPG @ 600×374, aspect 300:187 |
| User survey library | `public/articles/user-survey-library.jpg` | JPG @ 600×374, aspect 300:187 |

## About / Footer

| File | Path | Recommended export |
|---|---|---|
| Footer avatar | `public/footer-avatar.png` | PNG @ 960×960 (transparent background, blue duotone portrait). 2× for retina. |

## Resume

| File | Path | Notes |
|---|---|---|
| Resume PDF | `public/Resume-Damodar-Lead-Product-Designer-2026.pdf` | The "Resume" button in the nav opens this. **Filename must match exactly** including capitalization. |

---

## How to export from Figma (quick reminder)

1. Click the layer in Figma.
2. **Export** panel (bottom-right) → set format **JPG** (photos) or **PNG** (anything with transparency).
3. **Scale: 2x** for crisp retina display.
4. Click **Export [layer name]** → save to the right path above.

## What happens if a file is missing?

The image area shows a grey placeholder (`bg-grey-200`). The layout stays intact. Add files when you're ready — no rebuilds needed during dev (just refresh).
