# DFW Site Selection — Cartography

An 18-map analytical series, plus a criteria series and a site-profile series, for a regional
distribution-centre siting study in the Dallas–Fort Worth MSA. Built to one cartographic
standard so the whole set reads as a single document.

> **Status: in progress.** The analysis these maps draw from is still running. This repository
> holds the cartographic standard, the layout template, and the export scripts; the finished
> maps land in weeks 6–8.

## The approach

Eighteen maps made one at a time drift — different class breaks, different type sizes, a legend
in a different corner. Read together they look like eighteen separate efforts.

So: one layout template, one palette, one set of class breaks held constant **across scenarios**
so that maps can be compared rather than merely looked at. The map series are driven by an index
layer and dynamic text, which means a page per criterion and a page per shortlisted site are
generated, not laid out by hand.

## Cartographic standard

| | |
|---|---|
| **Page sizes** | Letter 8.5 × 11 in portrait (series) · Tabloid 11 × 17 in landscape (overview) · 1920 × 1080 px PNG (web) |
| **Template** | `layouts/LI_Template.pagx` — title, subtitle, legend, scale bar, north arrow, source and vintage credits, project label, page number |
| **Basemap** | Light Gray Canvas or Human Geography for analytical maps; Topographic for site profiles |
| **Colour** | Sequential 5-class for scores; diverging for rank change in sensitivity maps; **class breaks held constant across scenarios** |
| **Type** | One sans-serif family throughout; minimum 7 pt in print |
| **Recommended site** | Black dashed outline on **every** results map, without exception |

Holding class breaks constant across the three weighting scenarios is the decision that makes
the set comparable. Re-classifying per map would make every scenario look equally decisive.

## The maps

**M01–M18** — study area and market context · store-service network · candidate screening
results · labour pool · labour availability · commute flows · highway access · store-network
access · intermodal access · flood and wetland constraints · land value per acre · industrial
cluster · composite suitability under each of the three scenarios · rank stability · shortlist
overview · the recommended site.

**Map series**

- `MS01_Criteria.pdf` — one page per criterion C01–C11, identical layout, driven by a criteria
  index table, with the criterion's description, direction, and per-scenario weight in dynamic
  text.
- `MS02_SiteProfiles.pdf` — one page per shortlisted site: locator inset, site map at 1:24,000,
  30-minute labour-shed inset, a per-criterion score bar chart, and dynamic text for acreage,
  zoning, composite, rank, labour pool, minutes to interchange and intermodal, mean minutes to
  stores, SFHA %, and land value per acre.
- `MS03_CountyAtlas.pdf` — optional, one page per county.

## Repository layout

```
layouts/    LI_Template.pagx and page templates
scripts/    map export and map-series generation (arcpy.mp)
exports/    finished PDF and PNG output
```

Exports are scripted so the whole set can be regenerated after a re-run, rather than re-laid out
by hand.

## Attribution

Where OpenStreetMap-derived data is used, **ODbL attribution appears on the map**. Every map
carries its data sources and their vintage in the credits — a map without provenance is not
finished.

## Status detail

| Item | State |
|---|---|
| Cartographic standard | ✅ |
| Layout template `LI_Template.pagx` | ◻ week 6 |
| M01–M18 export script | ◻ week 6 |
| Map series MS01, MS02 | ◻ week 6 |
| Finished exports | ◻ |

## License

MIT for code and templates — see [LICENSE](LICENSE). Map output remains subject to the licences
of its data sources.

---

A component of [dsg-dfw-site-selection](https://github.com/ndeogobernard/dsg-dfw-site-selection),
a DFW regional-DC site-selection system.
