# Button

Triggers a single, clear action when activated by the user.

## Anatomy

See [`02-button-anatomy.svg`](02-button-anatomy.svg) for the annotated visual.

1. **Container** — the clickable surface; fill, radius, and shadow signal affordance.
2. **Label** — required text; one verb-led phrase.
3. **Leading icon** — optional glyph before the label (e.g. `+`); aids scannability.
4. **Trailing icon** — optional glyph after the label (e.g. chevron); for menus or directional intent.
5. **Focus ring** — visible outline drawn outside the container on keyboard focus.
6. **Content row** — icon + label laid out horizontally with a fixed gap.

## Variants

| Variant | Use when | Notes |
|---|---|---|
| Primary | main action on a view | one per view; fill `primary #4f46e5` |
| Secondary | a supporting action beside primary | `1px` `line #e2e8f0` border, `white` fill, `ink` label |
| Tertiary / Text | low-emphasis action in dense UI | no border/fill; `primary` label only |
| Danger | destructive, irreversible action | fill `danger #ef4444`; confirm first |

## States

- **default** — `primary #4f46e5` fill, `white` label.
- **hover** — fill darkens to `hover #4338ca`; cursor pointer.
- **focus** — `2px` `primary` ring offset `2px` from the container; persists with hover.
- **pressed** — fill darkens to `pressed #3730a3`; no movement.
- **disabled** — fill `muted #94a3b8`, label `surface #f8fafc`; `cursor: not-allowed`; no hover/focus.
- **loading** — spinner replaces leading icon, label dims to ~70% opacity; container stays sized, not interactive.
- **error** — only for inline-submit buttons; `1px` `danger #ef4444` border and a sibling message; never rely on color alone.

## Sizing & spacing

- Height: control height `48` (default); compact `40` where space is tight.
- Min-width: `64` so short labels stay tappable.
- Padding: `16` horizontal, vertical centered.
- Gap (icon to label): `8`.
- Radius: `8`; use `pill` for marketing/CTA contexts.

## Content rules

- Label length: 1–3 words, ideally a single verb phrase ("Save changes", "Add item").
- Casing: sentence case ("Save changes", not "Save Changes").
- Icon usage: at most one icon per side; never icon-only without an `aria-label`.
- Truncation: don't truncate labels — shorten the copy instead.

## Accessibility

- Role: native `<button>` (or `role="button"` with key handling).
- Labels: visible text is the accessible name; icon-only buttons need `aria-label`.
- Focus order: follows DOM order; focus ring always visible (never `outline: none` without a replacement).
- Contrast: label vs fill `>= 4.5:1` (`white` on `primary` passes).
- Hit target: `>= 44px` — the `48` height satisfies this; keep `40` compact only with adequate spacing.
- Keyboard: `Enter` and `Space` activate; `disabled` is not focusable; `loading` exposes `aria-busy="true"`.

## Do / Don't

- Do: keep one primary button per view so the main action stays obvious.
- Do: reference the height/padding/radius tokens instead of hard-coding pixels.
- Don't: use color alone to signal danger or error — pair it with text or an icon.
- Don't: disable a button silently; if it's disabled, make the reason discoverable.
