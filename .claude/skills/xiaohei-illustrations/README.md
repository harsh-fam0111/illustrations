# Xiaohei Illustrations — Usage

Ian-style **Xiaohei** hand-drawn body illustrations for articles, posts, blogs,
Notion docs, workflows, and methodology content. Turns one abstract idea —
a judgment, flow, structure, state, or metaphor — into a clean, weird,
white-background sketch where **Xiaohei** (a deadpan solid-black creature with
white-dot eyes) earnestly performs the core action.

By default it **draws each image as a hand-drawn-style SVG with code** — no API
key, no external service, fully editable. The full spec lives in
[`SKILL.md`](SKILL.md); this file is the quick how-to + prompt library + gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Make a Xiaohei illustration for this article."
> "Turn this idea into a weird hand-drawn explainer image."
> "Give me a shot list for illustrating this post."

Or invoke it explicitly:

```text
/xiaohei-illustrations <your request + the article / idea>
```

**Workflow:** digest the source → produce a shot list → generate one image per
shot (one core structure each). If you only want planning, ask for the shot list
and it stops there.

**Output:** images are saved to `assets/<article-slug>-illustrations/`, named in
order `01-topic.svg`, `02-topic.svg`, … Originals are kept; existing assets are
not overwritten unless you ask.

---

## Prompt examples

Copy any of these and paste straight in. (The `$ian-xiaohei-illustrations`
handle is the original Codex name; in Claude Code you can also just say
"use the xiaohei illustrations skill" or `/xiaohei-illustrations`.)

### Plan only — shot list, no images

```text
Use $ian-xiaohei-illustrations — don't generate images yet.
Analyze the article below and decide where illustrations would help.
Output a shot list of about 5 shots. For each shot, specify:
- which paragraph it goes after
- the theme
- the core idea
- the structure type
- what Xiaohei is doing
- suggested elements
- suggested short labels

<paste article>
```

### Body illustrations for an article

```text
Use $ian-xiaohei-illustrations — generate 4 weird Xiaohei body illustrations
for the article below.
Requirements: 16:9 landscape, pure white background, black hand-drawn linework,
a few red/orange/blue handwritten labels.
Each image covers only one core structure. No PPT infographics, no cute cartoons.

<paste article>
```

### Long-form illustration strategy

```text
Use $ian-xiaohei-illustrations — plan an illustration strategy for this long article.
Don't illustrate evenly; pick only the cognitive anchors: the core judgment,
input→output loops, before/after, common pitfalls, handoff paths.
Default 6-8 shots. Output the shot list first; don't generate images yet.

<paste article>
```

### One image for a single point

```text
Use $ian-xiaohei-illustrations — generate one 16:9 body illustration for this point:

Trust isn't shouted out; it's laid down one piece of evidence at a time.

The image should be weird but clean, and Xiaohei must carry the core action.
At most 5 labels, kept short.
```

### Workflow theme

```text
Use $ian-xiaohei-illustrations — generate one image for "turning a single raw
material into three kinds of content: reach, trust, and conversion."
Don't draw a formal flowchart, and don't replicate the old "one fish, many dishes" case.
Reinvent a fresh low-tech metaphor, and let Xiaohei drive the core action.
```

### Edit — remove a title

```text
Use $ian-xiaohei-illustrations — edit this image for me.
Remove the top-left "Workflow / Flowchart" title and its underline;
keep everything else unchanged.
Don't add any new text or objects.
```

### Edit — make Xiaohei carry the action

```text
Use $ian-xiaohei-illustrations — this image is on the right track, but Xiaohei
looks decorative.
Keep the core idea the same and regenerate a version where Xiaohei is the one
actually driving the structure.
Make it a bit weirder, but still pure white, clean, and sparse on text.
```

### Generate a style sample set

```text
Use $ian-xiaohei-illustrations — produce 5 Xiaohei body illustrations on
different themes.
Cover: information overload, product validation, content compounding,
the one-person company, building trust.
Generate each separately; don't combine them into one image.
```

---

## Best examples

A small gallery for style calibration — line density, whitespace, color
restraint, and how Xiaohei carries the core action. **Calibrate to these; never
copy their compositions** (the skill reinvents a fresh metaphor every time).

| Preview | File | Theme | Metaphor — what Xiaohei does |
|---|---|---|---|
| Trust = bricks | [01-trust-evidence-bricks.svg](../../../assets/xiaohei-illustrations/01-trust-evidence-bricks.svg) | Building trust | Bridges a void by laying evidence-bricks one at a time toward a far "trust" flag — a crossed-out megaphone says it's *not* shouted. |
| Info firehose | [02-info-firehose.svg](../../../assets/xiaohei-illustrations/02-info-firehose.svg) | Information overload | Holds up a tiny cup under a giant gushing faucet, catching almost none of the torrent. |
| Content snowball | [03-content-snowball.svg](../../../assets/xiaohei-illustrations/03-content-snowball.svg) | Content compounding | Pushes a snowball up a slope; the same push rolls up ever more content toward a huge "compounding" ball. |
| Info courier | [info-mover/01-info-courier.svg](../../../assets/info-mover-illustrations/01-info-courier.svg) | Busywork / moving info | Shuttles a stack of copy-pasted sheets between Tool A and Tool B, blank thought bubble overhead. |

Each is one 16:9 image, pure white, one core structure, ≤5 short labels.

---

## Quick rules of thumb

- **One image = one idea.** Never cram a whole article into one picture.
- **Xiaohei must act.** If removing Xiaohei leaves the metaphor intact, it was
  decoration — redo it.
- **Restrained color.** Black linework; orange only for the main flow/path;
  red only for key points/problems/results; blue only for secondary notes.
- **Clean white, lots of air.** Subject ~40–60% of canvas, ≥35% blank.
- **No corner titles, no PPT/flowchart look, no cute mascot.** Weird but clean.
- **Editing is just editing the SVG** — change a path, recolor a stroke, nudge a
  label. Prefer that over full regeneration.

See [`SKILL.md`](SKILL.md) for the full Style DNA, Xiaohei IP recipe,
composition patterns, the SVG construction guide, and the QA checklist.
