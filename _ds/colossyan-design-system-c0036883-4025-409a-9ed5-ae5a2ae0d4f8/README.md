# Colossyan Design System

A usable, HTML-first replica of Colossyan's brand and product surface — enough to design, prototype, and mock against with confidence.

## What Colossyan is

Colossyan is an **AI video generator for training and enablement**. Teams turn documents, scripts, and prompts into video-led courses delivered by photoreal **AI avatars** (300+ stock presenters + custom avatars) speaking **100+ languages** with lip-synced gestures. The newest avatar engine is **NEO 2** — full-body movement, natural weight shifts, gestures tied to speech. The learning surface is **Colossyan Learn** — videos wrapped into clickable, measurable, SCORM-ready courses.

Core product pillars surfaced across the site:

- **AI Avatars** — stock, custom, branded, scenario (healthcare, retail, etc.)
- **AI Video Creator** — prompt → video, PDF/PPT → video, screen recorder
- **Translation** — 100+ languages, lip-sync retargeting
- **Interactive video** — branching, quizzes, SCORM analytics
- **Collaboration / Brand Kits / Voice cloning / Conversational AI agents**

Named customers across the site: JLR, J&J, Continental, Under Armour, HP Enterprise, Paramount, UPS, Sonesta Hotels (80% production cost reduction cited).

## Sources consumed

- **Repo** — `colossyan/landing-pages` (GitHub): Astro 5 marketing site reverse-proxied onto `colossyan.com`.
- **Live imagery** — hosted externally on `lp-assets.colossyan.com` and `cdn.prod.website-files.com/6230cb61285b0d10e5c13daa/…`; referenced by URL, not mirrored.
- **Fonts** — Bricolage Grotesque + Inter (Google Fonts).

No Figma, decks, or app-side codebase were provided — so this system covers the **marketing website** surface. The Colossyan Creator editor UI is referenced by screenshot URL only; a true app UI kit would need access to that codebase.

## Index

| File / folder | What's in it |
|---|---|
| `colors_and_type.css` | CSS variables, fonts, base heading + body styles, `.cta-btn`, `.eyebrow`, containers |
| `README.md` | This file — context, content, visuals, iconography |
| `SKILL.md` | Skill manifest |
| `assets/` | Logos, icons, favicon, heading-underline SVG |
| `ui_kits/website/` | Recreation of the marketing site — components + index.html |
| `preview/` | Design-system review cards |

---

## Content fundamentals

**Voice is plain, confident, operator-focused.** The site talks to L&D leads, enablement teams, and training managers — people with a budget, a deadline, and a legacy authoring tool to replace. It assumes the reader knows the category.

- **Second person, direct.** "Your avatar speaks 100+ languages." "Create an AI avatar in 3 steps."
- **Sentence case everywhere.** Headings, eyebrows, buttons. No Title Case on CTAs. Examples: `Book a demo`, `Create your free video`, `Try Colossyan Free`.
- **Eyebrows are UPPERCASE with letter-spacing.** Above a heading: `300+ AI PRESENTERS`, `USE CASES`, `HOW IT WORKS`, `FAQ`. Short — 2–4 words. Coral.
- **Headlines are specific and often claim-forward.** "AI Avatars. Beyond the Talking Head." "One Avatar, Every Language." "See the Difference: NEO 1 vs NEO 2." They split into setup + punchline with a `.` between.
- **Body copy is short and concrete.** Stats show as raw numbers + noun: "300+ stock avatars", "100+ languages", "80% video production cost reduction". Product names (NEO 2, Colossyan Learn) are capitalized like software; nothing else is.
- **No emoji in marketing copy.** Flag emoji appear in the language switcher UI only (🇺🇸 🇪🇸 🇩🇪 🇵🇹).
- **FAQ tone is instructional, not chatty.** Answers inline-link to other product pages.
- **Dual CTA pattern: primary = Try / Book a demo, secondary = See how it works / Pricing.** Dark primary, white secondary with a hairline border.
- **Proof points are named**, not vague. Customers (JLR, UPS, J&J), reviewers (Jill Easton, Curriculum Manager), outcomes.

**Do / don't:**

- ✅ "NEO 2 avatars gesture and shift naturally while they speak."
- ❌ "Revolutionary, cutting-edge AI avatars that will transform your training!"
- ✅ "Thousands of training teams use Colossyan for onboarding, compliance, and enablement."
- ❌ "Unleash the power of AI video for next-gen learning experiences."

---

## Visual foundations

**Overall vibe.** Editorial-tech. Big grotesque display type at regular weight, generous whitespace, warm off-white surfaces, inky near-black text, one bold coral accent for eyebrows and emphasis. No drop-shadowed cards, no bluish-purple gradients, no glassmorphism. When things move, they move subtly.

### Colors

- **Neutral base.** `--white #FFFFFF` (hero bg), `--off-white #F5F4F2` (cards + muted surfaces), `--off-black #151515` (primary text + primary button), `--black #000000` (footer).
- **Brand accent.** `--coral #FF7C73` for eyebrow tags, accent underlines, gradient hotspots. `--light-coral #FDD7CF` / `--dark-coral #4E0D09` as tints.
- **Secondary accents** (used in gradient blobs + illustration backgrounds, rarely as direct UI color): blue `#70CCF4`, yellow `#FADD76`, green `#7DE98A`, each with a light + dark companion.
- **Grey scale.** `--light-grey #CFCECE` / `--grey #979797` / `--dark-grey #505050` — `--dark-grey` is the body-copy color.
- **Borders.** `--border-light #E8E8E8`, `--border-medium #d0d0d0` — hairlines, never heavier than 1px.

Backgrounds alternate section-by-section between `--white` and `--off-white`. Footer is `--off-black` → `--black`.

### Type

- **Display: Bricolage Grotesque**, all headings h1–h6, stat values, step titles. Always at `font-weight: 400`. Tight negative letter-spacing scaling with size (`-2px` at H1 → `-0.5px` at H4). **This is the signature — the system refuses bold display type.**
- **Body: Inter** — paragraphs, buttons, nav. Weights 400 / 500 / 600. Body color is `--dark-grey` (not black) — an intentional softening.
- **Scale.** 72 / 62 / 52 / 36 / 30 / 24 / 20 / 17 / 16 / 14 / 12 / 10. H1 desktop 62px, mobile 34.
- **Eyebrow** is the one uppercase moment in the whole system.
- **Custom underline.** `.custom-underline` draws a hand-drawn coral scribble under a key word via `assets/heading-underline.svg`. Once per screen, max.
- **Heading highlight.** `.heading-highlight` wraps a word in a coral→blue gradient pill.

### Spacing & layout

- **Container.** `max-width: 1280px`, 40px side padding (16px on mobile).
- **Section rhythm.** `<main class="sections">` has `gap: 120px` on desktop, `80px` on mobile, `padding-top: 101px`. Sections never touch.
- **Inside-section gap.** `--space-48` between heading block and content; `--space-20`–`--space-24` between tightly related elements.
- **Grid cards.** `padding: 36px`, `grid-template-columns: repeat(2, 1fr)`, `gap: var(--space-20)`. Card media always `aspect-ratio: 1 / 1`.

### Radii

- `--radius-sm 4` / `--radius-md 8` / `--radius-lg 12` / `--radius-xl 16` / `--radius-pill 100`.
- **Default is `md` (8px).** Pill only for badges. `xl` is rare.

### Shadows & elevation

- **Minimal elevation.** Variables exist (`--shadow-sm/md/lg`) but the site almost never uses them on cards. Elevation comes from **color contrast** (off-white card on white page), not drop shadow. Save shadows for floating things (popups, dropdowns).
- **Secondary button uses inset ring** (`box-shadow: inset 0 0 0 1px var(--border)`) not drop shadow.

### Backgrounds

- **Flat surfaces, no photography backplates.** Page bg solid white. Cards solid off-white.
- **Gradient blobs** — 7 named large radial/linear blobs (`.gradient-blob--sunset-on-venus`, `--distance-nebulae`, `--alfheim-forest`, `--fragment-of-saturn`, `--poseidons-realm`, `--cosmic-butterfly`, `--cosmic-butterfly-alt`) with `filter: blur(175px)`, positioned behind hero imagery. Each blends 2–3 brand colors. One per page. **Main source of color in the design.**
- No repeating patterns, textures, or grain.

### Animation

- **Restrained.** 150–200ms ease on hover. Steps component has a 5-second auto-advancing progress bar. Hero logo bar marquees on mobile. Swiper/Splide carousels. Fade-in embeds. No bounces, springs, parallax, or scroll-linked animation. `prefers-reduced-motion` respected.

### Hover & press states

- **Primary button hover:** `--off-black` → `--hover-dark #2a2a2a`.
- **Secondary button hover:** `--white` → `--off-white`.
- **Footer links:** `opacity: 0.7` on hover (not color shift).
- **Text links** in blog: `--link-blue #2c43b8` → `--link-blue-hover #1e2f82`. Elsewhere `<a>` often inherits.
- **No press/scale transforms.**

### Borders

- 1px hairlines in `--border-light`. Footer column titles separated by a 1px white underline. Secondary buttons use inset ring.

### Transparency & blur

- Used almost exclusively in gradient blobs (`filter: blur(175px)`, `opacity: 0.4`).
- Overlays: `--overlay-black-50` (video scrim), `--overlay-black-08`, `--overlay-white-15`, `--overlay-white-25`.
- No glassmorphism.

### Card anatomy

A typical content card is:

- `background: var(--off-white)`
- `border-radius: var(--radius-md)` (8px)
- `padding: 36px`
- Title: Bricolage Grotesque 30px regular
- Description: Inter 16px `--dark-grey`
- Square media (1:1), `border-radius: md`, clipped

No drop shadow. No border. Lives on a white page — contrast comes from fill.

### Imagery treatment

- **Warm, natural, editorial.** Product screenshots unfiltered. Avatar photography shot against clean real-world scenes (offices, factories, hospitals). Warm > cool. No b&w, no grain, no duotone.
- **Video is everywhere.** Muted, autoplay, looping, with a corner mute toggle.
- **Customer logos** desaturated (white-on-black footer, or held at 40% opacity in hero bars). Never rendered in their own brand colors.

### Layout rules

- **No fixed-position elements** other than navbar + bottom-right chat widget.
- **No sticky sidebars.** Single-column stacked sections.
- **Full-bleed** only for dark footer CTA, otherwise contained to 1280px.
- **Horizontal headers** (image right, text left) alternate-flip via a `--reverse` prop.

---

## Iconography

Colossyan uses **custom flat SVG icons at small sizes** with a very limited vocabulary. There is **no Lucide / Heroicons / Font Awesome** dependency — the repo ships a handful of one-off SVGs.

**What exists in the repo (now in `assets/icons/`):**

- `chevron-down.svg` — FAQ/menu expander
- `play.svg` / `pause.svg` — video controls
- `quote.svg` — coral decorative glyph above testimonials
- `muted.svg` / `unmuted.svg` — video mute toggle

**Replace-strip logos** (competitor tools — Adobe Captivate, Articulate, Canva, Descript, Synthesia) appear in the CTA-end component. Not imported here; grab from the repo on demand.

**What's missing and needs to be added:** nav/settings/upload/user icons. When you need one, substitute from **Lucide** at 20px, stroke 1.5–2px, color `currentColor`. Keep icons small — they are accent, never headline.

---

## Asset URLs

The site references a lot of externally-hosted imagery. For design mockups, use these base URLs:

- **Avatar videos / product screenshots:** `https://lp-assets.colossyan.com/website-images/images/…` and `…/videos/…`
- **Customer logos:** `https://lp-assets.colossyan.com/assets/logos/{JLR,JNJ,Under_armour,continental,hewlett-packard-enterprise-logo%201,paramount,ups}.png`
- **Legacy CMS assets:** `https://cdn.prod.website-files.com/6230cb61285b0d10e5c13daa/…` (OG image, footer certification badges, social icons)
- **Logo mark (light-on-dark):** `assets/logo.svg` (local, imported from repo)
- **Placeholder:** `https://lp-assets.colossyan.com/website-images/images/placeholder-img.webp`

---

## Deviations from the repo

Kept minimal and documented:

- Added **semantic aliases** (`--bg`, `--fg1`, `--accent`) on top of the raw tokens so designs don't hard-code `--off-black` everywhere. Raw tokens still present.
- **Removed blog.css** — the heavy, blog-specific stylesheet wasn't relevant to component-level design work. Available in the repo if needed.
- **Navbar** was 39KB of bespoke markup with nested mega-menus. A simplified recreation lives in `ui_kits/website/components/navbar.html` — preserves hierarchy and visual design, drops the full nav data. When in doubt, re-import `src/components/Navbar.astro`.
