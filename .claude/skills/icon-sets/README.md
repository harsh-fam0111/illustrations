# Icon Sets & Spot Illustrations — Usage

Cohesive **line-icon sets** and simple spot illustrations as editable SVG.
Turns a list of needs — a feature's UI glyphs, a navigation bar, a small set of
pictograms — into a family of icons that share one stroke weight, one corner
radius, and one visual language, so they read as a set rather than a pile of
mismatched marks.

By default it **draws every icon directly as SVG with code** — no API key, no
Figma, no external service, fully editable. The full spec lives in
[`SKILL.md`](SKILL.md); this file is the quick how-to + gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Make me a set of navigation icons."
> "I need a home, search, and settings glyph that all match."
> "Draw a consistent icon family for this feature."

Or invoke it explicitly:

```text
/icon-sets <your request + the list of icons or the feature they're for>
```

**Workflow:** list the icons needed and group them by metaphor family → fix the
shared grid/stroke/radius rules once → draw each icon to those rules on a
contact sheet for review → on approval, export individual 24×24 files. If you
only want the sheet, ask for that and it stops there.

**Output:** files are saved to `assets/icons/` — a contact sheet for review plus,
on approval, one `24×24` SVG per icon named for its metaphor (`home.svg`,
`search.svg`, …). The examples in this README live in
`assets/icon-sets-examples/`.

---

## Examples

A small gallery for calibration — uniform stroke weight, consistent corner
radius and 45° angles, one metaphor per icon, monochrome ink. **Calibrate to
these; the set is reinvented for each request.**

| File | Type | Description |
|---|---|---|
| [01-icon-set-contact-sheet.svg](../../../assets/icon-sets-examples/01-icon-set-contact-sheet.svg) | Contact sheet | Eight-glyph navigation family (home, search, bell, user, settings, mail, heart, add) on a labelled grid, captions in `#94a3b8` — the review artefact. |
| [02-icon-home.svg](../../../assets/icon-sets-examples/02-icon-home.svg) | Individual icon | `home` split out to a native `24×24` file with 2-unit padding, ready to drop into a product. |
| [03-icon-search.svg](../../../assets/icon-sets-examples/03-icon-search.svg) | Individual icon | `search` magnifier split out to a native `24×24` file, same weight and terminals as the rest of the set. |

Every icon shares stroke width 2.4–2.6, `stroke="#0f172a"`, `fill="none"`, and
round caps/joins — no single glyph is denser than the others.

---

## Quick rules of thumb

- **One metaphor per icon.** Strip detail until only the recognizable essence
  remains; if it needs a caption to read, simplify it.
- **The family shares everything.** Same grid (24×24, ~2-unit padding), same
  stroke weight, same corner radius, same 45° angles, same terminals.
- **Optical over mathematical.** Balance icons by eye; perfect centering often
  looks off.
- **Monochrome by default.** Ink only; add a single accent colour only if the
  user asks for one.
- **Legible small.** Test each glyph mentally at ~20px — if it muddies, it's too
  busy.
- **Sheet first, files second.** Review on the contact sheet, then export
  individual `24×24` SVGs for production.

See [`SKILL.md`](SKILL.md) for the full grid and stroke rules, output modes, the
SVG starter, and the QA checklist.
