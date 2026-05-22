# show-html

A cross-platform agent skill that teaches AI agents to generate self-contained, zero-dependency HTML pages for rich output — code reviews, slide decks, status reports, interactive editors, and more.

## Inspired by

This project is inspired by [ThariqS/html-effectiveness](https://github.com/ThariqS/html-effectiveness) — a gallery of standalone HTML examples demonstrating "the unreasonable effectiveness of HTML" as a flexible agent output format. The first 20 example HTML files in this skill's `assets/` are sourced from that repository under the Apache 2.0 license. Examples 21-24 are original additions covering dashboards, interactive tables, system architecture, and gantt charts.

## What's Included

- **SKILL.md** — The skill definition with design system, use case index, and generation workflow
- **24 HTML examples** — Self-contained reference pages covering:
  - Code review, understanding, design systems, component variants
  - Animation & interaction prototypes
  - Slide decks, status reports, incident reports, PR writeups
  - Flowcharts, feature/concept explainers, implementation plans
  - Interactive editors: triage board, feature flags, prompt tuner
  - Dashboards, interactive data tables, system architecture diagrams, gantt charts

## Usage

Install the skill for your agent, then either:
- Explicitly invoke `/show-html` or `/show-html:code-review` etc.
- Let the agent auto-trigger based on task context (e.g., "review this PR", "make a status report")

## License

- Skill packaging, documentation & original examples (21-24): MIT
- Examples 01-20: [Apache License 2.0](https://github.com/ThariqS/html-effectiveness/blob/main/LICENSE) (from ThariqS/html-effectiveness)
