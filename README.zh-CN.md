# AI Audiobook Generator Skill

[English](./README.md) | 简体中文 | [日本語](./README.ja.md)

> 👉 也看看 [AI Podcast Voiceover Skill](https://github.com/beatra-ai/ai-podcast-voiceover-skill)

把最终书稿或课程讲稿制作成按章节排列的音频，选择适合长篇聆听的旁白，先用代表性样章校准读音和节奏，再把同一声音延续到整本内容，在 Claude Code、Cursor、Codex、Windsurf、Cline 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 把最终书稿或课程讲稿制作成按章节排列的音频，选择适合长篇聆听的旁白，通过代表性样章校准读音和节奏，再把同一声音延续到整本内容。 |
| **底层模型** | MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、MiniMax Voice Clone、Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构中篇小说《The Lighthouse Keeper&#x27;s Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。"></p>

*虚构中篇小说《The Lighthouse Keeper's Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-audiobook-narration`](skills/ai-audiobook-narration) | [SKILL.md](skills/ai-audiobook-narration/SKILL.md) | 0.3.3 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-audiobook-narration) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-audiobook-generator-skill
```

作为 Claude Code 插件：

```bash
claude plugin marketplace add beatra-ai/ai-audiobook-generator-skill
claude plugin install ai-audiobook-narration@ai-audiobook-generator-skill
```

作为 Codex 插件：

```bash
codex plugin marketplace add beatra-ai/ai-audiobook-generator-skill
codex plugin add ai-audiobook-narration@ai-audiobook-generator-skill
```

作为 GitHub Copilot CLI 插件：

```bash
copilot plugin marketplace add beatra-ai/ai-audiobook-generator-skill
copilot plugin install ai-audiobook-narration@ai-audiobook-generator-skill
```

作为 Gemini CLI 扩展：

```bash
gemini extensions install https://github.com/beatra-ai/ai-audiobook-generator-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-audiobook-generator-skill ai-audiobook-narration
```

也可以克隆本仓库，把 `skills/ai-audiobook-narration` 复制到 `~/.claude/skills/`（Claude Code）、`~/.cursor/skills/`（Cursor）、`~/.agents/skills/`（Codex）、`~/.codeium/windsurf/skills/`（Windsurf）、`~/.cline/skills/`（Cline）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-audiobook-generator-skill 安装 ai-audiobook-narration skill（目录 skills/ai-audiobook-narration），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构中篇小说《The Lighthouse Keeper&#x27;s Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*虚构中篇小说《The Lighthouse Keeper's Almanac》的代表性样章，由同一位旁白声音朗读 43 秒，含对白和反复出现的人名地名。由 Beatra AI 生成。*

在你的 Agent 里这样说：

```text
把 ./almanac-manuscript.md 做成有声书，用同一个旁白声音。先从第一章选一段有代表性的试读，让我检查语速和人名读音，再继续做剩下的部分。
```

提示词：

```text
The Lighthouse Keeper's Almanac. Chapter one: the night the lamp went dark.

On the ninth of November, at a quarter past two in the morning, the lamp at Gullrock Point went out. Maren Holloway had kept that light for eleven winters, and it had never once failed her.

She climbed the hundred and six iron steps with a candle cupped in her hand. Outside, the wind worked at the glass like a patient thief.

"Tobias," she called down the stairwell, "bring the spare wick, and bring the almanac."

Her nephew's voice came up thin and frightened. "The almanac says nothing about tonight, Aunt Maren."

"Then we shall write tonight into it," she said, and struck the match.
```

## 技术规格与输出限制

截至 2026-10-18。实时列表：https://docs.beatra.ai/zh/docs/models

- **上传** — 单个文件最大 100 MB；同时适用下方各模型的输入限制
- **语音合成** — 2 个模型（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）；FLAC、MP3、OPUS、PCM、WAV；40 种语言；采样率 8、16、22.05、24、32、44.1 kHz；单次最多 50000 字符
  - 语言（ISO 639 代码）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **声音克隆** — 1 个模型（MiniMax Voice Clone）；样本 10–300 秒，最大 20 MB；需提交授权声明
- **文生图** — 10 个模型（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）；PNG；单次最多 4 张；画布最大 16.8 MP
  - 16.8 MP（4K 档）：Wan Image 2.7 Pro（单次最多 4 张）；GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（单次 1 张）

## 为什么用 Beatra，而不是直接调用模型 API

- **一个账号用到本 skill 的全部模型** — 语音合成 2；声音克隆 1；文生图 10（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、MiniMax Voice Clone、Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）（截至 2026-10-18），一次 Beatra 登录即可使用，不必分别管理各家模型的 key。
- **花不花钱由你决定** — 只有你明确要求这次生成，或批准显示实时积分估算的确认卡后才会付费。
- **先策划，再生成** — skill 先帮你规划、指导和检查，再在 Beatra 上生成。
- **文件可以核验** — `skills/` 下的每个文件都与 cdn.beatra.ai 上的发布归档逐字节一致，每次推送前用 SHA-256 校验。
- **更新由你掌控** — 不含自更新程序；用安装时的工具更新。
- **在你的 Agent 里运行** — Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw。

## 你能得到什么

- **先理清聆听顺序** — 在开始旁白前整理章节与自然分段，让每个音频片段都容易辨认、试听和复查。
- **为整本书选择旁白** — 选择适合长时间聆听的声音，把选好的节奏和读法延续到后续章节。
- **先听样章，再做整本** — 先试听有代表性的章节，再查看后续批次费用与章节计划。

## 适用场景

- **小说与连载播讲** — 在对白、叙述、反复出现的人物和各个章节中沿用熟悉的旁白音色与读法。
- **非虚构有声书** — 预先整理人名、数字、术语与章节结构，让信息密集的书稿更适合连续聆听。
- **课程旁白** — 把有顺序的课程和讲义做成章节音频，并重点检查专业词汇读音。
- **有声书样章试听** — 用一个有代表性的章节试听旁白、节奏、读音和格式，再规划其余章节。

## 常见问题

### 开始制作需要准备什么？

至少准备一个有代表性章节的最终可朗读文本、章节顺序、语言或方言，以及重要的人名和术语读音。

### 可以先听样章再决定是否做整本吗？

可以。先制作并试听一个有代表性的样章，用它校准旁白、读音与节奏，同时查看剩余章节数量和当前费用估算。

### 整本书会保持同一旁白音色吗？

选定的旁白声音和播读方式会延续到整本内容，并通过试听复查保持读音与跨章节表现一致。

### 这个流程会交付什么？

从最终可朗读文本开始，交付由同一旁白按顺序制作的章节音频，并为原文件整理、翻译审校、多人配音混音、M4B 合并、母带处理和平台发布做好清晰组织。

## 更新与安全

自 2026 年 10 月的版本起，本 skill 不再包含自更新程序：它只运行你安装的文件，从不自行替换。
请用安装时的工具更新——`npx skills update ai-audiobook-narration` 或 `gh skill update ai-audiobook-narration`。
详见 skill 内的 `references/updates-and-security.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。

## 相关链接

- 官网 — https://www.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill
- 文档 — https://docs.beatra.cn?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill
- 控制台 — https://console.beatra.cn
- 给 AI Agent 读的说明 — https://www.beatra.cn/llms.txt （索引）· https://www.beatra.cn/llms-full.txt （全部 skill 合成一个文件）

- 微信小程序 — 国内用户微信扫码使用

<img src="assets/beatra-mini-program-qr.jpg" alt="Beatra 微信小程序码" width="160">
