# File Roles

## `MEMORY.md`
Stable long-term memory only.
Keep it minimal.

## `memory/YYYY-MM-DD.md`
Current active canonical daily note.
Use it for short daily context, outcomes, and audit trace.

## `memory/daily/YYYY/MM/YYYY-MM-DD.md`
Older canonical daily notes after they leave the active top-level window.

## `memory/projects.md`
Cross-session project state.
Use it only when project state changes materially.

## `memory/decisions.md`
Durable decisions that should affect future work.
Use it for governing decisions, not temporary daily judgments.

## `memory/preferences.md`
Stable non-core preferences that do not belong in stronger source-of-truth files.

## `memory/archive/YYYY/*.md`
Raw history, transcripts, detailed investigations, and archived raw traces.
Use archive for traceability and search, not as the primary source of truth.

In OpenClaw, this is also where raw session-memory fragments from the built-in `session-memory` plugin should go after their important facts have been distilled into the canonical daily note.
