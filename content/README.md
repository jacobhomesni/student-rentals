# HomesNI university + uni areas content

Structured content for every NI university/campus, plus **Uni areas**, wired for campus pages with three separate sections.

## Campus page model (locked)

Each campus page has **three labelled sections**:

| Section | Job | Links to |
|---|---|---|
| **University Areas** | Well known student places for student rentals | Student search `/student-rentals?uni-area={slug}` |
| **Property Areas** | HomesNI neighbourhood property pages | `/properties-for-sale-*` |
| **Area guides** | Editorial guides | `/area/*` |

Same place can appear in more than one section (e.g. Ormeau) with different destinations.

## Inventory

### Universities

This pack is the full NI university / university-college set (FE colleges deferred):

| Institution | File | Campuses |
|---|---|---|
| Queen’s University Belfast | `universities/queens-university-belfast.json` | Main Belfast |
| Ulster University | `universities/ulster-university.json` | Belfast, Coleraine, Magee, Jordanstown |
| St Mary’s University College | `universities/st-marys-university-college.json` | Belfast |
| Stranmillis University College | `universities/stranmillis-university-college.json` | Belfast |
| Open University NI | `universities/open-university-ni.json` | Belfast office |

### Uni areas

Catalog: [`areas/uni-areas.json`](areas/uni-areas.json) — Botanic, Holylands, Stranmillis, Malone, Lisburn Road, Ormeau, Cathedral Quarter, Belfast City Centre, Falls, Jordanstown, Coleraine, Portstewart, Portrush, Magee/Northland.

### Example pages

- [`examples/campus-queens-university-belfast.html`](examples/campus-queens-university-belfast.html) — Queen’s (template)
- [`examples/campus-ulster-university.html`](examples/campus-ulster-university.html) — Ulster multi-campus switcher
- [`examples/campus-st-marys-university-college.html`](examples/campus-st-marys-university-college.html)
- [`examples/campus-stranmillis-university-college.html`](examples/campus-stranmillis-university-college.html)
- [`examples/campus-open-university-ni.html`](examples/campus-open-university-ni.html)

### Images

See [`IMAGE-REQUEST.md`](IMAGE-REQUEST.md) for the full photo list to supply (27 files).

## Folder layout

```
content/
  areas/homesni-areas.json
  areas/uni-areas.json
  universities/*.json
  examples/campus-queens-university-belfast.html
  IMAGE-REQUEST.md
  FIELD-MAP.md
  README.md
```

## Authoring rules

1. Uni area primary links = **uni search**, never `/properties-for-sale-*`.
2. Property Areas (`searchPlaces`) = HomesNI sale-area URLs from `homesni-areas.json` that are close to that campus only.
3. Area Guides = `/area/*` from the supplied guide list only, and only when surrounding. If none match, leave `areaGuides` empty and hide the section.
5. Keep campus `id` values aligned with student onboarding where they exist.
6. FE colleges are out of scope for this pack.
