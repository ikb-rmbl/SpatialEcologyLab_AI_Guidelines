# 02 — Writing an `AGENTS.md`

An `AGENTS.md` file is a short note you leave **for the AI assistant**, sitting in the root of your project. When the assistant starts working, it reads this file first — so it's how you tell it about your project *and*, crucially for us, how you tell it to **help you learn instead of doing your thinking for you.**

> `AGENTS.md` is an open convention many tools now read (the Posit Assistant, Claude Code, and others). Some tools historically used `CLAUDE.md`; the content is the same idea. We standardize on `AGENTS.md`. If a tool only reads `CLAUDE.md`, make it a copy or a symlink.

---

## Why this is the lab's secret weapon

Most people write `AGENTS.md` files that make the assistant a *faster contractor* — "here's the stack, here's the style, now go." We write them to make the assistant a **better tutor**. The same file that gives it project context can also instruct it to *ask before it answers*, to *make you explain code*, and to *not hand you solutions when you're supposed to be learning.*

This is the cheapest, highest-leverage thing you can do to keep yourself in the driver's seat: the good behavior becomes the **default**, so you don't have to summon the discipline every single prompt.

---

## What goes in an `AGENTS.md`

Keep it terse. It's a map for the assistant, not an essay. Good sections:

1. **Project** — one or two sentences on the scientific question and what the code does.
2. **Stack & layout** — language, key packages, where things live (`R/`, `data/`, etc.).
3. **Conventions** — style, naming, CRS defaults, anything project-specific.
4. **How to help me learn** — *the part most files skip and we require.* The teaching behavior you want.
5. **Things to be careful about** — gotchas, the big-data rules, "never commit secrets."

Sections 1–3 and 5 make the assistant *useful*. Section 4 makes it *good for you*. Don't skip 4.

---

## The "How to help me learn" section

This is where you tell the assistant to behave like a mentor. The exact wording matters less than the intent, but here are the moves that have evidence behind them (see [`reference/evidence-base.md`](../reference/evidence-base.md)):

**Make it coach, not just answer:**
```markdown
## How to help me learn
- I'm a student learning R and data science. Your job is to help me understand, not just to produce code.
- When I ask how to do something, first ask me what I've tried or what my plan is. Don't lead with a full solution.
- Prefer explaining the concept and giving a small example over writing my analysis for me.
```

**Build in the explanation gate:**
```markdown
- When you do write code, explain each non-obvious line and *why* it's there.
- After giving me code, ask me a question that checks I understood it before I move on.
```

**Set the consultant stance:**
```markdown
- Treat yourself as a consultant I'm interrogating, not a contractor I've handed the job to.
- It's fine — good, even — to tell me when my approach has a problem, and to ask me to make the call.
```

**Protect productive struggle:**
```markdown
- If I paste an error, help me read and understand it; don't just output a fixed version.
- For small/foundational things (basic dplyr, plotting, indexing), nudge me to try first rather than doing it for me.
```

You don't need all of these. Pick what fits where you are. A first-week undergrad wants the full Socratic treatment; a grad student debugging a Stan model wants context and gotchas, lighter coaching. That's the **two-mode** idea below.

---

## Two modes: tutor and teammate

We ship two templates because guardrails should match your expertise (the expertise-reversal effect — what helps a novice is friction for an expert):

- **[`templates/AGENTS.tutor.md`](../templates/AGENTS.tutor.md)** — *"I'm learning this skill."* The assistant defaults to Socratic mode: asks before answering, withholds full solutions, makes you explain. Use this for any area you're still building.
- **[`templates/AGENTS.starter.md`](../templates/AGENTS.starter.md)** — *"I own this; help me go faster."* Still requires explanation-on-request and honest verification, but lets the assistant be more direct. Use this once you've demonstrated (to yourself and your supervisor) that you understand the area.

**Be honest about which mode you're in.** Switching to teammate mode because tutor mode is "annoying" is exactly the cognitive-surrender slide the modes exist to prevent. Move up when you've earned it, and tell your supervisor when you do — it's a good checkpoint.

You can even scope modes by topic, e.g. "Socratic for stats and modeling; direct for boilerplate plotting I've done a hundred times."

---

## How to create one

1. Copy a template into your project root as `AGENTS.md`:
   ```bash
   cp ~/path/to/AI_Guidelines/templates/AGENTS.tutor.md ./AGENTS.md
   ```
   (The project skeleton already includes a starter `AGENTS.md` — edit that.)
2. Fill in the project/stack/conventions sections. Delete what doesn't apply.
3. Commit it. It's part of the project and should be versioned:
   ```bash
   git add AGENTS.md && git commit -m "Add AGENTS.md with tutor-mode coaching"
   ```
4. Revisit it as the project grows. When you keep telling the assistant the same thing in chat, that thing belongs in `AGENTS.md`.

---

## Good vs. weak `AGENTS.md` lines

| Weak | Strong |
|------|--------|
| "Help me with my R project." | "Help me *understand* my R project; ask what I've tried before giving solutions." |
| "Write clean code." | "Explain each non-obvious line and why it's there; quiz me before I move on." |
| "Use tidyverse." | "Use tidyverse (`dplyr`/`ggplot2`); default CRS is EPSG:32613; reusable functions go in `R/`." |
| (no learning section) | A "How to help me learn" section — non-negotiable in this lab. |

---

## A note on what `AGENTS.md` *can't* do

The file sets defaults; it doesn't enforce them. The assistant will sometimes ignore it, and you can always override it in chat. So `AGENTS.md` is a **support**, not a guarantee. The actual guarantee is you — the work patterns in [`03-working-with-the-assistant.md`](03-working-with-the-assistant.md) are what keep you honest when the file isn't watching.

> Think of `AGENTS.md` as setting the table for good habits. You still have to eat the vegetables.
