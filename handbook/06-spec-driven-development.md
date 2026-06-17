# 06 — Spec-Driven Development (for bigger projects)

> **Who this is for.** Senior technicians, graduate students, and anyone tackling a genuinely *complex*, multi-step build — a reproducible pipeline, an analysis package, a multi-stage modeling workflow. If you're in your first weeks and still building fundamentals, skip this for now: at that stage you learn most by doing the small pieces by hand ([00](00-start-here.md), [03](03-working-with-the-assistant.md)). Specs manage **complexity**, not learning — come back when complexity is your bottleneck.

When a project gets big, the failure mode isn't "I don't understand this line." It's **drift**: you prompt the assistant ad hoc, it makes a hundred local decisions you didn't quite track, and three days in you have a sprawl of code that sort-of works and that nobody — including you — fully holds in their head. That's cognitive surrender at the *project* scale, and it's exactly what spec-driven development prevents.

---

## The idea in one line

> **Write the specification first. Then have the assistant plan, break down, and implement *against it* — with you reviewing at each step.**

A spec is a structured, version-controlled document that states what you're building, why, and how you'll know it's right — *before* any code gets written. It becomes the **source of truth** that you and the assistant both refer back to. This replaces ad-hoc prompting ("vibe coding") with a disciplined loop.

It's the same move you already make in [Pattern 2 — "plan in your own words, then ask"](03-working-with-the-assistant.md) — just made **durable and explicit**, because the project is too big to fit in one plan or one chat.

---

## Why it fits the way this lab works

Spec-driven development is the friction-vs-thinking line ([02](02-writing-agents-md.md)) drawn at project scale:

| You own (the thinking) | The assistant owns (the implementation) |
|---|---|
| What to build and **why** | Translating tasks into code |
| The requirements and **acceptance criteria** | Boilerplate, wiring, syntax |
| The architecture decisions and trade-offs | First drafts of each task |
| Judging whether each piece is correct | Refactors *you've* approved |

Because every change traces back to a requirement *you wrote*, you stay the architect. The spec is also a **reviewable artifact**: your supervisor can review the spec *before* you build (catching a wrong turn when it's cheap), it lives in Git like everything else, and it makes your work reproducible — the spec explains the *intent* that the code alone never quite captures.

---

## The loop: Specify → Plan → Tasks → Implement

This is the workflow popularized by tools like [GitHub Spec Kit](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/), but you can do every step by hand with a `SPEC.md` file and your assistant.

### 1. Specify — *what and why* (you write this)
State the goal, the requirements, what's in and out of scope, and — critically — the **acceptance criteria** (how you'll know each requirement is met). Stay at the level of *intent*, not implementation. This is your thinking; don't outsource it.

### 2. Plan — *how* (you draft, assistant helps)
Turn the spec into a technical approach: the main phases, the key functions/data structures, dependencies, and risks. Ask the assistant to critique your plan ("what's missing? what will be hard?") before you commit to it — consultant, not contractor.

### 3. Tasks — *break it down* (assistant proposes, you approve)
Decompose the plan into small, individually testable chunks — each one something you can implement and verify in isolation, almost like test-driven development for the agent. You review and adjust the task list before any code is written.

### 4. Implement — *one task at a time* (assistant drafts, you verify)
The assistant implements tasks one by one. Instead of reviewing thousand-line dumps, you review **focused changes** that each satisfy a specific requirement. The [explanation gate](03-working-with-the-assistant.md) still applies to every task, and you check each against its acceptance criterion before moving on.

> **Worked example.** Goal: *a reproducible pipeline that produces 30 m seasonal bloom-timing forecasts from SDP climate layers and the phenology model.*
> - **Specify:** inputs (which SDP products, the SNOTEL snowpack covariate, the `o`/`w`/`h` model), outputs (a COG per species per date), acceptance criteria ("forecasts validate against Flower Blitz counts within X"), out of scope (the web viewer).
> - **Plan:** four phases — fetch/align covariates → fit/load model → predict over the grid → validate. Note the CRS handling and the memory risk of the full-domain raster.
> - **Tasks:** "write `align_covariates()` with a unit test on a 3-tile subset," "implement tiled prediction with `terra`," etc.
> - **Implement:** build and verify each task; the spec keeps phase 3 honest about what phase 1 promised.

---

## When is a spec worth it?

Not every task needs one. A useful heuristic ([Addy Osmani](https://addyosmani.com/blog/good-spec/)):

> **If you'd be annoyed that the assistant interpreted the requirements differently than you meant — write the spec. If you could fix the output in a quick follow-up prompt — just prompt.**

| Just prompt | Write a spec |
|---|---|
| A single function, a plot, a debug | A multi-step pipeline or package |
| You'll know the right answer when you see it | "Right" depends on requirements you need to pin down |
| One sitting, one chat | Spans days, multiple sessions, maybe multiple people |
| Throwaway exploration | Something that has to be reproducible and maintained |

---

## The spec is a living document

The point of spec-driven work is that **changing course is cheap**: when requirements change (they will), you update the spec, regenerate the plan and tasks, and re-implement the affected parts — rather than untangling code by hand. Keep `SPEC.md` in the repo, commit changes to it, and treat it as the current truth. A spec that's gone stale relative to the code is worse than none.

---

## Tooling

- **By hand (start here):** copy [`templates/SPEC.md`](../templates/SPEC.md) into your project, fill it in, and work the loop with the Posit Assistant. No new tools required.
- **GitHub Spec Kit:** an open-source CLI (`specify init`) that scaffolds the spec/plan/tasks structure and adds `/speckit.*` commands. It supports ~30 coding agents (GitHub Copilot, Claude Code, Gemini CLI, and others). If your assistant isn't one it drives directly, you can still use Spec Kit's structure with any agent, or just use the `SPEC.md` template. See the [GitHub blog intro](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/) and [Microsoft's walkthrough](https://developer.microsoft.com/blog/spec-driven-development-spec-kit).

Tools change fast; the *practice* — spec first, review at each phase — is what matters and is tool-agnostic.

---

## How this connects to the rest of the handbook

- **`PROJECT-BRIEF.md` vs `SPEC.md`:** the [brief](../templates/PROJECT-BRIEF.md) orients your *whole project* (question, data, what's plumbing vs. thinking); a spec designs *one substantial build* within it. A project may have one brief and several specs over the summer.
- **AGENTS.md:** spec-driven work is the natural mode once you're in [teammate mode](../templates/AGENTS.starter.md). Your `AGENTS.md` can tell the assistant to "work spec-first: propose tasks from `SPEC.md` and implement one at a time, pausing for review."
- **Explanation gate & verification:** unchanged, applied per task. The spec actually makes verification *easier* — acceptance criteria are your reality checks, written in advance.
- **AI-use notes:** a spec-driven build is easy to document honestly — the spec *is* much of the record of how you and the assistant divided the work.

---

## Pitfalls

- **Over-speccing.** Don't write a five-page spec for a 20-line function. Use the heuristic above.
- **The spec as an understanding-dodge.** A spec is *not* a license to accept code you can't explain because "it meets the criteria." You still own every task. If anything, a bigger project means more to understand, not less.
- **Spec drift.** If you change the code but not the spec, the spec becomes a lie. Update it, or delete it — don't let it rot.
- **Front-loading too much.** You don't need a perfect spec before starting. Spec the next coherent chunk well; let the document evolve as you learn.

---

### Further reading
- [Spec-driven development with AI — GitHub blog](https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/)
- [Diving into Spec-Driven Development — Microsoft for Developers](https://developer.microsoft.com/blog/spec-driven-development-spec-kit)
- [How to write a good spec for AI agents — Addy Osmani](https://addyosmani.com/blog/good-spec/)
- [Spec-Driven Development with Coding Agents — DeepLearning.AI (short course)](https://www.deeplearning.ai/courses/spec-driven-development-with-coding-agents)
