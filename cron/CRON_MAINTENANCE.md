# CRON_MAINTENANCE.md

## Session-memory cleanup

Run this check on every cron maintenance trigger.

1. Check for raw fragment files matching `memory/YYYY-MM-DD-*.md` for today.
2. Ignore the canonical daily note `memory/YYYY-MM-DD.md`.
3. Ignore non-fragment memory files and topic files.
4. If no raw fragment files exist, stop.

If raw fragment files exist:

5. Read the raw fragment files as session or heartbeat traces.
6. Compare them against the canonical daily note first.
7. Append only important net-new facts, outcomes, or findings to the canonical daily note.
8. Keep section discipline:
   - verified facts, outcomes, and findings → `Important events`
   - actual file, update, and archive actions → `Memory write log (audit)`
9. If a fragment contains no durable net-new information, do not write anything from it.
10. Move only the raw fragment files to `memory/archive/YYYY/`.
11. Add a short audit line to the canonical daily note only if consolidation or archiving occurred.

## Unsaved-important-state check

Run this check on every cron maintenance trigger after session-memory cleanup.

1. Ask: is there important net-new state from the current session or other very recent work that is not yet written to the canonical daily note or the appropriate topic memory file?
2. Use the current session context plus other very recent completed work as the evidence base for this check, not just files already on disk.
3. Count only meaningful items such as completed work blocks, verified findings, applied fixes, durable decisions, and cross-session project state changes.
4. Do not write speculative thoughts, partial scratch notes, or routine chatter just to satisfy the check.
5. If important state is missing, append only the net-new durable facts to today's canonical daily note using the existing section rules.
6. If the update creates or changes durable project, decision, update the appropriate memory files in the same work block, 
7. Before ending this check, make an explicit verdict for each target:
   - today's canonical daily note → updated / no change
   - `memory/projects.md` → updated / no change
   - `memory/decisions.md` → updated / no change
8. Do not treat this check as complete until each target has been explicitly judged, even if the final verdict is `no change`.
9. Add a short audit line to today's canonical daily note describing the memory write only if something was actually written.
