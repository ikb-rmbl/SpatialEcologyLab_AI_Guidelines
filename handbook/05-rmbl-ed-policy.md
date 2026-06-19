# 05 — How this fits the RMBL Undergraduate Program AI Policy

If you're participating in the **RMBL Undergraduate Research / Education Program**, that program has its own AI policy, and it governs you. This page explains how it relates to this lab handbook and resolves the few places where the two *seem* to pull in different directions.

> **Not in the program?** Read this anyway — the program's rules are good practice, and the lab expects them of everyone. They're also just a more formal version of what this handbook already asks.

---

## The governing rule

```
RMBL Ed Program AI Policy  =  the floor (the minimum)
This lab handbook          =  may be stricter, never looser
```

- A lab can be **more** restrictive than the program policy, but **not less**. Where this handbook looks more permissive, **the program policy wins**, and when two rules differ, **follow the stricter one.**
- **The rule that overrides everything else here:** for program undergrads, the **R coding workshop assignments are AI-free** — see the next section.
- When you're unsure whether a use is allowed, **ask** — your supervisor or the program coordinators. The policy explicitly invites this, and "I asked first" is always the right move.

> The program's AI policy is **being revised** (as of mid-2026) to spell out the workshop-assignment rule below. Get the official, current text from the program coordinators — the summary here is for orientation, not a substitute.

---

## The one firm rule for program undergrads: workshop assignments are AI-free

If you're an undergrad in the program, the **R coding workshop assignments are something you do entirely on your own.** Until an assignment is turned in:

- **No AI writing code for you, and no engaging the assistant at all** for the assignment — not for hints, not for debugging, not for "just explain this." You're on your own, by design.
- This includes the Posit Assistant, ChatGPT, Claude, Copilot — any of it.

**After you've turned the assignment in**, the assistant is back in play — use it in **tutor mode** exactly as the rest of this handbook describes (have it quiz you, explain what you did, show you a cleaner way).

**Why this is a feature, not a hurdle.** This is the strongest possible version of [Principle 2 — "try it first"](00-start-here.md): the workshop assignments are where you build the raw R fluency everything else stands on, and that fluency only forms if *you* generate the code, get stuck, and work through it. Handing those to an assistant would feel efficient and teach you almost nothing (the research on this is unambiguous — see [`reference/evidence-base.md`](../reference/evidence-base.md)). Do them by hand now so the assistant makes you *faster* later instead of *dependent*.

---

## The Ed policy in brief

The program **permits** generative AI (ChatGPT, Claude, Gemini, etc.) for **certain things**, used carefully and **cited correctly**. Specifically:

**✅ Explicitly appropriate uses**
- Debugging and **understanding R code**
- **Checking statistical interpretations**
- Transcribing your audio notes/recordings to speed up data entry
- "…and more" (similar supporting uses)

**🚫 Not allowed**
- **Any AI use on the R coding workshop assignments** until they're turned in (see the section above) — you complete those solo
- **Composition or writing of any pieces of the program** (your written products)
- The earlier blanket *"uploading any data"* line is **being revised** — see §1 for how data sharing actually works in this lab

**📌 Required if you use AI at all**
- **Cite the use** (the policy points to the [Purdue AI citation guide](https://guides.lib.purdue.edu/c.php?g=1371380&p=10135074)) **and describe how you used it in the methods section** of any product.
- **Failure to properly cite AI is a policy violation**, with consequences for continued participation and performance reviews.

And the closing spirit: *you are becoming an expert and need to rely on your own logic and background knowledge.* That is exactly this handbook's [philosophy](00-start-here.md).

---

## Where the policy and this handbook strongly agree

You'll notice these are the *same idea* said two ways:

| The Ed policy says… | This handbook says… |
|---|---|
| Workshop assignments are AI-free (do them solo) | "Try it first"; a bit of struggle is where the fundamentals form ([00](00-start-here.md)) |
| "rely on your own logic and background knowledge" | You're the scientist; don't hand over the thinking ([00](00-start-here.md)) |
| AI is good for "understanding R code" | Use the explanation gate; learn the code, don't just take it ([03](03-working-with-the-assistant.md)) |
| AI is good for "checking statistical interpretations" | The assistant as a consultant you interrogate; verify against reality ([03](03-working-with-the-assistant.md)) |
| "AI output is not always correct… only as useful as the prompts" | Plan first, verify everything, catch it being wrong ([03](03-working-with-the-assistant.md)) |
| You must cite/disclose AI use | Document your AI use honestly ([04](04-documenting-ai-use.md)) |

So most of this handbook is simply *how* to live up to the program policy. The differences are below.

---

## The three places to be careful (apparent conflicts, resolved)

### 1. Sharing data with the assistant

The program's earlier blanket "no uploading any data" line is **being revised**. Per the program coordinators, the real concern was making sure undergrads complete the **workshop assignments** on their own (covered above) — not stopping a coding assistant from seeing the open data in your project. So, **outside the AI-free workshop assignments:**

- The lab works only with **open, published, or otherwise non-proprietary data**.
- **Letting the assistant see the data in your workspace is fine.** You can point it at your files, paste a few rows to debug, and let it inspect your data frames.

**How your data is protected.** The lab runs the Assistant through a **paid Claude API key**, not a free consumer chatbot. We use paid API access specifically because it comes with Anthropic's commercial terms, under which **the prompts, code, and data you send are not used to train their models.** Free consumer chat tools don't necessarily give you that.

To be clear about what this is and isn't:

- ✅ Your work **won't be absorbed into a training set.** That's the protection we're paying for and the reason workspace data sharing is OK here.
- ⚠️ It is **not** Zero Data Retention — we don't have (or need) that. Your data may still be held briefly under Anthropic's standard retention (e.g., for abuse monitoring), and this isn't a formal legal data-protection guarantee.
- 🔒 It **doesn't override the limits below.** No-training terms don't make it OK to send someone else's restricted data or human-subjects data to an outside service.

**Still off-limits — never share these with any AI tool, training terms notwithstanding:**
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

- [ ] **Workshop assignments: I do them AI-free** and turn them in *before* using the assistant on that material.
- [ ] I follow the **RMBL Ed AI Policy as my minimum**; where rules differ, I follow the stricter one.
- [ ] Outside those assignments, the assistant may see my **open / lab workspace data** — but I keep **embargoed, restricted, collaborator-owned, or human-subjects data** out of any AI tool, and **ask if unsure**.
- [ ] I use AI for **code and understanding**, **not** to write my prose.
- [ ] I keep **lightweight notes** as I work, and **formally cite + describe in methods** for any program product.
- [ ] When I'm unsure, **I ask** before I act.

> The two policies want the same thing: that you leave this summer **more capable on your own**, with an honest record of how you got there. Do the workshop assignments solo, follow the stricter rule where they differ, cite your use, keep *sensitive* data and your own writing yours, and you're aligned with both.
