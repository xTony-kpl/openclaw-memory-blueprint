# Memory Blueprint

A shareable memory structure for assistant workspaces.

This template focuses only on memory and continuity:
- what to read at startup
- what to write after important work
- how to separate long-term memory from daily notes
- how to promote durable project and decision state
- how to preserve traceability without letting raw history become authority

This is a template, not a live memory export.
It intentionally contains:
- blank files
- structural guidance
- generalized rules
- no personal memory content

Think of this memory system like a small office with labeled boxes, not like a human brain.

There is not one giant magical memory file.
There are different places for different kinds of things.

Imagine a careful robot assistant in a workshop.

When something happens, it does not just "remember it in its head forever."

Instead:
- if it is about who we are, it goes on the important wall
- if it is a stable fact, it goes in the small permanent notebook
- if it is something from today, it goes on today's page
- if it is about a project or a decision, it goes in the right folder
- if it is a long messy conversation log, it goes in the archive box
- then a search system helps find it later

So the memory system is more like a tidy librarian system than a brain.

## Included

- `AGENTS.md` — memory-specific operating rules only
- `SOUL.md` — memory/recall/continuity discipline only
- `MEMORY.md` — minimal long-term memory surface
- `memory/INDEX.md` — memory map
- `memory/MEMORY_POLICY.md` — routing and promotion rules
- `memory/DAILY_TEMPLATE.md` — canonical daily-note template
- `memory/WEEKLY_REVIEW.md` — periodic distillation procedure
- `memory/projects.md` — cross-session project state
- `memory/decisions.md` — durable decisions
- `memory/preferences.md` — stable non-core preferences
- `memory/daily/YYYY/MM/README.md` — historical canonical daily-note location
- `memory/archive/YYYY/README.md` — raw history/archive location
- `docs/` — supporting explanation

## Design goals

- Keep long-term memory small.
- Keep daily notes useful without forcing them to carry everything.
- Promote durable project and decision state out of daily notes.
- Preserve history without letting raw logs govern current behavior.
- Make continuity explicit rather than assumed.

## Suggested use

 1. Copy this folder into a fresh assistant workspace.                                                            
 2. Adapt AGENTS.md and SOUL.md to your runtime.                                                                  
 3. From there, the assistant should:                                                                             
     - keep MEMORY.md minimal                                                                                     
     - use daily notes for active context and audit trail                                                         
     - promote durable project and decision state into topic files in the same work block                         
     - move older canonical daily notes into memory/daily/YYYY/MM/                                                
     - keep raw logs, transcripts, and long investigations in memory/archive/YYYY/

## Scope

This template is intentionally memory-focused, not a full agent framework.
It excludes self-improvement memory by design.
It is designed for OpenClaw workspaces.

## OpenClaw note

This structure makes the most sense if you use the raw session-summary flow too.

In practice that means:
- OpenClaw's built-in `session-memory` plugin leave a raw session-memory fragment such as `memory/YYYY-MM-DD-slug.md` on `/new` or `/reset`
- that raw file is not the canonical daily note
- the assistant should distill what matters into `memory/YYYY-MM-DD.md`
- then the raw fragment should be moved into `memory/archive/YYYY/`

So the structure can still work without that flow, but it is strongly recommended because it explains why archive exists and how raw session traces become clean daily memory.

## A personal note
My assistant Jarvis has been running under this memory structure for 33 days now and it has been good and pretty reliable for the most part, so this structure has been battefield tested to that extent. It is not over nor finished (it never is) but is in a good state to share now.
