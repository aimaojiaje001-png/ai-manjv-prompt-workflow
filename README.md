# AI 漫剧提示词工作流 Skill



## 包含内容

- 角色视觉 DNA 与多角度人物设定图
- 万物生式人物和场景资产拆解
- 场景、道具、局部资产与色卡参考图
- Image2 / SD2.0 资产图提示词
- 故事板、线稿分镜和奇幻动作分镜
- Seedance / SceneDance / 短剧镜头视频提示词
- 首尾帧、一镜到底和机甲变身连续性
- 活人感表演、镜头连续性和分镜自检

## 安装

把 skill 目录复制到 Codex skills 目录：

```powershell
git clone https://github.com/aimaojiaje001-png/ai-manjv-prompt-workflow.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.codex\skills" | Out-Null
Copy-Item -Recurse -Force `
  .\ai-manjv-prompt-workflow\skills\ai-manjv-prompt-workflow `
  "$env:USERPROFILE\.codex\skills\"
```

安装后重新打开 Codex，或刷新当前会话的 skill 列表。

## 使用示例

```text
Use $ai-manjv-prompt-workflow to turn this story into AI 短剧生图资产、故事板和视频提示词。
```

也可以直接描述需求，例如：

```text
把这段小说拆成 AI 短剧角色资产图、场景资产图、首尾帧和 Seedance 镜头提示词。
```

## 目录结构

```text
skills/
  ai-manjv-prompt-workflow/
    SKILL.md
    agents/openai.yaml
    references/prompt-patterns.md
    references/source-coverage.md
```



## 许可证

当前仓库未声明开源许可证。公开仓库仅表示可被访问，不代表自动授权复制、分发、商用或再授权。
