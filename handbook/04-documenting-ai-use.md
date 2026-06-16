# 04 — Documenting Your AI Use

We keep a light, honest record of how the assistant helped. This is **not** surveillance and it is **not** something you get in trouble for. It exists for three good reasons:

1. **Reproducibility** — science you can't reproduce isn't finished. "How was this made?" includes the AI.
2. **Your own learning** — noticing *what* you offloaded is how you spot the gaps to close next.
3. **Honesty as the default** — when disclosure is normal and safe, everyone tells the truth.

> **The golden rule of disclosure here:** *Using the assistant is never the problem. Hiding that you used it is the only problem.* There is no penalty for "the AI wrote most of this function." There's a real one for pretending it didn't.

> **Program participants: the lightweight notes below are necessary but not sufficient.** The RMBL Undergraduate Program requires you to **formally cite** AI use ([Purdue format](https://guides.lib.purdue.edu/c.php?g=1371380&p=10135074)) **and describe how you used it in the methods section** of any program product — and *failure to cite is a policy violation with consequences.* Keep the lab's lightweight notes as you work (they make the formal citation easy to write later), and cite formally on anything you submit or present. When in doubt, cite. See [`05-rmbl-ed-policy.md`](05-rmbl-ed-policy.md).

---

## Why we keep it lightweight (and why mandates backfire)

The research is clear that heavy-handed disclosure rules *fail*: in one study, **74% of students didn't declare AI use even when declaring carried no penalty** — driven by fear, ambiguity, and inconsistent enforcement, not dishonesty (see [`reference/evidence-base.md`](../reference/evidence-base.md) §8). So we deliberately make this:

- **Penalty-free** — disclosure never counts against you.
- **Low-friction** — a sentence, not a form.
- **Routine** — it rides along with things you already do (commits, PRs, the analysis doc).
- **Consistent** — everyone does it, including your supervisor.

If the record ever feels like a burden, it's too heavy — tell us and we'll lighten it. A record nobody keeps is worse than a light one everyone keeps.

---

## What "lightweight" looks like in practice

You don't log every keystroke. You note, in plain language, **where the assistant did meaningful work and what you did to make sure it's right.** Three places, none of them extra files:

### 1. In commit messages (for code)
When the assistant did substantial work in a commit, add a short trailer line:

```
Add NDVI compositing function for June

AI-assisted: assistant drafted the terra::app() call; I chose the
date window and verified output against 2022 plot means.
```

For tiny help (a syntax fix, a typo), you don't need to note it — same as you wouldn't credit a labmate for reminding you of a comma.

### 2. In the analysis document (for analysis)
The skeleton's `analysis.qmd` ends with an **AI-use note**. One or two sentences at the end of an analysis:

```markdown
<!-- AI-use note: AI suggested the group_by/summarise structure and helped
     debug a CRS mismatch. I wrote the plan, chose the elevation bins, and
     verified band counts against the field data. -->
```

### 3. In pull requests (for shared/reviewed work)
When you open a PR, the template asks one question: *how did the assistant help, and how did you verify the result?* A couple of sentences. This is where your supervisor sees the collaboration, and it's a natural mentoring checkpoint.

---

## What to actually write

Aim for **what the AI did + what you did to own it.** A good note answers: could someone reproduce this, and did you understand it?

| Situation | A good note |
|-----------|-------------|
| AI wrote a function you understand and checked | "AI drafted `bin_elevation()`; I set the bin width and tested it on the 2022 plots." |
| AI helped you debug | "AI helped me read a CRS-mismatch error; I fixed it by reprojecting to EPSG:32613." |
| AI taught you a concept you then applied yourself | "Used AI to understand spatial joins; wrote the join myself." |
| You used AI a *lot* on something you're shaky on | Say so honestly — "AI did most of this Stan model; I don't fully understand the priors yet" is a *useful* flag, not a confession. It tells your mentor where to help. |

The last row is the most important. **An honest "I leaned on it heavily here and I'm not solid yet" is exactly the signal that makes the system work.** It's the opposite of something to hide.

---

## What you do *not* need to do

- ❌ Log every autocomplete or one-line fix.
- ❌ Keep a separate spreadsheet or timesheet of AI use.
- ❌ Quote the AI verbatim or save chat transcripts (unless something was genuinely pivotal and worth saving — then drop it in the PR).
- ❌ Feel any embarrassment. Heavy use that you understood and verified is *good* use.

The whole thing should add up to **a sentence here and there**, not a paperwork habit.

---

## The honesty test

Before you mark something done, two questions:

1. **Could a labmate reproduce this** from what's written down (including how the AI helped)?
2. **Would I be comfortable** if my supervisor asked me to walk through any line of it, with the AI closed?

If yes to both, your documentation is sufficient and your work is honest. That's the bar — nothing heavier.

---

*See [`../templates/`](../templates/) for the PR template and the `analysis.qmd` AI-use note placeholder, so the prompts are already there when you need them.*
