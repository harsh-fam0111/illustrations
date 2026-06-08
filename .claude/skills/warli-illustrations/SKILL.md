---
name: warli-illustrations
description: Generate Warli-style (Indian tribal folk-art) hand-painted body illustrations for articles, posts, blogs, product/design docs, workflows, and methodology content. Use this skill WHENEVER the user wants article illustrations, body images, shot lists, "Warli", Indian folk-art explainer images, or wants to turn an abstract idea/flow/structure/state/metaphor into a clean white-on-earth geometric folk scene — even if they don't say the word "illustration". By default it DRAWS each image as a hand-painted-style SVG using Claude Code itself (no API key, no external service); a raster image-API path is optional. Default look: white rice-paste figures (circle head + two-triangle hourglass torso + stick limbs) on a warm terracotta/ochre background, monochrome, geometric, rhythmic, 16:9. NOT for photorealism, PPT infographics, glossy 3D, or dense corporate diagrams.
---

# Warli Body Illustrations

A Warli-style sibling of the Xiaohei skill, adapted for Claude Code. Warli is the tribal folk art of Maharashtra, India: simple white motifs painted in rice paste on earth-toned walls, built from circles, triangles, and lines. By default this skill **draws each illustration as a hand-painted-style SVG with code** — no API key, fully editable. An optional raster path (image API) exists for diffusion texture.

## Core positioning

Design and produce **16:9 landscape body illustrations** for articles and product/design docs, in Warli folk style. Take one key judgment, flow, structure, state, or metaphor and turn it into a clean, rhythmic, white-on-earth folk scene — interesting and warm, but never a corporate infographic.

The visual language is the **Warli figure**: a small circle head, an hourglass torso of two triangles meeting at a point, thin stick arms and legs. Warli is communal — figures appear in lines, rings, and groups around nature and daily life (trees, sun, huts, fields, animals, the spiral tarpa dance). For an explainer, one or a few figures carry the core action; the rest of the scene gives it rhythm.

One line: don't just decorate — paint one key idea as a small Warli world.

## Rendering modes

**Mode A — SVG (default, no key).** Claude Code writes the illustration directly as an `.svg` using the **SVG construction guide** below (hand-paint wobble filter + the Warli figure recipe + a motif library + sparse labels). Default. Needs nothing installed. Cleaner/more geometric than a diffusion model, but reproducible and editable. Save the `.svg`; optionally export `.png` (see **Rasterizing**).

**Mode B — raster via image API (optional).** Only if the user explicitly wants diffusion texture AND an image key/MCP is available. Write `generate_image.py`, set `OPENAI_API_KEY` (or Gemini branch), use the **raster prompt template**. If asked for raster with no key, say so once and fall back to Mode A.

**Choosing:** default to Mode A unless the user says "make it look hand-painted / use an image model / I want real texture".

## Workflow

1. **Digest** the article/doc/idea. Extract the core point and the cognitive anchors worth illustrating; leave the rest as text. Don't illustrate evenly.
2. **Shot list first** (if the user only wants planning): per shot — where it goes, theme, core idea, structure type, what the figures do, motifs, ≤5 short labels. Default 4–8 shots; short piece 1–3; long piece rarely >9.
3. **Render one image at a time** (never combine shots). Mode A: fill the scene spec, then build the `.svg` from the starter template — figures + 1–2 motifs + flow + ≤5 labels. Mode B: fill the raster prompt and call the script once. Reinvent a fresh metaphor each time; don't copy old compositions.
4. **QA** against the checklist; in Mode A iterate by editing the SVG directly.
5. **Save & deliver** to `assets/<article-slug>-illustrations/` as `01-topic.svg`, `02-topic.svg`, ... Report count, purpose of each, path, mode, and which are most reliable.

---

## Style DNA (must follow)

One line: warm earth ground, white folk motifs, geometric primitives, rhythmic repetition, lots of breathing room, hand-painted, clear but not a manual.

**Must:**
- 16:9 landscape.
- Warm terracotta/ochre background — flat, no photographic texture, gradient, or shadow.
- White (off-white) figures and linework — thin, slightly irregular hand-painted lines, not mechanical.
- Figures are geometric primitives only: circle head, two-triangle hourglass torso, stick limbs. No faces beyond the head dot, no clothing detail.
- Breathing room — the scene reads at a glance; one quiet zone of empty ground.
- Rhythm over density: repeat a motif (figures in a line/ring, trees, hatch marks) instead of cramming many different objects.
- Few labels — at most 5, each 2–6 words.
- One image = one core action / structure / state / metaphor.

**Color (restrained):**
- Background terracotta/ochre; figures + lines off-white. Monochrome by default.
- Optional single accent (deep red or mustard) ONLY for one key element — never a rainbow. Keep it tribal and earthy.

**Absolutely not:** photorealism, glossy/3D, PPT infographic, formal flowchart, corporate icons, gradients/shadows/drop-shadows, neon or pastel palettes, detailed faces/expressions, cute mascots, dense architecture diagrams, or corner titles like "Workflow / Roadmap".

**Aesthetic direction:** warm, communal, rhythmic, earthy, folk, a little mythic. Never slick, corporate, neon, or cute.

---

## The Warli figure & motif library

**Figure (the recurring unit):** circle head; hourglass torso = upper triangle (apex down) + lower triangle (apex up) sharing a center point; two thin arms from the shoulders; two thin legs from the lower triangle. Keep it tiny and repeatable. Action comes from arm/leg angles and what the figure holds or joins, NOT from facial expression.

**Let figures carry the action:** sowing/tending, carrying pots or bundles on the head, pulling a line, climbing a ladder, drumming the tarpa, joining hands in a ring, building a hut, fishing, herding, passing an object down a line.

**Motif pool (use 1–3, repeat for rhythm):** sun/moon, tree of life (symmetric branching with dot-fruit), hut (triangle roof + square), fields with hatch marks, water/river wavy lines, pots, ladder, bullock/animal as triangle-bodied forms, birds as simple V/chevrons, the spiral or circle dance.

**Test:** if you remove the figures and the idea still fully holds, they were decorative — rework so a figure performs the core action.

---

## Composition patterns & original-metaphor method

Pick ONE structure type: **Workflow** (figures pass an object down a line, left→right) · **System fragment** (3–5 motif "stations", figures working one) · **Before/after** (sparse left → abundant right, e.g. sprout→tree) · **Character state** (2–4 figure poses) · **Concept metaphor** (one big motif — tree, well, hut, river — figures interacting) · **Method layers** (stacked huts/fields, figures building) · **Map/route** (a winding path with figures walking, motifs as milestones) · **Mini-frames** (2–4 small scenes).

**Reinvent the metaphor every time** using the Indian/rural object world: tree of life, well, river, field, granary, pot, loom, bullock cart, ladder, drum, lamp/diya. Turn the abstract concept into a physical rural action (sow, carry, pour, weave, herd, build, gather) and let a figure do it. Don't reuse a prior composition unless asked.

---

## SVG construction guide (Mode A — default)

**Scene spec (fill first):** Theme / Structure type / Core idea / Composition (figure positions + actions + main motif + flow) / 1–3 motifs / ≤5 labels.

**Canvas:** `viewBox="0 0 1600 900"`. First child: a full terracotta `<rect>` — literal color, not a theme variable.

**Color tokens:** ground `#a0531e` (or `#9c4a1a`/`#b06a3a`) · paint `#f2e9dc` · optional accent `#c0392b` (deep red) or `#d9a441` (mustard), one element only.

**Strokes:** `stroke="#f2e9dc"`, width 3–3.4 main / 2.4 thin; round caps/joins; figures filled `#f2e9dc`.

**Hand-paint wobble:** wrap linework in a turbulence/displacement filter (`#paint`) so lines look brushed, not vector. Keep label wobble gentle. The wobble is a real browser feature — see **Rasterizing**.

**Labels:** handwriting font stack, gentle wobble, slight rotation, ≤5, 2–6 words. `font-family="'Bradley Hand','Comic Sans MS','Segoe Print',cursive"`.

**Starter template (define the figure once, reuse with `<use>`):**
```svg
<svg viewBox="0 0 1600 900" xmlns="http://www.w3.org/2000/svg"
     font-family="'Bradley Hand','Comic Sans MS','Segoe Print',cursive">
  <defs>
    <filter id="paint" x="-6%" y="-6%" width="112%" height="112%">
      <feTurbulence type="fractalNoise" baseFrequency="0.014" numOctaves="2" seed="5" result="n"/>
      <feDisplacementMap in="SourceGraphic" in2="n" scale="3.2" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <marker id="awh" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7"
            orient="auto-start-reverse">
      <path d="M0 0 L10 5 L0 10" fill="none" stroke="#f2e9dc" stroke-width="2"
            stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
    <!-- reusable Warli figure, origin at torso center -->
    <g id="warli">
      <circle cx="0" cy="-50" r="9" fill="#f2e9dc"/>
      <path d="M-15 -38 L15 -38 L0 0 L15 38 L-15 38 L0 0 Z" fill="#f2e9dc"/>
      <path d="M-12 -32 L-34 -14 M12 -32 L34 -14" stroke="#f2e9dc" stroke-width="3.4"
            fill="none" stroke-linecap="round"/>
      <path d="M-12 36 L-22 64 M12 36 L22 64" stroke="#f2e9dc" stroke-width="3.4"
            fill="none" stroke-linecap="round"/>
    </g>
  </defs>

  <rect width="1600" height="900" fill="#a0531e"/>

  <g filter="url(#paint)">
    <!-- place figures: translate to position, scale to size -->
    <use href="#warli" transform="translate(300,560) scale(0.95)"/>
    <!-- join hands / show action by adding connecting lines and held objects -->
    <!-- add 1-3 motifs from the pool (tree, sun, hut, pots, fields) -->
    <!-- flow: a brushed white path with marker-end="url(#awh)" -->
    <!-- a single ground line ties the scene together -->
  </g>

  <!-- labels: <=5, handwriting font, gentle rotation -->
  <text x="250" y="690" font-size="30" fill="#f2e9dc" filter="url(#paint)"
        transform="rotate(-2 250 690)">short note</text>
</svg>
```
Worked example shipped with this skill: `warli-sample.svg` (sprout → tree-of-life "it compounds", with a hands-joined dancing trio).

**Rasterizing (only if a PNG is needed):** the wobble filter and handwriting font are real browser features but are **ignored by some converters** (e.g. `cairosvg`). For a faithful PNG render via a browser engine — headless Chrome, `resvg`, or `rsvg-convert` — not `cairosvg`. Otherwise just deliver the `.svg`.

---

## Raster mode (Mode B — optional)

**Raster prompt template:**
```text
Generate one standalone 16:9 horizontal article illustration in authentic Warli tribal folk-art style.

Visual DNA:
Warm flat terracotta/ochre background. White rice-paste motifs only. Figures built from a small circle head, an hourglass torso of two triangles meeting at a point, and thin stick arms and legs — no faces, no clothing detail. Geometric, rhythmic, hand-painted slightly irregular lines. Monochrome white-on-earth (at most one earthy accent). No photorealism, no gradients, no shadows, no 3D, no PPT infographic look, no corporate icons, no cute cartoon.

Theme: {theme}
Structure type: {Workflow / System fragment / Before-after / Character state / Concept metaphor / Method layers / Map-route / Mini-frames}
Core idea: {the one idea this image expresses}
Composition: {figure positions and actions, the main motif (tree/well/hut/river/field), how things flow}
Motifs: {sun} / {tree of life} / {hut} / {pots/fields/animals}
Labels: {l1} / {l2} / {l3}

Constraints:
One image explains only one core idea. Keep generous empty ground. Use at most 5 short labels. No top-left title. Figures must perform the core action, not decorate. Repeat a motif for rhythm rather than crowding many different objects. Keep it warm, communal, folk — not slick, neon, or cute.
```

**Embedded script** — same `generate_image.py` as the Xiaohei skill (OpenAI `gpt-image-1` via `OPENAI_API_KEY`, prompt read from a file; optional Gemini branch). Reuse it as-is.

---

## QA checklist

**Must pass:** 16:9; flat terracotta/ochre background (literal color); white geometric figures present and performing the core action; circle-head + hourglass-torso + stick-limb construction (no faces/clothing); fresh metaphor (not a copied case); rhythmic, breathing room, reads at a glance; one core idea; ≤5 short labels; monochrome (≤1 earthy accent). **Mode A also:** linework runs through the paint wobble filter (not crisp vector); labels use the handwriting font + slight rotation; figures defined once and reused via `<use>`.

**Failure signals (redo/edit):** corner title; detailed faces/expressions or clothing; slick/corporate/neon/pastel look; gradients/shadows/3D; photographic texture; too many different objects (no rhythm); long paragraphs of text; figures merely decorating; (Mode A) perfectly straight mechanical lines.

**Iteration:** too plain → add a repeated motif (a line/ring of figures, a row of fields) and let a figure act. Too busy → cut to one motif + a few figures + one ground line. Too corporate → swap geometric icons for tree/well/hut/pot motifs. Too static → angle the arms/legs, join hands, add a tarpa drummer. (Mode A) too clean → raise `#paint` `scale`, vary `seed`.

**Delivery test:** a good image first reads as a warm folk scene, then within ~1 second the idea clicks. If it looks like a corporate slide rather than a painted wall, it fails.

---

## Notes

- One core idea per image; let rhythm and repetition carry it, not density.
- To swap traditions: **Madhubani** (ornate, colourful, double-line fills, dense pattern, fish/peacock/lotus motifs) or **Gond** (fine dotted/dashed infill, bold animal forms, vivid colour) need a different palette and a denser fill recipe — ask before assuming, since they break the monochrome/minimal default.
- Mode A is default and needs no key; reach for Mode B only for diffusion texture with a key/MCP available.
- Authentic Warli has no text; labels are an explainer concession — keep them minimal so the folk feel survives.