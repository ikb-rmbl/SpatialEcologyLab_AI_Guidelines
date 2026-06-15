# Lab Context

Orientation to what the Breckheimer Lab works on, the shared vocabulary, and the canonical data and tools you'll reach for. This is **lab-wide** context — the stable stuff. Project-specific detail (your question, your data, your methods) goes in your own project's `PROJECT-BRIEF.md` and `AGENTS.md`, not here.

> **Why this page exists:** so you can orient fast, and so the AI assistant has accurate *plumbing* (where data lives, what the conventions are) without us handing it the *science* — see the friction-vs-thinking note at the bottom. For the full picture, read the lab research proposal (in the lab Google Drive, `BreckheimerLab2026/Background/`). Don't copy it into any repo — it's a funding document.

---

## The big picture

The lab studies the **spatial ecology of environmental change in the Upper Gunnison watershed** (the East River basin around RMBL/Gothic, CO). The through-line: mountain ecosystems are changing fast under climate change, and **fine-scale spatial patterns** — microclimate, snow, vegetation, phenology — shape how those changes play out. We bring landscape ecology, physiological ecology, and remote sensing together, at scales from a single canopy gap to the whole watershed.

Everything is **spatial, climate-relevant, and reproducible**. Default CRS is **EPSG:32613** (UTM 13N) unless a dataset says otherwise.

## Research themes (the project lines students plug into)

1. **Canopy-airspace 3D microclimate** — Mapping the 3D structure of vapor pressure deficit (VPD) and microclimate in forest canopy gaps, combining in-situ sensors with drone (UAS) flights. Spruce-fir and aspen sites near Gothic.
2. **Sustainable weather/climate monitoring** — Building a small network of low-cost, solar-powered "Mark III" weather stations (with WCU students) to extend billy barr's long-term Gothic climate record.
3. **Landscape phenology** — Spatially explicit maps and forecasts of wildflower bloom timing/abundance, validated by "Flower Blitz" community-science events. Builds on 40+ years of RMBL phenology data.
4. **CHESS** (Colorado Headwaters Ecological Spectroscopy Study) — Quantifying vegetation composition and change with field + airborne hyperspectral data; 2026 adds tree cores (growth↔remote sensing) and vegetation surveys.
5. **Large-scale microclimate mapping** — A ~69-site network of micro-meteorological stations across the watershed, producing high-resolution gridded microclimate predictions.
6. **RMBL Spatial Data Platform (SDP)** — Synthesizing field + remote sensing into 100+ public spatial data products (topography, snow, vegetation, microclimate; new: LAI, vegetation classification, leaf traits).
7. **UAS & precision mapping** — Research-grade drone + RTK-GPS mapping of plant functional types, structure, surface temperature, and snow at cm-scale, partly fee-for-service.

## Glossary

The global lab glossary (SDP, COG, CHESS, catalog IDs, `EPSG:32613`, TimeSeriesType) still applies. Project-specific terms you'll hit:

| Term | Meaning |
|------|---------|
| **VPD** | Vapor pressure deficit — atmospheric "drying power"; central to the canopy-airspace project |
| **micro-met** | Micro-meteorological station; the ~69-site network measuring soil/air temp, moisture, etc. |
| **Flower Blitz** | Community-science events that collect independent field data to validate bloom predictions |
| **EnMAP** | Spaceborne hyperspectral imagery used in CHESS (Lekka et al. 2024) |
| **LAI / LMA** | Leaf Area Index / Leaf Mass per Area — vegetation traits being mapped as SDP products |
| **UAS** | Uncrewed Aircraft System (drone) |
| **RTK GPS** | Real-Time Kinematic GPS — cm-precision positioning for plots/trees |
| **SNOTEL** | USDA automated snow-telemetry network; source of operational snowpack data |
| **DOY** | Day of year — common time unit for phenology/snowmelt |
| **o / w / h** | Phenology-model parameters (Sethi et al. 2020): timing, duration, magnitude of flowering |
| **ESS-DIVE** | DOE permanent data archive where finalized datasets land |
| **TOMST TMS-4 / HOBO** | Common field sensor models (soil+air microclimate / temp-humidity & rain loggers) |

## Canonical data & tools

The lab runs the **RMBL Data Hub** ([data.rmbl.org](https://data.rmbl.org)) — a Knowledge Commons (literature/data search + an MCP server for the assistant), the SDP Browser (no-code data discovery + code generation), and the Compute Hub (cloud analysis). You're encouraged but not required to use them — see **[`rmbl-data-hub.md`](rmbl-data-hub.md)** for what each does and how to get started.

| Resource | What / where |
|----------|--------------|
| **RMBL Data Hub** | [data.rmbl.org](https://data.rmbl.org) — Knowledge Commons, SDP Browser, Compute Hub. See [`rmbl-data-hub.md`](rmbl-data-hub.md) |
| **Knowledge Commons** | [rmblknowledgecommons.org](https://rmblknowledgecommons.org) — search literature/datasets; **MCP server** at `/api/mcp` grounds the assistant in real sources |
| **SDP Browser** | [sdpbrowser.org](https://sdpbrowser.org) — discover/preview/extract SDP rasters, get `rSDP`/`pySDP` recipes |
| **Compute Hub** | [rmblcomputehub.org](https://rmblcomputehub.org) — cloud JupyterLab/RStudio next to the data (GitHub login, allowlist) |
| **RMBL Spatial Data Platform** | COGs on `s3://rmbl-sdp/` (us-east-2); access via **`rSDP`** (R) or **`pySDP`** (Python) |
| **rSDP / pySDP** | The lab client packages — start here for any SDP raster work |
| **RMBL phenology data** | CaraDonna plots: [osf.io/zq36h](https://osf.io/zq36h/) · Breckheimer spatial wildflower phenology: [doi.org/10.6073](https://doi.org/10.6073/) (EDI) |
| **Snowpack** | SNOTEL network (operational); SDP snow-cover products (1985–2025) |
| **Micro-met data** | Raw on the project Google Drive → cleaned → archived at ESS-DIVE (ask your supervisor for access) |
| **Tree-ring analysis** | `dplR` (R) for cross-dating/chronologies; WinDendro for ring measurement |
| **Phenology modeling** | Statistical framework from Sethi et al. 2020 (the `o`/`w`/`h` model) |

> If you're touching SDP data, read the `rSDP` README before asking the assistant for code — knowing the package exists changes every prompt.

---

## The one rule for putting this into an `AGENTS.md`

When you write your project's `AGENTS.md`, copy in the **plumbing** that removes friction (which packages, which CRS, where the data lives, sensor/file conventions). **Do not** write in the **science** that you're here to figure out (why VPD matters, which covariates to model, how to interpret a result). The first makes the assistant a useful tool; the second makes it do your thinking. Your `PROJECT-BRIEF.md` keeps these straight — see [`../templates/PROJECT-BRIEF.md`](../templates/PROJECT-BRIEF.md).
