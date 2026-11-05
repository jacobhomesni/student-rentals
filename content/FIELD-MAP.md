# Content → HomesNI field map

Suggested public URL: `/university/{slug}` (e.g. `/university/queens-university-belfast`).  
Uni area identity URLs (future): `/uni-area/{slug}`.  
Uni area **search** URLs (live CTAs): `/student-rentals?uni-area={slug}`.

## Campus page = three sections

Do not collapse these into one link list in the CMS or template.

| Section | JSON | Link field | Destination |
|---|---|---|---|
| University Areas | `campuses[].uniAreas[]` (ids → `uni-areas.json`) | `searchPath` | Student uni search |
| Property Areas | `campuses[].searchPlaces[]` | `path` | Chip links to `/properties-for-sale-*` |
| Area Guides | `campuses[].areaGuides[]` | `path` | `/area/*` from supplied guide list only; omit section if empty |

Also include a **campus map** (Google Map embed) for the active campus.

### Multi-campus switcher

If `campuses.length > 1` (e.g. Ulster), show campus chips and switching updates:

- map embed
- University Areas
- Property Areas
- Area guides
- location meta / search CTA

Single-campus unis (e.g. Queen’s) do **not** show a campus switcher.

FAQs should be student-rentals questions for that campus, not HomesNI product explanations.

Examples:

- [`examples/campus-queens-university-belfast.html`](examples/campus-queens-university-belfast.html) — single campus
- [`examples/campus-ulster-university.html`](examples/campus-ulster-university.html) — multi-campus switcher

## Page-level fields

| JSON | CMS / template |
|---|---|
| `name` | H1 / title |
| `shortName` | Nav / cards |
| `slug` | Permalink |
| `website` | External official site |
| `summary` | Card / archive excerpt |
| `intro` | Lead copy |
| `heroImage` | Hero |
| `seo.title` / `seo.description` / `seo.h1` / `seo.faqs` | Meta + FAQ block |

## Campus repeater

| JSON | CMS / template |
|---|---|
| `id` | Stable key |
| `name` | Campus heading |
| `locationLabel` | Address line |
| `lat` / `lng` | Map |
| `website` | Campus site |
| `image` | Campus photo |
| `notes` | Short context |
| `uniAreas` | Multi-select → uni area catalog |
| `searchPlaces` | Repeater name + path |
| `areaGuides` | Repeater name + path |

## Uni area catalog (`areas/uni-areas.json`)

| JSON | Use |
|---|---|
| `name` / `summary` | Card copy |
| `searchPath` | Primary CTA on campus page |
| `path` | Future `/uni-area/{slug}` landing |
| `image` | Card image |
| `seo.*` | Landing page SEO when built |
