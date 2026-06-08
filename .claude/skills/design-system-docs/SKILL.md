---
name: design-system-docs
description: Write design-system and component specification docs (Markdown), with optional SVG anatomy/state sheets, using Claude Code itself — no API key. Use this skill WHENEVER the user wants to document a component, write a component spec, define design tokens, create a design-system page, specify states/variants/anatomy/accessibility for a button/input/card/modal/etc., or standardize UI guidance. Output is a structured Markdown spec following a fixed template, plus optional SVG showing component anatomy and states. NOT for generating production component code or full screens (use ui-wireframes for screens).
---

# Design-System & Component Spec Docs

Produce consistent component specs as Markdown, with optional SVG visuals, in Claude Code. No key.

## Shared design tokens (reference set)
- ink `#0f172a` · slate `#475569` · muted `#94a3b8` · line `#e2e8f0` · surface `#f8fafc` · white `#ffffff`
- primary `#4f46e5` (hover `#4338ca`, pressed `#3730a3`) · success `#16a34a` · warn `#f59e0b` · danger `#ef4444`
- radius 8/12/16/pill · spacing 4/8/16/24/32 · type scale 12/14/16/20/28 · control height 48

## Component spec template (ALWAYS use this structure)
```markdown
# <Component name>
One-line purpose.

## Anatomy
Numbered parts (container, label, leading/trailing icon, etc.). Optional: link the anatomy SVG.

## Variants
| Variant | Use when | Notes |
|---|---|---|
| Primary | main action on a view | one per view |
| Secondary | … | … |

## States
default · hover · focus (visible ring) · pressed · disabled · loading · error. Describe the visual delta + token for each.

## Sizing & spacing
height, min-width, padding, gap, radius — as tokens.

## Content rules
label length, casing, icon usage, truncation.

## Accessibility
roles/labels, focus order, contrast (>= 4.5:1 text), hit target (>= 44px), keyboard behavior.

## Do / Don't
- Do: …
- Don't: …
```

## Optional SVG (anatomy + states)
A clean vector sheet: the component rendered once with measurement annotations (dimension lines in `#94a3b8`, labels in `#64748b`), plus a grid of state swatches. Then a token legend (color chips + hex). Calibration reference: `designsystem-sample.svg`.

## Workflow
1. Identify the component(s). If documenting several, one Markdown file each (or one page with sections).
2. Fill the template; keep guidance concrete and token-referenced (no vague adjectives).
3. Optionally generate the anatomy/states SVG.
4. Save the doc to `design-system/<component>.md` (+ SVG beside it). Report what's covered.

## QA checklist
Follows the template; every state covered; sizing in tokens not magic numbers; accessibility section present (contrast, focus, hit target); do/don't concrete; SVG (if any) uses the token palette and labels dimensions.

## Notes
- This is documentation, not code — describe behavior; don't emit framework components unless explicitly asked.
- Keep one source of truth for tokens; reference them rather than restating hexes everywhere.