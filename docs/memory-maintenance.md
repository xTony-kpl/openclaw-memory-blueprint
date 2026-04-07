# Memory Maintenance

The memory structure and the memory maintenance layer are not the same thing.

The structure is the set of files:
- `MEMORY.md`
- daily notes
- topic files such as `projects.md` and `decisions.md`
- archive

The maintenance layer is what keeps those files clean and up to date over time.

But the first layer of maintenance is not heartbeat or cron.
The assistant should already maintain memory during normal work.

That means:
- write the daily note after major work
- promote durable project and decision state in the same work block
- keep long-term memory small
- archive raw traces after distillation

The default expectation is: write important memory directly from the active session while doing the work.
Do not treat heartbeat or cron as the primary place where important state first gets written.

Heartbeat or cron are the backstop.
They help catch what was missed, reduce drift, and make periodic cleanup more reliable.

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

In OpenClaw, the maintenance layer often connects to:
- the built-in `session-memory` plugin
- `HEARTBEAT.md`
- cron jobs
- periodic review files such as `memory/WEEKLY_REVIEW.md`

## Raw fragment cleanup

A common OpenClaw flow is:
- the built-in `session-memory` plugin leaves a raw fragment on `/new` or `/reset`
- the assistant later reads that raw fragment
- important facts are distilled into the canonical daily note
- the raw fragment is then moved into `memory/archive/YYYY/`

This is one reason archive exists as part of the normal memory lifecycle.

## Heartbeat and cron

Heartbeat and cron are not the memory structure itself.
They are backstop tools that help keep the memory structure maintained when normal operation was incomplete or when periodic review is useful.

When they do run, they should not look only at files already on disk.
They should also use the current session context plus other very recent completed work when deciding whether memory writes or promotions are still missing.

Examples of what they can do:
- check for raw fragments that still need consolidation
- update the canonical daily note with important net-new state
- promote durable project or decision state into topic files
- reclassify stale or superseded decisions
- run weekly cleanup and distillation

## Which one to use

### Heartbeat
Use heartbeat when:
- timing can drift a little
- multiple lightweight checks can be batched together
- recent session context matters

### Cron
Use cron when:
- the maintenance should run on a real schedule
- timing matters
- you want a more reliable periodic trigger

In many real setups, cron is the better fit for memory maintenance because it is a true scheduler.

## Practical rule

Use maintenance to support the file structure, not replace it.

The structure should still make sense by itself.
The assistant should already do the normal memory work during regular operation, directly from the session where the work is happening.
Maintenance just helps catch misses and keep things tidy over time:
- distill raw traces
- promote durable state
- move old material out of the active working area
- keep the memory system readable over time
