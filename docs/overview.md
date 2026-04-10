# Overview

This template separates memory into layers so each file has a clear role, and uses cron maintenance as a backstop to keep those layers clean over time.

## Layers

- Long-term memory: stable facts worth keeping over time
- Topic memory: durable project state, durable decisions, and stable non-core preferences
- Daily memory: active short-term context and audit trail
- Archive: raw history, transcripts, and detailed traceability

## Principle

Do not let one file try to do everything.
Keep each layer narrow enough to stay usable.
Promote durable state out of daily notes when it should guide future work.
