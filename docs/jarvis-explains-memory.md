# Jarvis Explains Memory

How this memory system works in plain English.

## The simple version

Think of this memory system like a small office with labeled boxes, not like a human brain.

There is not one giant magical memory file.
There are different places for different kinds of things.

## Explain it like you're 5

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

## The actual layers

### 1) Source-of-truth files
These are the most important files.

They define:
- how the assistant should act
- who the assistant is
- who the user is
- what the operating rules are

Examples:
- `SOUL.md`
- `AGENTS.md`

These outrank everything else.
If an old note says one thing but a source-of-truth file says another, trust the source-of-truth file.

### 2) `MEMORY.md`
This is the small long-term memory.

It is for durable facts only.
Keep it intentionally small.
It should not become a junk drawer.

### 3) Daily notes
File format:
- `memory/YYYY-MM-DD.md`

This is today's notebook.

It stores:
- important events
- decisions made today
- follow-ups / TODOs
- memory write audit log

This is where most practical day-to-day continuity lives.

### 4) Topic files
These are the organized folders.

Main ones:
- `memory/projects.md`
- `memory/decisions.md`
- `memory/preferences.md`

These exist so the assistant does not need to dig through daily notes every time.

Examples:
- if you ask what the active projects are, `projects.md` should answer that
- if you ask what durable rules or conclusions govern current work, `decisions.md` should answer that

### 5) Archive
Folder:
- `memory/archive/YYYY/`

This is the storage room.

It keeps:
- old session logs
- raw traces
- detailed history
- noisy material that should not sit in the main working area

Important point:
- archive is kept for traceability
- it is not the main source of current truth

There is also an important OpenClaw-specific flow here.
OpenClaw's built-in `session-memory` plugin can leave a raw fragment such as `memory/YYYY-MM-DD-slug.md` on `/new` or `/reset`.
That file is not the canonical daily note.
The idea is:
- distill the important facts from the raw fragment into `memory/YYYY-MM-DD.md`
- then move the raw fragment into `memory/archive/YYYY/`

This memory structure makes the most sense with that flow in mind.
It explains why raw fragment files exist at all and why archive is part of the normal memory lifecycle rather than just a bin for random old junk.

### 6) Search
Search is the helper that finds the right note later.

The files themselves are the real memory.
Search is the tool that helps recover the right part of that memory quickly.

That distinction matters.
If something was edited moments ago, a direct file read may be more reliable than search for a short time.

## What happens when something is remembered

If something important happens, the good version is:

1. Decide what kind of thing it is.
   - stable fact?
   - today-only event?
   - project state?
   - durable decision?
   - raw history?
2. Write it to the right place.
3. Find it later by reading or searching the files.

So memory depends a lot on correct filing, not just recall.

## Important limitation

This system does not imply:
- a hidden perfect memory of every chat forever
- flawless instant recall of everything ever said
- human-style background remembering

If something matters and never gets written down properly, it can be lost across resets.
That is why the file system matters so much.

## Why this is good

This system is less magical, but better operationally.

Why:
- it survives resets
- it is inspectable
- it can be edited
- mistakes can be corrected
- it can be kept clean
- old junk does not automatically become truth

So instead of fake AI mysticism, it is more like:

notes + folders + search + rules

That is much more trustworthy.

## The short version

If this needs to fit in one sentence:

Memory works like a disciplined notebook system with a search engine on top, not like a human mind.

Or even shorter:

The assistant remembers by writing things into the right files, then searching those files later.
