# The Pacific can describe its rain. It cannot see it coming.

Entry for the **Pacific Data Viz Challenge 2026**.

The ocean around the Pacific islands is better observed than the world ocean on average.
The air above it is barely observed at all. This project is about which instruments exist,
which ones are switched on, and what happened the last time that gap mattered — Papua New
Guinea in the 2015–16 El Niño.

**Live app:** https://steng-luma.github.io/dataviz/dataviz.html

---

## What's in here

| Path | What it is |
|---|---|
| `dataviz.html` | The finished piece — a single self-contained scrollytelling app. No build step, no dependencies; open it in a browser. |
| `hypothesis.Rmd` | The analysis behind every number in the app. Knit from the repo root. |
| `data/` | Inputs, with provenance in `data/README.md`. |

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


## Notes

- The palette is shared between the app and the report so they read as one piece of work:
  `#0d1b2a` ocean navy, `#3987e5` blue, `#d95926` orange, `#199e70` green, `#e6b800` amber,
  `#e66767` red.
- No licence file yet. Add one if you want the code or the derived tables reused.
