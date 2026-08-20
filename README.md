# The Pacific can describe its rain. It cannot see it coming.

Entry for the **Pacific Data Viz Challenge 2026**.

The ocean around the Pacific islands is better observed than the world ocean on average.
The air above it is barely observed at all. This project is about which instruments exist,
which ones are switched on, and what happened the last time that gap mattered — Papua New
Guinea in the 2015–16 El Niño.

**Live app:** https://steng-luma.github.io/dataviz/
*(Settings → Pages → Source: deploy from branch `main`, folder `/root`.)*

---

## What's in here

| Path | What it is |
|---|---|
| `index.html` | The finished piece — a single self-contained scrollytelling app. No build step, no dependencies; open it in a browser. |
| `visualisations_hypothesis (final).Rmd` | The analysis behind every number in the app. Knit from the repo root. |
| `visualisations_hypothesis (improved) 20260817.Rmd` | Previous draft, kept for the revision history in its header notes. |
| `visualisations_hypothesis_simplified.Rmd` | Shorter variant with the exploratory sections stripped out. |
| `hypothesis.docx` | Written hypothesis the analysis set out to test. |
| `PNG2015droughtPolicyBriefNo11.pdf` | Primary source for the PNG 2015 drought district ratings. |
| `data/` | Inputs, with provenance in `data/README.md`. |
| `powerbi/` | A parallel build of the same fourteen charts as a five-tab Power BI report. |

---

## Reproducing the analysis

R with **tidyverse**, **geosphere** and **ggrepel**.

```r
install.packages(c("tidyverse", "geosphere", "ggrepel"))
```

Then knit `visualisations_hypothesis (final).Rmd` **from the repository root** — it reads
`climate_change.csv` and `oni.csv` from the working directory and everything else from `data/`,
so the paths only resolve if the root is the working directory.

Three raw files are too large for the repo and are gitignored. Download them into `data/`
first; links are in [`data/README.md`](data/README.md).

The app in `index.html` is hand-built rather than knitted — the series it plots are baked into
a single `D` object near the bottom of the file, taken from the analysis above. Changing a
number means changing it in both places.

---

## Data

Full source table in [`data/README.md`](data/README.md). In short: SPC Pacific Data Hub for the
climate indicators, NOAA CPC for ENSO, NOAA GHCN-Daily and IGRA for station and radiosonde
inventories, WMO WDQMS for what those stations actually reported in July 2026, and Marine
Regions for EEZ and land areas.

---

## Power BI rebuild

`powerbi/` holds the same story as a five-tab report — Global Warming, The Swing, PNG 2015,
Three Layers, The Gap. It's a separate artefact, not generated from the R code:

- `pacific-rainfall-model-data.xlsx` — 14 model tables, one per sheet, ready to load in one step
- `data/` — the same tables as CSVs
- `deneb/` — five Vega-Lite specs for the charts native Power BI can't draw
- `images/` — PNG renders of those charts for static use
- `pbi-layout-preview.html` — all five pages at 1280×720, viewable without Power BI
- `LOAD-THE-DATA-FIRST.md` — loading steps and troubleshooting

---

## Notes

- The palette is shared between the app and the report so they read as one piece of work:
  `#0d1b2a` ocean navy, `#3987e5` blue, `#d95926` orange, `#199e70` green, `#e6b800` amber,
  `#e66767` red.
- No licence file yet. Add one if you want the code or the derived tables reused.
