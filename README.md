# voice-copywriter

A [skills.sh](https://skills.sh) skill for AI agents that write content in an author's authentic voice across multiple channels.

## What it does

The agent reads layered memory files (HOT/WARM/COLD) and per-channel style guides to match voice exactly — sentence rhythm, vocabulary, characteristic phrases, and things the author never writes.

**Works with:** Telegram channels, YouTube scripts, newsletters, or any combination.

## Core ideas

**3-tier memory** — session drafts (HOT), stable facts (WARM), and a feedback log (COLD) that accumulates style corrections over time.

**Per-channel style files** — each channel gets its own `channel-{name}.md` with tone, structure, real post examples, and prohibited patterns. The agent reads the right file before writing.

**Feedback loop** — when the author edits a generated post, the change is logged in COLD memory: what changed, what it became, and why. The agent applies these lessons in future sessions.

**Write permissions** — explicit rules on what the agent can write freely, append-only, or never touch. Prevents the agent from overwriting style files with its own interpretations.

## File structure

```
voice-copywriter/
├── SKILL.md                      Main skill file (agent reads this)
└── references/
    ├── memory-structure.md       Full memory file map and formats
    └── channel-template.md      Template for setting up a new channel
```

## Setup

1. Install the skill via skills.sh
2. Create your memory directory structure (see `references/memory-structure.md`)
3. Add your author profile to `memory/warm/WARM_MEMORY.md`
4. Set up at least one channel file from `references/channel-template.md`
5. Add 3–5 real posts to the channel file as examples
6. Start sending posts to `memory/prince/library/` over time — this is the primary voice signal

The more real examples you add to the library and channel files, the better the style match.

## License

MIT
