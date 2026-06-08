---
name: icon-sets
description: Generate cohesive line-icon sets and simple spot illustrations as SVG, using Claude Code itself — no API key. Use this skill WHENEVER the user wants icons, an icon set, a UI icon, a glyph, a pictogram, a logo mark sketch, or small spot illustrations that must look consistent as a family. Produces editable SVG on a fixed grid with consistent stroke weight, corner radius, and visual language — either as a contact sheet or individual files. NOT for detailed illustrations (use the illustration skills), photos, or brand logos of real companies.
---

# Icon Sets & Spot Illustrations

Draw consistent icon families directly as editable `.svg` with Claude Code. No key. Precise vector.

## Grid & style rules (the source of consistency)
- Canvas per icon: 24×24 logical units (scale up for display). Keep a ~2-unit padding (live area ~20×20).
- Stroke: width `2.4–2.6`, `stroke="#0f172a"`, `fill="none"`, `stroke-linecap="round"`, `stroke-linejoin="round"`.
- Geometry: align to the grid; consistent corner radius; consistent angles (45°); optical balance over mathematical centering.
- One metaphor per icon; remove detail until only the recognizable essence remains. The whole set must share weight, terminals, and density — an icon that's noticeably busier than the others is wrong.
- Color: monochrome ink by default. A single accent only if the user asks.

## Output modes
- **Contact sheet** (default): all icons on one SVG, a labelled grid (cells ~200u, icon centered, caption below in `#94a3b8`). Good for review.
- **Individual files**: one `24×24` SVG per icon, named `home.svg`, `search.svg`, … for use in a product.

## Workflow
1. List the icons needed (from the user's set or feature). Group by metaphor family.
2. Define the shared rules above once, then draw each icon to them.
3. Draw on the sheet for review; on approval, also export individual 24×24 files.
4. Save to `assets/icons/`. Report the set and any icons that needed a metaphor compromise.

## Starter (single icon, 24×24) + sheet cell
```svg
<!-- single icon -->
<svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" fill="none"
     stroke="#0f172a" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round">
  <path d="M4 11 l8 -7 l8 7 v8 a1 1 0 0 1 -1 1 h-14 a1 1 0 0 1 -1 -1 z"/>  <!-- home -->
</svg>

<!-- on a contact sheet, place each icon in a cell and caption it -->
<g transform="translate(125,150)" fill="none" stroke="#0f172a" stroke-width="2.6"
   stroke-linecap="round" stroke-linejoin="round">
  <path d="M-16 4 l16 -16 l16 16 v16 a2 2 0 0 1 -2 2 h-28 a2 2 0 0 1 -2 -2 z"/>
</g>
```
Calibration reference: `iconset-sample.svg` (home, search, heart, bell, user, settings, add, delete).

## QA checklist
Uniform stroke weight and terminals across the set; all on the same grid/size; consistent corner radius and angles; each icon legible at small size (test mentally at 20px); one metaphor each; optically balanced; monochrome unless an accent was requested; no single icon noticeably denser than the rest.

## Notes
- Renders faithfully anywhere (no filters/custom fonts).
- For richer or narrative art, use the `xiaohei-illustrations` or `warli-illustrations` skills instead — this skill is for tight, uniform UI glyphs.