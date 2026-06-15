# Onboarding Checklist — Your First Week

Work top to bottom. None of this should take more than an afternoon or two. Ask a human the moment you're stuck for more than ~15 minutes — that's a rule, not a weakness.

## Day 1 — Read & orient
- [ ] Read [`handbook/00-start-here.md`](../handbook/00-start-here.md) (10 min — the whole philosophy).
- [ ] Skim the rest of the handbook so you know what's there.
- [ ] Understand the one rule: **if you can't explain it, you don't ship it.**

## Set up your tools
- [ ] Install **Positron** ([positron.posit.co](https://positron.posit.co/)).
- [ ] Confirm the **Posit Assistant** is available in Positron (sign in if prompted).
- [ ] Install **R** and check it runs in Positron's console (`R.version.string`).
- [ ] Create a **GitHub account**; send your username to your supervisor to be added to the lab org.
- [ ] Install **Git** and the **GitHub CLI** (`gh`), then run `gh auth login` — see [`handbook/01-git-and-github.md`](../handbook/01-git-and-github.md).
- [ ] Set your Git identity:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  ```

## Learn the Git basics (do, don't just read)
- [ ] Clone a repo in Positron (Command Palette → **Git: Clone**).
- [ ] Make a trivial edit, then **stage → commit → push** it (UI or terminal).
- [ ] Confirm your commit shows up on GitHub.
- [ ] Memorize the six commands at the end of [`handbook/01-git-and-github.md`](../handbook/01-git-and-github.md).

## Get oriented to the lab's science
- [ ] Read [`reference/lab-context.md`](../reference/lab-context.md) — the research themes, glossary, and where the canonical data lives.
- [ ] Skim the `rSDP` README if your project touches SDP rasters.

## Explore the RMBL Data Hub (optional but recommended)
- [ ] Read [`reference/rmbl-data-hub.md`](../reference/rmbl-data-hub.md) for what each tool does.
- [ ] Try a search on the [Knowledge Commons](https://rmblknowledgecommons.org) for your topic.
- [ ] Connect the Knowledge Commons MCP server to Posit Assistant so it cites real sources — follow "Connecting the Commons to Posit Assistant" in [`reference/rmbl-data-hub.md`](../reference/rmbl-data-hub.md). (If you start from the project skeleton, it's already wired in `.vscode/settings.json`.)
- [ ] Browse a layer on the [SDP Browser](https://sdpbrowser.org) and generate an `rSDP` recipe — then practice the explanation gate on the generated code.
- [ ] If you'll need cloud compute, ask your supervisor to add your GitHub username to the [Compute Hub](https://rmblcomputehub.org) allowlist.

## Start your project
- [ ] Copy [`templates/project-skeleton/`](../templates/project-skeleton/) into a new folder under `~/code/`.
- [ ] Make it a Git repo and push it to the lab org (see the Git guide, "Starting a repository").
- [ ] Confirm your `.gitignore` is working: add a dummy big file to `output/` and check `git status` ignores it.
- [ ] Fill in `PROJECT-BRIEF.md` with your supervisor — including the two lists at the bottom (plumbing vs. thinking).
- [ ] Open the `AGENTS.md` (it's tutor mode by default), fill in project/stack, and copy in **only** the "plumbing" pile from your brief. Commit both.

## Set up good AI habits
- [ ] Read [`handbook/03-working-with-the-assistant.md`](../handbook/03-working-with-the-assistant.md) and note the four patterns.
- [ ] Try the **Socratic prompt**: ask the assistant to quiz you on something instead of answering. (`"Quiz me on dplyr joins; don't give answers until I try."`)
- [ ] Practice the **explanation gate** once: get a bit of code, then comment every line in your own words.
- [ ] Read [`handbook/04-documenting-ai-use.md`](../handbook/04-documenting-ai-use.md) and write one AI-use note in a commit.

## First-week check-in (with your supervisor)
- [ ] Walk through one small thing you built — explaining it with the AI closed.
- [ ] Confirm which `AGENTS.md` mode (tutor vs. teammate) is right for your starting skills.
- [ ] Ask any question you've been sitting on. There are no dumb ones in week one.

---

> ✅ **You're set up when:** you can clone, edit, commit, and push from Positron; your project has a filled-in `AGENTS.md`; and you've used the assistant once as a tutor (quizzing/coaching) rather than an answer machine.
