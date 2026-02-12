# State of AI 2026.2: Agents for Software Development

A KT (Knowledge Transfer) meeting covering the current landscape of AI agents for software engineering — where the industry is heading, the emerging methodologies, and what it means for practitioners.

## The Thesis

The software engineering world is converging on a single direction despite a flood of competing terminology: **harness engineering**, **compound engineering**, **the Ralph loop**, **agentic engineering**, **AI-assisted software engineering**, and more. No single idiomatic term has been coined yet, but everyone is saying the same thing:

> The era of vibe coding is over. Agents are now production-capable when harnessed correctly. The engineer becomes an architect — directing agents through rigorous architecture, methodology, and testing.

## Contents

| File | Description |
|------|-------------|
| [`state-of-ai-2026.2-refined-thoughts.md`](state-of-ai-2026.2-refined-thoughts.md) | Refined writeup of the thesis, synthesizing insights from across the references |
| [`meeting-outline.md`](meeting-outline.md) | Slide-by-slide outline for a ~20–30 minute casual KT meeting |
| [`marp-agent-prompt.md`](marp-agent-prompt.md) | A prompt to hand to an AI agent to generate a [Marp](https://marp.app/) slideshow from the outline |
| [`references.md`](references.md) | Curated list of source URLs and references |
| [`shinji-chair-bg.png`](shinji-chair-bg.png) | Title slide background — because the current agents landscape is overwhelming |

## Key References

- **Harness Engineering** — [OpenAI](https://openai.com/index/harness-engineering/) (Feb 11, 2026): *"Humans steer. Agents execute."*
- **The Ralph Loop** — [The Ralph Playbook](https://claytonfarr.github.io/ralph-playbook/): Autonomous coding loops with file-based state and backpressure
- **Compound Engineering** — [Every.to](https://every.to/guides/compound-engineering): Plan → Work → Review → Compound → Repeat
- **Shaping Methodology** — [Ryan Singer](https://x.com/rjs/status/2020184079350563263): Shape Up adapted for LLMs via [shaping-skills](https://github.com/rjs/shaping-skills)
- **Agentic Engineering** — [GLM-5](https://z.ai/blog/glm-5): *"From Vibe Coding to Agentic Engineering"*

## Weekend Demo

As part of catching up with the agentic workflow firsthand, I built [**ElmishPaint**](https://github.com/rastreus/ElmishPaint) — a weekend project in F# with Fable + Elmish + Feliz v3, built using agents (Codex).

## Building the Slideshow

The `marp-agent-prompt.md` file contains a complete prompt for an AI agent to generate a Marp presentation. To build it manually after generation:

```bash
npm install -g @marp-team/marp-cli

# HTML
marp state-of-ai-2026.2.md --html --allow-local-files -o state-of-ai-2026.2.html

# PDF
marp state-of-ai-2026.2.md --html --allow-local-files --pdf -o state-of-ai-2026.2.pdf

# PowerPoint
marp state-of-ai-2026.2.md --html --allow-local-files --pptx -o state-of-ai-2026.2.pptx
```

## This Meeting Presentation

1. I manually created the list of references in the [`references.md`](./references.md) file.
2. I created a quick, initial draft of my thoughts and prompted Claude Opus 4.6 Extended ([`initial-draft.md`](./initial-draft.md)) for files.
3. I gave the [`marp-agent-prompt.md`](./marp-agent-prompt.md) to Kimi K2.5 using OpenCode ([`opencode-Kimi-K2.5-session-transcript.md`](./opencode-Kimi-K2.5-session-transcript.md)).

## License

MIT (see [LICENSE](./LICENSE)).
