# The evidence base

Everything in this handbook is opinionated, but it isn't made up. This page is the short, cited version of *why* we work the way we do, so you can check our reasoning and read the sources yourself. If you're a grad student, read the primary sources — they're good.

> **How to read this:** each finding is followed by what it means for *your* daily work. Confidence labels reflect how settled the evidence is. We've deliberately excluded a few widely-repeated claims that didn't survive scrutiny (see the bottom).

---

## 1. AI makes your *output* better and can leave your *learning* flat

**Finding (high confidence).** Across randomized and controlled experiments — in writing, K–12 math, and intro programming — using a generative AI assistant reliably boosts the quality of what you produce *right now*, but produces little or no durable learning, and **unrestricted use can actively hurt your ability to perform once the AI is taken away.**

- Bastani et al. 2025 (*PNAS*), RCT with ~1,000 students: students with GPT access scored **+48%** during practice — but when the AI was removed, they did **17% worse** than students who never had it. ([pnas.org](https://www.pnas.org/doi/10.1073/pnas.2422633122))
- Yan et al. 2025 (*Nature Reviews Psychology*): generative AI "can boost learners' performance on tasks" but "risks undermining the cognitive and metacognitive processes that are essential for durable learning"; gains "diminished once the generative AI assistance was removed." ([arxiv](https://arxiv.org/html/2605.13731v1))
- Kazemitabaar et al. 2023 (*CHI*), n=69: AI access raised code-authoring scores 1.8× during training; the one-week retention advantage was **not** statistically significant. ([dl.acm.org](https://dl.acm.org/doi/10.1145/3544548.3580919))

**What this means for you.** A polished result is not evidence that you learned anything. The only test that counts is whether you can do it again *without* the AI. That's why our work patterns and the explain-back rule exist.

---

## 2. The mechanism is "metacognitive laziness"

**Finding (high confidence).** Heavy, unscaffolded AI use leads learners to delegate the very things that build expertise — planning, evaluating, reasoning, monitoring their own understanding. Researchers call this **metacognitive laziness** or **cognitive offloading**.

- Fan et al. 2025 (*BJET*), RCT n=117: the ChatGPT group got the biggest improvement in essay *scores* but showed **no** advantage in actual knowledge gain or transfer versus other groups — they had bypassed the evaluation and reflection the other groups did. The authors warn AI "may promote learners' dependence on technology and potentially trigger metacognitive laziness." ([bera-journals](https://bera-journals.onlinelibrary.wiley.com/doi/abs/10.1111/bjet.13544))
- Students relying on AI for research reported **lower** cognitive load but produced **weaker** reasoning than those using more effortful methods.

**What this means for you.** "This felt easy" is a warning sign, not a success metric. Feeling lower effort often means you skipped the part where learning happens.

---

## 3. The single most effective fix: explain it before you accept it

**Finding (high confidence in direction; effect size from a small recent study).** A scaffold that forces the learner to give a real, causal explanation of AI-generated code *before* accepting it dramatically improves later independent performance.

- Sankaranarayanan 2026 (L@S, N=78): on a 30-minute task with the AI switched off, students who'd used AI without any guardrail had a **77% failure rate**; students who'd had to explain AI code before merging it failed only **39%**. Repair success was 61.5% vs 23.1%. The "Explanation Gate" required a *relational* (cause-and-effect) explanation, not just a paraphrase. ([arxiv](https://arxiv.org/pdf/2602.20206))

**What this means for you.** This is the origin of our number-one rule: **if you can't explain it, you don't ship it.** It's not a moral stance — it's the intervention with the best evidence behind it.

---

## 4. *How* you engage matters more than *whether* you use AI: be a consultant-hirer, not a contractor-hirer

**Finding (high confidence in direction; small samples).** The students who learn treat the AI as a **consultant** they interrogate ("why did you do it this way?", "what are the trade-offs?") and adopt its code **granularly**, line by line. The students who don't learn treat it as a **contractor** they hand the whole job to, and paste its output wholesale.

- Shihab et al. 2025 (*ICER*): granular adopters outperformed wholesale adopters; the one statistically significant behavioral difference was that low performers spent more time **pasting AI code directly** (p<0.001). The tool shifted them from *read→understand→implement* to *prompt→skim→paste* — "cognitively disengaged, accepting suggestions without reflecting." ([arxiv](https://arxiv.org/pdf/2506.10051))
- Sankaranarayanan 2026: successful users "self-scaffold, treating the AI as a consultant rather than a contractor," using interrogative prompts.

**What this means for you.** Prompt with questions, not just commands. Read every line. Pasting code you didn't read is the exact behavior that correlates with not learning.

---

## 5. Pair AI with study strategies that actually work

**Finding (high confidence).** AI should *support* deep-processing strategies — explaining in your own words, comparing approaches, self-quizzing/retrieval — not replace them. These strategies have decades of evidence; passive ones (rereading, highlighting) don't.

- Stanford CTL/AIMES: "what's important is that you're using effective strategies to facilitate your learning and not delegating your learning process to an AI tool." ([stanford](https://ctl.stanford.edu/aimes/ai-learning-guide-students))
- Dunlosky et al. 2013: practice testing and self-explanation = high utility; rereading and highlighting = low. Replicated across 242 studies by Hattie & Donoghue 2021.

**What this means for you.** Use the AI to *quiz you*, to *check your explanation*, to *compare two approaches* — these turn it into a study tool instead of an answer vending machine. See [`03-working-with-the-assistant.md`](../handbook/03-working-with-the-assistant.md).

---

## 6. Guardrails should loosen as your expertise grows (the expertise-reversal effect)

**Finding (medium confidence; theory-consistent, indirectly shown for AI coding).** Scaffolds that help a novice can become unnecessary friction for an expert. In Kazemitabaar 2023, learners with **more** prior knowledge retained significantly more from AI access — a signal that the right amount of guardrail depends on where you are.

**What this means for you.** A first-year undergrad and a third-year grad student shouldn't use the assistant identically. Our `AGENTS.md` templates come in a stricter "tutor" mode (you're learning the skill) and a lighter mode (you've demonstrated you own it). Move between them honestly, with your supervisor.

---

## 7. The riskiest AI use happens exactly when struggle matters most

**Finding (medium confidence; small qualitative study).** Heavy AI use clusters around procrastination and time pressure ("exam week overload"), while light, healthy use clusters around **verification** ("I wanted to check my work"). ([Frontiers in Education 2025](https://www.frontiersin.org/journals/education/articles/10.3389/feduc.2025.1654805/full))

**What this means for you.** When you're behind and stressed is precisely when offloading is most tempting and most harmful. Manage time so you're not forced into it; the "attempt-first" rule protects you here.

---

## 8. Disclosure has to be safe and routine, or people just won't do it

**Finding (high confidence).** Mandates alone fail. At King's Business School, **74% of students didn't declare AI use** even though declaring permitted use carried *no penalty*. The drivers were fear of repercussions, ambiguous guidelines, and inconsistent enforcement — "not simple dishonesty." ([Taylor & Francis 2024](https://www.tandfonline.com/doi/full/10.1080/02602938.2024.2415654))

**What this means for you (and us).** This is why our AI-use notes are **penalty-free, lightweight, and routine**. Disclosing that the AI wrote a function is never something you get in trouble for — *not* disclosing is the only problem. See [`04-documenting-ai-use.md`](../handbook/04-documenting-ai-use.md).

---

## 9. A sane default policy

**Finding (high confidence — a widely adopted norm).** Stanford's guidance: treat AI consultation "analogously to assistance from another person"; using it "to substantially complete an assignment... is not permitted"; default to "assume AI use is not allowed unless otherwise indicated," and disclose any use. ([stanford](https://ctl.stanford.edu/aimes/ai-learning-guide-students))

**What this means for you.** Our lab's version: **the AI is a smart labmate, not a ghostwriter.** Anything it helped with is fine and normal — as long as you understand it, can defend it, and noted the help.

---

## Claims we deliberately left out

Three plausible-sounding claims were checked and **rejected** in verification, so they're *not* in this handbook:

- That scaffolded and unscaffolded AI groups produce identical immediate output (we don't claim guardrails are free of any cost to short-term output).
- A specific "56% of students used AI for 76–100% of an assignment" statistic.
- A specific "75% produced substantive reflections" claim about a structured tutoring system.

We mention this on purpose: **checking sources and discarding the ones that don't hold up is the same skill we're asking you to apply to AI output.** Methodology matters, including ours.

---

### Open questions (good summer-project fodder, honestly)

- Do these findings replicate for **R / data-science / remote-sensing** workflows specifically? Most were collected on Python/JS web tasks.
- What's the right schedule for loosening guardrails across the undergrad→grad gradient?
- How do you cheaply measure *durable* learning (AI-off) in a research lab, not just finished output?
