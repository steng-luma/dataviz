# Data sources

Everything here is public. Three files are too large to keep in the repo and are
listed in `.gitignore` — download them into `data/` before knitting the analysis.

## Not in the repo — fetch these first

| File | Size | Where from |
|---|---|---|
| `ghcnd-inventory.txt` | 36 MB | NOAA GHCN-Daily station inventory — `https://www.ncei.noaa.gov/pub/data/ghcn/daily/ghcnd-inventory.txt` |
| `Pacific islands region land.geojson` | 80 MB | Derived from Marine Regions *EEZ + land union v4* (see below) |
| `EEZ_land_union_v4_202410/` | 25 MB | Marine Regions — `https://www.marineregions.org/downloads.php` → *EEZ and land union v4 (2024-10)* |

## In the repo

| File | Source |
|---|---|
| `../climate_change.csv` | SPC Pacific Data Hub, dataflow `DF_CLIMATE_CHANGE`. Indicators used: `SST_ANOM`, `ST_ANOM`, `RAIN_ANOM`, `SEA_LVL`, `METEO_MONITOR_NET` |
| `../oni.csv` | NOAA Climate Prediction Center — Oceanic Niño Index |
| `../roni.csv` | NOAA Climate Prediction Center — Relative Oceanic Niño Index |
| `../Combined_Pacific_area.csv` | Land area (SPC `DF_POCKET`) joined to EEZ area (Marine Regions v4) |
| `../sweet-potato-production.csv` | Our World in Data — sweet potato production |
| `../png_2015_cat45_llga.csv` | Districts rated 4 or 5 in the 2015–16 PNG drought, transcribed from `../PNG2015droughtPolicyBriefNo11.pdf` |
| `Land_area.csv` | SPC Pacific Data Hub, dataflow `DF_POCKET`, indicator `LAR` |
| `ghcnd-stations.txt` | NOAA GHCN-Daily station list |
| `igra2-station-list.txt` | NOAA Integrated Global Radiosonde Archive v2 |
| `wdqms_LandSurface_synop_availability_monthly_pressure_oscar_2026-07.csv` | WMO WIGOS Data Quality Monitoring System, surface synop availability, July 2026 |
| `wdqms_UpperAir_temp_availability_monthly_oscar_2026-07.csv` | WMO WDQMS, upper-air temperature availability, July 2026 |
| `wdqms_marine_surface_quality_monthly_pressure_2026-07.csv` | WMO WDQMS, marine surface pressure quality, July 2026 |
| `Pacific islands region EEZs.geojson` | Marine Regions EEZ v4, clipped to the Pacific islands region |
