# art_info_site

QR-code-driven information pages for **Art Engineering — Season 2**, the second edition of an ecological / environmental art exhibition hosted by **Kimyo International University in Tashkent (KIUT)**. Season 1 was staged in 2024; Season 2 opens Spring 2026. Each stand has a QR code that, when scanned, opens a web page with the artwork's image, title, story, and metadata.

- Exhibition: Art Engineering — Season 2
- First staged: 2024 (Season 1) · Current: Spring 2026 (Season 2)
- Host: Kimyo International University in Tashkent — https://kiut.uz/en
- Venue: Shota Rustaveli St., 156, 100121 Tashkent (ул. Шота Руставели, 156, 100121 Ташкент)

## Goal

Visitors at the exhibition scan a QR code at each stand and see a dedicated page with:
- Photo of the work
- Title, year, medium, size
- Artist's note / story / concept behind the piece
- Related works in the same exhibition
- Follow / contact CTAs (Telegram, email)

## Exhibition theme

Environmental and ecological commentary — waste, pollution, climate, and nature. Artworks are mostly assemblages from discarded materials (glass bottles, e-waste, cellophane) and immersive installations about pollution and ecosystems.

## Approach chosen

**Static site hosted on GitHub Pages** (free, universal — works from any phone camera, no app required).

Alternatives considered:
- Telegram bot with deep links (`t.me/bot?start=stand1`) — works but filters out non-Telegram visitors
- Telegram channel posts — no coding, but Telegram-only
- Hybrid — web page with "Open in Telegram" button (best reach + follow-up channel)

## Current state

- Demo mockup exists: `index.html` (catalog) + `stand-03.html` (detail page), still using portrait placeholder text — needs to be rewritten for ecological theme
- Aesthetic direction draft: editorial / gallery-catalog — warm parchment, Instrument Serif + Manrope, terracotta accent. **May be revised** to better suit the ecological/industrial tone of the work
- 10 real artwork photos in `pictures/`, renamed with descriptive slugs

## Artworks (photo-time order, not yet confirmed as exhibition order)

| # | File | Description |
|---|---|---|
| 01 | `01-bottle-turtle.jpg` | Sea turtle sculpture from green glass bottles and wire |
| 02 | `02-cloud-garden.jpg` | Hydroponic tower with cotton "cloud" on top, grass growing down the sides |
| 03 | `03-wire-fish.jpg` | Fish sculpture from computer wires, circuit board, and keyboard keys (e-waste) |
| 04 | `04-plastic-skyline.jpg` | Glass case with hanging plastic strips; city skyline photo inside |
| 05 | `05-smog-vitrine.jpg` | Illuminated vitrine with miniature city and purple smog clouds |
| 06 | `06-fetus-reaching-earth.jpg` | Cellophane relief: fetus reaching for wrapped Earth globe |
| 07 | `07-hall-projection.jpg` | Exhibition-hall view — black pillar sculpture with floor projection of river/nature |
| 08 | `08-climate-chamber.jpg` | Cylindrical glass terrarium with plants and pressure gauges |
| 09 | `09-golden-dragonfly.jpg` | Golden dragonfly sculpture with wire-mesh wings |
| 10 | `10-ruined-city-diorama.jpg` | Diorama of decayed post-Soviet cityscape (Russian signage) |
| 11 | `11-pipe-tree-pond.jpg` | Industrial pipe "tree" rising out of a koi pond |
| 12 | `12-climate-accords.jpg` | 5x5 grid of crumpled international climate treaty documents |
| 13 | `13-renewable-tree.jpg` | White tree with solar-panel leaves and wind-turbine fruit |
| 14 | `14-zoetrope.jpg` | Large zoetrope drum; rotating reveals tree + people animation |

## Languages

Language switcher (EN / UZ / RU) live on `index.html`. Visitor's choice persists across pages via `localStorage` key `kiut.lang`.

Translations for UI chrome (labels, lede, footer, CTA, address format) are in place but **Uzbek and Russian translations need native-speaker review** before publishing. Artwork titles are currently placeholder English strings — they will need translation once real titles are finalized.

Not yet translated: `stand-01.html` (artist statement, piece metadata). Same switcher pattern can be extended — requires UZ/RU copy for each piece.

## Open decisions

1. **Exhibition order**: is the photo-time order above the actual stand order, or does it need reordering?
2. **Artist / exhibition metadata**: artist name(s), exhibition title, venue, dates, any institutional affiliation
3. **Per-artwork content**: title, year, medium, size, artist statement for each of the 10 pieces
4. **Aesthetic direction**: current mockup is warm/editorial. For ecological work we might prefer: dark/industrial, raw/recycled aesthetic (paper-bag textures, stamped-ink type), or clean museum minimal
5. **Content sections per stand**: current is title / photo / story / metadata / "also in series" / follow CTA. Add audio narration? Video? Credits for sourced materials?
6. **Language**: English only, or bilingual (e.g. local language + English)?
7. **QR generation**: batch tool once final URLs exist

## Deployment plan

1. Repo on GitHub (name TBD)
2. HTML + compressed images (WebP, ~300–500 KB each) committed
3. Settings → Pages → enable from main branch
4. Public URL: `https://<username>.github.io/<repo>/`
5. Generate one QR per stand pointing to `.../stand-01/` (etc.)

## Files

- `index.html` — exhibition catalog overview (placeholder portrait content, to be rewritten)
- `stand-03.html` — sample individual stand page (placeholder, to be templated for 10 artworks)
- `pictures/` — 10 renamed artwork photos
- `PROJECT.md` — this file
