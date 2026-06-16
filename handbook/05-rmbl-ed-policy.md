# 05 — How this fits the RMBL Undergraduate Program AI Policy

If you're participating in the **RMBL Undergraduate Research / Education Program**, that program has its own AI policy, and it governs you. This page explains how it relates to this lab handbook and resolves the few places where the two *seem* to pull in different directions.

> **Not in the program?** Read this anyway — the program's rules are good practice, and the lab expects them of everyone. They're also just a more formal version of what this handbook already asks.

---

## The governing rule

```
RMBL Ed Program AI Policy  =  the floor (the minimum)
This lab handbook          =  may be stricter, never looser
```

- A lab can be **more** restrictive than the program policy, but **not less**. Where this handbook looks more permissive than the program policy, **the program policy wins.**
- When two rules differ, **follow the stricter one.**
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
- **Uploading any data**

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

### 1. Do not upload your data to AI tools

**This is the one most likely to trip you up,** because a coding assistant naturally wants to look at your data — and the program flatly **prohibits uploading any data.**

What that means in practice when you work with the assistant:

- **Don't paste data rows** (or whole files) into the chat.
- **Don't ask the assistant to read your raw data files.** Agentic assistants (including Posit Assistant) can pull files from your workspace into the model's context — that counts as uploading. Keep raw data out of what the assistant can see, or describe it instead.
- **Describe the *structure* instead of showing the data:** column names and types, units, what one row means. The assistant can write correct `dplyr`/`terra` code from a schema — it doesn't need your actual values.
- **Use a tiny *synthetic* example** to illustrate a problem ("suppose I have a tibble with `plot`, `elev_m`, `melt_doy`…"), not your real dataset.
- **Public SDP data** is already published, but the policy says "any data" — so don't assume it's exempt. If you think a specific case is reasonable, **ask the coordinators first** rather than deciding for yourself.

> This does *not* cripple your workflow — it just changes *what you share*. You can still get help with every line of code; you describe the data rather than handing it over. Most of the worked examples in [03](03-working-with-the-assistant.md) already work this way (you share your *plan*, not your data).
>
> **The Knowledge Commons MCP is fine.** Connecting the assistant to the [Knowledge Commons](../reference/rmbl-data-hub.md) sends your *search queries* to RMBL's own public literature server — it does **not** upload your research data. (Still, don't type sensitive data into a search box.)

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

- [ ] I follow the **RMBL Ed AI Policy as my minimum**; the lab handbook only adds *more* care, never less.
- [ ] I **don't upload data** — I describe its structure or use synthetic examples.
- [ ] I use AI for **code and understanding**, **not** to write my prose.
- [ ] I keep **lightweight notes** as I work, and **formally cite + describe in methods** for any program product.
- [ ] When I'm unsure, **I ask** before I act.

> The two policies want the same thing: that you leave this summer **more capable on your own**, with an honest record of how you got there. Follow the stricter rule, cite your use, keep your data and your writing your own, and you're aligned with both.
