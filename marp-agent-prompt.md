# Agent Prompt: Create Marp Slideshow Presentation

## Task

Create a Marp Markdown slideshow presentation from the provided meeting outline (`meeting-outline.md`). The output should be a single `.md` file with Marp frontmatter that can be rendered to HTML, PDF, or PPTX using the Marp CLI.

## Setup

Install Marp CLI if not already available:

```bash
npm install -g @marp-team/marp-cli
```

## Input Files

- `meeting-outline.md` — The slide-by-slide outline with content for each slide
- `shinji-chair-bg.png` — Background image for the title slide (anime character slumped in a chair on top of the world — represents the overwhelming agents landscape)

## Requirements

### Marp Frontmatter

Use the following Marp frontmatter at the top of the file:

```yaml
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
```

### Slide Construction Rules

1. **Title Slide (Slide 1):**
   - Use `<!-- _class: title -->` directive
   - Use `shinji-chair-bg.png` as the background image: `![bg](shinji-chair-bg.png)` with an overlay/dim effect so text is readable. Use `![bg brightness:0.4](shinji-chair-bg.png)` to dim the background.
   - Title: "State of AI 2026.2"
   - Subtitle: "Agents for Software Development"
   - Tertiary line: "KT Meeting / Knowledge Transfer"

2. **Slide Separators:** Use `---` between each slide (standard Marp convention).

3. **Content Density:** Keep each slide focused. Maximum 5-7 bullet points per slide. Use speaker notes (`<!-- speaker notes here -->`) for additional context the presenter can reference.

4. **Emphasis:** Use `**bold**` for key terms and concepts that should stand out (they will render gold per the theme).

5. **Quotes/Callouts:** Use blockquotes (`>`) for key phrases from the references, such as:
   - > "Humans steer. Agents execute." — OpenAI
   - > "From Vibe Coding to Agentic Engineering" — GLM-5

6. **Slide 5 (Ralph Loop):** Consider using a simple flow representation:
   ```
   Read Plan → Pick Task → Implement → Test → Commit → Clear Context → ♻️
   ```

7. **Slide 7 (Engineer as Architect):** Use a numbered list for the 4 pillars. Keep it clean.

8. **Slide 9 (Demo):** Include the GitHub link prominently. Mention the tech stack (F#, Fable, Elmish, Feliz v3).

9. **Slide 12 (References):** List the key links. Use markdown link syntax. Group by methodology name.

10. **Speaker Notes:** Add `<!-- -->` HTML comments as speaker notes on each slide with talking points from the outline's "Presenter Notes" section. These won't render visually but are available in presenter mode.

### Tone and Style

- **Casual and conversational** — this is a KT meeting, not a keynote
- **Dark theme** — the provided CSS uses a dark navy background with cyan/gold accents
- The overall vibe should feel like a tech-savvy internal meeting, not a sales pitch
- Use occasional humor where appropriate (the title slide background is intentionally comedic — a character overwhelmed by the weight of the world, much like an engineer trying to keep up with the AI landscape)

### Output

Generate a single file: `state-of-ai-2026.2.md`

Place `shinji-chair-bg.png` in the same directory as the markdown file.

### Build Commands

After creating the file, render it:

```bash
# HTML (for browser presentation)
marp state-of-ai-2026.2.md --html --allow-local-files -o state-of-ai-2026.2.html

# PDF
marp state-of-ai-2026.2.md --html --allow-local-files --pdf -o state-of-ai-2026.2.pdf

# PowerPoint
marp state-of-ai-2026.2.md --html --allow-local-files --pptx -o state-of-ai-2026.2.pptx
```

### Validation

After generating, verify:
1. The Marp file renders without errors
2. The title slide background image displays correctly
3. All 12 slides are present and properly separated
4. Pagination is visible on all slides except the title
5. Links are clickable in HTML output
6. Speaker notes are present (check with `marp --preview`)
