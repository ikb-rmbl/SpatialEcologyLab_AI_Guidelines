# Spatial Ecology Lab — AI Assistant Guidelines

Infrastructure for using AI coding assistants (the Posit Assistant in [Positron](https://positron.posit.co/), or any agent that reads `AGENTS.md`) as a **partner in learning**, not a replacement for it.

This repo is meant to be **cloned/forked by every student** at the start of the summer. It gives you:

- A short **handbook** on how we work with AI in this lab.
- **Templates** you copy into your own project (an `AGENTS.md`, a project skeleton, a `.gitignore`).
- **Checklists** for getting set up and for keeping your work honest and reproducible.

> **The one-sentence version:** Use the assistant to learn *faster*, never to think *less*. If you couldn't explain it to a labmate, you don't get to ship it.

---

## Who this is for

Students at every level — from undergraduates who have never taken a data science class to grad students with a few stats courses. The defaults assume **R in Positron**, the IDE and language we use most. The principles transfer to Python, the terminal, or any assistant.

## How to use this repo

1. Read **[`handbook/00-start-here.md`](handbook/00-start-here.md)** first. It's the philosophy and the 10-minute version of everything else.
2. Work through the rest of the handbook in order. It's short on purpose.
3. When you start your own project, copy **[`templates/project-skeleton/`](templates/project-skeleton/)** as your starting point and fill in the `AGENTS.md`.
4. Use **[`checklists/onboarding-checklist.md`](checklists/onboarding-checklist.md)** to get your environment working in the first week.

## Map of the handbook

| File | What it covers |
|------|----------------|
| [`handbook/00-start-here.md`](handbook/00-start-here.md) | Lab philosophy: AI as partner, avoiding "cognitive surrender" |
| [`handbook/01-git-and-github.md`](handbook/01-git-and-github.md) | Git & GitHub from scratch, in Positron |
| [`handbook/02-writing-agents-md.md`](handbook/02-writing-agents-md.md) | How to write an `AGENTS.md` that helps you *and* makes you a better scientist |
| [`handbook/03-working-with-the-assistant.md`](handbook/03-working-with-the-assistant.md) | Day-to-day work patterns that keep you in the driver's seat |
| [`handbook/04-documenting-ai-use.md`](handbook/04-documenting-ai-use.md) | Lightweight, honest records of how you used AI |
| [`handbook/05-rmbl-ed-policy.md`](handbook/05-rmbl-ed-policy.md) | How this fits the RMBL Undergraduate Program AI policy (read if you're a program participant) |
| [`handbook/06-spec-driven-development.md`](handbook/06-spec-driven-development.md) | Spec-first workflow for bigger projects (for grad students / senior techs) |
| [`reference/lab-context.md`](reference/lab-context.md) | Lab research themes, glossary, and canonical data/tools |
| [`reference/rmbl-data-hub.md`](reference/rmbl-data-hub.md) | The RMBL Data Hub tools (Knowledge Commons, SDP Browser, Compute Hub) and how to use them |
| [`reference/evidence-base.md`](reference/evidence-base.md) | The cited research behind *why* we work this way |

## Templates

| Path | What it is |
|------|------------|
| [`templates/project-skeleton/`](templates/project-skeleton/) | A minimal R analysis project you copy to start |
| [`templates/AGENTS.starter.md`](templates/AGENTS.starter.md) | A fill-in-the-blanks `AGENTS.md` for a brand-new project |
| [`templates/AGENTS.tutor.md`](templates/AGENTS.tutor.md) | A "teach me, don't just do it" `AGENTS.md` for when you're learning a new skill |
| [`templates/PROJECT-BRIEF.md`](templates/PROJECT-BRIEF.md) | Distill your project — and sort its context into "plumbing for the AI" vs. "thinking you keep" |
| [`templates/SPEC.md`](templates/SPEC.md) | Spec one substantial build (pipeline/package) before the assistant implements it |

---

*Maintained by the Spatial Ecology Lab. Suggestions welcome — open an issue or a pull request (that's good Git practice anyway).*
