# AI Audiobook Generator Skill

[English](./README.md) | 简体中文

把最终书稿或课程讲稿制作成按章节排列的音频，选择适合长篇聆听的旁白，先用代表性样章校准读音和节奏，再把同一声音延续到整本内容，在 Claude Code、Codex 或 OpenClaw 里直接完成。

> [!IMPORTANT]
> 生成需要 [Beatra](https://beatra.ai) 账号并消耗积分，安装本身不收费。

| 问题 | 回答 |
| --- | --- |
| **能做什么** | 把最终书稿或课程讲稿制作成按章节排列的音频，选择适合长篇聆听的旁白，通过代表性样章校准读音和节奏，再把同一声音延续到整本内容。 |
| **运行要求** | Python 3.10+，以及能加载 `SKILL.md` 的 Agent |
| **费用** | 安装免费。每次生成消耗 Beatra 账号积分，只有你明确要求这次生成或批准确认卡后才会付费。 |
| **支持的 Agent** | Claude Code、Codex、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构中篇小说《The Lighthouse Keeper&#x27;s Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。"></p>

*虚构中篇小说《The Lighthouse Keeper's Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-audiobook-narration`](skills/ai-audiobook-narration) | [SKILL.md](skills/ai-audiobook-narration/SKILL.md) | 0.2.2 |

本仓库由 [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-audiobook-narration) 自动发布，问题请到那里反馈。

## 安装

使用 [`skills`](https://skills.sh) CLI：

```bash
npx skills add beatra-ai/ai-audiobook-generator-skill
```

使用 GitHub CLI：

```bash
gh skill install beatra-ai/ai-audiobook-generator-skill ai-audiobook-narration
```

也可以克隆本仓库，把 `skills/ai-audiobook-narration` 复制到 `~/.claude/skills/`（Claude Code）、`~/.agents/skills/`（Codex）或 `~/.openclaw/skills/`（OpenClaw）。

或者把下面这段话发给你的 Agent：

```text
从 https://github.com/beatra-ai/ai-audiobook-generator-skill 安装 ai-audiobook-narration skill（目录 skills/ai-audiobook-narration），然后按它的 SKILL.md 连接我的 Beatra 账号。
```

## 效果示例

<p align="center"><img src="assets/cover.webp" width="800" alt="虚构中篇小说《The Lighthouse Keeper&#x27;s Almanac》的有声书封面，画面是风暴中只剩一支烛光的灯塔。由 Beatra AI 生成。"></p>

[▶ 试听（MP3）](assets/sample.mp3)

*虚构中篇小说《The Lighthouse Keeper's Almanac》的代表性样章，由同一位旁白声音朗读 43 秒，含对白和反复出现的人名地名。由 Beatra AI 生成。*

提示词：

```text
The Lighthouse Keeper's Almanac. Chapter one: the night the lamp went dark.

On the ninth of November, at a quarter past two in the morning, the lamp at Gullrock Point went out. Maren Holloway had kept that light for eleven winters, and it had never once failed her.

She climbed the hundred and six iron steps with a candle cupped in her hand. Outside, the wind worked at the glass like a patient thief.

"Tobias," she called down the stairwell, "bring the spare wick, and bring the almanac."

Her nephew's voice came up thin and frightened. "The almanac says nothing about tonight, Aunt Maren."

"Then we shall write tonight into it," she said, and struck the match.
```

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

## 更新

安装后的 skill 每天最多检查一次新版本，替换前先校验官方归档，任何一步失败都不会动你已安装的版本。
随时可以关闭，见 skill 内的 `references/automatic-updates-and-safety.md`。

## 许可证

[MIT-0](LICENSE)：可自由使用、修改和再分发，包括商用，无需署名；与这些 skill 在 ClawHub 上的条款一致。
