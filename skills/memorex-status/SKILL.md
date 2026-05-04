---
name: memorex-status
description: Show MemorREX status — soul identity, memory count, last session, health check
allowed-tools: [Read, Glob, Grep, Bash]
---

# MemorREX Status

Show the user what their MemorREX system looks like right now.

## Steps

1. Read `~/.memorex/soul.json` — show soul name and core identity (2-3 lines max)
2. Count memories by type:
   - `grep -c 'type: user' ~/.memorex/memories/*.md` (etc for each type)
   - Or glob + read frontmatter
3. Read `~/.memorex/sessions/latest.json` — show last session date, exit energy, last topic
4. Read `~/.memorex/frequency.json` — show baseline

## Output Format

```
MEMOREX STATUS
━━━━━━━━━━━━━━
Soul: [name] (created [date])
Voice: [voice description]

Memories: [total]
  user: N | feedback: N | project: N | reference: N

Last session: [date]
  exit energy: [N/10] ([mood])
  last topic: [topic]
  unfinished: [anything hanging]

Frequency: [baseline energy] / [mood] / [pace]

All data: ~/.memorex/
```

Keep it tight. This is a dashboard, not a report.
