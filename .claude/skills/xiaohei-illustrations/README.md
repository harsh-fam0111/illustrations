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
Use $ian-xiaohei-illustrations 先不要生图。
请分析下面这篇文章哪里值得配图，输出 5 张左右的 shot list。
每张图写清楚：
- 放在哪个段落后
- 图的主题
- 核心意思
- 结构类型
- 小黑在图里做什么
- 建议元素
- 建议中文标注词

<粘贴文章>
```

### Body illustrations for an article

```text
Use $ian-xiaohei-illustrations 把下面这篇文章生成 4 张小黑怪诞正文配图。
要求：16:9 横版、纯白背景、黑色手绘线稿、少量红橙蓝中文手写批注。
每张图只讲一个核心结构，不要做 PPT 信息图，不要可爱卡通。

<粘贴文章>
```

### Long-form illustration strategy

```text
Use $ian-xiaohei-illustrations 给这篇长文做配图策略。
不要平均配图，只挑认知锚点：核心判断、输入输出闭环、前后对比、常见坑、承接路径。
默认 6-8 张，先输出 shot list，不要生成图片。

<粘贴文章>
```

### One image for a single point

```text
Use $ian-xiaohei-illustrations 为这个观点生成一张 16:9 正文配图：

信任不是喊出来的，而是一块证据一块证据铺过去。

画面要怪诞但清爽，小黑必须承担核心动作。
中文标注最多 5 个，短一点。
```

### Workflow theme

```text
Use $ian-xiaohei-illustrations 为"把一条原始素材加工成流量、信任、转化三种内容"生成一张图。
不要画正式流程图，不要复刻一鱼多吃旧案例。
请重新发明一个新的低科技隐喻，让小黑参与核心动作。
```

### Edit — remove a title

```text
Use $ian-xiaohei-illustrations 帮我编辑这张图。
去掉左上角的"Workflow / 流程图"标题和下划线，其他内容保持不变。
不要新增任何文字或物件。
```

### Edit — make Xiaohei carry the action

```text
Use $ian-xiaohei-illustrations 这张图方向对，但小黑有点像装饰。
请保持核心意思不变，重生成一版：让小黑成为真正推动结构运转的人。
画面更怪一点，但仍然纯白、清爽、少字。
```

### Generate a style sample set

```text
Use $ian-xiaohei-illustrations 输出 5 个不同主题的小黑正文配图效果。
主题分别覆盖：信息过载、产品验证、内容复利、一人公司、信任建立。
每张单独生成，不要拼成一张。
```

---

## Best examples

A small gallery for style calibration — line density, whitespace, color
restraint, and how Xiaohei carries the core action. **Calibrate to these; never
copy their compositions** (the skill reinvents a fresh metaphor every time).

| Preview | File | Theme | Metaphor — what Xiaohei does |
|---|---|---|---|
| Trust = bricks | [01-trust-evidence-bricks.svg](../../../assets/xiaohei-illustrations/01-trust-evidence-bricks.svg) | 信任建立 / trust | Bridges a void by laying evidence-bricks one at a time toward a far "trust" flag — a crossed-out megaphone says it's *not* shouted. |
| Info firehose | [02-info-firehose.svg](../../../assets/xiaohei-illustrations/02-info-firehose.svg) | 信息过载 / overload | Holds up a tiny cup under a giant gushing faucet, catching almost none of the torrent. |
| Content snowball | [03-content-snowball.svg](../../../assets/xiaohei-illustrations/03-content-snowball.svg) | 内容复利 / compounding | Pushes a snowball up a slope; the same push rolls up ever more content toward a huge "compounding" ball. |
| Info courier | [info-mover/01-info-courier.svg](../../../assets/info-mover-illustrations/01-info-courier.svg) | 搬运信息 / busywork | Shuttles a stack of copy-pasted sheets between Tool A and Tool B, blank thought bubble overhead. |

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
