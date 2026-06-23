# Slide outline — "AI as a Partner, Not a Replacement"

> **Rendered slides:** [`philosophy-talk.html`](philosophy-talk.html) (self-contained; open in a browser). This outline is the source/script behind them.

A ~15-minute, high-level talk on the *philosophy* behind the lab AI handbook. No step-by-step — the hands-on portion covers mechanics. ~13 slides, ~1–1.5 min each.

**Audience:** mixed (first-summer undergrads → grad students). Keep jargon low; let the pull-quotes do the work.

---

### 1 · Title (~30s)
**AI as a Partner, Not a Replacement**
*The thinking behind how we use AI in this lab*
- Spatial Ecology Lab · summer 2026
- *Say:* "This is the 'why.' The how comes in the hands-on part."

### 2 · The opportunity — and the trap (~1 min)
- AI assistants can write code, explain errors, answer instantly. Genuinely powerful.
- But there's a subtle trap:
> **It can make your *work* look better while leaving *you* no better.**
- *Say:* a clean analysis you can't reproduce or defend isn't a win.

### 3 · The deal (~1 min)
> **Use the assistant to learn faster, never to think less.**
- It's a **tutor, not a ghostwriter.**
- We're not anti-AI. We're anti-*cognitive-surrender*.

### 4 · What's actually at stake (~1 min)
- The real product of your summer isn't the figures or the code.
- It's **your judgment as a scientist** — what you can do and understand on your own.
- AI is worth using only if it grows that, not replaces it.

### 5 · The evidence: performance ≠ learning (~1.5 min)  *(credibility slide)*
- In a randomized study (~1,000 students): **+48%** on tasks *with* AI…
- …but **−17%** vs. peers once the AI was taken away. *(Bastani et al., PNAS 2025)*
- The pattern repeats across writing, math, and coding studies.
- *Takeaway:* feeling productive ≠ getting better. Researchers call the shortcut **"metacognitive laziness"** — letting the AI do the thinking that builds expertise.

### 6 · The failure mode: cognitive surrender (~1.5 min)
When you let the AI hand you answers, three things quietly go wrong:
- **You feel like you understand more than you do** (watching ≠ doing).
- **You skip the struggle** — which is exactly where learning happens.
- **You can't tell when it's wrong** — and it's confidently wrong often.

### 7 · Three principles (~1.5 min)
1. **You are the scientist. The AI is the assistant.** Never let it own the thinking.
2. **Try it first.** A few minutes of being stuck is the point, not a failure.
3. **If you can't explain it, you don't ship it.**

### 8 · The one rule (~1 min)
> **If you can't explain it, you don't ship it.**
- Can you explain what it does, and why it's right, to a labmate — *with the AI closed*?
- This is the single best-evidenced habit: explaining code before accepting it roughly **halved** later failure when people worked on their own.

### 9 · Consultant, not contractor (~1 min)
- *How* you use AI matters more than *whether* you do.
- **Consultant:** you interrogate it — "why this way?", "what are the trade-offs?", read every line.
- **Contractor:** you hand off the whole job and paste the result unread → the behavior that predicts *not* learning.

### 10 · We meet you where you are (~1 min)
- **Tutor mode** — learning the area: the assistant coaches, asks before answering.
- **Teammate mode** — you already own it: more direct; spec-first for big builds.
- Guardrails loosen as your skill grows — honestly, and with your mentor.

### 11 · Doing it honestly + safely (~1 min)
- **Be honest about AI use** — a light, routine note. Using it is never the problem; hiding it is.
- **Your data is protected** — we run on a paid Claude API key; your data isn't used to train models.
- **Program undergrads:** R workshop assignments are **AI-free** — do them solo first; that's where the fundamentals form.

### 12 · A quick word on version control (~1.5 min)  *(concept, before the hands-on)*
> **Git is a time machine and a lab notebook for your work.**
- A **commit** = a labeled snapshot you can always return to.
- A **repository** = your project *plus its whole history*.
- **GitHub** = the cloud copy: backup, sharing, and collaboration.
- Why bother: you *will* break things (go back); **"works on my machine" isn't science** (reproducibility); it's how research code is shared; and it's an honest record of what changed.
- *Say:* "Don't memorize commands — we'll do those next. Just hold the mental model: snapshots you can return to, backed up and shareable."

### 13 · The test — and over to the hands-on (~1 min)
> **Can you do more, and understand more, than you could in May — *without* the AI in front of you?**
- If yes, you used it right. **That's the whole game.**
- *Transition:* "Now let's open Positron and try it."

---

### Delivery notes
- **One idea per slide.** Put the **bold pull-quotes** big; say the rest.
- With the Git slide this runs ~16 min. To hold ~15, merge **5 + 6** or trim **10**. Don't cut **3, 7, 8, 13** — they're the spine.
- Tone: encouraging, not scolding. The message is "this makes you better," not "don't cheat."
- Optional opener: ask for a show of hands — "who's used ChatGPT/Claude for code?" — then "great, this is about using it *well*."
