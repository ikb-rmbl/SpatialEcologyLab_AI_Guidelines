# 03 — Working with the Assistant

This is the practical core of the handbook: the actual moves you make, day to day, that keep you learning while you use the assistant. Every pattern here is backed by evidence — see [`reference/evidence-base.md`](../reference/evidence-base.md) for the studies.

> **The frame:** you've hired a fast, knowledgeable, occasionally-wrong **consultant**. You interrogate a consultant; you don't hand the whole job to a contractor and sign off unread. The research is blunt about this: the people who paste AI output wholesale are the ones who don't learn.

---

## The four patterns

If you internalize four things, you've got it.

### Pattern 1 — Attempt first (the 10-minute rule)

Before you ask the assistant for an answer, **spend ~10 minutes trying it yourself.** Sketch the plan, write the first attempt, predict what the code will do.

Why: being a little stuck is not a failure state — it's the condition under which learning actually happens. AI use is most harmful exactly when you reach for it the instant something gets hard (that's when struggle matters most). The 10-minute rule reserves the productive part of the struggle for you.

> This doesn't mean suffer for an hour. If you're truly stuck after a genuine attempt, *then* the assistant is a great next step — and you'll learn more from its answer because you have a question shaped to receive it.

### Pattern 2 — Plan in your words, then ask

State your plan **before** you ask for code. In an analysis, write it into the `.qmd` (there's a spot for it in the skeleton). In a chat, type it out.

> "I want to compute mean NDVI per plot for June. My plan: filter to June, group by plot, summarise the mean. I think I need `group_by()` then `summarise()`. Is this the right approach, and what am I missing?"

This does three things: it forces *you* to do the thinking, it gives the assistant the context to actually help, and it turns a "write my code" request into a "check my reasoning" request. If you can't write the plan, you're not ready for the code — you're ready to *learn the concept*, which is Pattern 4.

### Pattern 3 — The explanation gate (the most important one)

**Before any AI-generated code enters your project, explain it — out loud or in a comment — in terms of cause and effect. Not "it filters the data" but "it drops rows where `quality < 3` *because* those are flagged sensor errors that would bias the mean upward."**

This is the rule with the strongest evidence in the whole handbook. In a controlled study, students who had to explain AI code before accepting it failed a later AI-off task **half as often** as those who didn't (39% vs 77%). The explanation is what converts borrowed code into your own understanding.

Operationally:
- Read every line the assistant wrote.
- For anything you can't explain, ask: **"Explain this line and why it's here. What would break if I removed it?"**
- If you still can't explain it after that, it does not go in. Flag it, ask a human, or learn the underlying concept first.

> **The shipping bar, restated:** could you defend this code to a labmate, with the AI closed? If no, it's not done.

### Pattern 4 — Verify against reality

The assistant is confidently wrong on a regular basis. Never let "the AI said so" be your evidence. Check its output against something real:

- A **known case** — does it give the right answer for a row you computed by hand?
- A **sanity plot** — does the map/histogram look physically plausible?
- A **count** — do the number of plots/pixels/dates match what you expect?
- The **docs** — does `?group_by` actually say what the assistant claimed?

Catching the assistant being wrong is one of the most valuable skills you'll build this summer. It only develops if you look.

---

## Turning the assistant into a study tool

The assistant is most valuable when it makes you *do* the high-value learning strategies — not when it does them for you. Concrete prompts:

| Goal | Prompt the assistant like this |
|------|-------------------------------|
| **Self-explanation** | "I think this code works because [my explanation]. Is my understanding correct? Where am I wrong?" |
| **Retrieval practice** | "Quiz me with 3 questions on `dplyr` joins. Don't give answers until I've tried." |
| **Compare approaches** | "Show me two ways to do this — a base R way and a tidyverse way — and explain the trade-offs. Don't pick for me." |
| **Socratic help** | "Don't give me the answer. Ask me questions that help me figure out why my join is producing duplicate rows." |
| **Concept, not code** | "Explain what a coordinate reference system mismatch is, with a small example. No code for my actual problem yet." |

The `AGENTS.tutor.md` template ([`../templates/AGENTS.tutor.md`](../templates/AGENTS.tutor.md)) bakes the Socratic mode in, so the assistant defaults to coaching instead of answering when you're learning a new skill.

---

## A worked example

**Task:** "Summarize snowmelt timing by elevation band."

❌ **Cognitive surrender:**
> "Write R code to summarize snowmelt timing by elevation band from my data."
>
> *...pastes the 30-line response, it runs, moves on.*

You now have a result you can't defend and learned nothing.

✅ **Partner mode:**
1. *(Attempt)* You open the data, look at the columns, realize you need elevation bins and a melt-date column.
2. *(Plan)* You write: "Bin elevation into 100 m classes with `cut()`, group by band, take median melt DOY. I'm unsure how `cut()` labels work."
3. *(Ask)* "Here's my plan [above]. Is binning with `cut()` right here, and how do its labels work?"
4. *(Explanation gate)* The assistant gives code. You read it, and comment each step: "`cut(elev, breaks=seq(...))` → makes elevation classes; `right=FALSE` → bins are [lower, upper)..." One argument you don't get — you ask about it.
5. *(Verify)* You check: do the band counts sum to the total number of plots? Does the lowest band melt earliest? It does. Plausible.
6. *(Note)* In your AI-use note: "AI suggested `cut()` + `group_by`/`summarise`; I chose the bin width and verified band counts."

Same code. Completely different outcome for *you*.

---

## Things to be careful about

- **The fluency trap.** A clear explanation from the assistant makes you *feel* like you understand. The only proof is producing it yourself. Feeling "this is easy now" right after reading an answer is not the same as knowing it.
- **Wrong-but-confident code.** Especially on anything CRS-, units-, or join-related — the assistant will produce plausible code that's subtly wrong. Verify (Pattern 4).
- **Scope creep in suggestions.** The assistant often "helpfully" rewrites more than you asked. Take only the line you needed; don't accept a refactor you didn't request and don't understand.
- **Stale or invented APIs.** It may call functions/arguments that don't exist or have changed. If it errors with "unused argument" or "could not find function," that's often the assistant guessing — check the docs.
- **Time pressure.** When you're behind, the urge to offload spikes. That's the moment to slow down, not speed up. Tell a human you're behind; that's always cheaper than a result you can't trust.

---

## When you're stuck (the escalation ladder)

1. **Try it** (~10 min, Pattern 1).
2. **Ask the assistant to teach, not solve** — Socratic prompt, or "explain the concept."
3. **Check the real docs** / a labmate's similar code.
4. **Ask a human.** For Git problems, CRS confusion, or anything where you've burned ~15–20 minutes — ask. You're not expected to know everything; you're expected to keep learning, and humans are part of that loop.

---

## The self-check

Once a week, ask yourself honestly:

- Can I write more R from a blank file than I could last week?
- When the assistant suggests something, can I tell whether it's *right*?
- Have I caught the assistant being wrong recently? (If never — am I actually checking?)
- Could I reproduce my last analysis with the AI turned off?

If those are trending "yes," you're using the assistant exactly as intended.
