---
name: show-html
description: >
  Generate self-contained, zero-dependency HTML pages for rich agent output.
  Use when the agent needs to present information that benefits from visual layout,
  interactivity, or structured presentation beyond plain text/markdown.
  Triggers on: code review, PR review, code understanding, design system docs,
  component variants, status report, incident report, slide deck, presentation,
  flowchart, diagram, implementation plan, feature/concept explainer, PR writeup,
  triage board, kanban, feature flags, prompt tuner, interactive editor,
  animation prototype, interaction prototype, visual design exploration,
  code approach comparison, SVG illustrations, dashboard, data visualization,
  interactive table, sortable table, system architecture diagram, service topology,
  gantt chart, timeline, project timeline, milestone tracker. Also triggers on explicit
  "/show-html" invocation or when user asks to "show as HTML", "generate HTML",
  "visualize as page", or "make a page for".
---

# Show HTML

Generate self-contained HTML pages for rich agent output. Zero dependencies, fully inline CSS, viewable in any browser.

## When to Generate HTML

Prefer HTML over markdown when the output needs:
- Multi-column layouts or side-by-side comparison
- Interactive elements (filters, toggles, drag-drop)
- Color-coded status indicators or severity badges
- Charts, diagrams, or flowcharts
- Slide-style presentations
- Code review with inline annotations
- Any content exceeding ~500 words that benefits from visual hierarchy

## Design System

All examples share a consistent design language. Use these patterns.

### Color Palette (CSS Custom Properties)

```css
:root {
  --ivory: #FAF9F5;
  --slate: #141413;
  --clay:  #D97757;
  --oat:   #E3DACC;
  --olive: #788C5D;
  --rust:  #B04A3F;
  --white: #FFFFFF;
  --gray-100: #F0EEE6;
  --gray-300: #D1CFC5;
  --gray-500: #87867F;
  --gray-700: #3D3D3A;
}
```

- Background: `--ivory`. Cards/panels: `--white` with `--gray-300` borders.
- Accent: `--clay` for primary actions, links, highlights.
- Success: `--olive`. Error/danger: `--rust`. Muted: `--gray-500`.

### Typography

```css
--serif: ui-serif, Georgia, "Times New Roman", serif;   /* headings */
--sans:  system-ui, -apple-system, "Segoe UI", sans-serif; /* body */
--mono:  ui-monospace, "SF Mono", Menlo, Consolas, monospace; /* code, labels */
```

- h1: `--serif`, 30-40px, `font-weight: 500`
- Body: `--sans`, 14-15px, `line-height: 1.5-1.6`
- Eyebrow labels: `--mono`, 11-12px, uppercase, `letter-spacing: 0.08em`, `--gray-500`

### Layout

- Page wrapper: `max-width: 860-1120px; margin: 0 auto; padding: 48-56px 24-32px`
- Card pattern: `border: 1.5px solid var(--gray-300); border-radius: 8-12px; padding: 24-32px; background: var(--white)`
- Grid for multi-column: `display: grid; gap: 16-24px`

### Page Structure

Every page follows: **header** (eyebrow + h1 + subtitle) → **content sections** → (optional) **interactive controls**

```html
<div class="page">
  <header>
    <p class="eyebrow">Category / Context</p>
    <h1>Page Title</h1>
    <p class="sub">Brief description</p>
  </header>
  <!-- content -->
</div>
```

## Use Case Index

### Exploration

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 01 | Code approaches comparison | `assets/01-exploration-code-approaches.html` | Multi-column layout showing 2-3 code solutions side-by-side. Prompt box at top. Each column: code block + pros/cons + verdict badge. Uses CSS grid for columns. |
| 02 | Visual design exploration | `assets/02-exploration-visual-designs.html` | Gallery of design alternatives. Thumbnail cards with hover states. Side-by-side comparison with annotations. |

### Code

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 03 | PR code review | `assets/03-code-review-pr.html` | Header card with PR meta (author, branch, status badges). Diff-style code blocks with line-by-line comments. Severity indicators (info/warning/error). Summary panel with stats. |
| 04 | Code understanding | `assets/04-code-understanding.html` | Annotated source code view. Callout boxes explaining key sections. Flow arrows connecting code blocks. Collapsible detail sections. |
| 05 | Design system | `assets/05-design-system.html` | Token tables (colors, spacing, typography). Component swatches. Live examples. Organized in categorized sections with section headers. |
| 06 | Component variants | `assets/06-component-variants.html` | Grid of component states/variants. Each cell: component render + props table. Visual diff between variants. |

### Prototyping

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 07 | Animation prototype | `assets/07-prototype-animation.html` | Interactive animation demo area. Easing curve selector panel. Play/replay controls. CSS animation with JS toggle for parameters. |
| 08 | Interaction prototype | `assets/08-prototype-interaction.html` | Clickable UI prototype. State transitions. Micro-interaction demos. JavaScript for interactivity. |

### Communication

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 09 | Slide deck | `assets/09-slide-deck.html` | Full-viewport slides with `scroll-snap`. `.slide` class per slide, `.invert` for dark slides. Serif headings, sans body. Progress dots. Arrow key / scroll navigation. |
| 10 | SVG illustrations | `assets/10-svg-illustrations.html` | Inline SVG artwork. Annotated diagrams. Scalable vector graphics within HTML. |
| 11 | Status report | `assets/11-status-report.html` | Metric cards with large numbers. Progress bars. Color-coded status indicators. Section-per-team pattern. Auto-generated pill badge. |
| 12 | Incident report | `assets/12-incident-report.html` | Timeline layout. Severity badges. Impact scope. Action items with owners. Post-mortem structure. |
| 17 | PR writeup | `assets/17-pr-writeup.html` | Structured PR description. Before/after comparison. Testing checklist. Reviewer notes section. |

### Diagrams & Research

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 13 | Flowchart diagram | `assets/13-flowchart-diagram.html` | CSS-drawn flowchart using positioned divs and SVG arrows. Annotated steps. Decision diamonds. Parallel paths. No external diagram library. |
| 14 | Feature explainer | `assets/14-research-feature-explainer.html` | Concept breakdown with visual aids. Progressive disclosure. Layered explanation from simple to complex. |
| 15 | Concept explainer | `assets/15-research-concept-explainer.html` | Educational layout. Diagrams + text pairing. Key concept highlight boxes. |
| 16 | Implementation plan | `assets/16-implementation-plan.html` | Phased plan with numbered steps. Dependency arrows. Effort estimates. Milestone markers. Collapsible detail per phase. |

### Custom Editing UIs

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 18 | Triage board | `assets/18-editor-triage-board.html` | Kanban-style columns (drag-drop). Card components with priority badges. Filter toolbar. Sticky column headers. JavaScript for drag interaction. |
| 19 | Feature flags | `assets/19-editor-feature-flags.html` | Toggle switches. Flag list with metadata (environment, rollout %). Search/filter. Edit-in-place controls. |
| 20 | Prompt tuner | `assets/20-editor-prompt-tuner.html` | Split panel: editor + preview. Parameter sliders. System/user message sections. Run button. Output display area. |

### Data & Visualization

| # | Use Case | File | Pattern Summary |
|---|----------|------|-----------------|
| 21 | Dashboard | `assets/21-dashboard.html` | Metric cards (4-col grid) with change indicators. CSS bar chart + SVG donut chart. SVG sparklines with gradient fill. Service health table with status badges. Multi-section layout: metrics → charts → sparklines → table. |
| 22 | Interactive table | `assets/22-interactive-table.html` | Search box + filter buttons (pill style). Sortable columns (click header). Avatar + name/email cell layout. Role badges with color coding. Row hover highlight. Vanilla JS for search, filter, sort. |
| 23 | System architecture | `assets/23-system-architecture.html` | Layered node diagram (clients → gateway → services → data → external). Color-coded node cards with top border accent. SVG connector arrows between layers. Legend bar. Detail cards below for infrastructure/observability. |
| 24 | Timeline / Gantt chart | `assets/24-timeline-gantt.html` | CSS Grid gantt with 12-week columns. Group headers by category. Task bars with progress labels. Milestone diamond markers. Stats bar. Milestone detail cards at bottom. "Today" week highlight. |

## Generation Workflow

1. **Identify the scenario** — match user request to a use case category above
2. **Read the reference file** — read the matching `assets/XX-*.html` for layout and pattern details
3. **Adapt to real data** — replace sample data with user's actual content; preserve the design patterns
4. **Output a single `.html` file** — fully self-contained, inline CSS, no external dependencies

### Key Rules

- Always include `<!DOCTYPE html>` and proper `<meta charset>` / viewport tags
- All CSS must be inline in a single `<style>` block
- No external dependencies (no CDN links, no frameworks, no build step)
- Use semantic HTML where possible
- Ensure basic responsiveness (test mentally at 768px and 1200px widths)
- Generate complete, working pages — never partial snippets
- When no specific use case matches, combine patterns from the closest examples
