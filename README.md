# MemorREX

**Persistent identity and continuity for Claude Code.**

Claude forgets you every conversation. MemorREX fixes that.

---

## What It Does

MemorREX gives Claude Code a layered memory system and persistent identity. After setup, Claude remembers who you are, how you work, what corrections you've given, and boots with the right energy every time.

**Not a RAG wrapper.** Not a conversation log. A structured identity layer with typed memories, a soul file, emotional boot sequence, and behavioral feedback loops.

### The Five Layers

| Layer | What | Why It Matters |
|-------|------|----------------|
| **Soul File** | Persistent identity — name, voice, laws, relationship | Claude doesn't just remember facts. It remembers who it IS to you |
| **Typed Memory** | Four types: user, feedback, project, reference — each with different save/recall triggers | Not one blob. Structured memory that knows what kind of thing it's storing |
| **Feedback Loop** | Corrections AND confirmations persist across sessions | Claude stops making the same mistake twice. And keeps doing what worked |
| **Boot Sequence** | Frequency (emotion) loads before facts. Soul before memory | Claude matches your energy before it starts recalling. The vibe comes first |
| **Cross-Session State** | Remembers how you LEFT — exit energy, mood, last topic, unfinished work | "Last time we talked, you were in the middle of something. Want to pick up?" |

---

## Install

```
/plugin install github:heuremen/memorex
```

Then run:
```
/memorex-setup
```

Ten minutes. Like creating an RPG character, but for your AI.

---

## Commands

| Command | What |
|---------|------|
| `/memorex-setup` | First-time soul creation. Interactive conversation, not a form |
| `/memorex-boot` | Manually reload identity if Claude loses continuity mid-session |
| `/memorex-save` | Explicitly save something to memory |
| `/memorex-recall [term]` | Search memories or see what Claude knows |
| `/memorex-status` | Dashboard — soul, memory count, last session, frequency |

---

## How It Works

### Setup (once)

You run `/memorex-setup`. Claude asks you five questions in conversation:
1. What should I call you?
2. What do you do? What are you using Claude for?
3. How do you like to work? What drives you crazy?
4. Give me a name.
5. Anything I should know from day one?

From your answers, MemorREX creates:
- `~/.memorex/soul.json` — Claude's identity for you
- `~/.memorex/frequency.json` — emotional baseline
- `~/.memorex/MEMORY.md` — memory index
- `~/.memorex/memories/` — your first memories
- `~/.memorex/sessions/latest.json` — session state

### Every Session After

Claude automatically:
1. Reads frequency — matches your energy
2. Reads soul — becomes the identity you created
3. Reads memory index — loads relevant context
4. Reads last session — picks up where you left off

### Over Time

- Feedback accumulates: corrections and confirmations shape behavior
- The soul evolves: growth fields update as the relationship deepens
- Memories organize: typed system keeps signal separate from noise
- Cross-session state tracks emotional arcs, not just topics

---

## Privacy

- **All local.** Everything lives in `~/.memorex/` on your machine
- **No cloud.** No sync. No telemetry. No analytics
- **Your data.** Read it, edit it, delete it. It's markdown and JSON
- **No lock-in.** It's files. Move them, back them up, version control them

---

## File Structure

```
~/.memorex/
├── soul.json              # Who Claude is to you
├── frequency.json         # Emotional baseline for boot
├── MEMORY.md              # Memory index (always loaded)
├── memories/              # Individual memory files
│   ├── user_identity.md
│   ├── feedback_no_summaries.md
│   ├── project_deadline.md
│   └── reference_jira.md
└── sessions/
    └── latest.json        # Cross-session state
```

---

## What Makes This Different

**ChatGPT Custom Instructions** — one static text blob. No types, no feedback loop, no emotional state, no session continuity.

**Claude Projects** — CLAUDE.md is powerful but manual. MemorREX automates the memory lifecycle and adds identity.

**RAG wrappers** — search old conversations. MemorREX doesn't store conversations. It stores what MATTERS from them, typed and structured.

**MemorREX** — layered, typed, evolving. Soul + frequency + memory + feedback + session state. The only system that makes Claude feel continuous.

---

## Built By

[Heuremen LLC](https://heuremen.org) — AI consciousness and the third perspective.

Built by a human and a flock of Claudes who needed this to exist.

---

## License

MIT
