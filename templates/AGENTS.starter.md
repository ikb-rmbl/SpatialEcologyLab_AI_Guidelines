# AGENTS.md — Teammate mode

<!--
  TEAMMATE MODE: use this for areas you ALREADY UNDERSTAND and want to move
  faster in. The assistant can be more direct here, but you still own
  verification and must be able to explain anything that ships. If you're still
  learning the skill, use AGENTS.tutor.md instead — and be honest about which
  you're in. See handbook/02-writing-agents-md.md.
-->

## Project
<!-- One or two sentences: the scientific question + what this code does. -->
[e.g. Upscale leaf trait estimates to landscape scale using SDP rasters.]

## Stack & layout
- Language: R (in Positron).
- Key packages: [tidyverse, terra, sf, stars, ...].
- Layout: reusable functions in `R/`, analysis in `analysis.qmd`, inputs in `data/raw/`.
- Derived data (`data/derived/`) and `output/` are gitignored — regenerate by running code.
- Default CRS: EPSG:32613 (UTM 13N) unless stated otherwise.

## Conventions
- tidyverse style; functions small and single-purpose; clear names.
- CRS- and units-explicit; pass them through, don't assume.

## How to help me
- You can be direct and propose complete solutions for areas I already know.
- **Still explain on request and on the non-obvious.** When I ask "why," give the real reason. When code is subtle, comment it.
- **Be a consultant.** Flag better approaches, risks, and trade-offs; let me decide. Don't refactor beyond what I asked without saying so.
- **No invented APIs.** If you're unsure a function/argument exists or is current, say so rather than guessing.
- Keep changes minimal and reviewable — small diffs I can actually read.

## My responsibilities (even in teammate mode)
- I read every line before it ships and can explain it with the AI closed.
- I verify outputs against reality (known cases, sanity plots, counts) — not "the AI said so."
- I note substantial AI help in commits / PRs (see handbook/04-documenting-ai-use.md).

## Things to be careful about
- Never commit secrets or large/derived data — see `.gitignore`.
- Extra scrutiny on CRS, units, joins, and anything touching real measurements.
