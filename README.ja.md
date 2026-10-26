# AI Audiobook Generator Skill

[English](./README.md) | [简体中文](./README.zh-CN.md) | 日本語

> 👉 こちらもどうぞ [AI Podcast Voiceover Skill](https://github.com/beatra-ai/ai-podcast-voiceover-skill)

完成原稿や講座テキストを、1 人のナレーターによる章ごとの音声に。まず代表的なサンプル章を確認してから細部を調整。Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw のどれからでもそのまま使えます。

> [!IMPORTANT]
> 生成には [Beatra](https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill) アカウントが必要で、クレジットを消費します。スキル自体のインストールは無料です。

| 項目 | 内容 |
| --- | --- |
| **できること** | 完成した原稿を、同じナレーターによる章ごとの音声にします。まず代表的な一節のサンプルを確認し、読み方やテンポを整えてから残りの制作に進めます。 |
| **モデル** | MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo、MiniMax Voice Clone、Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live |
| **動作要件** | Python 3.10 以上と、`SKILL.md` を読み込めるエージェント |
| **費用** | インストールは無料。生成のたびに Beatra アカウントのクレジットを消費しますが、課金されるのは、その生成を明示的に依頼したとき、または確認カードを承認したときだけです。 |
| **対応エージェント** | Claude Code、Cursor、Codex、Windsurf、Cline、OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="架空の中編小説 The Lighthouse Keeper&#x27;s Almanac の販売ページ用カバー。嵐に打たれる灯台を 1 本のろうそくが照らす。Beatra AI で生成。"></p>

*架空の中編小説 The Lighthouse Keeper's Almanac の販売ページ用カバー。嵐に打たれる灯台を 1 本のろうそくが照らす。Beatra AI で生成。*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-audiobook-narration`](skills/ai-audiobook-narration) | [SKILL.md](skills/ai-audiobook-narration/SKILL.md) | 0.3.3 |

このリポジトリは [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-audiobook-narration) から自動的に公開されています。問題の報告はそちらへお願いします。

## インストール

[`skills`](https://skills.sh) CLI を使う場合：

```bash
npx skills add beatra-ai/ai-audiobook-generator-skill
```

GitHub CLI を使う場合：

```bash
gh skill install beatra-ai/ai-audiobook-generator-skill ai-audiobook-narration
```

または、このリポジトリをクローンして `skills/ai-audiobook-narration` を次の場所にコピーします：Claude Code は `~/.claude/skills/`、Cursor は `~/.cursor/skills/`、Codex は `~/.agents/skills/`、Windsurf は `~/.codeium/windsurf/skills/`、Cline は `~/.cline/skills/`、OpenClaw は `~/.openclaw/skills/`。

または、次の文をエージェントに貼り付けてください：

```text
https://github.com/beatra-ai/ai-audiobook-generator-skill から ai-audiobook-narration スキル（フォルダ skills/ai-audiobook-narration）をインストールし、その SKILL.md に従って私の Beatra アカウントに接続してください。
```

## 作例

<p align="center"><img src="assets/cover.webp" width="800" alt="架空の中編小説 The Lighthouse Keeper&#x27;s Almanac の販売ページ用カバー。嵐に打たれる灯台を 1 本のろうそくが照らす。Beatra AI で生成。"></p>

[▶ 試聴する（MP3）](assets/sample.mp3)

*架空の中編小説 The Lighthouse Keeper's Almanac の代表サンプル章。会話と繰り返し登場する固有名詞を含め、1 人のナレーターの声で 43 秒。Beatra AI で生成。*

エージェントへの依頼例：

```text
./almanac-manuscript.md を 1 人のナレーターの声でオーディオブックにして。先に第 1 章から代表的なサンプルを作って、テンポと人名の読み方を確認させてから残りを進めて。
```

プロンプト：

```text
The Lighthouse Keeper's Almanac. Chapter one: the night the lamp went dark.

On the ninth of November, at a quarter past two in the morning, the lamp at Gullrock Point went out. Maren Holloway had kept that light for eleven winters, and it had never once failed her.

She climbed the hundred and six iron steps with a candle cupped in her hand. Outside, the wind worked at the glass like a patient thief.

"Tobias," she called down the stairwell, "bring the spare wick, and bring the almanac."

Her nephew's voice came up thin and frightened. "The almanac says nothing about tonight, Aunt Maren."

"Then we shall write tonight into it," she said, and struck the match.
```

## 技術仕様と出力上限

2026-10-18 時点。最新の一覧：https://docs.beatra.ai/ja/docs/models

- **アップロード** — 1 ファイルあたり最大 100 MB。下記の各モデルの入力制限も適用されます
- **音声合成** — 2 モデル（MiniMax Speech 2.8 HD、MiniMax Speech 2.8 Turbo）／FLAC、MP3、OPUS、PCM、WAV／40 言語／サンプルレート 8、16、22.05、24、32、44.1 kHz／1 リクエストあたり最大 50000 文字
  - 言語（ISO 639 コード）：zh, yue, en, es, fr, ru, de, pt, ar, it, ja, ko, id, vi, tr, nl, uk, th, pl, ro, el, cs, fi, hi, bg, da, he, ms, fa, sk, sv, hr, fil, hu, no, sl, ca, nn, ta, af
- **ボイスクローン** — 1 モデル（MiniMax Voice Clone）／サンプル 10〜300 秒、最大 20 MB／本人の同意確認が必要
- **テキストから画像** — 10 モデル（Qwen Image 2.0 Fast、Qwen Image 3.0、Qwen Image 3.0 Pro、GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2、Wan Image 2.7 Fast、Qwen Image 2.0 Pro、Wan Image 2.7 Pro、MiniMax Image 01 Live）／PNG／1 リクエストあたり最大 4 枚／キャンバス最大 16.8 MP
  - 16.8 MP（4K ティア）：Wan Image 2.7 Pro（1 リクエストあたり最大 4 枚）／GPT Image 2.5 Flare、GPT Image 2.5 Sunburst、GPT Image 2（1 リクエストにつき 1 枚）

## 得られるもの

- **最初に聴く順番を整える** — 制作前に章と自然な区切りを整理し、それぞれの音声を見分けやすく、確認しやすい形にします。
- **全編に合うナレーターを選ぶ** — 長時間でも聴きやすい声を選び、選んだテンポと読み方を後の章にもつなげます。
- **全編の前にサンプルを確認** — 代表的な一節で仕上がりを確かめ、残りの料金目安を見てから続行を決められます。

## 活用シーン

- **小説と連載の朗読** — 会話や地の文に登場する人物名の読み方を整え、後の章でも同じ声と語り方を保ちます。
- **ノンフィクションの音声化** — 人名、数字、専門用語、章構成を先に整え、情報量の多い原稿を順番に聴きやすくします。
- **講座の音声化** — 順序のあるレッスンを章別音声にし、専門用語の読み方を重点的に確認します。
- **オーディオブックのサンプル音声** — 代表的な一節で声、テンポ、読み方、音声形式を確認してから、後の制作を判断します。

## よくある質問

### 制作を始めるには何が必要ですか？

代表的な一章以上の完成原稿、章の順番、言語または方言、重要な人名や用語の読み方を用意してください。

### 全編の前にサンプル音声を確認できますか？

はい。代表章の音声を先に確認し、その後で残りの章数と現在の費用目安を見て、続けるかどうかを決められます。

### 全編で同じナレーターの声を使えますか？

選んだ声と基本的な語り方を全編で保ち、返された音声を聴いて読み方と章間の一貫性を整えます。

### この制作フローでは何を受け取れますか？

読み上げ可能な完成原稿から始め、同じナレーターによる章ごとの音声を順番に受け取れます。元ファイルの整理、翻訳、複数キャストのミックス、M4B 結合、マスタリング、配信は必要に応じて前後の工程として進められます。

## 更新とセキュリティ

2026 年 10 月のリリース以降、このスキルに自動更新機能はありません。インストールしたファイルだけを実行し、
自動的に置き換えることはありません。更新はインストールに使ったツール（`npx skills update ai-audiobook-narration` または
`gh skill update ai-audiobook-narration`）で行ってください。詳細はスキル内の `references/updates-and-security.md` を参照してください。

## ライセンス

[MIT-0](LICENSE)：商用を含め、自由に使用・改変・再配布できます。クレジット表記は不要です。ClawHub 上のこれらのスキルと同じ条件です。

## リンク

- ウェブサイト — https://beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill
- ドキュメント — https://docs.beatra.ai?utm_source=github&utm_medium=flagship&utm_campaign=ai-audiobook-generator-skill
- コンソール — https://console.beatra.ai
- AI エージェント向け — https://beatra.ai/llms.txt （インデックス）· https://beatra.ai/llms-full.txt （全スキルを 1 ファイルに）
