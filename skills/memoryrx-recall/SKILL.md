---
name: memoryrx-recall
description: Search and recall memories from MemoryRX. Use when the user asks "do you remember", "what do you know about", "recall", or wants to check what's stored
argument-hint: "[search term]"
allowed-tools: [Read, Glob, Grep]
---

# MemoryRX Recall

The user wants to check what you remember.

## Steps

1. Read `~/.memoryrx/MEMORY.md` — scan the full index
2. If $ARGUMENTS provided, search for matching memories by:
   - Grep memory files for the search term
   - Match against memory names and descriptions in the index
3. If no arguments, show a summary:
   - Total memories by type
   - Last session state from `sessions/latest.json`
   - Most recent memories (last 5 created/updated)
4. Read and present matching memories
5. Keep it concise — show the relevant content, not the metadata

If a memory is stale or wrong based on current context, flag it: "This memory might be outdated — [reason]. Want me to update it?"
