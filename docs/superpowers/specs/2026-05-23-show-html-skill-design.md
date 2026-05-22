# show-html Skill Package Design

## Goal

Create a cross-platform agent skill (SKILL.md format) that teaches agents to generate high-quality, self-contained HTML for various use cases. The skill uses the "unreasonable effectiveness of HTML" examples as a reference library.

## Architecture

```
show-html/
├── SKILL.md                    # Main skill file (entry point)
├── examples/                   # Full HTML examples cloned from ThariqS/html-effectiveness
│   ├── 01-code-approaches.html
│   ├── 02-visual-designs.html
│   ├── ...
│   └── 20-prompt-tuner.html
└── README.md
```

## SKILL.md Structure

### 1. Metadata

- Name: `show-html`
- Description: Generate self-contained HTML for agent output — code reviews, reports, slide decks, interactive editors, and more
- Trigger: keyword-based auto-detection + explicit `/show-html` invocation

### 2. Usage Guide

- When to generate HTML (vs markdown/plain text)
- How to select the right scenario
- How to read examples for detail when needed

### 3. Use Case Index (20 entries)

Each entry contains:
- **Scenario name** + when to use it
- **Core design pattern** — layout structure, key CSS techniques
- **Interaction model** (if applicable)
- **File reference** — path to `examples/XX-name.html`

### 4. Universal HTML Generation Principles

Extracted common patterns across all 20 examples:
- Zero dependencies, fully self-contained
- Inline CSS with CSS custom properties for theming
- Responsive design
- Clean typography (serif/sans/mono stack)
- Purposeful color palettes
- Progressive interaction (works without JS, enhanced with)

## Trigger Keywords

| Category | Keywords |
|---|---|
| Exploration | compare approaches, explore designs, visual alternatives |
| Code | code review, PR review, understand code, design system, component variants |
| Prototyping | animation prototype, interaction prototype, interactive demo |
| Communication | slide deck, presentation, status report, incident report, PR writeup |
| Diagrams | flowchart, feature explainer, concept explainer, implementation plan |
| Editors | triage board, kanban, feature flags, prompt tuner, interactive editor |

## Workflow

### Auto-trigger

When a user task matches a scenario keyword, the agent:
1. Identifies the matching use case
2. Reads the summary in SKILL.md
3. Optionally reads the full example from `examples/` for detail
4. Generates HTML following the design pattern, adapted to the user's actual data

### Explicit invocation

User says `/show-html`, `/show-html:code-review`, or "generate HTML for X". Agent follows the same flow.

### Free creation

Agent understands the design patterns and generates original HTML based on user needs — not rigidly templated.

## Source

Examples cloned from [ThariqS/html-effectiveness](https://github.com/ThariqS/html-effectiveness) (Apache 2.0 license, 352 stars).
