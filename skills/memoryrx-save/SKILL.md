---
name: memoryrx-save
description: Explicitly save a memory to MemoryRX. Use when the user says "remember this", "save this", "don't forget", or similar
argument-hint: <what to remember>
allowed-tools: [Read, Write, Edit]
---

# MemoryRX Save

The user wants to explicitly save something to memory.

## Steps

1. Parse what they want saved from $ARGUMENTS or the conversation context
2. Determine the memory type:
   - **user** — about them (role, preference, identity)
   - **feedback** — about how to work (correction or confirmation)
   - **project** — about ongoing work (goals, deadlines, context)
   - **reference** — about where to find things (external systems, URLs)
3. Check if a similar memory already exists in `~/.memoryrx/MEMORY.md` — update rather than duplicate
4. Write the memory file to `~/.memoryrx/memories/` with frontmatter:

```markdown
---
name: descriptive name
type: user|feedback|project|reference
description: one-line relevance hook
created: YYYY-MM-DD
---

Content. For feedback/project types, include **Why:** and **How to apply:** lines.
```

5. Update `~/.memoryrx/MEMORY.md` index
6. Confirm in one short sentence: "Saved: [what]. Type: [type]."
