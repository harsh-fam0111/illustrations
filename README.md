# Illustrations & Diagram Skills

A small toolkit of **Claude Code skills** that turn ideas, articles, and specs
into clean, hand-made visuals and design docs — drawn directly as editable SVG
(and Markdown) with code. **No API keys, no Figma, no external services.**

Ask Claude Code in plain language ("make a Xiaohei illustration for this post",
"wireframe a login screen", "give me an icon set", "document this button") and
the matching skill triggers automatically. Each skill can also be invoked
explicitly as `/<skill-name>`.

---

## What's in here

Six skills, each with its own `README.md` (usage + prompts + example gallery)
and a full `SKILL.md` spec. Generated examples live under `assets/`.

| Skill | What it makes | README | Examples |
|---|---|---|---|
| **xiaohei-illustrations** | Ian-style "Xiaohei" weird hand-drawn explainer images (white background, wobbly black linework, sparse red/orange/blue labels) | [README](.claude/skills/xiaohei-illustrations/README.md) · [SKILL](.claude/skills/xiaohei-illustrations/SKILL.md) | [`assets/xiaohei-illustrations/`](assets/xiaohei-illustrations/) |
| **warli-illustrations** | Warli (Indian tribal folk-art) illustrations — white rice-paste figures on warm terracotta | [README](.claude/skills/warli-illustrations/README.md) · [SKILL](.claude/skills/warli-illustrations/SKILL.md) | [`assets/warli-illustrations-examples/`](assets/warli-illustrations-examples/) |
| **icon-sets** | Cohesive line-icon families & spot illustrations on a fixed grid | [README](.claude/skills/icon-sets/README.md) · [SKILL](.claude/skills/icon-sets/SKILL.md) | [`assets/icon-sets-examples/`](assets/icon-sets-examples/) |
| **ui-wireframes** | App/web screen mockups & wireframes (lo-fi by default, mid-fi on request) | [README](.claude/skills/ui-wireframes/README.md) · [SKILL](.claude/skills/ui-wireframes/SKILL.md) | [`assets/ui-wireframes-examples/`](assets/ui-wireframes-examples/) |
| **user-flow-diagrams** | User flows & customer journey maps (node/arrow flows, journey grids with emotion curve) | [README](.claude/skills/user-flow-diagrams/README.md) · [SKILL](.claude/skills/user-flow-diagrams/SKILL.md) | [`assets/user-flow-diagrams-examples/`](assets/user-flow-diagrams-examples/) |
| **design-system-docs** | Design-system & component specs in Markdown, with optional SVG anatomy/state sheets | [README](.claude/skills/design-system-docs/README.md) · [SKILL](.claude/skills/design-system-docs/SKILL.md) | [`assets/design-system-docs-examples/`](assets/design-system-docs-examples/) |

---

## How to use

1. **Just ask.** Describe what you want in plain language; the relevant skill
   triggers on its own. Or invoke it directly: `/xiaohei-illustrations`,
   `/ui-wireframes`, `/icon-sets`, `/user-flow-diagrams`, `/warli-illustrations`,
   `/design-system-docs`.
2. **Each skill follows its own workflow** — illustration skills digest the
   source, propose a shot list, then render one image per shot; the others go
   straight to the artifact. See the skill's README for prompt examples.
3. **Output is saved under `assets/`** as editable `.svg` (or `.md`), named in
   order. SVGs render in any browser and are easy to tweak by hand.

For the best copy-paste prompts and a per-skill example gallery, open that
skill's README (linked above).

---

## Repository layout

```
.
├── README.md                     ← you are here (project index)
├── CLAUDE.md                     ← project instructions for Claude Code
├── .claude/skills/               ← the skills
│   ├── xiaohei-illustrations/    ← README.md + SKILL.md
│   ├── warli-illustrations/      ← README.md + SKILL.md
│   ├── icon-sets/                ← README.md + SKILL.md
│   ├── ui-wireframes/            ← README.md + SKILL.md
│   ├── user-flow-diagrams/       ← README.md + SKILL.md
│   └── design-system-docs/       ← README.md + SKILL.md
└── assets/                       ← generated examples, one folder per skill
    ├── xiaohei-illustrations/
    ├── warli-illustrations-examples/
    ├── icon-sets-examples/
    ├── ui-wireframes-examples/
    ├── user-flow-diagrams-examples/
    └── design-system-docs-examples/
```

---

## Conventions

- **Editable by default.** Everything is generated as SVG/Markdown with code, so
  outputs are version-controllable and easy to edit (change a path, recolor a
  stroke, nudge a label) — no full regeneration needed.
- **One artifact = one idea.** Illustrations and diagrams each express a single
  core structure; don't cram everything into one picture.
- **English-only labels** across all skills and examples.
- **Examples are for calibration, not copying.** They show the house style
  (line weight, whitespace, color restraint); the skills reinvent a fresh
  composition each time.

See [`CLAUDE.md`](CLAUDE.md) for the project-level instructions Claude Code
follows in this repo.
