# Memory Policy

## File roles

### `../MEMORY.md` — long-term memory
Store only stable facts that should remain true over time.
Do not store temporary status or debug notes here.

Examples:
- identity
- user preferences
- durable conventions

### `YYYY-MM-DD.md` — active daily note
Store the current active canonical daily note at the top level of `memory/`.
Use this for short daily notes and temporary context that still matters in the active working window.
Keep entries concise.

### `daily/YYYY/MM/YYYY-MM-DD.md` — historical canonical daily notes
Store older canonical daily notes here after they roll out of the active top-level window.
These files remain canonical daily memory, not raw archive.
Keep the original date-based filename unchanged when moving a canonical daily note into this tree.

### `archive/YYYY/*.md` — archive
Store long transcripts, detailed investigations, old logs, and archived raw session-memory traces.
Use archive for traceability and search. Do not delete by default.

Filename format:
- `YYYY-MM-DD-topic.md`

Rule:
- Files such as `memory/YYYY-MM-DD-slug.md` created by the session-memory hook are raw traces, not canonical daily notes.
- After consolidating important facts into the canonical daily note, move those raw files into `archive/YYYY/`.
- Do not move canonical daily notes into `archive/`; move them into `daily/YYYY/MM/` when they should leave the active top-level window.

## Topic files

### `projects.md`
Use for cross-session project state.

Update only when project state changes materially, such as:
- a project starts
- a project pauses
- a project completes
- direction changes
- the next step changes
- key files change

Do not use for:
- one-off tasks
- daily activity noise
- minor progress chatter

### `decisions.md`
Use for durable decisions that should affect future work.

Update only when a decision changes how work should be done later.
Do not use for temporary daily judgments.
`decisions.md` is not append-only: when a recorded decision is superseded, abandoned, reduced to trial-only status, or otherwise stops governing current behavior, update its status instead of leaving it `active` indefinitely.

### `preferences.md`
Use for stable non-core preferences that do not belong in more authoritative workspace files.

## Cross-file update rules
- When a major completed work block materially changes project state, update `projects.md` in the same work block.
- When a major completed work block creates a durable decision, update `decisions.md` in the same work block.

## Retention

- Keep the active canonical daily note at top level as `memory/YYYY-MM-DD.md`.
- Keep recent active-window daily notes at top level when useful for near-term context.
- Move older canonical daily notes into `memory/daily/YYYY/MM/` once they are no longer part of the active working window.
- Review archive monthly.
- Keep important logs.
- Remove only obvious junk or duplicates.
- Do not delete by default without intent.

## Ingestion

If the user says `remember this`, store it immediately in the correct location.

## Routing decision tree

1. Stable for months and belongs in long-term memory? → `../MEMORY.md`
2. Cross-session project state? → `projects.md`
3. Durable decision that should affect future work? → `decisions.md`
4. Stable non-duplicative preference not better stored in stronger workspace files? → `preferences.md`
5. Useful mainly today or this week and still in active working context? → `YYYY-MM-DD.md`
6. Useful mainly in a prior day/week but still worth keeping as canonical daily memory? → `daily/YYYY/MM/YYYY-MM-DD.md`
7. Long raw transcript or detailed history? → `archive/YYYY/YYYY-MM-DD-topic.md`
8. Already present in a stronger source-of-truth file? → do not duplicate in memory files
9. Contains secrets? → do not store secret values

## Memory write log

When storing an important memory, add a short daily note describing what was saved, where, and why.

## Conflict resolution

Use this order only when two sources make competing claims about the same point.
Silence in a higher layer does not invalidate a lower layer.

1. Governing workspace files
2. `../MEMORY.md`
3. topic files: `preferences.md`, `projects.md`, `decisions.md`
4. daily notes and archive files

## Quick checklist

- Stable for months? → `../MEMORY.md`
- Useful mainly today or this week and still active? → top-level daily note
- Older canonical daily memory? → `daily/YYYY/MM/`
- Long raw history? → archive
- Already in a source-of-truth file? → do not duplicate in memory files
- Contains secrets? → do not store secret values
