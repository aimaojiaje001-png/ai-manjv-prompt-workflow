---
name: ai-manjv-prompt-workflow
description: Use when producing Chinese AI漫剧 or AI short-drama image/video prompt packages from novels, scripts, story beats, or reference images, especially for Image2, Seedance, SD2.0, character visual DNA, character/scene/prop/color asset sheets, 万物生-style asset extraction, storyboard boards, line-art shot boards, one-take first/last frames, mecha transformation continuity, shot continuity checks, or “活人感” performance prompts.
---

# AI 漫剧提示词工作流

## Overview

把小说、剧本或镜头想法转成 AI 漫剧/AI 短剧的生图与视频提示词。只处理资产图、故事板、首尾帧、视频镜头、连续性和表演相关内容；平台邀请码、PSD 工具、配音网站、纯编剧设定不进入本 skill。

## Quick Start

1. 先判断用户要的是哪一种交付：万物生式人物和场景资产拆解、角色资产、场景/道具资产、色板、故事板、线稿分镜、连续动作视频、机甲变身首尾帧、一镜到底、活人感表演，或完整生图短剧工作流。
2. 读取 `references/prompt-patterns.md` 中对应模板，不需要一次加载所有模板之外的外部来源。
3. 若用户只给小说原文，先输出剧情压缩和资产清单；若用户已给分镜/资产，直接进入对应提示词。
4. 对每条提示词保留可替换字段，例如【角色视觉DNA】【场景描述】【故事=】【镜号】【时长】。
5. 输出时区分“给思考模型的分析要求”和“给图像/视频模型的最终生成提示词”。

## Workflow

### 1. Normalize Story Input

将原文按时间顺序压成短句，每句包含“谁做了什么/发生什么 + 关键结果或反应”。不要单独写外貌或背景；视觉信息必须融入动作、冲突、结果或人物反应。

### 2. Build Asset Foundation

先做资产再做分镜：

- 角色：从身份、经历、欲望、恐惧、行为习惯推导视觉 DNA，再生成角色三视图/多角度设定图。
- 场景：输出全景、俯视关系、关键局部细节、材质、光影、禁用项。
- 道具/配饰：说明来源故事、功能、状态和与人物关系。
- 色板：从参考图提取 10-15 个核心 HEX 色，并标注每个颜色的叙事功能。
- 万物生式拆解：从小说或目标短片中一次性列出人物状态、场景层级、道具符号、氛围色彩和可直接生图的资产提示词。

### 3. Generate Storyboard Layer

故事板提示词应让模型生成导演预制作板，而不是单张插画。必须包含：

- 顶部共享创意指导：镜头数量、统一调色、整体环境。
- 角色与风格参考：同一角色多角度、一致身份、服装、配饰和体型。
- 环境/场景设计：空间路径、机位、镜头类型。
- 编号故事板帧：景别、镜头感觉、运动方式、动作、情绪推进、时长。
- 灯光/情绪/关键词、音频氛围、摄影哲学。

### 4. Generate Video Layer

视频提示词要写“状态如何连续变化”，不要只写静态画面。15 秒左右的连续动作建议拆成 0-3s、3-6s、6-10s、10-13s、13-15s 的节奏段。人物表演必须由心理动机驱动，并显式写出眼神、停顿、语速、微表情和伴随性肢体动作。

### 5. Validate Continuity

每组相邻镜头检查动作相位、180 度轴线、30 度规则、景别差异、视线匹配、运动向量、服装/伤痕/道具/环境/光线/天气、对白和剪辑动机。无动机的相似硬切必须退回重写。

## Output Rules

- 默认中文输出，保留 Image2、Seedance、SD2.0、character turnaround sheet 等原有技术词。
- 给图像模型的提示词必须包含画幅比例、主体、构图、风格、光影、质量和负面限制。
- 含文字的画面要提醒文字清晰可读，但关键 UI/字幕不要依赖生图模型生成，必要时建议后期叠字。
- 排除与生图/AI 短剧无关的页面信息：邀请码、充值、平台教程、PSD 拆图、纯配音网站、纯编剧大师 system prompt。
- 当飞书来源只显示视频、附件或会员文档说明而没有正文时，标注“来源不可见”，不要补写不存在的原文提示词。
- 若用户要求溯源或完整来源覆盖情况，读取 `references/source-coverage.md`。

## Reference

- `references/prompt-patterns.md`: 可复用模板和模块化提示词。
- `references/source-coverage.md`: 飞书索引及子页的可见内容覆盖情况。
