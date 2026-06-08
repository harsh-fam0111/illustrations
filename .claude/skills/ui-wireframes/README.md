# UI Wireframes & Screen Mockups — Usage

Generate clean app and web **screen mockups** as editable SVG, drawn directly
with Claude Code — no API key, no Figma, no external service. Describe the
screen you want (a login, a feed, a settings page, a checkout step) and the
skill builds it from a consistent component kit — app bar, cards, lists, inputs,
buttons, chips, tab bar — on a phone or desktop frame. Output is precise vector,
deliberately **not** hand-drawn: lo-fi grayscale wireframes by default, mid-fi
mockups with the indigo design tokens on request.

The full spec lives in [`SKILL.md`](SKILL.md); this file is the quick how-to plus
a small example gallery.

---

## How to use it

In Claude Code, just ask in plain language and the skill triggers automatically:

> "Wireframe a mobile login screen."
> "Show me the feed screen for this app."
> "Sketch a settings page before we build it."
> "Make me a checkout screen — mid-fi, styled."

Or invoke it explicitly:

```text
/ui-wireframes <the screen you want + platform + lo-fi or mid-fi>
```

**Workflow:** state the screen's job in one line and the platform (mobile or
desktop) → pick a layout (app bar → content → primary action → nav) → build one
screen per SVG from the component kit, on an 8px rhythm with one clear primary
action. For a multi-screen flow, the skill emits one SVG per screen in order.

**Lo-fi vs mid-fi:** lo-fi grayscale is the default — text becomes gray bars,
images become placeholder boxes, and only the primary action is a solid dark
block. Ask for "mid-fi", "hi-fi", or "make it look real" to switch to real
labels, icons, and the indigo token palette.

**Output:** screens are saved to `assets/<feature>-screens/`, named in order
`01-login.svg`, `02-home.svg`, … Existing assets are not overwritten unless you
ask.

---

## Examples

A small gallery for calibration — frame proportions, the 8px spacing rhythm,
lo-fi grayscale discipline, and one clear primary action per screen. **Calibrate
to these; don't copy the layouts** — every screen is built fresh for its job.

| File | Screen | What it shows |
|---|---|---|
| [01-login-screen.svg](../../../assets/ui-wireframes-examples/01-login-screen.svg) | Mobile login | Logo placeholder, email + password input fields, a dark primary "sign in" block, an outline secondary button, an "or" divider, and a sign-up footer. |
| [02-feed-screen.svg](../../../assets/ui-wireframes-examples/02-feed-screen.svg) | Mobile feed / list | App bar with avatar, filter chips, a hero media card, a "see all" section header, four avatar list rows, a FAB, and a 5-icon bottom tab bar. |
| [03-settings-screen.svg](../../../assets/ui-wireframes-examples/03-settings-screen.svg) | Mobile settings | Back chevron app bar, a profile header card, grouped setting rows with toggles (on/off) and chevrons, and dark save + outline log-out actions. |

Each is a 390×844 mobile frame inside a rounded phone shell, lo-fi grayscale,
with a single dark primary action.

---

## Quick rules of thumb

- **One screen = one SVG.** A flow is several files, not one crowded canvas.
- **One clear primary action.** In lo-fi, the dark `#0f172a` block is the only
  filled element — everything else stays gray.
- **Stay lo-fi unless asked.** Grayscale communicates structure; resist brand
  polish until the user requests mid-fi.
- **8px rhythm, consistent radii.** Cards rx 16, controls rx 12, pills rx 999.
  Align edges; keep generous spacing; never crowd.
- **Right frame + status bar.** Mobile 390×844 phone shell, or desktop
  1440×900; always include the `9:41` status bar on mobile.
- **No lorem walls, no real photos.** Text is gray bars; images are placeholder
  boxes with a simple glyph.
- **Editing is just editing the SVG** — nudge a rect, swap a fill, move a row.
  Prefer that over full regeneration.

See [`SKILL.md`](SKILL.md) for the full design tokens, frame specs, the complete
component kit, the starter template, and the QA checklist.
