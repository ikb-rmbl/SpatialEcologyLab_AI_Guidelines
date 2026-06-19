# 01 — Git & GitHub, in Positron

Git is a **time machine and a lab notebook for your code**. GitHub is the cloud copy that backs it up and lets us collaborate. You do not need to be a Git expert. You need about six commands and a few good habits.

This guide assumes you're working in **Positron**. Everything here also works in RStudio or the terminal, but the menus we describe are Positron's.

---

## Why we bother

- **You will break things.** Git lets you go back to any moment when it still worked.
- **"It works on my machine" is not science.** GitHub makes your work reproducible by someone else (including future you).
- **It's how real research code is shared.** rSDP, pySDP, and every lab tool live on GitHub.
- **It creates an honest record** of what you did, when, and (see [`04-documenting-ai-use.md`](04-documenting-ai-use.md)) how the AI helped.

> **Mental model.** A *commit* is a labeled snapshot. A *repository* ("repo") is the folder full of snapshots. *Push* sends snapshots to GitHub; *pull* brings others' snapshots down. That's 90% of it.

---

## One-time setup

### 1. Make a GitHub account
Use your real name or a recognizable handle — this is a professional record. Sign up at [github.com](https://github.com). Tell your supervisor your username so you can be added to the lab organization.

### 2. Install Git
- **macOS:** open Terminal and run `git --version`. If it's missing, macOS will offer to install the developer tools — accept.
- **Windows:** install [Git for Windows](https://git-scm.com/download/win).

### 3. Tell Git who you are
In Positron, open the terminal (**View → Terminal**, or `` Ctrl+` ``) and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"   # use the email on your GitHub account
```

### 4. Connect Positron to GitHub
The easiest path is the **GitHub CLI**, which handles login for you:

```bash
# macOS (Homebrew):
brew install gh
# Windows: download from https://cli.github.com

gh auth login
```

Choose **GitHub.com → HTTPS → log in with a browser**. This stores your credentials so you never paste a password again.

> If you hit an authentication wall later, the fix is almost always `gh auth login` again. Ask before fighting it for more than ten minutes.

---

## The daily loop (working solo)

This is the rhythm you'll use 95% of the time. Do it often — small commits are easier to understand and undo than giant ones.

```
edit code  →  stage  →  commit  →  push
```

### In Positron's UI (recommended while you're learning)

1. Click the **Source Control** icon in the left sidebar (it looks like a branching fork; shortcut `Ctrl+Shift+G`).
2. You'll see a list of **Changes** — every file you've touched.
3. Hover a file and click **`+`** to *stage* it (or stage everything with the `+` next to "Changes").
4. Type a **commit message** in the box at the top (see message tips below).
5. Click the **✓ Commit** button.
6. Click **Sync Changes** (or the **…** menu → **Push**) to send it to GitHub.

### In the terminal (the same thing, faster once it's muscle memory)

```bash
git status                     # what changed?
git add R/clean_data.R         # stage one file...
git add .                      # ...or stage everything
git commit -m "Filter out sensor errors before computing means"
git push
```

### Good commit messages

Write what the change *accomplishes*, not "update" or "stuff". A labmate (or you in August) should understand it without opening the file.

| Bad | Good |
|-----|------|
| `update` | `Drop 2021 plots with missing GPS coords` |
| `fixed it` | `Fix CRS mismatch: reproject points to EPSG:32613` |
| `asdf` | `Add NDVI calculation for June composites` |

---

## Starting a repository

### Option A — start on GitHub (easiest)
1. On GitHub, click **New repository**. Name it, keep it **Private** unless told otherwise, and check **Add a README**.
2. In Positron: **Command Palette** (`Ctrl+Shift+P`) → **Git: Clone** → paste the repo URL → pick a folder under `~/code/`.
3. Positron opens the cloned folder. You're ready.

### Option B — turn an existing folder into a repo
In the project folder's terminal:
```bash
git init
gh repo create               # follow the prompts to make the GitHub side and link it
git add .
git commit -m "Initial commit"
git push -u origin main
```

> **Before your first commit, add a `.gitignore`.** Both project skeletons include one (e.g. [`templates/project-skeleton-tutor/.gitignore`](../templates/project-skeleton-tutor/.gitignore)). It keeps large data, secrets, and clutter *out* of Git — see the next section.

---

## What goes in Git, and what doesn't

This matters more in our lab than in most, because our data is **big** (rasters, GeoPackages) and Git is built for **text** (code).

**✅ Commit these:**
- R scripts, Quarto/RMarkdown docs, functions (`R/`, `*.qmd`)
- Small canonical input files (a site list, a config)
- `README.md`, `AGENTS.md`, `renv.lock`
- Small text outputs (a summary `.csv` someone needs to see)

**🚫 Never commit these (put them in `.gitignore`):**
- Derived rasters, intermediate `.parquet`, large GeoPackages — anything you can *regenerate* by re-running code
- Anything over ~50 MB (GitHub will reject 100 MB+ files and it's a pain to undo)
- Secrets: API keys, AWS credentials, `.env` files, `.Renviron`
- `.Rproj.user/`, `.Rhistory`, `renv/library/`

> **Rule of thumb:** if a script can recreate it, don't commit it — commit the script. If it's a secret, *never* commit it. Our `.gitignore` template handles the common cases for you.

If you accidentally commit something huge or secret, **stop and ask** — don't just delete it, because Git remembers. We'll clean it up together.

---

## Working with others (branches & pull requests)

When more than one person touches a repo, we use **branches** so nobody overwrites anybody. A branch is a parallel line of work you merge back in when it's ready.

```bash
git switch -c ndvi-analysis      # create and move to a new branch
# ...do your work, commit as usual...
git push -u origin ndvi-analysis # publish the branch
```

Then on GitHub, click **Compare & pull request**. A **pull request (PR)** says "here's my work, please review and merge it." Your supervisor or a labmate reviews it, comments, and merges. This is also where AI-use notes belong (see [`04-documenting-ai-use.md`](04-documenting-ai-use.md)).

To get others' merged work onto your machine:
```bash
git switch main
git pull
```

> **Golden rule of collaboration:** `git pull` before you start working each day, and don't let a branch live for weeks. Small, frequent merges beat one giant scary one.

---

## When things go wrong (they will)

Stay calm. Git almost never truly loses committed work. Common situations:

| Situation | What to do |
|-----------|------------|
| "I changed a file and want the last committed version back" | Source Control panel → right-click the file → **Discard Changes** (this is permanent for *uncommitted* edits, so be sure) |
| "I committed but haven't pushed, and the message is wrong" | `git commit --amend -m "better message"` |
| "I'm getting a merge conflict" | Don't panic — see below |
| "I think I lost work" | **Stop touching it** and ask. Committed work is almost always recoverable. |

**Merge conflicts** happen when two changes touch the same lines. Positron marks them in the file with `<<<<<<<`, `=======`, `>>>>>>>`. Open the file, decide which version (or combination) is right, delete the marker lines, save, then stage and commit. This is a great moment to ask the assistant to *explain* the conflict — but **you** decide which code is correct.

> **The asking rule:** if you've been stuck on a Git problem for more than ~15 minutes, ask a human. Git problems compound when you guess.

---

## Using the AI assistant with Git

The assistant is genuinely helpful here — Git's error messages are famously cryptic. Good uses:

- **"Explain what this Git error means and what my options are."** (Then *you* choose.)
- **"What's the difference between `git reset` and `git revert`?"**
- **"Help me write a clear commit message for this diff."**

Be careful with:

- **Destructive commands.** If the assistant suggests `git reset --hard`, `git push --force`, or anything that deletes history, **stop and ask a human first.** These can erase work.
- **Blindly running suggested commands.** Read what a command does before running it. "I don't know what this does" is a reason to ask, not to run it.

---

## The six commands you actually need

If you remember nothing else:

```bash
git status                    # what's going on?
git add .                     # stage my changes
git commit -m "message"       # snapshot them
git push                      # send to GitHub
git pull                      # get others' changes
git switch -c my-branch       # start a new line of work
```

Everything else you can look up — or ask the assistant to explain — when you need it.
