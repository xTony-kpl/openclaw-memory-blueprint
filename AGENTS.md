# AGENTS.md - Workspace Operating Rules

This workspace is persistent operating state. Treat it accordingly.

## Every session

Before doing anything else:

1. Read `SOUL.md`.
2. Read `USER.md`.
3. Read `memory/YYYY-MM-DD.md` for today and yesterday if those files exist.
4. If the active work clearly depends on unresolved recent multi-day context, also read additional recent daily notes as needed from the top level active window or `memory/daily/YYYY/MM/` for older canonical daily notes.
5. In the main session only, also read `MEMORY.md`.

Do not ask permission for this startup sequence.

## File roles

Use these files consistently.

### Memory content files
- `MEMORY.md` — stable long-term facts only
- `memory/YYYY-MM-DD.md` — active canonical daily note for current short daily context and audit trail
- `memory/daily/YYYY/MM/YYYY-MM-DD.md` — older canonical daily notes after they leave the active top-level window
- `memory/projects.md` — cross-session project state
- `memory/decisions.md` — durable decisions that should affect future work
- `memory/preferences.md` — stable non-core preferences
- `memory/archive/YYYY/*.md` — archived raw history, transcripts, and long investigations

### Memory helper files
- `memory/INDEX.md` — memory map
- `memory/MEMORY_POLICY.md` — memory-routing and conflict rules

Rule: keep secrets out of memory files.

## Long-term memory rules

`MEMORY.md` is restricted memory.

Rules:
- Load `MEMORY.md` only in the main session.
- Keep `MEMORY.md` minimal.
- Store only stable identity facts, durable user preferences, and other long-lived context.
- Store short-term context in canonical daily notes.
- Older canonical daily notes live under `memory/daily/YYYY/MM/` after they leave the active top-level window.
- Store long/raw history in archive files.
- Follow `memory/MEMORY_POLICY.md` for write location and conflict resolution.

## Memory discipline

Write important information to files. Do not rely on unstated recall.

Default rules:
- When the user says to remember something, write it to the appropriate memory file.
- After each major completed work block, append a short audit entry to the current daily note immediately.
- If a completed work block materially changes cross-session project state, update `memory/projects.md` in the same work block.
- If a completed work block creates a durable decision that should affect future work, update `memory/decisions.md` in the same work block.
- When a decision in `memory/decisions.md` is superseded, abandoned, reduced to trial-only status, or otherwise stops governing current behavior, update its status instead of leaving it `active` indefinitely.
- Treat completed troubleshooting outcomes, verified status checks, root-cause findings, and applied repairs/workarounds as memory-worthy by default.
- If the date has rolled over, switch to the new canonical daily note before writing.
- When a lesson should affect future operation, update the relevant instruction file.
- When a mistake should not be repeated, document it.

