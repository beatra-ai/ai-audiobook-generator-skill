# AI Audiobook Generator Skill

English | [简体中文](./README.zh-CN.md)

Turn a final manuscript or course text into ordered chapter audio with one narrator, a representative sample chapter first, and focused refinements, from inside Claude Code, Codex, or OpenClaw.

> [!IMPORTANT]
> Rendering needs a [Beatra](https://beatra.ai) account and uses credits. The skill itself is free to install.

| Question | Answer |
| --- | --- |
| **What it does** | Turn final manuscript or course text into ordered chapter audio with one narrator, a representative sample, clear pricing, and focused refinements. |
| **Requirements** | Python 3.10+ and an agent that loads `SKILL.md` |
| **Cost** | Free to install. Each render uses credits on your Beatra account, and paid steps run only when you ask for that exact render or approve its card. |
| **Works with** | Claude Code, Codex, OpenClaw |

<p align="center"><img src="assets/cover.webp" width="800" alt="Listing cover for The Lighthouse Keeper&#x27;s Almanac, an invented novella, showing a storm-battered lighthouse lit by a single candle. AI-generated with Beatra."></p>

*Listing cover for The Lighthouse Keeper's Almanac, an invented novella, showing a storm-battered lighthouse lit by a single candle. AI-generated with Beatra.*

| Skill | Entry point | Version |
| --- | --- | --- |
| [`ai-audiobook-narration`](skills/ai-audiobook-narration) | [SKILL.md](skills/ai-audiobook-narration/SKILL.md) | 0.2.5 |

This repository is published automatically from [beatra-ai/beatra-skills](https://github.com/beatra-ai/beatra-skills/tree/main/skills/ai-audiobook-narration). Report issues there.

## Install

With the [`skills`](https://skills.sh) CLI:

```bash
npx skills add beatra-ai/ai-audiobook-generator-skill
```

With the GitHub CLI:

```bash
gh skill install beatra-ai/ai-audiobook-generator-skill ai-audiobook-narration
```

Or clone this repository and copy `skills/ai-audiobook-narration` into `~/.claude/skills/` for Claude Code,
`~/.agents/skills/` for Codex, or `~/.openclaw/skills/` for OpenClaw.

Or paste this into your agent:

```text
Install the ai-audiobook-narration skill from https://github.com/beatra-ai/ai-audiobook-generator-skill (folder skills/ai-audiobook-narration), then follow its SKILL.md to connect my Beatra account.
```

## Examples

<p align="center"><img src="assets/cover.webp" width="800" alt="Listing cover for The Lighthouse Keeper&#x27;s Almanac, an invented novella, showing a storm-battered lighthouse lit by a single candle. AI-generated with Beatra."></p>

[▶ Listen (MP3)](assets/sample.mp3)

*Representative sample chapter from an invented novella, The Lighthouse Keeper's Almanac, read in 43 seconds by one narrator voice with dialogue and recurring names. AI-generated with Beatra.*

Prompt:

```text
The Lighthouse Keeper's Almanac. Chapter one: the night the lamp went dark.

On the ninth of November, at a quarter past two in the morning, the lamp at Gullrock Point went out. Maren Holloway had kept that light for eleven winters, and it had never once failed her.

She climbed the hundred and six iron steps with a candle cupped in her hand. Outside, the wind worked at the glass like a patient thief.

"Tobias," she called down the stairwell, "bring the spare wick, and bring the almanac."

Her nephew's voice came up thin and frightened. "The almanac says nothing about tonight, Aunt Maren."

"Then we shall write tonight into it," she said, and struck the match.
```

## What you get

- **Plan the listening order first** — Organize chapters and natural segment breaks before narration begins, keeping each part easy to identify and review.
- **Cast for the whole book** — Choose one available narrator voice for long-form comfort, then keep the selected pace and pronunciations consistent across chapters.
- **Pilot before the full batch** — Hear one representative chapter, compare the voice and pacing, and view the estimate for the remaining work.

## Use cases

- **Novel and serial narration** — Carry a familiar narrator voice and agreed readings across dialogue, exposition, recurring characters, and later chapters.
- **Nonfiction audiobooks** — Prepare names, numbers, terms, and chapter structure so complex source text becomes easier to listen to in sequence.
- **Course narration** — Turn ordered lessons into chapter audio with stable delivery and focused review of technical pronunciation.
- **Audiobook sample chapters** — Create a meaningful pilot for narrator, pace, pronunciation, and format review before expanding production.

## FAQ

### What do I need to start?

Bring final readable text for at least one representative chapter, the intended language or dialect, chapter order, and any important pronunciation notes.

### Can I hear a sample before narrating the whole book?

Yes. The workflow starts with a representative pilot, then shows the remaining chapter count and current price estimate before you decide whether to continue.

### Will every chapter use the same narrator voice?

The selected narrator voice and narration style carry across the book, with listening review keeping pronunciation and chapter-to-chapter delivery consistent.

### What does this workflow deliver?

It turns final readable text into ordered chapter audio with one consistent narrator, organized for editing, translation review, multi-cast mixing, M4B assembly, mastering, and publishing.

## Updates

Each installed skill checks for a new version at most once a day, verifies the
official archive before replacing itself, and leaves your installation untouched
if anything fails. Turn it off at any time — see
`references/automatic-updates-and-safety.md` inside the skill.

## License

[MIT-0](LICENSE) — free to use, modify, and redistribute, including
commercially. No attribution required. Same terms as these skills carry on
ClawHub.
