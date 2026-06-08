---
name: ui-wireframes
description: Generate clean app/web UI screen mockups and wireframes as SVG, using Claude Code itself — no API key, no Figma, no external service. Use this skill WHENEVER the user wants a wireframe, mockup, screen, app UI, web page layout, lo-fi or mid-fi design, "show me the screen", a login/onboarding/settings/feed/checkout screen, or wants to sketch an interface before building it. Produces editable SVG with a phone/desktop frame and a consistent component kit (app bar, cards, lists, inputs, buttons, tab bar). Lo-fi (grayscale placeholders) by default; mid-fi (with the indigo design tokens) on request. NOT for production code, pixel-perfect brand comps, or photographic content.
---

# UI Wireframes & Screen Mockups

Draw app and web screens directly as editable `.svg` with Claude Code. No key, no Figma. Lo-fi wireframes (grayscale placeholders) by default; mid-fi mockups (real tokens) when asked. The output is clean, precise vector — deliberately NOT hand-drawn.

## Shared design tokens
- ink `#0f172a` · slate `#475569` · muted `#94a3b8` · line `#e2e8f0` · surface `#f8fafc` · white `#ffffff`
- primary `#4f46e5` (hover `#4338ca`, pressed `#3730a3`) · success `#16a34a` · warn `#f59e0b` · danger `#ef4444`
- radius: card 16, control 12, pill 999 · spacing scale 8/16/24 · icon stroke 2.4–2.6
- type: system sans (`Inter, Arial, sans-serif`); title ~22–32, body ~16–18, caption ~12–14

## Frames
- Mobile: 390×844 screen inside a rounded phone shell (rx 46, ink stroke 2.5). Status bar with `9:41` + indicators; optional bottom tab bar.
- Desktop/web: 1440×900 viewport, optional browser chrome bar (dots + URL pill).
- Center the frame on a soft `#f1f5f9` canvas with margin.

## Lo-fi vs mid-fi
- **Lo-fi (default):** grayscale only. Text = rounded rect bars (`#cbd5e1` headings, `#e2e8f0` body). Images = `#e2e8f0` box with a simple mountain+sun glyph. One dark `#0f172a` block for the primary action. Mark it `— lo-fi wireframe —`.
- **Mid-fi:** real labels, primary in indigo, real icons, the token palette. Use when the user says "make it look more real / hi-fi / styled".

## Component kit (build screens from these)
App bar (back chevron + title bar + trailing avatar) · hero/media card · section header (title bar + "see all") · list row (avatar circle + two text bars) · input field (rounded rect + label bar) · primary/secondary button · chips/tags (pills) · tab bar (4–5 line icons, active one inked) · FAB (circle + plus).

## Workflow
1. Clarify the screen's job in one line and the platform (mobile/desktop). If obvious from the prompt, proceed.
2. Pick a layout: app bar → content (hero, list, form, grid) → primary action → nav.
3. Build ONE screen per SVG from the component kit. Keep alignment to an 8px rhythm; generous spacing; one clear primary action.
4. For a multi-screen flow, output one SVG per screen, named `01-login.svg`, `02-home.svg`, … (and consider pairing with the `user-flow-diagrams` skill).
5. Save to `assets/<feature>-screens/`. Report each screen's purpose.

## Starter template (mobile, lo-fi)
```svg
<svg viewBox="0 0 560 1080" xmlns="http://www.w3.org/2000/svg" font-family="Inter, Arial, sans-serif">
  <rect width="560" height="1080" fill="#f1f5f9"/>
  <rect x="40" y="30" width="480" height="1020" rx="46" fill="#ffffff" stroke="#0f172a" stroke-width="2.5"/>
  <text x="74" y="78" font-size="20" font-weight="600" fill="#0f172a">9:41</text>
  <!-- app bar -->
  <path d="M88 124 l-14 14 l14 14" fill="none" stroke="#0f172a" stroke-width="2.5"
        stroke-linecap="round" stroke-linejoin="round"/>
  <rect x="120" y="126" width="180" height="22" rx="6" fill="#cbd5e1"/>
  <!-- content: cards, list rows, inputs ... -->
  <!-- primary action -->
  <rect x="74" y="880" width="412" height="60" rx="14" fill="#0f172a"/>
  <rect x="232" y="903" width="96" height="14" rx="7" fill="#ffffff"/>
</svg>
```
Calibration reference shipped with this skill: `wireframe-sample.svg`.

## QA checklist
Right frame + status bar; one clear primary action; consistent radii and 8px spacing; aligned edges; lo-fi stays grayscale (only the primary block is dark); mid-fi uses tokens consistently; readable hierarchy; not crowded; no lorem walls; no real photos.

## Notes
- These render faithfully in any browser (no filters/custom fonts needed); rasterize with anything.
- Wireframes communicate structure, not final visuals — resist adding brand polish unless asked for mid-fi.