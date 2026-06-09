# 分镜故事版交付规范

Use this file when the user asks for "分镜图", "分镜故事版", "像我发的图那种", storyboard sheets, contact sheets, shot boards, or visual storyboard tables.

The deliverable should not stop at a text-only shot list. It should include:

- one storyboard table with thumbnail images;
- one image prompt per shot;
- actual storyboard panel images when image generation tools are available;
- a contact sheet / story board page for review;
- a production-ready table matching the user's sample style.

## Default Output Folder

When creating files, use:

```text
张艺谋导演分镜_项目名_YYYYMMDD/
├── 00_导演风格设定.md
├── 01_分镜脚本.md
├── 02_分镜图Prompt_逐镜.md
├── 03_分镜故事版.md
├── 04_分镜故事版.html
├── storyboard_panels/
│   ├── S001.png
│   ├── S002.png
│   └── ...
├── storyboard_sheets/
│   ├── story_sheet_01.png
│   └── story_sheet_01.pdf
└── 99_执行状态.md
```

If the user only wants a conversational answer, still format the storyboard table in markdown and provide per-shot prompts.

## Storyboard Table Columns

Match this structure unless the user asks otherwise:

| Column | Required content |
| --- | --- |
| 镜号 | S001, S002... |
| 分镜图 | embedded image path or prompt placeholder |
| 景别 | 全景/远景/中景/近景/特写/过肩/俯拍/仰拍 |
| 运镜 | 固定/缓慢前推/横移/跟拍/手持/切入/拉远/俯仰 |
| 情绪/动作 | blocking, gesture, emotional pressure, visual turn |
| 台词 | subtitle-ready dialogue or "-" |
| 音效 | diegetic sound, motif, silence, music cue |
| 时长 | seconds |
| 张艺谋式功能 | color/ritual/object/crowd/space function |

For a page like the user's sample, keep 6-8 shots per page. If there are more than 8 shots, create multiple sheets.

## Visual Style Modes

Choose one:

### Pencil Storyboard Mode

Use for planning and production communication.

Style:

- black-and-white pencil sketch;
- clean linework;
- light grayscale shading;
- readable faces/hands/props;
- vertical 9:16 frame inside each panel when the project is for short drama;
- no polished poster look.

Prompt phrase:

```text
black and white pencil storyboard sketch, clean production storyboard panel, light grayscale shading, readable character blocking, clear symbolic prop, vertical 9:16 composition, no color, no text
```

### Cinematic Keyframe Mode

Use for AI image/video generation and mood approval.

Style:

- cinematic lighting;
- chosen color system;
- realistic short-drama characters;
- precise blocking;
- visible symbolic object.

Prompt phrase:

```text
cinematic keyframe for an original Chinese vertical short drama, Zhang Yimou-inspired high-level visual principles without copying any film, strong color dramaturgy, precise blocking, symbolic object, restrained performance, vertical 9:16
```

### Hybrid Pitch Board Mode

Use when the user wants something visually impressive but still useful.

Style:

- storyboard linework plus selective color accent;
- one dominant story color only;
- clean production board;
- each panel readable at small size.

Prompt phrase:

```text
production storyboard panel with pencil linework and one controlled color accent, cinematic composition, symbolic object emphasized, vertical 9:16, no text
```

## Panel Prompt Template

```markdown
### S001
- 镜头功能:
- 景别:
- 运镜:
- 构图:
- 色彩/光线:
- 人物调度:
- 关键道具:
- 情绪:
- 声音:
- 时长:

Prompt:
original Chinese short-drama storyboard panel, [style mode], [location], [shot size], [camera angle], [blocking], [symbolic object], [color/light rule], [emotion], Zhang Yimou-inspired high-level cinematic principles without copying any film, vertical 9:16, no text

Negative:
direct recreation of any existing film, random lanterns, tourist costume cliche, overacting, unreadable faces, extra text, watermark, messy hands
```

## Board-Level Prompt

Use only when generating one full sheet at once. Prefer generating separate panels first, then composing them into a sheet.

```text
one clean Chinese storyboard sheet for a vertical short drama, 720x1280 portrait page, 8 rows, table columns for shot number, storyboard image, shot size, camera movement, action/emotion, dialogue, sound, duration, black and white pencil storyboard thumbnails, production planning document, clean grid layout, readable but no tiny paragraph text inside generated image
```

Warning: image models often fail at small readable table text. Better workflow:

1. Generate image panels separately.
2. Create the table in markdown/html using real text.
3. Embed panels into the table.
4. Export/screenshot the HTML if a PNG sheet is needed.

## Zhang-Inspired Storyboard Requirements

Each board must include at least five of these:

- a ritual action;
- an object close-up;
- a crowd or authority arrangement;
- a color or light rule;
- a silence beat;
- a door/window/frame-within-frame;
- a hand gesture that changes power;
- a first/last image rhyme;
- an image cliffhanger.

## Example Shot Progression

### Family Banquet Short Drama

| Shot | Image idea | Function |
| --- | --- | --- |
| S001 | Symmetrical banquet table, empty center chair, red envelope under bowl | establish ritual prison |
| S002 | Close-up: elder's hand taps chopsticks three times | sound motif |
| S003 | Over-shoulder: heroine at table edge, everyone facing her | crowd pressure |
| S004 | Close-up: red envelope opens, hospital bill inside | object evidence |
| S005 | Medium: heroine pours toast wine onto ledger | ritual break |
| S006 | Wide: family turns from heroine to eldest son | public reversal |
| S007 | Close-up: red stain spreads over signature | visual verdict |
| S008 | Doorway: unseen witness steps into frame | cliffhanger |

### Hospital Window Short Drama

| Shot | Image idea | Function |
| --- | --- | --- |
| S001 | Queue number screen, protagonist clutching bill | institutional pressure |
| S002 | Close-up: missing red stamp | object obstacle |
| S003 | Through glass: clerk expressionless, patient blurred behind | space as power |
| S004 | Crowd behind protagonist, phones raised | public pressure |
| S005 | Protagonist places medicine bag at payment window | body/object challenge |
| S006 | Printer stops; fluorescent hum cuts to silence | reveal beat |
| S007 | Stamp hits paper in extreme close-up | verdict |
| S008 | Patient curtain opens with empty bed | cliffhanger |

## Markdown Storyboard Table Template

```markdown
| 镜号 | 分镜图 | 景别 | 运镜 | 情绪/动作 | 台词 | 音效 | 时长 | 张艺谋式功能 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| S001 | ![](storyboard_panels/S001.png) | 全景/建立镜头 | 固定镜头, 轻微前推 | [动作] | - | [音效] | 2s | [仪式/空间/颜色] |
```

## HTML Sheet Requirements

When creating `04_分镜故事版.html`:

- page ratio portrait 720x1280 or A4 portrait;
- title top-left, resolution/format top-right;
- table grid with thin gray borders;
- image column about 28-35% width;
- text columns compact but readable;
- 6-8 shots per page;
- use local relative image paths;
- no decorative backgrounds;
- print CSS included for PDF export.

## Generation Workflow

### If Image Generation Is Available

1. Write `01_分镜脚本.md`.
2. Write `02_分镜图Prompt_逐镜.md`.
3. Generate `storyboard_panels/S001.png`, `S002.png`, etc.
4. Write `03_分镜故事版.md` embedding the images.
5. Create `04_分镜故事版.html`.
6. If browser/screenshot tooling is available, export `storyboard_sheets/story_sheet_01.png`.
7. Record what was generated in `99_执行状态.md`.

### If Image Generation Is Not Available

1. Still write all prompts.
2. In the table's 分镜图 column, use `[待生成: S001]`.
3. Add exact prompt blocks.
4. State the blocker in `99_执行状态.md`.

## Per-Shot Quality Gate

For every panel:

- Is the shot readable as a small thumbnail?
- Is the main action visible without reading the text?
- Is the symbolic object visible?
- Does the shot have a clear function in the story?
- Does it avoid copying an existing film image?
- Is the frame usable for 9:16 short drama?

## Full-Board Quality Gate

Before delivery:

- Does the board tell the story visually from top to bottom?
- Are shot sizes varied?
- Is there at least one object close-up?
- Is there one public-pressure shot?
- Is there one ritual-breaking shot?
- Are durations realistic?
- Are dialogue lines short enough for subtitles?
- Does the last panel end on an image cliffhanger?
