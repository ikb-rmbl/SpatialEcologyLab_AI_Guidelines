# Project Brief — <your project name>

<!--
  Fill this in early, with your supervisor, when you start a project. It does two jobs:
   1. It makes YOU articulate what you're doing (which is half of understanding it).
   2. It sorts your project's context into two piles — see the two sections at the end.
      That sorting is the whole point, so don't skip it.

  This is a living document. Update it as the project evolves. Keep it short.
-->

**Student:** <name>  ·  **Supervisor:** <name>  ·  **Started:** <month year>
**Lab theme:** <which research theme from reference/lab-context.md, e.g. "Landscape phenology">

---

## 1. The question (in your own words)
<!-- One or two plain sentences. What are you actually trying to find out?
     If you can't write this yet, that's your first conversation with your supervisor. -->


## 2. Why it matters
<!-- One or two sentences. How does answering it move the lab's science forward?
     Write this YOURSELF — it's exactly the kind of thinking you're here to build. -->


## 3. The data
<!-- What data, where it lives, what one row / one pixel / one sensor reading represents.
     Note the canonical sources from reference/lab-context.md (SDP product IDs, OSF/EDI
     links, the micro-met Drive folder, etc.). Note units and CRS. -->


## 4. The approach (your current plan)
<!-- Bullet the steps you THINK the analysis takes. It's fine to be wrong — this is your
     hypothesis about the method, and updating it as you learn is the work.
     This is also what you show the assistant when you ask "is this the right approach?" -->


## 5. Known gotchas / things to be careful about
<!-- CRS mismatches, sensor dropouts, missing years, weird units, scale mismatch between
     prediction and validation, etc. Add to this as you discover them — future-you will thank you. -->


## 6. How will I know it's right?
<!-- What's your reality check? A known case, a sanity plot, a count, field data to compare
     against (e.g. Flower Blitz observations, 2022 plot means). "It runs" is not an answer. -->


---

## What goes in my AGENTS.md  (the *plumbing* — removes friction)
<!--
  Copy these facts into your project's AGENTS.md so the assistant is genuinely useful.
  These are TECHNICAL facts that don't do your thinking for you:
-->
- Packages & access: <e.g. rSDP for SDP rasters; dplR for tree cores; tidyverse>
- Data location & format: <e.g. SDP product R3D009 via VSICURL; micro-met CSVs on Drive>
- CRS & units: <e.g. EPSG:32613; temps in °C; DOY for dates>
- File/naming conventions: <...>
- Sensor / instrument facts: <e.g. TOMST TMS-4 channels; HOBO logger quirks>

## What I keep for myself  (the *thinking* — do NOT hand this to the assistant)
<!--
  These are the judgments the summer is meant to build. Use the assistant to TEST your
  thinking on them (Socratic prompts, explain-back) — never to make the call for you:
-->
- The scientific interpretation: <e.g. what a phenology shift or ring-width trend MEANS>
- Modeling decisions: <e.g. which covariates belong in the model and why>
- Whether a result is believable / a problem is real: <e.g. is this scale mismatch a bug or a finding?>
- The conclusions and how I'd defend them with the AI closed.

> If you ever can't tell which pile a piece of context belongs in, ask your supervisor.
> That conversation is one of the most useful you'll have all summer.
