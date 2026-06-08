# Warli Illustrations — Usage

Warli-style **Indian tribal folk-art** body illustrations for articles, posts,
blogs, product/design docs, workflows, and methodology content. Turns one
abstract idea — a judgment, flow, structure, state, or metaphor — into a clean,
rhythmic, white-on-earth folk scene where small **Warli figures** (circle head,
two-triangle hourglass torso, stick limbs) earnestly perform the core action
around trees, wells, huts, pots, and fields.

By default it **draws each image as a hand-painted-style SVG with code** — no API
key, no external service, fully editable. The full spec lives in
[`SKILL.md`](SKILL.md); this file is the quick how-to + prompt library + gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Make a Warli illustration for this article."
> "Turn this idea into an Indian folk-art explainer image."
> "Give me a shot list for illustrating this post in Warli style."

Or invoke it explicitly:

```text
/warli-illustrations <your request + the article / idea>
```

**Workflow:** digest the source → produce a shot list → render one image per
shot (one core idea each, built from the Warli figure + 1–3 motifs + ≤5 labels).
If you only want planning, ask for the shot list and it stops there.

**Output:** images are saved to `assets/<article-slug>-illustrations/`, named in
order `01-topic.svg`, `02-topic.svg`, … Originals are kept; existing assets are
not overwritten unless you ask.

---

## Prompt examples

Copy any of these and paste straight in.

### Plan only — shot list, no images

```text
Use /warli-illustrations — don't generate images yet.
Analyze the article below and decide where illustrations would help.
Output a shot list of about 5 shots. For each shot, specify:
- where it goes in the piece
- the theme
- the core idea
- the structure type
- what the figures are doing
- suggested motifs (tree / well / hut / pots / fields)
- suggested short labels

<paste article>
```

### Body illustrations for an article

```text
Use /warli-illustrations — generate 4 Warli body illustrations for the
article below.
Requirements: 16:9 landscape, flat terracotta/ochre background, white rice-paste
figures and linework, at most 5 short handwritten labels each.
Each image covers only one core idea. No PPT infographics, no gradients, no 3D.

<paste article>
```

### Long-form illustration strategy

```text
Use /warli-illustrations — plan an illustration strategy for this long article.
Don't illustrate evenly; pick only the cognitive anchors: the core judgment,
input→output flows, before/after, common pitfalls, handoff paths.
Default 6-8 shots. Output the shot list first; don't generate images yet.

<paste article>
```

### One image for a single point

```text
Use /warli-illustrations — generate one 16:9 body illustration for this point:

Knowledge isn't hoarded; it's passed hand to hand until everyone is lit.

The figures must carry the core action, not just decorate.
Keep it warm and folk, monochrome white-on-earth, at most 5 short labels.
```

### Workflow theme

```text
Use /warli-illustrations — generate one image for "a single shared resource
that many people draw from without it running dry."
Don't draw a formal flowchart, and don't copy any shipped sample composition.
Reinvent a fresh rural metaphor (well, tree, granary, loom) and let a figure
perform the core action.
```

### Edit — make a figure carry the action

```text
Use /warli-illustrations — this image is close, but the figures look decorative.
Keep the core idea the same and regenerate a version where a figure is the one
actually performing the structure (sowing, carrying, pouring, joining hands).
Keep it flat terracotta, white geometric figures, sparse on text.
```

### Generate a style sample set

```text
Use /warli-illustrations — produce 3 Warli body illustrations on different themes.
Cover: sharing knowledge, a shared resource, and small habits compounding.
Generate each separately; don't combine them into one image.
```

---

## Examples

A small gallery for style calibration — figure construction, motif rhythm,
breathing room, and how a figure carries the core action. **Calibrate to these;
never copy their compositions** (the skill reinvents a fresh metaphor every time).

| File | Theme | Metaphor — what the figures do |
|---|---|---|
| [01-passing-the-lamp.svg](../../../assets/warli-illustrations-examples/01-passing-the-lamp.svg) | Sharing knowledge | A line of figures pass a lit clay lamp (diya) hand to hand; each lamp glows brighter down the row until all are lit. |
| [02-shared-well.svg](../../../assets/warli-illustrations-examples/02-shared-well.svg) | One source, many users | Figures arrive from both sides with pots on their heads to draw from a single central well that never runs dry. |
| [03-filling-the-granary.svg](../../../assets/warli-illustrations-examples/03-filling-the-granary.svg) | Small habits compound | A lone figure starts with one handful of grain on the left; on the right, figures pour daily handfuls into a brimming round granary. |

Each is one 16:9 image, flat terracotta ground, white geometric figures, one core
idea, ≤5 short labels.

---

## Quick rules of thumb

- **One image = one idea.** Let rhythm and repetition carry it, never density.
- **Figures must act.** If removing the figures leaves the idea fully intact, they
  were decoration — rework so a figure performs the core action.
- **Restrained color.** White rice-paste figures and lines on terracotta/ochre;
  monochrome by default, with at most one earthy accent (deep red or mustard) on
  a single key element. Never a rainbow.
- **Warm ground, lots of air.** Keep one quiet zone of empty ground so the scene
  reads at a glance.
- **No corner titles, no PPT/flowchart look, no detailed faces or 3D.** Geometric
  primitives only: circle head, hourglass torso, stick limbs.
- **Editing is just editing the SVG** — change a path, move a `<use>` figure,
  swap a motif, nudge a label. Prefer that over full regeneration.

See [`SKILL.md`](SKILL.md) for the full Style DNA, the Warli figure & motif
library, composition patterns, the SVG construction guide, and the QA checklist.
