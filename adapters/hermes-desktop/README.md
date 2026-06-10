# Hermes Desktop Adapter

这个目录用于让 `张艺谋Skill` 适配 Hermes Desktop / Hermes Agent 类桌面 agent。

## 使用方式

Hermes Desktop 通常可以读取当前 workspace 文件。推荐把本仓库作为一个 skill/project 包放入 Hermes 可访问目录：

```text
{Hermes workspace}/skills/zhang-yimou-skill/
```

也可以直接把 GitHub 仓库作为上下文源：

```text
https://github.com/Ye-Zayne/zhang-yimou-skill
```

## Hermes 读取顺序

1. `SKILL.md`：总规则和导演工作流。
2. `references/`：导演语言、短剧压缩、分镜表和输出模板。
3. `examples/complete-case/gray-bell-campus/`：完整图片案例。
4. `adapters/hermes-desktop/README.md`：当前适配说明。

## 推荐系统提示

```text
你正在使用 zhang-yimou-skill。
必须把短剧创意拆成文件化导演项目包：
1. 剧本与流程清单
2. 镜头表与单元切分
3. 站位图
4. 分镜表 + 图片故事版/3x3九宫格
5. Seedance Prompt 逐单元
6. 询问后再生成视频
7. 询问后再自动剪辑
所有图片输出必须能在 Markdown 中预览，不能只给文字占位。
```

## Hermes 图片规则

- 支持 SVG 时，优先输出 SVG 故事版、站位图、九宫格，保证跨平台可预览。
- 支持图像生成工具时，基于 `storyboards/` 中的 image prompt 生成 PNG/JPG。
- 如果 Hermes 当前没有图像工具，必须保留 `images/TODO_*.md` 或 `*_prompt.md`，明确下一步生成命令。

## 视频与剪辑

第六步和第七步是可选外部动作，必须先问用户：

```text
是否需要继续调用即梦/Dreamina CLI 生成视频？
是否需要继续生成自动剪辑 manifest 并调用剪辑工具？
```

用户确认前，不自动调用外部 CLI，不批量消耗额度。
