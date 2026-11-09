---
name: brokenoak-vault-notes
description: Rules for creating notes in the BrokenOak Obsidian vault (synced to Dropbox at /Apps/remotely-save/BrokenOak). Use whenever an agent writes, records a session, files a ticket note, or saves a brief or handoff into the BrokenOak vault. The vault is create-only.
---

# Writing notes in the BrokenOak vault

The vault's own copy of this rule is `decisions/RULE-vault-note-writing.md`, and the starting point for reading the vault is `decisions/HUB - Home.md`. If they differ, the vault copy wins.

Before linking, check that the target note exists. Hubs: `HUB - eggdrop`, `HUB - winedrop`, `HUB - scenedrop`, `HUB - honeydrop`, `HUB - Infrastructure`, `HUB - Session log`, `HUB - Agent playbook`, `HUB - Design and research`.

## The rule

Applies to every agent (Claude Code, Claude chat, Cursor, Codex) that creates a note in the BrokenOak Obsidian vault. The vault is create-only: never edit, move, rename or delete an existing note. To change something, write a new note that supersedes the old one.

1. Every new note starts with a header: `type` (session, ticket, brief, handoff, template, report, transcript, clipping, hub), `status` (draft, active, superseded, archived), `area` (eggdrop, winedrop, scenedrop, honeydrop, wagdrop, infrastructure, agents, design, research), `ticket` if any, `related` (wikilinks), `supersedes` if any, `updated` (date), `source` (claude-code, claude-chat, cursor, codex, human, web), `tags`.
2. Link, don't name. Mentions of another note or ticket are `[[wikilinks]]` to the exact file name, never backticks or bare keys. Every note links its area hub in `related`; session records also link `[[HUB - Session log]]`, the previous session record on the same work, and every ticket note they touched. Check the target exists first; otherwise use plain text. Code paths and commit hashes stay in backticks.
3. Supersede, don't edit. A replacement note sets `supersedes` and says so in its first line. The one exception: an agent may append one line to the matching hub under "Current" or "Log" linking its new note. Never remove or rewrite hub lines.
4. Tags only for the areas the note is actually about. No blanket app tags, no `#decision` on everything.
5. No empty notes, no copies, no raw pastes without `type: transcript` and a one-line summary, never secrets.
6. File name: `<TICKET or TYPE>-<short-subject>.md`, e.g. `EGGS-696-hen-stats-fix.md`, `SESSION-2026-11-09-cc-1930.md`.
