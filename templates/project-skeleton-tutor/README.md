# <Project Name>

> One sentence: what scientific question does this project answer?

<!--
  TUTOR-MODE starter project — for when you're learning the skills this project
  uses. The AI assistant here is set up to coach you (ask before answering, make
  you explain) rather than just hand over code. If you already own this area and
  want to move faster, use the project-skeleton-teammate starter instead.
  New here? Read handbook/00-start-here.md and handbook/03-working-with-the-assistant.md.
-->

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
| `analysis.qmd` | The main narrative analysis (start here) |
| `AGENTS.md` | Instructions for the AI assistant — **tutor mode** (coaches you) |
| `PROJECT-BRIEF.md` | What this project is, and what context the AI gets vs. what you keep |

## How you work here

1. Fill in `PROJECT-BRIEF.md` with your supervisor first.
2. Do your thinking in `analysis.qmd` — write your *plan* before you ask for code.
3. Keep the one rule: **if you can't explain it, you don't ship it.**

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
