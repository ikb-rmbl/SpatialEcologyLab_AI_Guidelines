# <Project Name>

> One sentence: what scientific question does this project answer?

<!--
  TEAMMATE-MODE starter project — for areas you ALREADY understand and want to
  move faster in. The AI assistant here is set up to be direct, but you still own
  verification and must be able to explain anything that ships. Still learning the
  skills this project uses? Use the project-skeleton-tutor starter instead, and be
  honest about which mode you're in (handbook/02-writing-agents-md.md).
  For bigger builds, work spec-first: handbook/06-spec-driven-development.md.
-->

**Lead:** <your name>
**Supervisor:** <name>
**Started:** <month year>

## What's here

| Path | Contents |
|------|----------|
| `R/` | Functions and scripts — the workhorses; keep them small and single-purpose |
| `data/raw/` | Canonical input data (small files only; big data lives elsewhere — note where below) |
| `data/derived/` | Generated data — **gitignored**, recreate by running the code |
| `output/` | Figures, tables, reports — **gitignored** |
| `analysis.qmd` | Narrative analysis (use for exploratory / write-up work) |
| `SPEC.md` | Design one substantial build before the assistant implements it (delete if unused) |
| `AGENTS.md` | Instructions for the AI assistant — **teammate mode** (direct; spec-first for big builds) |
| `PROJECT-BRIEF.md` | What this project is, and what context the AI gets vs. what you keep |

## How you work here

1. Fill in `PROJECT-BRIEF.md` (whole-project context, plumbing vs. thinking).
2. For anything bigger than a quick script, **write `SPEC.md` first** and have the assistant implement against it, one reviewed task at a time. For small/exploratory work, use `analysis.qmd` and just prompt.
3. Teammate mode still means: you read every line, verify against reality, and can explain it all with the AI closed.

## Where the big data lives

<!-- e.g. "SDP COGs via rSDP, product R3D009"; Compute Hub for large rasters -->

## How to reproduce this

```r
# 1. Restore the package environment
renv::restore()

# 2. Run the pipeline / analysis
# source("R/run_pipeline.R")   # for a SPEC-driven build
quarto::quarto_render("analysis.qmd")   # for narrative analysis
```

## Notes

- <anything a labmate needs to know to run this>
