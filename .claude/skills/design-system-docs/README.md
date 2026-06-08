# Design-System Docs — Usage

Write design-system and component specification docs as **Markdown**, with an
optional **SVG anatomy/state sheet**, using Claude Code itself. Turns a single
component — a button, input, card, modal, and so on — into a structured spec that
covers anatomy, variants, states, sizing, content rules, accessibility, and
do/don't guidance, all referenced against one shared set of design tokens.

By default it **writes documentation, not code** — no API key, no external
service, fully editable. The full spec lives in [`SKILL.md`](SKILL.md); this file
is the quick how-to + gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Document the button component for our design system."
> "Write a spec for the text input — states, variants, accessibility."
> "Define the design tokens and standardize how we use cards."

Or invoke it explicitly:

```text
/design-system-docs <the component(s) + any constraints>
```

**Workflow:** identify the component(s) → fill the fixed template with concrete,
token-referenced guidance → optionally generate the anatomy/states SVG → report
what's covered. If you only want the Markdown spec, ask for that and it skips the
SVG.

**Output:** specs are saved to `design-system/<component>.md`, with the optional
SVG sheet saved beside the doc. Each doc follows the same template so a set of
components reads consistently.

---

## Examples

A small gallery for calibration — the template structure, how guidance stays
token-referenced, and what the optional SVG sheet looks like. **Calibrate to
these; adapt the content to your own component** (the skill fills the template
fresh each time).

| File | What it is | Notes |
|---|---|---|
| [01-button-spec.md](../../../assets/design-system-docs-examples/01-button-spec.md) | Button component spec (Markdown) | Full template: anatomy, 4 variants, 7 states, sizing/spacing in tokens, content rules, accessibility, do/don't. |
| [02-button-anatomy.svg](../../../assets/design-system-docs-examples/02-button-anatomy.svg) | Button anatomy + states sheet (SVG) | Annotated anatomy with dimension lines, a grid of state swatches, and a token legend of color chips + hex. |

Each spec follows the template exactly and references the shared tokens rather
than restating hexes everywhere.

---

## Quick rules of thumb

- **One source of truth for tokens.** Reference `primary #4f46e5`, `radius 8`,
  `control height 48` — never re-hardcode the same hex or pixel in three places.
- **Tokens, not magic numbers.** Every size, color, and spacing value points back
  to the shared token set.
- **Every state covered.** default · hover · focus (visible ring) · pressed ·
  disabled · loading · error — each with its visual delta and token.
- **Accessibility is required, not optional.** Roles/labels, focus order, contrast
  `>= 4.5:1`, hit target `>= 44px`, keyboard behavior — always present.
- **Concrete do/don't.** Specific, testable guidance — no vague adjectives.
- **Docs, not code.** Describe behavior; don't emit framework components unless
  explicitly asked. For full screens use `ui-wireframes`.

See [`SKILL.md`](SKILL.md) for the full template, the shared token set, the
optional SVG construction guide, and the QA checklist.
