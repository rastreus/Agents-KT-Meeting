---
marp: true
theme: default
paginate: true
backgroundColor: #1a1a2e
color: #e0e0e0
style: |
  section {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
  }
  h1 {
    color: #00d4ff;
    border-bottom: 2px solid #00d4ff;
    padding-bottom: 8px;
  }
  h2 {
    color: #7fdbff;
  }
  a {
    color: #00d4ff;
  }
  strong {
    color: #ffd700;
  }
  code {
    background: #2d2d4e;
    color: #7fdbff;
    padding: 2px 6px;
    border-radius: 4px;
  }
  section.title {
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  section.title h1 {
    border-bottom: none;
    font-size: 2.2em;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8);
  }
  section.title h2 {
    text-shadow: 1px 1px 6px rgba(0, 0, 0, 0.8);
  }
  section.takeaways {
    font-size: 0.95em;
  }
  blockquote {
    border-left: 4px solid #00d4ff;
    padding-left: 16px;
    font-style: italic;
    color: #b0b0d0;
  }
  table {
    font-size: 0.85em;
  }
  th {
    background: #2d2d4e;
    color: #00d4ff;
  }
---

<!-- _class: title -->

![bg brightness:0.4](shinji-chair-bg.png)

# State of AI 2026.2

## Agents for Software Development

KT Meeting / Knowledge Transfer

<!-- This is a casual knowledge transfer meeting, not a formal presentation. The background image represents how overwhelming the current AI agents landscape feels — like being crushed by the weight of the world. There are dozens of terms, frameworks, and methodologies all saying similar things. Our goal today is to cut through the noise and find the common patterns. -->

---

## Everyone's Saying the Same Thing (Differently)

The jargon explosion:

- **Harness Engineering** (OpenAI)
- **The Ralph Loop** / Ralph Wiggum (Geoff Huntley)
- **Compound Engineering** (Every.to)
- **Shaping Methodology** (Ryan Singer / Shape Up)
- **Agentic Engineering** (GLM-5 / Zhipu AI)
- **AI-Assisted Software Engineering** (Allen Holub)
- **Agentic Coding**, **100x Engineer**, etc.

> No single idiomatic term yet — but the **direction is the same**.

<!-- All these terms are converging on the same core idea: humans define the what and why, agents handle the how. The terminology hasn't settled because this is happening in real-time. Different teams are discovering the same patterns independently and naming them differently. Don't get hung up on which term to use — focus on the underlying principles. -->

---

## From Vibe Coding to Agentic Engineering

**"Vibe Coding"** = toss a prompt, get something that kinda works — a toy for non-practitioners

**2026**: Models AND harnesses are now capable for **real engineering**

> "From Vibe Coding to Agentic Engineering" — GLM-5

The turning point isn't model capability alone — it's **discipline + tooling**

<!-- Vibe coding was fun for prototypes and demos, but it breaks down quickly in production. You get spaghetti code, no tests, no architecture. The shift to agentic engineering is about bringing software engineering discipline to AI-assisted development. It's not just about having a smarter model — it's about how you structure the work environment around the agent. -->

---

## Humans Steer. Agents Execute.

**Source:** OpenAI — "Harness Engineering" (Feb 11, 2026)

- Built ~**1M lines of code**, **1,500 PRs** — all agent-generated
- Early progress was slow because the **environment** was underspecified
- The fix was never "try harder" — it was "what capability is missing?"
- Give the agent a **map**, not a 1,000-page manual

> The **harness** (scaffolding around the agent) is where failures happen — and where the biggest wins are

<!-- OpenAI's experience is instructive: they didn't solve their agent problems by prompting better. They solved them by building better infrastructure around the agent. The harness includes your testing setup, your architecture documentation, your CI/CD pipeline, your coding standards. When the agent fails, 90% of the time it's because the harness is incomplete, not because the model is incapable. -->

---

## The Ralph Loop

**Source:** Geoff Huntley / The Ralph Playbook

```
Read Plan → Pick Task → Implement → Test → Commit → Clear Context → ♻️
```

- Autonomous loop: agent works, tests, commits — fresh context each iteration
- **Fresh context** = agent stays in its "smart zone"
- File-based memory persists learnings across iterations
- **Backpressure** (tests, lints, builds) forces self-correction

> Human sits **ON** the loop, not **IN** it

<!-- The Ralph Loop is named after Ralph Wiggum from The Simpsons — the idea that you keep the agent in its "smart zone" by giving it fresh context each time. Old context accumulates errors and distractions. By clearing context after each commit and re-reading the plan, the agent stays focused. The human's job is to build the loop and monitor from above, not micromanage each step. -->

---

## Compound Engineering

**Source:** Every.to / Kieran Klaassen

**Plan → Work → Review → Compound → Repeat**

The 4th step ("**Compound**") is what separates this from traditional dev:

- Each solved problem becomes a **tool for future work**
- Bug fixes eliminate **categories** of future bugs
- Codebase gets **easier** over time, not harder
- Running **5 products** with single-person engineering teams

<!-- Traditional development accumulates technical debt. Compound engineering accumulates assets. When an agent fixes a bug, it should also add a test or a lint rule that prevents that class of bugs from recurring. When it builds a feature, it should create reusable components. The codebase should become more maintainable over time, not less. This is the opposite of the "move fast and break things" mentality. -->

---

## The New Role of the Engineer

**The 4 pillars of the architect role:**

1. **Define architecture & constraints** — guardrails the agent works within
2. **Specify intent clearly** — structured specs, not "make it pop"
3. **Build feedback loops (backpressure)** — tests, lints, type checks
4. **Observe & course-correct** — tune the environment, not the code

> The engineer becomes an **architect** directing agents through rigorous architecture, methodology, and testing

<!-- This is the fundamental shift. You're not writing code line by line anymore. You're designing the system that writes code. Your value is in architectural decisions, constraint definition, and quality assurance. The agent is the implementer; you are the thinker. This requires a different skill set — more systems thinking, less syntax memorization. -->

---

## When You Close the Loop, Everything Changes

- Agent attempts → validates → self-corrects → commits — **no human in each step**
- This is where gains go from **incremental** to **transformational**
- **Unit testing is the backbone** — without tests, no backpressure; without backpressure, you're just vibe coding

> Heavy unit testing enables **agent autonomy**

<!-- The magic happens when the loop is truly closed. If the agent has to ask you "is this right?" after every change, you're still the bottleneck. But if tests and linters can validate the work, the agent can iterate autonomously. You might check in every hour instead of every minute. This is only possible with comprehensive test coverage — it's the foundation everything else builds on. -->

---

## Hands-On: ElmishPaint Weekend Project

**Demo:** [github.com/rastreus/ElmishPaint](https://github.com/rastreus/ElmishPaint)

**Tech stack:**
- **F#** with **Fable** + **Elmish** + **Feliz v3**

**Experience:**
- Built using agents (**Codex**)
- Weekend project to experience the agentic workflow firsthand
- Key takeaway: had to learn to **define constraints**, **write specs**, and **let the agent work**

<!-- This is a real project I built over a weekend using agentic workflows. The tech stack is F# compiled to JavaScript via Fable, using the Elmish architecture (Model-View-Update). I used Codex as the agent. The learning curve wasn't the model — it was learning to write good specs and stay out of the way. Once I got the harness right, the agent was surprisingly productive. -->

---

## Early Days of a Paradigm Shift

- The jargon hasn't settled — and that's **okay**
- The tooling is evolving **weekly**
- Best practices are being **discovered in real-time** by practitioners
- **This works for real engineering, today, when done correctly**

> The gap was never model capability — it was **discipline**: clear requirements, sound architecture, comprehensive testing

<!-- We're in the early days. Don't wait for the "standard" approach to emerge — you can start now. The practitioners are figuring this out as they go. The key insight is that this isn't about waiting for better models; current models are capable. What's missing is engineering discipline: treating AI-assisted development like real software engineering, not a magic trick. -->

---

<!-- _class: takeaways -->

## TL;DR — Key Takeaways

1. Everyone is converging on the same approach, just using **different words**
2. **Vibe coding** was a toy → Agents are now **production-capable** when harnessed
3. The engineer's role shifts to **architect**: define constraints, specify intent, build feedback loops
4. **Close the loop** (tests + backpressure) = **transformational** productivity
5. **Try it yourself** — the learning curve is the harness, not the model

<!-- Quick recap: Don't get distracted by terminology. The patterns are consistent across frameworks. Start with one project, build your harness, and iterate. The hardest part is learning to think like an architect instead of a coder. -->

---

## References & Further Reading

**Harness Engineering**
- [OpenAI: Harness engineering](https://openai.com/index/harness-engineering/)

**The Ralph Playbook**
- [The Ralph Playbook](https://claytonfarr.github.io/ralph-playbook/)
- [11 Tips For AI Coding With Ralph Wiggum](https://www.aihero.dev/tips-for-ai-coding-with-ralph-wiggum)
- [GitHub: snarktank/ralph](https://github.com/snarktank/ralph)

**Compound Engineering**
- [Every.to: Compound Engineering](https://every.to/guides/compound-engineering)

**Agentic Engineering**
- [GLM-5: From Vibe Coding to Agentic Engineering](https://z.ai/blog/glm-5)

**Demo Project**
- [ElmishPaint on GitHub](https://github.com/rastreus/ElmishPaint)

<!-- These are the primary sources for the methodologies discussed. The OpenAI and GLM-5 blog posts are particularly good for understanding the current state of agentic development. The Ralph Playbook is practical and actionable. -->
