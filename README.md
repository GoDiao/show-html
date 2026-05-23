# show-html

A cross-platform agent skill that teaches AI agents to generate self-contained, zero-dependency HTML pages for rich output — code reviews, slide decks, status reports, interactive editors, dashboards, and more.

## Inspired by

This project is inspired by [ThariqS/html-effectiveness](https://github.com/ThariqS/html-effectiveness) — a gallery of standalone HTML examples demonstrating "the unreasonable effectiveness of HTML" as a flexible agent output format. The first 20 example HTML files in this skill's `assets/` are sourced from that repository under the Apache 2.0 license. Examples 21–24 are original additions.

## What's Included

- **SKILL.md** — Skill definition with design system, use case index, and generation workflow
- **25 HTML files** — A gallery index + 24 self-contained reference pages
- **4 switchable themes** — Gallery, Dark Exhibition, Terminal, Zen (color-only, preserves each page's unique layout & typography)

### 24 Examples across 12 Categories

| # | Category | Examples |
|---|----------|---------|
| 01–02 | Code Exploration | Three approaches comparison, visual design directions |
| 03–04 | Code Review | Annotated PR diff, module dependency map |
| 05–06 | Design System | Living design tokens, component variant matrix |
| 07–08 | Prototyping | Animation sandbox with easing controls, clickable interaction flow |
| 09–10 | Presentations | Arrow-key slide deck, SVG figure sheet |
| 11–12 | Reports | Weekly status with charts, incident timeline |
| 13 | Diagrams | Annotated flowchart with clickable steps |
| 14–15 | Research | Feature explainer with collapsible sections, concept explainer with live visualization |
| 16 | Planning | Implementation plan with milestones and risk table |
| 17 | Communication | PR writeup for reviewers |
| 18–20 | Editor Tools | Triage board (drag & drop), feature flag editor, prompt tuner |
| 21–24 | Data & Visualization | Metrics dashboard, sortable/filterable table, system architecture (Mermaid.js), gantt timeline |

### Design Highlights

Each file has a **unique visual personality**:

- **Editorial Lookbook** (05) — Cormorant Garamond, paint-chip swatches
- **Swiss International Style** (06) — Space Grotesk, dot grid, zero border-radius
- **Creative Studio Dark** (07) — Syne, glassmorphism, floating orbs
- **Product Showcase** (08) — Plus Jakarta Sans, teal accents, device frame
- **Blueprint/Technical** (13) — Navy grid overlay, glow-on-hover nodes
- **Academic Textbook** (15) — Georgia serif, margin line, reading progress bar
- **Notion-quality PM** (16) — Milestone timeline, effort badges, progress tracking
- **Dark Dashboard** (21) — DM Serif Display, sparklines, donut charts
- **Mermaid Architecture** (23) — Declarative flowcharts & sequence diagrams

### Theme System

The gallery index (`index.html`) offers 4 themes via a floating switcher:

| Theme | Description |
|-------|-------------|
| **Gallery** (default) | Warm editorial — Playfair Display, ivory backgrounds |
| **Dark Exhibition** | Deep charcoal with neon accents, spotlight cards |
| **Terminal** | Black & green hacker aesthetic, Space Mono, glow effects |
| **Zen** | Ultra-minimal white, barely-there accents, no shadows |

All 24 sub-pages inherit the selected theme via `localStorage` — only colors change, layout and typography remain untouched.

## Installation

1. Place the `show-html/` directory in your agent's skill path
2. Or install the `show-html.skill` package

## Usage

- Explicitly invoke: `/show-html` or `/show-html:code-review` etc.
- Auto-trigger based on task context (e.g., "review this PR", "make a status report")
- Agent reads the examples as a reference library, then generates similar HTML from scratch

## Opening the Gallery

Open `show-html/assets/index.html` directly in a browser — no build step, no server needed.

## License

- Skill packaging, documentation & original examples (21–24): **MIT**
- Examples 01–20: [Apache License 2.0](https://github.com/ThariqS/html-effectiveness/blob/main/LICENSE) (from ThariqS/html-effectiveness)
