# KT Meeting Outline: State of AI 2026.2

## Slide Deck Structure

---

### Slide 1: Title Slide
- **Title:** State of AI 2026.2 — Agents for Software Development
- **Subtitle:** KT Meeting / Knowledge Transfer
- **Background:** `shinji-chair-bg.png` — the anime character slumped in a chair on top of the world, representing how dizzying and overwhelming the current agents landscape feels
- **Presenter/Date info**

---

### Slide 2: The Jargon Explosion
- **Title:** Everyone's Saying the Same Thing (Differently)
- **Content:** List of terms flying around right now:
  - Harness Engineering (OpenAI)
  - The Ralph Loop / Ralph Wiggum (Geoff Huntley)
  - Compound Engineering (Every.to)
  - Shaping Methodology (Ryan Singer / Shape Up)
  - Agentic Engineering (GLM-5 / Zhipu AI)
  - AI-Assisted Software Engineering (Allen Holub)
  - Agentic Coding, 100x Engineer, etc.
- **Key point:** No single idiomatic term yet — but the direction is the same

---

### Slide 3: The Shift
- **Title:** From Vibe Coding to Agentic Engineering
- **Content:**
  - "Vibe Coding" = toss a prompt, get something that kinda works — a toy for non-practitioners
  - 2026: Models AND harnesses are now capable for real engineering
  - GLM-5 title captured the moment: *"From Vibe Coding to Agentic Engineering"*
  - The turning point isn't model capability alone — it's **discipline + tooling**

---

### Slide 4: What "Harness Engineering" Means
- **Title:** Humans Steer. Agents Execute.
- **Source:** OpenAI — "Harness Engineering" (Feb 11, 2026)
- **Content:**
  - Built ~1M lines of code, 1,500 PRs — all agent-generated
  - Early progress was slow because the **environment** was underspecified
  - The fix was never "try harder" — it was "what capability is missing?"
  - Give the agent a map, not a 1,000-page manual
  - The harness (scaffolding around the agent) is where failures happen and where the biggest wins are

---

### Slide 5: The Ralph Loop
- **Title:** Read → Pick → Implement → Test → Commit → Clear → Repeat
- **Source:** Geoff Huntley / The Ralph Playbook
- **Content:**
  - Autonomous loop: agent works, tests, commits — fresh context each iteration
  - Fresh context = agent stays in its "smart zone"
  - File-based memory persists learnings across iterations
  - **Backpressure** (tests, lints, builds) forces self-correction
  - Human sits ON the loop, not IN it

---

### Slide 6: Compound Engineering
- **Title:** Plan → Work → Review → Compound → Repeat
- **Source:** Every.to / Kieran Klaassen
- **Content:**
  - The 4th step ("Compound") is what separates this from traditional dev
  - Each solved problem becomes a tool for future work
  - Bug fixes eliminate categories of future bugs
  - Codebase gets easier over time, not harder
  - Running 5 products with single-person engineering teams

---

### Slide 7: The Common Pattern — Engineer as Architect
- **Title:** The New Role of the Engineer
- **Content (4 pillars):**
  1. **Define architecture & constraints** — guardrails the agent works within
  2. **Specify intent clearly** — structured specs, not "make it pop"
  3. **Build feedback loops (backpressure)** — tests, lints, type checks
  4. **Observe & course-correct** — tune the environment, not the code
- **Key insight:** The engineer becomes an architect directing agents through rigorous architecture, methodology, and testing

---

### Slide 8: Closing the Loop
- **Title:** When You Close the Loop, Everything Changes
- **Content:**
  - Agent attempts → validates → self-corrects → commits — no human in each step
  - This is where gains go from incremental to transformational
  - **Unit testing is the backbone** — without tests, no backpressure; without backpressure, you're just vibe coding
  - Heavy unit testing enables agent autonomy

---

### Slide 9: Weekend Demo — ElmishPaint
- **Title:** Hands-On: ElmishPaint Weekend Project
- **Link:** github.com/rastreus/ElmishPaint
- **Content:**
  - F# with Fable + Elmish + Feliz v3
  - Built using agents (Codex)
  - Weekend project to experience the agentic workflow firsthand
  - Key takeaway: had to learn to define constraints, write specs, and let the agent work

---

### Slide 10: Where We Are Now
- **Title:** Early Days of a Paradigm Shift
- **Content:**
  - The jargon hasn't settled — and that's okay
  - The tooling is evolving weekly
  - Best practices are being discovered in real-time by practitioners
  - **This works for real engineering, today, when done correctly**
  - The gap was never model capability — it was discipline: clear requirements, sound architecture, comprehensive testing

---

### Slide 11: Key Takeaways
- **Title:** TL;DR
- **Content:**
  1. Everyone is converging on the same approach, just using different words
  2. Vibe coding was a toy → Agents are now production-capable when harnessed
  3. The engineer's role shifts to architect: define constraints, specify intent, build feedback loops
  4. Close the loop (tests + backpressure) = transformational productivity
  5. Try it yourself — the learning curve is the harness, not the model

---

### Slide 12: References & Links
- **Title:** References & Further Reading
- **Content:** Key links organized by methodology (see references.md)
  - Harness Engineering (OpenAI)
  - The Ralph Playbook
  - Compound Engineering (Every.to)
  - Shaping Methodology (Ryan Singer)
  - GLM-5 Blog
  - ElmishPaint Demo

---

## Presenter Notes Summary

- **Tone:** Casual KT meeting — conversational, not a keynote
- **Duration:** ~20–30 minutes including discussion
- **Key narrative arc:** Overwhelm (title slide) → Convergence (jargon → same direction) → The shift (vibe coding → real engineering) → How it works (methodologies) → Common pattern (architect role) → Demo → Where we are
- **Discussion prompts:** Has anyone tried agentic workflows? What's your experience with AI coding tools? What would it take to try this on a real project?
