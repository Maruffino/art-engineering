# art_info_site

QR-code-driven multilingual information pages for **Art Engineering — Season 2**, the second edition of the ecological/engineering art exhibition hosted by **Kimyo International University in Tashkent (KIUT)**. Season 1 was staged in 2024.

- Exhibition dates: **20–25 April 2026**
- Host: Kimyo International University in Tashkent (KIUT) — https://kiut.uz/en
- Venue: Shota Rustaveli St., 156, 100121 Tashkent (Yandex Maps: https://yandex.uz/maps/-/CPCirU0f)
- Director/curator: Prof. Djamshid Kaniev
- Main designer: Husan Pulatov (Instagram [@husanpulatov](https://www.instagram.com/husanpulatov))
- Build team: KIUT Engineering team (Instagram [@muhandis_d](https://www.instagram.com/muhandis_d))

## Live

- **Catalog**: https://maruffino.github.io/art-engineering/
- **Repo**: https://github.com/Maruffino/art-engineering (public)
- **14 stand detail pages**: `stand-01.html` through `stand-14.html`
- **15 QR codes** printed and attached to stands (14 per-stand + 1 catalog-entry QR)

⚠ **URLs are frozen** — QR codes are printed. Never rename `stand-NN.html`, `pictures/*`, `qrcodes/*`, or the repo itself. Content inside files is safe to edit.

## Languages

Language switcher live in 4 languages: **EN · UZ (Latin) · RU · KO**.
Switcher persists choice across pages via `localStorage` key `kiut.lang`.
Copyright line stays in English across all languages ("© 2026 Kimyo International University in Tashkent") — legal/institutional name.

## Piece titles and status (April 2026)

| # | Title (EN) | Status |
|---|---|---|
| 01 | Glass *Current* | placeholder body |
| 02 | After the *Drought* | placeholder body |
| 03 | Silicon *Tide* | placeholder body |
| 04 | Behind the *Veil* | placeholder body |
| 05 | The *Wounds of the City* | real content ✓ (retitled from "Respirator for a City") |
| 06 | *Inheritance* | placeholder body |
| 07 | The Music of *Motion* | real content ✓ (retitled from "The River That Was Here"; interactive RTSP camera + motion-detection music installation) |
| 08 | A Missing *Climate* | placeholder body |
| 09 | Last of the *Gilded* | real materials ✓ (dragonfly from recycled plastic, wires, pens, markers) |
| 10 | One *Choice Apart* | real content ✓ (retitled from "The City Remembers Itself"; two-sided forest/destroyed-nature piece); image still old diorama — user-approved |
| 11 | Rust and *Lily* | body = ship-in-desert philosophical framing; materials = salvaged pipes + coral-reef imitations + live fish; title kept per user |
| 12 | A Wall of *Accords* | placeholder body |
| 13 | The Renewable *Tree* | real content ✓ (engineering+art tree with solar leaves + wind-turbine fruit) |
| 14 | The Living *Wheel* | placeholder body (zoetrope) |

"Placeholder body" = philosophical prose written by me, not by the artist/team. All UZ/RU/KO translations are placeholder and need native-speaker review before reprint.

## Structure

```
art_info_site/
├── index.html              # catalog + language switcher + 14 piece tiles
├── stand-01.html .. stand-14.html   # detail pages (frozen URLs)
├── PROJECT.md              # this file
├── pictures/
│   ├── 01-bottle-turtle.jpg .. 14-zoetrope.jpg   # piece images
│   └── 13-renewable-tree.png  # one piece is .png not .jpg
├── qrcodes/
│   ├── index.png           # catalog QR
│   └── stand-01.png .. stand-14.png   # per-piece QRs
└── assets/
    ├── logo-header.svg     # KIUT logo (original, white+blue, for dark bg)
    ├── logo-header-dark.svg  # same but recoloured for light bg
    ├── logo-blue.svg       # blue-only variant
    └── logo-mono.svg       # ink-only variant
```

## Translation key conventions

**Shared chrome** (same across all stand pages):
- `chrome.back`, `chrome.kicker`, `chrome.meta.year|medium|size`, `chrome.also`, `chrome.stayintouch`, `chrome.follow`, `chrome.instagram`, `chrome.address`, `chrome.season`

**Per-piece** (unique per stand):
- `piece.title.prefix`, `piece.title.accent`, `piece.medium`, `piece.size`, `piece.caption`, `piece.p1`, `piece.p2`
- `piece.dl.dt1..5`, `piece.dl.dd1..5` (5 rows in the materials/details block)

**Catalog-only** (`index.html`):
- `meta.season` (masthead right), `hero.brand1|brand2|season`, `hero.lede.before|team|after`
- `intro.exhibition.label|brand|season|since`, `intro.artist.label`, `intro.location.label|street|city`
- `section.catalog`, `section.count`, `footer.copy`, `footer.follow`, `footer.designer`

## Update workflow

When the user provides new source text for a piece (usually in Uzbek):

1. Propose rephrased drafts in all 4 languages, philosophically rather than literally
2. Wait for approval (`go` / `p1` / `both`)
3. On approval, **sweep everything related** to the piece: p1, p2, caption, medium, `<dl>` rows, image `alt`, `<title>` tag. Never leave stale halves.
4. If title changes, update: page `<title>`, piece-title H1 (prefix + em accent), catalog tile in `index.html`, all 4 language dicts
5. Commit with cohesive message
6. Push, wait for Pages build to complete, verify live with cache-busted curl

## Known cosmetic issues

- Stand 10 image `pictures/10-ruined-city-diorama.jpg` doesn't match the current "One Choice Apart" (forest/destroyed) body — user approved keeping as-is
- Stand 11 image `pictures/11-pipe-tree-pond.jpg` doesn't match the ship-in-desert body — no new photo available
- Stands 01/02/03/04/06/08/12/14 bodies are placeholder philosophical drafts, not real artist statements

## Analytics

Available via GitHub Pages built-in traffic insights:
https://github.com/Maruffino/art-engineering/graphs/traffic
(last 14 days, visible to repo owner only)
