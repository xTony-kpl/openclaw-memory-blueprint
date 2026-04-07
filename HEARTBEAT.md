# HEARTBEAT.md

## Weekly memory distillation

Run this check only when due.

1. Read `memory/heartbeat-state.json`.
2. If `lastWeeklyReview` is null or older than 7 days, continue. Otherwise stop.
3. Run `memory/WEEKLY_REVIEW.md`.
4. Distill durable facts from recent daily notes into `memory/decisions.md`, `memory/projects.md`, and `memory/self-improvement.md` when appropriate.
5. Review `memory/decisions.md` entries still marked `active`; if any have been superseded, abandoned, reduced to trial-only status, or otherwise stopped governing current behavior, reclassify them instead of leaving them indefinitely active.
6. Update `../MEMORY.md` only if long-term memory should change.
7. Move long or noisy logs to `memory/archive/YYYY/` when appropriate.
8. If older canonical daily notes should leave the active top-level window, move them to `memory/daily/YYYY/MM/`, not `memory/archive/YYYY/`.
9. Add an audit line to today's daily note only if something changed.
10. Update `lastWeeklyReview` in `memory/heartbeat-state.json`.
