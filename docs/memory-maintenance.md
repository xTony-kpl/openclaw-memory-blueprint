# Memory Maintenance

The memory structure and the memory maintenance layer are not the same thing.

The structure is the set of files:
- `MEMORY.md`
- daily notes
- topic files such as `projects.md` and `decisions.md`
- archive

The maintenance layer is what keeps those files clean and up to date over time.

But the first layer of maintenance is not scheduled automation.
The assistant should already maintain memory during normal work.

That means:
- write the daily note after major work
- promote durable project and decision state in the same work block
- keep long-term memory small
- archive raw traces after distillation

The default expectation is: write important memory directly from the active session while doing the work.
Do not treat cron as the primary place where important state first gets written.

Cron is the backstop.
It helps catch what was missed, reduce drift, and make periodic cleanup more reliable.

## Why maintenance matters

Without maintenance, memory structures drift.
Even a good assistant can miss things after resets, interruptions, long sessions, or partial work blocks.

What usually goes wrong:
- raw fragments pile up
- daily notes keep important facts that never get promoted
- durable decisions stay buried in recent notes
- older notes clutter the top level
- archive fills up without a clear story for why

So a good memory structure also needs a maintenance habit.

## In OpenClaw

In OpenClaw, the maintenance layer commonly runs through:
- the built-in `session-memory` plugin
- cron jobs
- periodic review files such as `memory/WEEKLY_REVIEW.md`

A practical default is a scheduled cron trigger that runs every 60 minutes and executes a maintenance procedure file such as:
- `cron/CRON_MAINTENANCE.md`

Use 60 minutes as a baseline, then adjust cadence to workload and risk tolerance.

## Raw fragment cleanup

A common OpenClaw flow is:
- the built-in `session-memory` plugin leaves a raw fragment on `/new` or `/reset`
- the assistant later reads that raw fragment
- important facts are distilled into the canonical daily note
- the raw fragment is then moved into `memory/archive/YYYY/`

This is one reason archive exists as part of the normal memory lifecycle.

## Cron maintenance

Cron is not the memory structure itself.
It is a backstop tool that helps keep the memory structure maintained when normal operation was incomplete or when periodic review is useful.

When cron runs, it should not look only at files already on disk.
It should also use the current session context plus other very recent completed work when deciding whether memory writes or promotions are still missing.

Examples of what cron maintenance can do:
- check for raw fragments that still need consolidation
- update the canonical daily note with important net-new state
- promote durable project or decision state into topic files
- reclassify stale or superseded decisions
- run weekly cleanup and distillation

## Practical rule

Use maintenance to support the file structure, not replace it.

The structure should still make sense by itself.
The assistant should already do the normal memory work during regular operation, directly from the session where the work is happening.
Maintenance just helps catch misses and keep things tidy over time:
- distill raw traces
- promote durable state
- move old material out of the active working area
- keep the memory system readable over time
