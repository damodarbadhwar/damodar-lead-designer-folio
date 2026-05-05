# Project instructions — Damodar's folio

Paste this into the first message of any new chat working on this site. Each chat = one new page (case study, about, etc.).

---

## What this is

Personal folio for **Damodar Badhwar — Lead Product Designer**. Live preview at `localhost:4321`. Deploys to Netlify from GitHub repo `damodar-lead-designer-folio`. Project folder: `~/Documents/Claude Cowork/Design folio`.

## Stack

- **Astro 5** — static site generator, ships near-zero JS by default
- **Tailwind CSS v4** — design tokens defined inline in `src/styles/global.css` via `@theme`
- **No external animation library** — fades use IntersectionObserver + CSS transitions, hovers use Tailwind variants
- **Inter** (UI) + **Noto Serif** (display) loaded from Google Fonts in `BaseLayout.astro`

## Run locally (Mac)

```bash
cd ~/"Documents/Claude Cowork/Design folio"
npm install     # first time only
npm run dev     # http://localhost:4321
```

Hot reload is on — edits show immediately. Don't run `npm audit fix --force`.

If a class isn't applying, **restart `npm run dev`**. Tailwind v4's JIT scanner silently bails on `.astro` syntax errors.

## Project structure

```
src/
├── pages/
│   ├── index.astro                  ← Home
│   └── work/
│       ├── smart-start-banking.astro
│       └── flipkart-upi.astro
├── layouts/
│   └── BaseLayout.astro             ← <head>, fonts, meta, OG tags
├── components/
│   ├── Nav.astro                    ← Sticky pill nav (Home / Resume)
│   ├── Hero.astro                   ← Home page only, named slot "nav"
│   ├── SectionTitle.astro           ← All section headings
│   ├── ProjectCard.astro            ← Case-study tile on home
│   ├── ArticleCard.astro            ← Horizontal article card
│   ├── AboutSection.astro           ← About panel + duotone avatar
│   ├── SiteFooter.astro             ← Footer with social links
│   ├── FadeIn.astro                 ← Scroll-fade wrapper
│   ├── TextBlock.astro              ← Typography variants (see Typography table)
│   ├── MetaData.astro               ← Case-study summary block
│   └── NumberedItem.astro           ← Case-study numbered list rows
└── styles/
    └── global.css                   ← Tailwind import + design tokens (@theme)
public/
├── hero-image.jpg / footer-avatar.png / Resume-...pdf
├── projects/{smart-start-banking,flipkart-upi}.jpg
├── articles/{progress-tracker,user-survey-library}.jpg
└── case-studies/<slug>/             ← Per case study assets
```

---

## Design tokens

All colors, fonts, and type sizes live in `src/styles/global.css` under `@theme`. Edit there, restart dev, everything updates. **Never hardcode hex** in `.astro` files — extend the token instead.

### Colors

| Utility | Hex | Use |
|---|---|---|
| `bg-surface-1` / `text-surface-1` | `#FFFFFF` | Default page bg |
| `bg-surface-2` / `text-surface-2` | `#F6F8FB` | Panel bg (about, footer, article cards) |
| `border-divider` / `bg-divider` | `#DBE0EC` | Borders, hairlines, table rows |
| `bg-grey-200` | `#EDEAEA` | Tag chip bg, mockup wells |
| `text-ink-1` / `bg-ink-1` | `#212121` | Body text default, primary buttons, headlines |
| `text-ink-3` | `#454545` | Display fonts (hero, section titles), footer note |
| `text-ink-muted` | `#6C6C6C` | Captions / muted body |

#### Process plan accents (case-study scoped)

Used only on the workshop plan rows. Don't reuse elsewhere without promoting them to tokens.

| Phase | Accent |
|---|---|
| Discovery | Cyan |
| Craft | Orange |
| Handoff | Green |

### Typography

Fonts: `font-sans` = Inter, `font-serif` = Noto Serif. All variants used across the site (home + case studies) live here. Case-study type goes through `src/components/TextBlock.astro` — don't hand-roll text classes inside case studies, extend the variant map instead.

| Variant | Spec | Use |
|---|---|---|
| `text-display-hero` | Noto Serif Medium, **mobile 32px** / **desktop 56px**, line-height 1.2, tracking `-0.64px md:-1.12px` | Home hero title, case study page H1 |
| `SectionTitle` | `text-[24px] md:text-[32px]` italic semibold serif, `tracking-[-0.24px] md:tracking-[-0.32px]`, line-height 1.2 | All section headings — use `<SectionTitle>` |
| `text-h5` (medium) | 20px / 1.4 / weight 500 | Case study card titles |
| `text-h5` (regular) | 20px / 1.4 / weight 400 | Lead paragraphs, key findings |
| `text-body` | 14 / 20 | Body, button labels, text-buttons, meta |
| `body-medium` | 14 weight 500 | Inline emphasis |
| `body-semibold` | 14 weight 600 | Names, labels in prose |
| `text-caption` | 12px / medium / uppercase / line-height 1 / tracking 0.02em | Tag chips, image captions, two-col label column, metadata keys |
| `Display` | `text-[24px] md:text-[32px]` semibold, tracking 0, line-height 1.2 | Success metric numbers |
| `text-quote` | Italic 18 / 20 lh | Pull quotes |

**Tailwind v4 JIT gotcha**: variant-lookup maps typed as `Record<string, string>` sometimes get missed by the scanner — classes silently don't apply. Inline class strings literally for any variant that's typographically critical.

### Spacing rhythm — global page shell

- Mobile gutters: `px-5` (20px)
- Desktop gutters: `md:px-[150px]`
- Max content width: `max-w-[1540px]` (centered)
- Section vertical: `pb-16 md:pb-24`
- Inner gaps: 6 / 8 / 10 / 16

### Spacing rhythm — case study pages

Pick from this scale. Don't invent new gaps.

| Gap | Sections |
|---|---|
| `pt-6` (24px) | Page top → nav |
| `pt-14` (56px) | Nav → H1 |
| `mb-14` (56px) | After Title, Summary, Hero, Win rows |
| `mb-[72px]` | After Overview, Refined brief, My role image, Process plan, Persona, Success metrics, Next read |
| `mb-10` (40px) | After section-title-only blocks (Persona title, Key wins title, Internal alignment, My role text, Process intro) |
| `mb-6` (24px) | Between key findings → comp table (tight pairing) |

Case-study horizontal gutters: `px-4` mobile, `md:px-[60px]` desktop.

### Width rhythm — case study pages

Each container width signals a different reading mode. Mixing widths makes a page feel janky.

| Width | Sections |
|---|---|
| **1280px** | Title, Summary, Hero, Overview, Internal alignment, Comp study, Refined brief, My role, Process, Persona, Success metrics, Next read |
| **1400px** | Key wins, Pushbacks (wider for side-by-side mockup comparisons) |
| **full-bleed** | Thank you |

### Inner two-col layout

Used on Overview, Internal alignment, Refined brief, My role, Success metrics:

```
280px label column  →  32px gap  →  flex-1 content column
```

Label = `text-caption` variant. Content = `text-h5` (regular) or `text-body`.

### Radii & shadows

The home page uses lifts and shadows. Case studies lean **flat** — borders only, no shadows, no rounded full-bleed sections.

- Cards (home): `rounded-xl md:rounded-2xl`
- Buttons / chips: `rounded-lg` / `rounded`
- Pill nav: `rounded-full`
- Resting nav shadow: `shadow-[0_8px_24px_rgba(0,0,0,0.05),0_2px_6px_rgba(0,0,0,0.04)]`
- Card hover lift: `hover:-translate-y-1 hover:shadow-[0_14px_32px_rgba(0,0,0,0.08)]`
- Article hover: `hover:-translate-y-0.5 hover:shadow-[0_10px_24px_rgba(0,0,0,0.06)]`
- Button hover: `hover:-translate-y-0.5 hover:shadow-[0_6px_16px_rgba(0,0,0,0.10)]`
- All transitions: `duration-200` (UI) or `duration-300` (cards)
- Case study cards max: `rounded-lg`. No shadows. Mockup wells use `bg-grey-200` only — no border, no shadow.

If you reach for `shadow-md` or `border-2` on a case study, stop and ask whether the layout is doing the work.

---

## Components — reuse before creating new ones

```
src/components/
├── BaseLayout.astro     ← <head>, fonts, meta. Wrap every page.
├── Nav.astro            ← Sticky pill nav. Props: { active?: "home" | "resume" }
├── Hero.astro           ← Home only. Named slot "nav".
├── SectionTitle.astro   ← All section headings. Props: { class? }
├── ProjectCard.astro    ← Case-study tile. Props: { href, image, imageAlt, title, blurb, showcases[] }
├── ArticleCard.astro    ← Horizontal article card
├── AboutSection.astro   ← About panel + duotone avatar overflow
├── SiteFooter.astro     ← Footer with social links
├── FadeIn.astro         ← Wrapper. Props: { delay?: number, class?, as? }
├── TextBlock.astro      ← Typography variants (see Typography table)
├── MetaData.astro       ← Case-study Summary block (role, year, team)
└── NumberedItem.astro   ← Case-study numbered list rows
```

### FadeIn usage (animation pattern)

Wrap any element that should fade in on scroll:

```astro
<FadeIn>
  <SectionTitle>Heading</SectionTitle>
</FadeIn>

<!-- Stagger by passing delay (ms) -->
{items.map((item, i) => (
  <FadeIn delay={100 + i * 100}>
    <ProjectCard {...item} />
  </FadeIn>
))}
```

Section titles, paragraphs, cards, images all fade in. Hover states are CSS-only (no FadeIn needed).

### Mockup slots (case studies)

Section data fields support both `img:` and `video:`:

- **Images** — rendered as-is.
- **Videos** — `autoplay muted loop playsinline`, `object-contain`, **no bg / border / rounding** so iPhone mockup videos blend seamlessly into the surrounding canvas.

If a video shows a visible frame/edge, check the wrapper isn't applying `overflow-hidden rounded-*` — those should live on the device frame inside the asset, not the wrapper.

---

## Image handling

Drop into `public/`. Reference as `/filename.ext`. The image area shows a `bg-grey-200` placeholder if the file is missing — layout never breaks.

Image filenames already wired up:

```
public/
├── hero-image.jpg
├── footer-avatar.png
├── Resume-Damodar-Lead-Product-Designer-2026.pdf
├── projects/{smart-start-banking,flipkart-upi}.jpg
└── articles/{progress-tracker,user-survey-library}.jpg
```

For new case study pages: `public/case-studies/<slug>/<asset>.{jpg,webm}`. Conventions:

```
public/case-studies/<slug>/
├── hero.jpg
├── team.jpg
├── persona-<role>-<name>.jpg          ← e.g. persona-mark-ethan.jpg
├── <feature>-before.webm              ← e.g. pp-before.webm
├── <feature>-after.webm
└── IMAGE-CHECKLIST.md                 ← Per-case-study list of required assets
```

Videos: `.webm` preferred. Always have a static `.jpg` poster for hero.

---

## Page conventions

### Where pages live

- Home: `src/pages/index.astro`
- Case studies: `src/pages/work/<slug>.astro` (e.g. `work/smart-start-banking.astro`)
- Standalone: `src/pages/<slug>.astro`

### Page skeleton

```astro
---
import BaseLayout from "../layouts/BaseLayout.astro";
import Nav from "../components/Nav.astro";
import SectionTitle from "../components/SectionTitle.astro";
import FadeIn from "../components/FadeIn.astro";
import SiteFooter from "../components/SiteFooter.astro";
---

<BaseLayout title="Page title" description="SEO blurb">
  <Nav active="home" />

  <main class="mx-auto w-full max-w-[1540px] px-5 py-12 md:px-[150px] md:py-16">
    <FadeIn>
      <SectionTitle>Section name</SectionTitle>
    </FadeIn>
    <!-- Content -->
  </main>

  <SiteFooter />
</BaseLayout>
```

### Content lives in the page file

Don't create a CMS or separate data files. Put content directly in the page's frontmatter as JS objects so Damodar can edit it inline:

```astro
---
const sections = [
  { title: "Problem", body: "..." },
  { title: "Approach", body: "..." },
];
---
{sections.map((s, i) => (
  <FadeIn delay={100 + i * 100}>
    <h3 class="text-h5 font-medium text-ink-2">{s.title}</h3>
    <p class="text-body text-ink-2">{s.body}</p>
  </FadeIn>
))}
```

### Case study section order

Mirror Smart Start Banking unless the brief explicitly differs:

Title → Summary metadata → Hero → Overview → Internal alignment → Comp study (key findings + benchmark table) → Refined brief → My role + image → Process intro + workshop plan → Persona + 4-card grid → Key wins → Pushbacks → Success metrics → Thank you → Next read.

**Figma source**: file key `QSKAV1CUWvprU4PBlZAqYO`. Pull design context with `mcp__figma...get_design_context` using `fileKey` + the page nodeId. Reference Figma node IDs (e.g. `47:1705`) as shared vocabulary instead of describing renders.

---

## Working style — important

1. **Mobile-first**, then `md:` overrides for desktop. Default `md` = 768px.
2. **Desktop is 1540px max** centered with `mx-auto max-w-[1540px]`.
3. **Always wrap in `<BaseLayout>` and end with `<SiteFooter />`** unless told otherwise.
4. **Use existing components** before writing new HTML.
5. **All new sections fade in**: wrap in `<FadeIn>`, stagger lists with `delay={i * 100}`.
6. **Hover states**: use the rules in "Radii & shadows" — don't invent new ones.
7. **No emojis, no markdown headers in HTML.** Use `<h1>`, `<h2>`, etc. with the typography utilities.
8. **Don't add CMS, frameworks, or libraries** without asking. Astro + Tailwind is the whole stack.
9. **One issue at a time.** Fix-and-verify loops, not batched rewrites.
10. **Element-inspector classes > screenshots** when a render is wrong. Faster to diagnose.
11. **Section-scoped fixes.** Don't touch the whole page when one section is wrong.

---

## Workflow when starting a new page

1. Ask Damodar:
   - What's the page about? (case study, about, blog post, etc.)
   - URL slug?
   - What sections does it need?
   - Which images, where to source them, what filenames?
2. Show a structure plan before writing code.
3. Build the page in `src/pages/...` using the skeleton above.
4. Apply width + spacing rhythm **before** filling in content. Skeleton first.
5. Use `TextBlock` for every text element on case studies. No raw `<p class="text-...">`.
6. Update `public/case-studies/<slug>/` with image filenames in `IMAGE-CHECKLIST.md`.
7. Tell Damodar the new URL — `localhost:4321/work/<slug>` — to preview.
8. Iterate on his feedback.

---

## Deploy

Push to GitHub → Netlify auto-builds.

---

## Open structural debt

- `TextBlock`'s variant-map could be refactored to inline conditionals if more JIT detection issues appear.
- Persona "About" column still uses inline HTML (semibold names + lists), not yet converted to TextBlock variants.
- Custom `text-*` sizes used in a few places but not exhaustive — consider a typographic audit before case study #3.
