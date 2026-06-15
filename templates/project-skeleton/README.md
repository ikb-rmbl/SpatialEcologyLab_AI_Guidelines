# <Project Name>

> One sentence: what scientific question does this project answer?

**Student:** <your name>
**Supervisor:** <name>
**Started:** <month year>

## What's here

| Path | Contents |
|------|----------|
| `R/` | Functions and scripts (the code that does the work) |
| `data/raw/` | Canonical input data (small files only; big data lives elsewhere — note where below) |
| `data/derived/` | Generated data — **gitignored**, recreate by running the code |
| `output/` | Figures, tables, reports — **gitignored** |
| `analysis.qmd` | The main narrative analysis |
| `AGENTS.md` | Instructions for the AI assistant on this project |

## Where the big data lives

<!-- e.g. "SDP COGs via rSDP, product R3D009" or "/lab_share/project_x/rasters" -->

## How to reproduce this analysis

```r
# 1. Restore the package environment
renv::restore()

# 2. Run the analysis
quarto::quarto_render("analysis.qmd")
```

## Notes

- <anything a labmate needs to know to run this>
