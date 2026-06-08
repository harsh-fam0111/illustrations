---
name: user-flow-diagrams
description: Generate clean user-flow diagrams and customer journey maps as SVG, using Claude Code itself — no API key, no external service. Use this skill WHENEVER the user wants a user flow, app flow, navigation flow, onboarding/checkout/signup flow, decision tree, screen-to-screen map, or a customer journey map (stages × actions/thoughts/emotions/touchpoints) — even phrased as "map out the steps" or "how does the user get from X to Y". Produces editable node-and-arrow flows (start/end pills, process rects, decision diamonds) and journey-map grids with an emotion curve. NOT for code, infra/architecture diagrams, or org charts.
---

# User-Flow Diagrams & Journey Maps

Draw flows and journey maps directly as editable `.svg` with Claude Code. No key. Clean, precise vector.

## Shared design tokens
- ink `#0f172a` · slate `#475569` · muted `#94a3b8` · line `#e2e8f0` · surface `#f8fafc`
- primary `#4f46e5` (+ tint `#eef2ff`) · success `#16a34a` (+ `#ecfdf5`) · warn `#d97706` (+ `#fffbeb`) · danger `#ef4444`
- connector stroke `#64748b` width 2.4; type system sans; radius 14 (nodes), pill 999.

## Two outputs

### A) Flow diagram (node + arrow)
Node types: **Start/End** = pill, primary tint. **Process/Screen** = rounded rect, surface fill, ink stroke. **Decision** = diamond, warn tint; two labelled exits (`yes`/`no`). Connectors are orthogonal where possible, single arrowhead (`marker-end`), labelled at branches. Left→right main path; branch downward then rejoin. Title top-left with a short underline; never a boxed title inside the canvas.

### B) Journey map (grid)
Columns = stages (e.g. Discover · Onboard · Use · Renew). Rows = lanes: Actions, Thoughts, Touchpoints, Emotion, Opportunities. Each cell holds 1–2 short chips/notes. The **Emotion** row is a polyline curve across stages (dot per stage; green high, red low) — the signature element. Keep one idea per cell.

## Workflow
1. Identify which output: a *flow* (branching path) or a *journey map* (experience across stages). If unclear and the prompt says "flow", do a flow.
2. List the nodes/stages first (as a shot list) and confirm only if genuinely ambiguous.
3. Lay out on a grid: fixed column x-positions, consistent node sizes, aligned centers. Route connectors after placing nodes.
4. One diagram per SVG. Save to `assets/<feature>-flow/`.

## Starter template (flow)
```svg
<svg viewBox="0 0 1600 760" xmlns="http://www.w3.org/2000/svg" font-family="Inter, Arial, sans-serif">
  <defs>
    <marker id="fa" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="8" markerHeight="8"
            orient="auto-start-reverse"><path d="M0 0 L10 5 L0 10 z" fill="#64748b"/></marker>
  </defs>
  <rect width="1600" height="760" fill="#ffffff"/>
  <text x="80" y="120" font-size="30" font-weight="700" fill="#0f172a">User flow — title</text>
  <line x1="80" y1="140" x2="360" y2="140" stroke="#e2e8f0" stroke-width="3"/>
  <!-- start pill -->
  <rect x="80" y="320" width="150" height="64" rx="32" fill="#eef2ff" stroke="#4f46e5" stroke-width="2"/>
  <text x="155" y="358" font-size="22" fill="#4f46e5" text-anchor="middle" font-weight="600">Start</text>
  <!-- process rect / decision diamond / end pill ... -->
  <!-- connectors -->
  <path d="M230 352 H300" fill="none" stroke="#64748b" stroke-width="2.4" marker-end="url(#fa)"/>
</svg>
```
Calibration reference: `userflow-sample.svg`.

## QA checklist
Correct node shapes for each type; single clear main path; every branch labelled; arrows don't cross nodes; aligned columns/centers; ≤ ~9 nodes per flow (split if more); journey map has the emotion curve and one idea per cell; title is a top-left heading, not a boxed label.

## Notes
- For many screens, pair with `ui-wireframes` (one wireframe per node).
- Renders faithfully in any browser.