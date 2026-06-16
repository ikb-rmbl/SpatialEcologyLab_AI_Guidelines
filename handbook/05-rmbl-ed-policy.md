# 05 — How this fits the RMBL Undergraduate Program AI Policy

If you're participating in the **RMBL Undergraduate Research / Education Program**, that program has its own AI policy, and it governs you. This page explains how it relates to this lab handbook and resolves the few places where the two *seem* to pull in different directions.

> **Not in the program?** Read this anyway — the program's rules are good practice, and the lab expects them of everyone. They're also just a more formal version of what this handbook already asks.

---

## The governing rule

```
RMBL Ed Program AI Policy  =  the floor (the minimum)
This lab handbook          =  may be stricter, never looser
```

- A lab can be **more** restrictive than the program policy, but **not less**. Where this handbook looks more permissive, **the program policy wins** — with **one explicit, reasoned exception** the lab has made about *data sharing with workspace-aware tools*, explained in §1 below.
- Everywhere else, when two rules differ, **follow the stricter one.**
- When you're unsure whether a use is allowed, **ask** — your supervisor or the program coordinators. The policy explicitly invites this, and "I asked first" is always the right move.

> Get the official, current policy text from the program coordinators (it may be updated). The summary below is for orientation, not a substitute.

---

## The Ed policy in brief

The program **permits** generative AI (ChatGPT, Claude, Gemini, etc.) for **certain things**, used carefully and **cited correctly**. Specifically:

**✅ Explicitly appropriate uses**
- Debugging and **understanding R code**
- **Checking statistical interpretations**
- Transcribing your audio notes/recordings to speed up data entry
- "…and more" (similar supporting uses)

**🚫 Not allowed**
- **Composition or writing of any pieces of the program** (your written products)
- **Uploading any data** — *see §1 for how this lab reads this provision in its open-data context*

**📌 Required if you use AI at all**
- **Cite the use** (the policy points to the [Purdue AI citation guide](https://guides.lib.purdue.edu/c.php?g=1371380&p=10135074)) **and describe how you used it in the methods section** of any product.
- **Failure to properly cite AI is a policy violation**, with consequences for continued participation and performance reviews.

And the closing spirit: *you are becoming an expert and need to rely on your own logic and background knowledge.* That is exactly this handbook's [philosophy](00-start-here.md).

---

## Where the policy and this handbook strongly agree

You'll notice these are the *same idea* said two ways:

| The Ed policy says… | This handbook says… |
|---|---|
| "rely on your own logic and background knowledge" | Avoid cognitive surrender; you're the scientist ([00](00-start-here.md)) |
| AI is good for "understanding R code" | Use the explanation gate; learn the code, don't just take it ([03](03-working-with-the-assistant.md)) |
| AI is good for "checking statistical interpretations" | The assistant as a consultant you interrogate; verify against reality ([03](03-working-with-the-assistant.md)) |
| "AI output is not always correct… only as useful as the prompts" | Plan first, verify everything, catch it being wrong ([03](03-working-with-the-assistant.md)) |
| You must cite/disclose AI use | Document your AI use honestly ([04](04-documenting-ai-use.md)) |

So most of this handbook is simply *how* to live up to the program policy. The differences are below.

---

## The three places to be careful (apparent conflicts, resolved)

### 1. Sharing data with the assistant — the lab's reasoned position

Read literally, the program policy prohibits "uploading any data." **This lab reads that provision in light of its purpose** — keeping *sensitive or proprietary* data from leaving RMBL — and in our setting that concern doesn't apply:

- The lab works only with **open, published, or otherwise non-proprietary data** — that's the lab's standing data policy.
- We use **workspace-aware tools and infrastructure with appropriate protections** (Positron and the [Data Hub](../reference/rmbl-data-hub.md)), where the assistant seeing your data is a designed, contained part of the workflow.
- A coding assistant that *can't* see your data is sharply less useful, and hand-describing every dataset is real friction with little protective benefit when the data is already open.

**So in this lab, letting the assistant see the data in your workspace is permitted.** You can point it at your files, paste a few rows to debug, and let it inspect your data frames. (This is the one place the lab *interprets* the policy rather than simply matching it — see the governing rule above.)

**Still off-limits — never share these with any AI tool:**
- Embargoed or not-yet-published data you've agreed to keep private
- Data from outside collaborators that came to you with restrictions
- Human-subjects data or any personally identifying information (PII)
- Anything you don't have the rights to share

> **Program participants:** if your project involves *any* data that isn't clearly open — restricted, embargoed, collaborator-owned, human-subjects — treat upload as prohibited and **confirm with your supervisor or the program coordinators before sharing it.** When you're unsure whether your data counts as "open," ask first.

> **The Knowledge Commons MCP** sends your *search queries* to RMBL's own public literature server — it doesn't transmit your research data either way. (Still, don't type anything sensitive into a search box.)

### 2. AI may help you with code — not write your prose

The policy bars AI from "composition or writing of any pieces of the program," but explicitly *allows* code debugging and understanding. So draw the line clearly:

- ✅ **Allowed:** help writing/debugging/understanding **R code**, explaining concepts, checking a stat interpretation, quizzing you.
- 🚫 **Not allowed:** having AI **write your written products** — report text, poster text, methods narratives, reflections, abstracts, emails-as-deliverables. The *words* of your program pieces must be yours.

If you're unsure whether something is "code" or "writing" (e.g., a heavily-commented script, or a figure caption), treat it as writing and keep it yours — or ask.

### 3. Citation: the lab's notes are necessary, but the program wants more

This handbook calls AI-use documentation **"lightweight"** and says you can skip noting *tiny* help ([04](04-documenting-ai-use.md)). That's the right habit for **day-to-day lab work** — but it is **not sufficient for program products**, where the policy requires formal citation:

| | Day-to-day lab work | Program products (reports, posters, methods, anything you submit/present) |
|---|---|---|
| **What's required** | Lightweight notes (commit trailers, PR notes, the `analysis.qmd` AI-use note) | **Formal citation** ([Purdue format](https://guides.lib.purdue.edu/c.php?g=1371380&p=10135074)) **+ a description of how AI was used in your methods section** |
| **Stakes of not doing it** | It's just good practice | **Policy violation** — real consequences for participation and reviews |

How to reconcile them:
- Keep doing the lightweight lab notes — they're your **paper trail**, and they make writing the formal citation later trivial (you'll already know what AI did).
- For **anything that's a program deliverable, cite formally and describe in methods.** Do not rely on "it was tiny" — the program penalizes *missing* citations, so **when in doubt, cite.**
- The lab's "disclosure is penalty-free" still holds: you never get in trouble for *using and citing* AI appropriately. The program's consequences are for **failing to cite**, not for using AI. Same direction, higher stakes.

---

## Quick reference — if you're a program participant

- [ ] I follow the **RMBL Ed AI Policy as my minimum** (with the lab's one reasoned exception on data sharing, §1).
- [ ] I can let the assistant see my **open / lab workspace data** — but I keep **embargoed, restricted, collaborator-owned, or human-subjects data** out of any AI tool, and **ask if unsure**.
- [ ] I use AI for **code and understanding**, **not** to write my prose.
- [ ] I keep **lightweight notes** as I work, and **formally cite + describe in methods** for any program product.
- [ ] When I'm unsure, **I ask** before I act.

> The two policies want the same thing: that you leave this summer **more capable on your own**, with an honest record of how you got there. Mind the policy (follow the stricter rule where they differ), cite your use, keep *sensitive* data and your own writing yours, and you're aligned with both.
