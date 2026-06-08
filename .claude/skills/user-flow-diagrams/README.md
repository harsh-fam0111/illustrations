# User-Flow Diagrams & Journey Maps — Usage

Generate clean **user-flow diagrams** and **customer journey maps** as editable
SVG. Turns a path through your product — a signup, checkout, or onboarding
sequence, a decision tree, or a whole experience across stages — into a precise
vector diagram with proper node shapes (start/end pills, process rectangles,
decision diamonds) or a journey grid with the signature **emotion curve**.

By default it **draws each diagram as an SVG with code** — no API key, no Figma,
no external service, fully editable. The full spec lives in
[`SKILL.md`](SKILL.md); this file is the quick how-to + gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Map out the signup flow with a decision for existing accounts."
> "Show me the screen-to-screen flow for checkout."
> "Build a customer journey map for new-user onboarding."
> "How does a user get from the landing page to first value?"

Or invoke it explicitly:

```text
/user-flow-diagrams <your request + the steps or stages you have in mind>
```

**Workflow:** decide the output — a *flow* (a branching path) or a *journey map*
(an experience across stages) → list the nodes or stages first as a short shot
list → lay them out on a fixed grid with aligned centers → route the connectors
last. One diagram per SVG. If the request only asks for planning, it stops at
the shot list.

**Output:** diagrams are saved to `assets/<feature>-flow/`, named in order
`01-...svg`, `02-...svg`, … Each file is one diagram. Existing assets are not
overwritten unless you ask.

---

## Examples

A small gallery for calibration — node shapes, connector routing, column
alignment, and how the emotion curve reads. **Calibrate to these; don't copy the
exact content** (each diagram is built fresh for its own flow).

| File | Type | What it shows |
|---|---|---|
| [01-signup-flow.svg](../../../assets/user-flow-diagrams-examples/01-signup-flow.svg) | Node-and-arrow flow | Account signup, left-to-right main path with start/end pills, process rects, and two decision diamonds ("email already registered?", "code confirmed?") whose `yes`/`no` branches drop down and rejoin. |
| [02-onboarding-journey-map.svg](../../../assets/user-flow-diagrams-examples/02-onboarding-journey-map.svg) | Customer journey map | New-user onboarding across four stages (Discover · Sign up · First setup · First value) with Actions, Thoughts, Touchpoints, Opportunities lanes and an emotion-curve polyline dipping at setup, peaking at first value. |

Each is one diagram, clean vector, aligned columns, and a single clear reading order.

---

## Quick rules of thumb

- **Right shape per node.** Pills for start/end, rounded rects for process/screen,
  diamonds for decisions — never mix them up.
- **One main path.** Read left-to-right; branches drop down and rejoin so the
  spine stays obvious.
- **Label every branch.** Each diamond exit gets a short `yes`/`no` (or named)
  label; unlabelled forks are a redo.
- **Arrows route around nodes.** Connectors are orthogonal where possible and
  never cut through a box.
- **Keep flows small.** Roughly ≤9 nodes per flow; split a bigger one into
  linked diagrams.
- **The emotion curve is the point.** A journey map without the polyline (green
  high, red low, one dot per stage) is just a table.
- **One idea per cell, title top-left.** No boxed title floating inside the
  canvas; keep each chip to one short note.
- **Editing is just editing the SVG** — move a node, reroute a path, recolor a
  dot. Prefer that over full regeneration.

See [`SKILL.md`](SKILL.md) for the full design tokens, the two output specs, the
starter template, and the QA checklist.
