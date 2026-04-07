# Search and Indexing

The files are the real memory.

That comes first.
The memory system lives in:
- `MEMORY.md`
- daily notes
- topic files
- archive

Search and indexing are the retrieval layer on top.
They help the assistant find the right memory later.

## The simple version

Think of it like this:
- the files are the notebooks and folders
- the index is the card catalog
- embeddings help the card catalog understand meaning, not just exact words

## SQLite

In OpenClaw, SQLite is the default local backend for the search/index layer.

In simple terms, that means:
- memory files stay as normal files on disk
- SQLite helps keep a local searchable index over them
- this is useful for exact wording, filenames, dates, and explicit terms

## Embeddings

Embeddings add semantic search.

That means the system can search by meaning, not only by exact wording.

Example:
- one note says "durable decision"
- another says "rule that should affect future work"

Embeddings help the search understand that those may be about the same idea even if the words do not match exactly.

## Hybrid search

In practice, the useful setup is hybrid search:
- exact or lexical matching for direct terms
- semantic matching for related meaning

That usually works better than either one alone.

## Important distinction

Do not confuse the index with the memory itself.

- the files are the memory
- the index helps find the memory

If the index is stale, degraded, or catching up, the files are still the source of truth.
That is why direct file reads still matter.

## Practical note

Very recent edits may briefly be easier to confirm by directly reading the file than by relying only on search.

So the healthy mental model is:
- write to files first
- use search to find the right files later
- treat indexing as helper infrastructure, not as the memory itself
