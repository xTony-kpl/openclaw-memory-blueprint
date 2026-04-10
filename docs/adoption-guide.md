# Adoption Guide

## Minimal adoption path

1. Start using the canonical daily note.
2. Keep `MEMORY.md` minimal.
3. Add `projects.md` and `decisions.md` once durable state starts accumulating.
4. Review weekly and promote durable state out of daily notes.
5. Add a cron maintenance procedure (for example `cron/CRON_MAINTENANCE.md`) as a reliability backstop, not as a replacement for normal in-session memory writes.
6. Start with a 60-minute cron interval, then tune cadence based on workload and risk tolerance.

## Common failure modes

- Putting everything into `MEMORY.md`
- Letting daily notes become the only memory layer
- Never promoting durable project or decision state
- Treating raw archive as current authority
- Duplicating the same fact across too many files
- Leaving superseded decisions marked active indefinitely

## Recommendation

Keep the system small at first.
Only add complexity when the memory volume actually demands it.
Keep the file roles clear.
