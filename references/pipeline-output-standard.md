# Director Style Storyboard Pipeline 输出规范

Use this file when the user wants the output form shown in a staged production table: 风格锁定 -> 剧本规范化 -> 专业分镜脚本 -> 导演分镜表 -> 人物设定 -> 场景设定 -> 静态确认 -> 视频 prompt -> 视频宫格分镜.

This is the full file-based pipeline for turning "短剧剧本 + 张艺谋启发导演视觉风格 + 人物场景参考" into a complete director-style storyboard and Seedance-ready production package.

## 一句话总结

Director Style Storyboard Pipeline 适合把"短剧剧本 + 导演视觉风格 + 人物场景参考"推进成一套从文档、分镜、设定图到 Seedance 视频 prompt 与视频生成的完整导演风格分镜生产链。

## 适用场景

Use this pipeline when the user wants:

- a complete project package, not only a chat answer;
- 张艺谋启发的导演风格锁定;
- standardized screenplay rewrite;
- professional shot-by-shot storyboard script;
- character and scene reference assets;
- illustrated director storyboard sheets;
- static confirmation before video prompt generation;
- Seedance / 即梦 video prompts;
- 2x2 or 3x3 video reference grids;
- production handoff files organized by folder.

## 不适合的情况

Do not force this full pipeline when:

- the user only wants one quick storyboard board image;
- the user does not need a director style and only wants ordinary shot splitting;
- the user only needs the four-doc set: `镜头表与单元切分.md`, `站位图.md`, `关键帧Prompt_逐张拆分版.md`, `Seedance_Prompt_逐单元.md`;
- the user wants to skip static confirmation and immediately batch-run video;
- the user wants to recreate a specific original film scene rather than borrow high-level director language.

In those cases, use a lighter workflow or route conceptually to Storyboard Board, script-to-storyboard-prompts, storyboard-orchestrator-video, or storyboard-blocking-keyframes if those skills are available.

## Required Output Table

Always include a stage/output table near the top of the result:

| 阶段 | 输出 |
| --- | --- |
| 风格锁定 | `docs/00A_导演风格设定.md` |
| 剧本规范化 | `docs/01_规范剧本.md` |
| 专业分镜脚本 | `docs/02_专业分镜脚本.md` |
| 导演分镜表 | 竖版、低细节、黑白手绘结构分镜图 |
| 人物设定 | 面部特写、面部三视图、全身三视图等角色资产 |
| 场景设定 | 场景正反打、全景、俯视图和 9 宫格设定图 |
| 静态确认 | 等待用户确认风格、镜头、人物和场景 |
| 视频 prompt | `docs/04_Seedance_视频Prompt_15秒单元.md` |
| 视频宫格分镜 | 2x2 或 3x3 无文字视频参考图 |

## Default Directory Structure

Create or describe this structure for complete projects:

```text
storyboard_pipeline/{项目名}/
├── 00_流程清单.md
├── docs/
│   ├── 00A_导演风格设定.md
│   ├── 01_规范剧本.md
│   ├── 02_专业分镜脚本.md
│   ├── 03_静态资产确认.md
│   └── 04_Seedance_视频Prompt_15秒单元.md
├── characters/
│   ├── {角色名}_面部特写.png
│   ├── {角色名}_面部三视图.png
│   └── {角色名}_全身三视图.png
├── scenes/
│   ├── {场景名}_正向.png
│   ├── {场景名}_反打.png
│   ├── {场景名}_全景.png
│   ├── {场景名}_俯视图.png
│   └── {场景名}_9宫格设定图.png
├── storyboards/
│   ├── panels/
│   │   ├── S001.png
│   │   └── S002.png
│   ├── sheets/
│   │   ├── 分镜故事版_01.html
│   │   └── 分镜故事版_01.png
│   └── 03_分镜故事版.md
├── director_sheets/
│   ├── 导演分镜表_竖版.png
│   ├── 导演分镜表_低细节.png
│   └── 导演分镜表_黑白手绘结构.png
├── video_grids/
│   ├── U01_2x2_无文字参考图.png
│   └── U01_3x3_无文字参考图.png
├── videos/
│   ├── manifest.md
│   ├── manifest.json
│   └── seedance_commands.sh
└── 99_执行状态.md
```

Adjust exact folder names for the user's current workspace, project title, and scene names. Keep the core outputs organized around director style, standardized script, professional storyboard script, static assets, video prompts, and video files.

## Workflow

### Phase 1: 风格锁定

Write `docs/00A_导演风格设定.md`.

Must include:

- chosen Zhang-inspired period or mixture;
- one-sentence visual thesis;
- color system;
- ritual/social order;
- symbolic object system;
- space and crowd grammar;
- performance style;
- sound motif;
- forbidden visual cliches;
- production budget assumptions.

Quality bar:

- It must be an executable production rulebook, not a film-review essay.
- It must define what to shoot, how to block, what colors/props to use, and what not to do.

### Phase 2: 剧本规范化

Write `docs/01_规范剧本.md`.

Must include:

- normalized title, logline, duration, episode/scene count;
- character list;
- location list;
- scene-by-scene dramatic beats;
- action and dialogue with readable subtitles;
- image hooks and cliffhangers;
- retained original intent;
- changes made for director style.

Quality bar:

- Do not change the story type only for style.
- Preserve core character intention.
- Make every scene playable and shootable.

### Phase 3: 专业分镜脚本

Write `docs/02_专业分镜脚本.md`.

Must include:

- shot number;
- unit/scene;
- duration;
- shot size;
- camera angle;
- camera movement;
- blocking;
- action;
- dialogue/subtitle;
- sound;
- visual motif;
- Seedance-readiness notes.

Quality bar:

- The director storyboard table must clearly express 镜号, 构图, 机位, 动线, and 节奏.
- Every 10-15 seconds should have an escalation or visual turn.

### Phase 4: 导演分镜表

Create director storyboard sheets in `director_sheets/` and/or `storyboards/sheets/`.

Required variants:

- 竖版: phone-first 9:16 review board.
- 低细节: rough composition and rhythm board.
- 黑白手绘结构: pencil/sketch structure board for production discussion.

Optional:

- cinematic color keyframes after static style is approved.

Quality bar:

- Use no embedded explanatory text inside generated image panels.
- If text labels are needed, create them in HTML/Markdown, not inside AI-generated images.
- Panel images should be readable at thumbnail size.

### Phase 5: 人物设定

Create or prompt assets in `characters/`.

Required for each main character:

- face close-up;
- face three-view sheet;
- full-body three-view sheet;
- age impression;
- costume silhouette;
- key prop continuity;
- expression range if needed.

Quality bar:

- Character identity, age, costume silhouette, and key props must remain consistent.
- Do not proceed to Seedance prompt if character identity is unstable.

### Phase 6: 场景设定

Create or prompt assets in `scenes/`.

Required for each key scene:

- front view;
- reverse angle;
- wide shot;
- top view;
- 9-grid scene design board.

Must define:

- spatial structure;
- light direction;
- color temperature;
- main shooting axis;
- entrance/exit paths;
- authority/crowd positions;
- prop placement.

Quality bar:

- Scene design must show space, not only atmosphere.
- Reverse shots and top views must support continuity.

### Phase 7: 静态确认

Write `docs/03_静态资产确认.md` and stop.

The confirmation must summarize:

- locked director style;
- approved/review-needed shots;
- character assets;
- scene assets;
- storyboard sheets;
- known inconsistencies;
- what will be generated next.

Hard rule:

- Do not continue to `docs/04_Seedance_视频Prompt_15秒单元.md` or batch video generation before static assets are confirmed, unless the user explicitly says to continue despite the risk.

Suggested user-facing line:

```text
静态资产已到确认点。请确认：风格、镜头、人物、场景是否可以锁定。确认后我再继续生成 Seedance 视频 prompt 和视频宫格参考图。
```

### Phase 8: 视频 Prompt

After static confirmation, write `docs/04_Seedance_视频Prompt_15秒单元.md`.

Break video into 15-second units by default.

Each unit must include:

- unit number;
- source shots;
- duration;
- start/end image reference;
- character references;
- scene references;
- motion design;
- camera movement;
- performance;
- sound;
- continuity constraints;
- negative prompt;
- exact Seedance-ready prompt.

Quality bar:

- The prompt must be grounded in confirmed character and scene assets.
- No prompt should introduce new costume, face, location, color system, or camera axis unless documented.

### Phase 9: 视频宫格分镜

Create 2x2 or 3x3 no-text video reference grids in `video_grids/`.

Rules:

- no shot number text, subtitles, labels, watermarks, titles, or explanatory text inside the grid image;
- use images only;
- each tile must show a key moment from the video unit;
- maintain character and location continuity;
- prefer 2x2 for 15-second units with four major beats;
- prefer 3x3 for complex units with movement progression.

Quality bar:

- A video grid should help video generation, not replace the storyboard table.
- It should communicate motion progression visually without words.

## `00_流程清单.md` Template

```markdown
# 流程清单

| 阶段 | 状态 | 输出 | 备注 |
| --- | --- | --- | --- |
| 风格锁定 | pending/in_progress/done | docs/00A_导演风格设定.md |  |
| 剧本规范化 | pending/in_progress/done | docs/01_规范剧本.md |  |
| 专业分镜脚本 | pending/in_progress/done | docs/02_专业分镜脚本.md |  |
| 导演分镜表 | pending/in_progress/done | director_sheets/ |  |
| 人物设定 | pending/in_progress/done | characters/ |  |
| 场景设定 | pending/in_progress/done | scenes/ |  |
| 静态确认 | pending/in_progress/done | docs/03_静态资产确认.md | stop before video prompt |
| 视频 prompt | pending/in_progress/done | docs/04_Seedance_视频Prompt_15秒单元.md |  |
| 视频宫格分镜 | pending/in_progress/done | video_grids/ | no text in image |
```

## Quality Standards

- 导演风格必须先锁定，再进入任何剧本、图像或视频 prompt 生产。
- `docs/00A_导演风格设定.md` 必须是可执行的制作规则，而不是影评式散文。
- 分镜脚本必须保留原剧情和角色意图，不能为了风格改变故事类型。
- 导演分镜表必须清楚表达镜号、构图、机位、动线和节奏。
- 人物设定必须保持角色身份、年龄感、服装轮廓和关键道具连续。
- 场景设定必须体现空间结构、光线方向、色彩温度和摄影轴线。
- 视频宫格图不能出现镜号、字幕、角标、水印、标题或说明文字。
- 静态资产确认前，不能继续生成 Seedance 视频 prompt 或批量视频。

## Delivery Response Format

When reporting progress or final delivery, use:

```markdown
**输出形式**
| 阶段 | 输出 |
| --- | --- |
| 风格锁定 | docs/00A_导演风格设定.md |
...

**项目目录**
storyboard_pipeline/{项目名}/ ...

**当前状态**
- Done:
- Waiting:
- Next:

**质量标准**
- ...
```

Keep this compact in chat; put full detail in files.
