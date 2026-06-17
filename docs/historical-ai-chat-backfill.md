---
type: workflow
status: draft
---

# Historical AI Chat Backfill

Historical AI chat backfill is the process of turning old conversations from AI tools into traceable vault context without turning every chat into long-term memory.

The goal is not to remember everything. The goal is to recover useful context, decisions, project state, and durable lessons while keeping memory narrow, sourced, and human-approved.

## Core Principle

```text
Wide capture, narrow memory.
Structure first, retrieval later.
Human confirmation before durable memory.
```

Historical conversations should move through the normal CobrainVault lifecycle:

```text
Raw Tool History
  -> Source Record
  -> Session or Phase Summary
  -> Candidate Memory
  -> Confirmed Memory
  -> Retrieval Briefing
```

Never convert raw chat logs directly into Confirmed Memory.

## When to Use This Workflow

Use this workflow when you have historical AI tool conversations from tools such as:

- code agents;
- chat assistants;
- research assistants;
- local CLI agents;
- browser-based assistants;
- any tool with session ids, transcripts, exports, logs, or conversation files.

The workflow works even when tools have different metadata formats. Preserve the difference instead of forcing every tool into the same shape too early.

## Phase 1: Build a Backfill Queue

Start by listing historical sessions before summarizing them.

Each queue entry should include, when available:

- source tool;
- source id or session id;
- title or short hint;
- started at;
- ended at;
- message count or rough size;
- locator, export path, or tool URI;
- processing status;
- signal level;
- related theme or project;
- notes and caveats.

Recommended statuses:

- `unprocessed`
- `captured`
- `triaged`
- `summarized`
- `phase-summarized`
- `candidates-proposed`
- `reviewed`
- `archived`

Recommended signal levels:

- `low`: tests, greetings, one-off commands, dead ends.
- `medium`: concrete project work, debugging, research, implementation.
- `high`: durable decisions, repeated principles, long-running themes, project strategy, reusable workflows.

Do not deeply process every low-signal session. Registering it may be enough.

## Phase 2: Deduplicate Before Processing

Before processing a historical session, check:

1. `90_indexes/session-registry.md`
2. `10_sources/`
3. `20_sessions/`
4. related `40_themes/` and `50_projects/`

Deduplication should be conservative.

- Source-level duplicates can be marked, not deleted.
- Session summaries should not be regenerated for the same source and phase unless you intentionally create a new version.
- Candidate memories should be semantically merged when they say the same thing.
- Confirmed memories should be especially narrow and non-duplicative.

Useful weak identity fields:

```text
source_tool + source_id + date_range + message_count + transcript_hash
```

When metadata is incomplete, use best-effort ordering and mark confidence.

## Phase 3: Process Chronologically, But Triage First

Chronological order matters because decisions, preferences, and project direction evolve over time.

Process by `started_at` or the closest available timestamp. If a tool lacks reliable timestamps, use file modified time, export order, message timestamps, or surrounding project history, and mark the ordering as approximate.

However, chronological does not mean exhaustive deep summarization.

Suggested triage:

| Signal | Minimum action |
| --- | --- |
| Low | Add or update registry entry only. |
| Medium | Create Source Record and short Session Summary. |
| High | Create Source Record, phase summaries, Candidate Memories, and possibly Retrieval Briefing. |

## Phase 4: Split Long Sessions into Phases

Do not summarize long, multi-topic, or multi-day sessions as one flat note.

Use phase segmentation:

```text
Tool Session
  - Phase 1: context and intent
  - Phase 2: exploration
  - Phase 3: decision
  - Phase 4: implementation or execution
  - Phase 5: failure, correction, or reusable learning
```

Each phase summary should preserve:

- message range, timestamp range, or approximate boundary;
- goal at that point;
- key turns and reversals;
- rejected options and why they were rejected;
- current conclusion;
- open questions;
- candidate memories, if any.

This protects the reasoning chain. A final conclusion without the reason it emerged is usually not enough for future AI collaboration.

## Phase 5: Propose Candidate Memories Narrowly

Candidate Memory is the buffer between historical context and durable memory.

Only propose candidates for things that may matter repeatedly:

- stable collaboration preferences;
- repeated judgment standards;
- durable project decisions;
- reusable workflows;
- terms or conventions that future AI should understand;
- principles that affect future behavior.

Do not propose candidates for:

- temporary emotions;
- stale project facts;
- speculative ideas;
- one-off implementation details;
- anything contradicted later in the same historical sequence.

Each candidate should link back to its source session or phase summary.

## Phase 6: Confirm Manually

Confirmed Memory requires explicit human approval.

During review, ask:

- Will this repeatedly affect future judgment?
- Does it hold across contexts?
- Would the human otherwise need to re-explain it?
- Does it change how AI should behave later?
- Is the statement narrow enough to avoid overreach?

Keep unconfirmed material in Session Summary or Candidate Memory. Searchable context is useful even when it is not durable memory.

## Phase 7: Generate Retrieval Briefings

After a meaningful batch is processed, generate Retrieval Briefings for the themes or projects that need continuity.

A good briefing should include:

- relevant confirmed memories;
- recent session or phase context;
- still-unconfirmed candidate memories;
- open questions;
- known conflicts or stale assumptions;
- suggested next starting point.

Briefings are temporary context packs, not the knowledge body itself.

## What Not to Automate First

Do not automate these until the manual workflow is reliable:

1. raw chat to Confirmed Memory;
2. bulk importing all conversations as long-term memory;
3. destructive deduplication of source evidence;
4. automatic merging of sessions across tools;
5. automatic rewriting of existing confirmed memories;
6. embedding-heavy retrieval before the lifecycle is clean.

Automation should first help with listing, triage, duplicate detection, and draft summaries. Promotion to durable memory should remain human-controlled.

## Minimum Viable Backfill

Start with a small batch:

1. Export or list historical sessions from one tool.
2. Create a Backfill Queue.
3. Exclude sessions already listed in `session-registry.md`.
4. Select 20 to 50 medium/high-signal sessions.
5. Process them chronologically.
6. Split long sessions into phases.
7. Propose a small number of Candidate Memories.
8. Human reviews and confirms only the highest-signal memories.
9. Generate one Retrieval Briefing per active theme or project.

Scale only after the first batch proves the workflow does not pollute memory.
