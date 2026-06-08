---
name: xiaohei-illustrations
description: Generate Ian-style "Xiaohei" hand-drawn body illustrations for articles, posts, blogs, Notion docs, workflows, and methodology content. Use this skill WHENEVER the user wants article illustrations, body images, shot lists, "Xiaohei", weird hand-drawn explainer images, or wants to turn an abstract idea/flow/structure/state/metaphor into a clean weird white-background sketch — even if they don't say the word "illustration". Also use for editing such images. By default it DRAWS each image as a hand-drawn-style SVG using Claude Code itself (no API key, no external service); a raster image-API path is optional. Default look: Xiaohei IP, pure white background, thin wobbly black linework, sparse red/orange/blue handwritten annotations, 16:9, clean but bizarre. NOT for commercial illustration, PPT infographics, cute mascots, children's art, or dense diagrams.
---

# Xiaohei Body Illustrations

Port of Ian's `ian-xiaohei-illustrations` Codex skill, adapted for Claude Code. The original relied on Codex's built-in `image_gen`. Claude Code has no native image generator, so by default this skill **draws each illustration as a hand-drawn-style SVG with code** — no API key, no external service, fully editable and reproducible. An optional raster path (image API) exists for when you want diffusion-model texture.

## Core positioning

Design and produce **16:9 landscape body illustrations** for articles. The goal is NOT commercial illustration, PPT infographics, or cute cartoons. It is to take one key judgment, flow, structure, state, or metaphor from the article and turn it into a clean, weird, creative, readable hand-drawn explainer image — interesting, but never an instruction manual.

The default visual IP is **Xiaohei**: a solid-black creature with white-dot eyes, thin legs, blank expression, earnestly doing one absurd-but-coherent thing. Xiaohei must perform the core action of the scene — never just stand beside it as decoration.

One line: don't just "add an image" — draw out one key cognitive action from the article.

## Rendering modes

**Mode A — SVG (default, no key).** Claude Code writes the illustration directly as an `.svg` file using the **SVG construction guide** below (hand-drawn wobble filter + the Xiaohei character recipe + sparse colored labels). This is the default. It needs nothing installed. The look is cleaner and more geometric than a diffusion model, but it is reproducible, editable, and on-brand for explainer diagrams. Save the `.svg`; optionally also export a `.png` (see **Rasterizing an SVG**).

**Mode B — raster via image API (optional).** Only if the user explicitly wants photographic/diffusion hand-drawn texture AND an image key is available. Write the embedded `generate_image.py`, set `OPENAI_API_KEY` (or use the Gemini branch / a connected image MCP), and use the **raster prompt template**. If the user asks for raster but no key is set, say so once and fall back to Mode A.

**Choosing:** default to Mode A unless the user says something like "make it look like a real sketch / use an image model / I want the diffusion texture". When in doubt, do Mode A and offer Mode B as an upgrade.

## Workflow

### 1. Digest the article

Read the user's article / link / Notion page / Markdown / screenshot. Extract: the core point, which paragraphs carry a cognitive turn, what is worth illustrating, and what should stay text-only. Don't illustrate evenly — prioritize "cognitive anchors": the core judgment, two breakpoints, an input→output loop, a split, a before/after, one-input-many-outputs, a handoff path, a common pitfall, a character state change.

### 2. Produce the shot list first

If the user only asks to plan / think about what to illustrate, output a shot list and stop. For each shot specify: where it goes (after which paragraph), theme, core idea, structure type, what Xiaohei is doing, suggested elements, suggested short labels.

Default 4–8 shots. Short article: 1–3. Long article: rarely exceed 9. Enough is enough — don't turn the body into a picture book.

### 3. Render one image at a time

If the user clearly asks to generate / output / make images, don't pause for confirmation. For EACH shot, do ONE image (never combine shots). Each image explains exactly one core structure.

- **Mode A:** fill the **scene spec** (below), then build the `.svg` by hand using the **SVG construction guide**. Start from the **starter template**; place the Xiaohei character, 1–2 objects, the flow, and ≤5 short labels.
- **Mode B:** fill the **raster prompt template**, write it to a temp file, call `generate_image.py` once.

Do NOT replicate prior case compositions. Reinvent a fresh weird-but-coherent metaphor from the current article every time (see **Original-metaphor method**).

### 4. QA and iterate

Check each result against the **QA checklist**. In Mode A, iterate by editing the SVG directly (cheap and exact). Regenerate/edit if Xiaohei is decorative, the canvas is crowded, it looks like a PPT/flowchart, there's a corner title, the style is too cute/stiff, or the background isn't clean white.

### 5. Save and deliver

Save to `assets/<article-slug>-illustrations/`, named in order: `01-topic-name.svg`, `02-topic-name.svg`, ... Keep originals; don't overwrite existing assets unless asked. Report: how many were produced, what each is for, the save path, the mode used, and which are most reliable vs optional. Let the images speak — don't write a long style essay.

---

## Style DNA (must follow)

One line: pure white, minimal, hand-drawn, lots of whitespace, restrained, bizarre, product-sketch feel, handwritten feel, clear structure but not a manual.

**Must:**
- 16:9 landscape body illustration.
- Pure white background — no beige, warm gray, paper texture, gradient, shadow, noise.
- Black hand-drawn linework dominant — thin lines, slight wobble, not mechanical, not heavy outlines. (In SVG: a turbulence/displacement filter provides the wobble.)
- Lots of whitespace — subject occupies ~40–60% of the canvas, at least 35% blank, ideally one quiet empty zone.
- Few handwritten annotations — at most 5–8, each ideally 2–8 words.
- One image = one core action / structure / state / metaphor.
- Express structure naturally; never write the structure-type name on the image.

**Color (restrained — fewer is better):**
- Black: main linework, Xiaohei, frames, structure, primary text, main objects.
- Red: key annotations, problems, emotional points, critical reminders, results.
- Orange: main flow, paths, arrows, automation direction, A→B movement.
- Blue: secondary notes, mental/system state, second-layer explanation. Optional, not every time.

**Absolutely not:** commercial illustration, PPT infographic, formal flowchart, course slide, cute cartoon poster, children's art, complex architecture diagram, polished flat illustration, techy UI, real app screenshot, complex backgrounds/gradients/shadows/textures, explaining every node, or corner titles like "Workflow / System Architecture / Common Pitfalls / Roadmap".

**Aesthetic direction:** weird, creative, interesting, clean, imaginative. Never cute, childish, overly complex, or stiff.

---

## Xiaohei IP

The fixed visual IP. By default Xiaohei appears in every image. Not a mascot, sticker, or cute decoration — an absurd worker earnestly keeping a system running.

**Form:** solid-black little creature; white round dot eyes; thin legs, occasionally thin arms; body can be a cylinder, black bean, black box, funnel, shadow, hole, or black block inside a machine; slightly irregular hand-drawn outline; blank, deadpan, calm, serious expression.

**Personality:** very earnest but doing something slightly absurd; a low-key system operator; dry humor, never cutesy; a bit clumsy but not dumb; genuinely responsible for some job inside a whiteboard sketch.

**Common duties (let Xiaohei carry the core action):** hauling material; pulling lines to converge info sources; stuck in a breakpoint; operating a "judgment" lever inside a machine; becoming a sorting funnel; cutting open a "material fish"; stamping handoff scripts; leading a handoff path; holding a warning sign over a pit; reaching out of a hole but failing to catch content.

**Forbidden:** overly cute mascot; children's cartoon character; complex clothing / emoji-face / shiny eyes; Xiaohei just standing in a corner; Xiaohei stealing the structural meaning; too commercial / too round / too polished.

**Test:** if you remove Xiaohei and the core metaphor still fully holds, Xiaohei was decorative — redo it so Xiaohei is the action subject.

---

## Composition patterns & original-metaphor method

Pick ONE structure type; don't mix too many.

- **Workflow** — input→process→output. Input left, Xiaohei/weird machine center, output right, orange arrows for main flow.
- **System fragment** — info sources, filters, databases, renderers. 3–5 core modules; Xiaohei in one key action.
- **Before/after** — chaos/order, manual/auto, scattered/converged. Chaos left, stable right, orange arrow between.
- **Character state** — user pain, info anxiety, stuck→running. 2–4 small states, one short label each.
- **Concept metaphor** — content factory, info warehouse, mental black box. One big weird object/machine, few inputs, one output.
- **Method layers** — frameworks, capability stacks. Stacked boxes (NOT a formal pyramid); Xiaohei building beside it.
- **Map / route** — idea→launch, user path, learning path. One curved path, few nodes, Xiaohei pulling the line or walking.
- **Mini-comic frames** — failure→success, before/after. 2–4 small scenes, one action per frame.

### Original-metaphor method (reinvent every time — never copy old images)

1. **Turn the abstract concept into a physical action:** stuck, leaking, getting heavier, sorting, settling, fermenting, opening a door, folding, unpacking, flowing back.
2. **Turn the system structure into a low-tech object:** broken machine, cardboard box, drawer, water pipe, mailbox, weird dial, scale, well, ladder, strange workstation.
3. **Make Xiaohei carry the action:** stuck inside the machine, pulling the wrong line, guarding a gate, hauling, patching, weighing, holding a ladder, recording, stuffing something into a strange device.

Object pool: box, drawer, old machine, funnel, scale, mailbox, door, well, ladder, water pipe, ball of string, gate/sluice, turntable, black box, hole punch, pasta press, clothesline, weird workstation. Use only 1–2 at a time.

Xiaohei action pool: pull, carry, stuff, scoop, press, weigh, sew, cut, twist, guard, push, catch, unpack, mark, recycle. The action must serve the core meaning.

### Anti-replication rule

Do NOT reuse known case compositions (two-breakpoint conveyor, judgment-lever machine, funnel-sorter, material-fish, handoff path, three info-source lines, horn/bridge/door trio, script-stamp toolbox, pitfall-path sign) unless the user explicitly says "copy this one". For repeat themes, invent a new metaphor.

---

## SVG construction guide (Mode A — default)

### Scene spec (fill before drawing)

Theme / Structure type / Core idea / Composition (where Xiaohei is + what it does + main object + how info flows) / 1–2 objects / ≤5 short labels / colors used.

### Canvas
`viewBox="0 0 1600 900"` (16:9). First child: `<rect width="1600" height="900" fill="#ffffff"/>` — always an explicit white background (do NOT use theme/CSS variables; this style is literally white paper + black ink).

### Color tokens
- ink `#1b1b1b` · orange `#ea7317` · red `#d83a2e` · blue `#2f6fd0` · white `#ffffff`

### Strokes
`stroke-width` 2.5–3 for main lines, 2 for thin detail; `stroke-linecap="round"`, `stroke-linejoin="round"`; `fill="none"` for linework; Xiaohei body is `fill="#1b1b1b"`.

### The hand-drawn wobble (the key to not looking like clip-art)
Put linework inside a group with a turbulence/displacement filter. Two strengths: stronger for shapes (`#wob`), gentler for text (`#wobt`). Draw **white-dot eyes crisp (outside the filter)** so they stay clean.

### Labels
Use a handwriting font stack and a slight rotation; mild wobble. `font-family="'Bradley Hand','Comic Sans MS','Segoe Print',cursive"`, `font-size` ~28–32, `transform="rotate(-2 ...)"`. Keep ≤5 labels, 2–8 words each. Colors per tokens.

### Xiaohei character recipe (drop-in)
A vertical-bean blob ~110×185, black fill; two white dot eyes; two thin legs with tiny feet; optional thin arms reaching to an object. Scale/translate via a wrapping `<g transform="translate(x,y) scale(s)">`. Vary the body path slightly each time so it isn't identical.

### Starter template (copy, then build the scene into it)
```svg
<svg viewBox="0 0 1600 900" xmlns="http://www.w3.org/2000/svg"
     font-family="'Bradley Hand','Comic Sans MS','Segoe Print',cursive">
  <defs>
    <filter id="wob" x="-6%" y="-6%" width="112%" height="112%">
      <feTurbulence type="fractalNoise" baseFrequency="0.012" numOctaves="2" seed="7" result="n"/>
      <feDisplacementMap in="SourceGraphic" in2="n" scale="3.6" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <filter id="wobt" x="-6%" y="-6%" width="112%" height="112%">
      <feTurbulence type="fractalNoise" baseFrequency="0.02" numOctaves="2" seed="3" result="n"/>
      <feDisplacementMap in="SourceGraphic" in2="n" scale="1.6" xChannelSelector="R" yChannelSelector="G"/>
    </filter>
    <marker id="ah" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="7" markerHeight="7"
            orient="auto-start-reverse">
      <path d="M0 0 L10 5 L0 10" fill="none" stroke="#ea7317" stroke-width="2"
            stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
  </defs>

  <rect width="1600" height="900" fill="#ffffff"/>

  <!-- LINEWORK: objects + Xiaohei body + flow go in here -->
  <g filter="url(#wob)" fill="none" stroke="#1b1b1b" stroke-width="3"
     stroke-linecap="round" stroke-linejoin="round">

    <!-- Xiaohei (translate into place) -->
    <g transform="translate(0,0)">
      <path d="M800 455 C762 455 745 492 746 536 C747 586 758 636 800 638
               C842 636 855 586 854 536 C853 492 838 455 800 455 Z"
            fill="#1b1b1b" stroke="none"/>
      <path d="M785 636 L782 686 M815 636 L818 686"/>        <!-- legs -->
      <path d="M770 686 L792 686 M806 686 L830 686"/>        <!-- feet -->
      <path d="M752 560 L734 600 M848 560 L866 600"/>        <!-- arms (optional) -->
    </g>

    <!-- objects from the pool (example: a funnel) -->
    <!-- <path d="..."/> -->

    <!-- flow (recolor stroke to orange where needed) -->
    <!-- <path d="..." stroke="#ea7317" stroke-width="4" marker-end="url(#ah)"/> -->
  </g>

  <!-- EYES: crisp, outside the wobble group -->
  <circle cx="784" cy="522" r="7.5" fill="#ffffff"/>
  <circle cx="818" cy="522" r="7.5" fill="#ffffff"/>

  <!-- LABELS: handwriting font, gentle wobble, slight rotation, <=5 total -->
  <text x="700" y="270" font-size="30" fill="#1b1b1b" filter="url(#wobt)"
        transform="rotate(-2 700 270)">one short note</text>
</svg>
```
A worked example shipped alongside this skill: `xiaohei-sample.svg` (Xiaohei shuttling between Tool A and Tool B with an empty thought bubble).

### Rasterizing an SVG (only if a PNG is needed)
The wobble filter and the handwriting font are real browser features but are **ignored by some converters** (e.g. `cairosvg`), which would flatten the lines and drop the font. To get a faithful PNG, render via a browser engine — e.g. headless Chrome, `resvg`, or `rsvg-convert` — not `cairosvg`. Otherwise just deliver the `.svg`; it renders correctly in any browser.

---

## Raster mode (Mode B — optional)

### Raster prompt template
```text
Generate one standalone 16:9 horizontal article illustration.

Visual DNA:
Pure white background. Minimalist black hand-drawn line art. Slightly wobbly pen lines. Lots of empty white space. Sparse red/orange/blue handwritten annotations. Clean absurd product-sketch feeling. No gradients, no shadows, no paper texture, no complex background, no commercial vector style, no PPT infographic look, no cute mascot poster, no children's illustration, no realistic UI.

Recurring IP character required:
Xiaohei, a small solid-black absurd creature with white dot eyes, tiny thin legs, blank serious expression, slightly uneven hand-drawn body shape. Xiaohei must perform the core conceptual action, not decorate the scene. Make Xiaohei serious, deadpan, and slightly bizarre, not cute.

Theme: {theme}
Structure type: {Workflow / System fragment / Before-after / Character state / Concept metaphor / Method layers / Map-route / Mini-comic}
Core idea: {the one idea this image expresses}
Composition: {where Xiaohei is, what it is doing, the main object, how information flows}
Suggested elements: {e1} / {e2} / {e3}
Handwritten labels: {l1} / {l2} / {l3} / {optional l4}
Color use: Black for main line art and Xiaohei. Orange for main flow/path/arrows. Red only for key warnings/problems/results. Blue only for secondary notes or feedback/system state.

Constraints:
One image explains only one core structure. Keep the main subject around 40%-60% of the canvas. Preserve at least 35% blank white space. Use at most 5-8 short handwritten labels. Do not write a title in the top-left corner. Do not write the structure type on the image. Do not make it a formal diagram, course slide, or dense explainer. Invent a fresh visual metaphor for this specific article. Clear but not instructional, interesting but not childish, strange but clean.
```

### Embedded generation script (write to `generate_image.py` on first use)
```python
#!/usr/bin/env python3
"""Generate one Xiaohei-style illustration via an image API. Prompt comes from
a file (safe for long text); writes a PNG."""
import argparse, base64, json, os, sys, urllib.request

def gen_openai(prompt, out, size="1536x1024"):
    key = os.environ.get("OPENAI_API_KEY")
    if not key:
        sys.exit("Set OPENAI_API_KEY (or switch to the Gemini branch).")
    req = urllib.request.Request(
        "https://api.openai.com/v1/images/generations",
        data=json.dumps({"model": "gpt-image-1", "prompt": prompt,
                         "size": size, "n": 1}).encode(),
        headers={"Authorization": f"Bearer {key}", "Content-Type": "application/json"},
        method="POST")
    with urllib.request.urlopen(req, timeout=180) as r:
        data = json.load(r)
    os.makedirs(os.path.dirname(out) or ".", exist_ok=True)
    with open(out, "wb") as f:
        f.write(base64.b64decode(data["data"][0]["b64_json"]))
    print(f"Saved {out}")

# --- Alternative: Gemini 2.5 Flash Image (GEMINI_API_KEY); response carries
#     inlineData base64 under candidates[0].content.parts[*].inlineData.data ---

if __name__ == "__main__":
    p = argparse.ArgumentParser()
    p.add_argument("--prompt-file", required=True)
    p.add_argument("--out", required=True)
    p.add_argument("--size", default="1536x1024")
    a = p.parse_args()
    gen_openai(open(a.prompt_file, encoding="utf-8").read(), a.out, a.size)
```

---

## QA checklist

**Must pass:** 16:9 landscape; clean white background (explicit white rect, no theme color); Xiaohei present; Xiaohei carries the core action (not decoration); a fresh metaphor (not a copied case); weird/creative/interesting; clean, subject <= ~60% of canvas; one core structure only; few, short, readable labels; orange only for main path/arrows; red only for key points/problems/results; blue only for secondary notes/state. **Mode A also:** linework runs through the wobble filter (not crisp clip-art); eyes drawn crisp; labels use the handwriting font + slight rotation.

**Failure signals (redo/edit):** corner title like "Common Pitfalls / Workflow / System Architecture / Roadmap"; Xiaohei looks like a mascot/cute cartoon; looks like a PPT/course slide/formal flowchart; too many elements/arrows/nodes; long paragraphs of text; paper texture/shadow/gradient/beige/noise in background; realistic UI; unreadable labels; too stiff with no absurd metaphor; too similar to a known old case; (Mode A) perfectly straight mechanical lines with no wobble.

**Iteration:** too plain → make Xiaohei the action subject, add one weird-but-coherent metaphor. Too complex → cut nodes, keep one action + 3–5 short labels. Too cute → emphasize deadpan/blank-serious, not mascot. Too PPT → drop title/border/grid/excess arrows. Too like an old case → keep the meaning, swap the object and Xiaohei's action. (Mode A) too clean → raise the `#wob` `scale`, vary `seed`, hand-vary the body path.

**Delivery test:** a good image first reads as "a bit weird," then within 1 second the structure clicks. If it looks like a tutorial page rather than a bizarre product sketch on blank paper, it fails.

---

## Notes

- One core structure per image; never cram the whole article into one picture.
- Mode A is the default and needs no key; reach for Mode B only when the user wants diffusion texture and a key/MCP is available.
- Reference example images are for style calibration only (line density, whitespace, color restraint, Xiaohei's vibe) — never copy their compositions.
- In Mode A, editing is just editing the SVG: change a path, recolor a stroke, nudge a label. Use that instead of full regeneration whenever possible.