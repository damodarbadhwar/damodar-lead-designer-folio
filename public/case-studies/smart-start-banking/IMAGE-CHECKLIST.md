# Smart Start Banking — image assets to drop in

All paths are relative to `public/`. Drop the file with the exact name below — the page will pick it up automatically. Until a file is present, the layout shows a `bg-grey-200` placeholder, so the page never breaks.

## Required

- `case-studies/smart-start-banking/hero.jpg` — full-width hero. Aspect 1160:434 (≈ 2.67:1). Export at 2320×868.
- `case-studies/smart-start-banking/team.jpg` — "My role & team shape" wide image. Aspect 1160:416. Export at 2320×832.
- `case-studies/smart-start-banking/persona-mark-ethan.jpg` — square persona portrait, 200×200 minimum. Export at 400×400.

## Key wins + Pushbacks — videos

All mockup slots in **Key wins** and **Proposals that were pushed back** sections are wired up as `.webm` videos. Each plays autoplay + muted + loop + playsinline. Encode at 280×552 (or 560×1104 retina) portrait aspect so it fills the slot cleanly.

Either `img:` or `video:` works in the data — swap freely in `src/pages/work/smart-start-banking.astro`.

### Key wins (2 pairs)

- `case-studies/smart-start-banking/pp-before.webm` — pre-fill flow, before
- `case-studies/smart-start-banking/pp-after.webm` — pre-fill flow, after
- `case-studies/smart-start-banking/tnc-before.webm` — terms & conditions, before
- `case-studies/smart-start-banking/tnc-after.webm` — terms & conditions, after

### Pushbacks (2 pairs)

- `case-studies/smart-start-banking/rejected-1-before.webm`
- `case-studies/smart-start-banking/rejected-1-after.webm`
- `case-studies/smart-start-banking/rejected-2-before.webm`
- `case-studies/smart-start-banking/rejected-2-after.webm`

## Notes

The next-read card uses `/flipkart-upi.jpg` (already in `public/`).

Preview the page at: http://localhost:4321/work/smart-start-banking
