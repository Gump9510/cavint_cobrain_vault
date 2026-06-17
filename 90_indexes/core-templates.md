---
type: template_index
status: active
---

# CobrainVault Core Templates

These templates support the minimum memory loop:

```text
Source -> Session -> Candidate Memory -> Confirmed Memory -> Retrieval Briefing
```

## 1. Source Record

```markdown
---
id: src-YYYY-MM-DD-001
type: source_record
source_type: recording | ai_chat | web_clip | paper | doc | meeting | code | other
status: raw | parsed | summarized | organized | organized_with_review | triaged | archived
title: ""
origin:
  app: ""
  uri: ""
  author: ""
captured_at: YYYY-MM-DD HH:mm
language: en
project: ""
themes: []
people: []
related_sessions: []
created: YYYY-MM-DD
---

# Source: Title

## Raw Content / Pointer

Add raw text, transcript, link, local path, citation, or pointer.

## Lightweight Notes

- What this source is about.
- Whether it deserves further processing.
- Whether it contains sensitive information.

## Processing Log

- YYYY-MM-DD: captured
- YYYY-MM-DD: summarized / organized / archived
```

## 2. Session Summary

```markdown
---
id: session-YYYY-MM-DD-001
type: session_summary
status: active
title: ""
date: YYYY-MM-DD
source:
  - src-YYYY-MM-DD-001
themes: []
projects: []
participants: []
next_review: ""
created: YYYY-MM-DD
---

# Session: Title

## Goal

What this conversation, reading session, meeting, or work block tried to solve.

## Current State

Where things stand after this session.

## Actions Performed

- `CREATE | UPDATE | AUDIT | MOVE | DELETE`: `path/to/file.md` — why this action happened.
- If nothing was written, explicitly say: “No vault writes in this session.”

## Source / Environment

- Where the original material came from.
- If this was an AI tool session, record tool name and stable session pointer when available.

## Topic Timeline

- Capture major topic shifts in order.
- If there was only one topic, say so.

## Key Conclusions

- Concrete conclusions from this session.
- These are not automatically long-term memory.

## Lessons Learned

- Workflow or judgment lessons discovered during the session.
- Durable lessons should be proposed as Candidate Memory first.

## Open Questions

- Unresolved questions.
- Things to judge later.

## Candidate Memories

- Potential long-term memories that still need human confirmation.

## Theme Updates

- Themes that may need updates.

## Relationship Integrity Check

- [ ] Has source link or explains why no source exists.
- [ ] Has relevant session/tool pointer if applicable.
- [ ] Has project file link or marks project as missing/candidate.
- [ ] Has theme link or marks theme as new/candidate.
- [ ] Topic switches captured if conversation had multiple topics.
- [ ] Lessons separated from confirmed memory.
- [ ] Candidate memories remain unconfirmed until human approval.

## Next Actions

- Where to resume next time.
```

## 3. Candidate Memory

```markdown
---
id: cand-YYYY-MM-DD-001
type: candidate_memory
memory_type: preference | principle | decision | insight | procedure | project_context | question
status: candidate
scope: global | theme | project
confidence: low | medium | high
source:
  - 20_sessions/session-YYYY-MM-DD-001.md
relates_to: []
affects: []
suggested_by: ai | human
created: YYYY-MM-DD
---

# Candidate: Title

## Proposed Statement

One clear sentence describing what might be worth remembering.

## Why It Might Matter

Why this could matter in future sessions.

## Evidence

- Source, session, quote, or context that supports the candidate.

## Promotion Criteria Check

- [ ] Will repeatedly affect judgment.
- [ ] Holds across multiple contexts.
- [ ] Human expressed it more than once.
- [ ] Avoids repeated re-explanation.
- [ ] Changes how AI should behave later.

## Decision

- [ ] Promote to Confirmed Memory
- [ ] Keep as Candidate
- [ ] Merge into Existing Memory
- [ ] Reject

## Notes

Reason for confirmation, rejection, narrowing, or merge.
```

## 4. Confirmed Memory

```markdown
---
id: mem-YYYY-MM-DD-001
type: confirmed_memory
memory_type: preference | principle | decision | insight | procedure | project_context
scope: global | theme | project
status: active | stale | superseded | deprecated
confidence: high | medium | low
source:
  - 20_sessions/session-YYYY-MM-DD-001.md
relates_to: []
affects: []
supports: []
challenges: []
supersedes: []
used_by: []
created: YYYY-MM-DD
last_confirmed: YYYY-MM-DD
review_after: YYYY-MM-DD
summary: ""
---

# Memory: Title

## Statement

The durable memory, written clearly and narrowly.

## Why

Why it deserves to be remembered long-term.

## How

How it should affect future AI behavior, judgment, or collaboration.

## Evidence

- Linked source/session and key excerpts when useful.

## Boundaries

Where this memory does not apply.

## Review Notes

- When to review.
- What could supersede or narrow it.
```

## 5. Retrieval Briefing

```markdown
---
id: briefing-YYYY-MM-DD-001
type: retrieval_briefing
status: temporary
query_or_task: ""
themes: []
projects: []
generated_at: YYYY-MM-DD HH:mm
sources_used: []
memories_used: []
sessions_used: []
---

# Retrieval Briefing: Title

## Current Task

What the next session is trying to continue or solve.

## Current Theme State

Where the relevant theme currently stands.

## Relevant Memories

- Active confirmed memories relevant to this task.

## Relevant Decisions

- Decisions already made and not worth relitigating.

## Recent Session Context

- Recent sessions and what they changed.

## Open Questions

- Questions to prioritize next.

## Conflicts / Risks

- Conflicting, stale, or uncertain context.

## Suggested Starting Point

Recommended first move for the next session.

## Context Sources

- Files read to create this briefing.
```

## 6. Session Registry Entry

```markdown
### tool-session-id-here

~~~yaml
tool: OpenCode | Codex | Claude | ChatGPT | other
primary_uri: tool://session/session-id-here
date_range: ""
status:
  - captured
  - summarized
  - project-linked
  - theme-linked
  - outputs-linked
  - candidates-proposed
  - briefing-linked
  - actions-logged
  - needs-review
~~~

#### What this session contains

- What this session was about.

#### Vault artifacts

Source:
- `../10_sources/...`

Sessions:
- `../20_sessions/...`

Themes:
- `../40_themes/...`

Projects:
- `../50_projects/...`

Candidate memories:
- `../30_memories/candidates/...`

Outputs:
- `../70_outputs/...`

Briefings:
- `../90_indexes/...`

Open review items:
- What remains unorganized.
```

## 7. Backfill Queue Entry

Use this when processing historical AI tool sessions before deciding whether they deserve Source Records, Session Summaries, or Candidate Memories.

```markdown
### tool-session-id-or-source-id

~~~yaml
source_tool: OpenCode | Codex | Claude | ChatGPT | other
source_id: ""
locator: "tool://session/session-id-or-export-path"
title_or_hint: ""
started_at: ""
ended_at: ""
message_count: unknown
ordering_confidence: high | medium | low
processing_status: unprocessed | captured | triaged | summarized | phase-summarized | candidates-proposed | reviewed | archived
signal_level: low | medium | high
related_themes: []
related_projects: []
derived_sources: []
derived_sessions: []
candidate_memories: []
confirmed_memories: []
notes: ""
~~~

#### Triage notes

- Why this historical session does or does not deserve deeper processing.

#### Phase plan

- If this is a long or multi-topic session, list planned phases before summarizing.

#### Review status

- What still needs human review.
```

## 8. Confirmation Card

```markdown
---
id: confirm-YYYY-MM-DD-001
type: confirmation_card
confirmation_type: memory_promotion | memory_conflict | project_decision | protocol_update | other
status: pending | approved | rejected | revised | deferred
title: ""
statement: ""
why_now: ""
scope: global | theme | project
related_theme: ""
related_project: ""
source_evidence:
  - source: ""
    excerpt: ""
    reason: ""
risks: []
boundaries: []
options:
  - key: confirm
    label: ""
    effect: ""
default_recommendation: ""
needs_user_input: true
decision: ""
decision_notes: ""
recording_required: true
---

# Confirmation: Title

## What Needs Confirmation

The one thing that needs approval.

## Why Now

Why the system is asking for confirmation now.

## Evidence

- Small, high-signal excerpts only.

## Risks / Boundaries

- What could go wrong if confirmed too broadly.
- Where this does not apply.

## Options

- Confirm and execute
- Keep pending
- Narrow and re-review
- Merge
- Reject

## Final Decision

- Record the human choice here after confirmation.
```

## 9. Vault Change Log Entry

```markdown
## YYYY-MM-DD — Title

~~~yaml
operator: "AI / tool name"
trigger: "User request or task description"
mode:
  - session capture | memory proposal | theme maintenance | project maintenance | protocol maintenance | output production
confirmed_memory_created: false
~~~

### Why

Why this organization or write occurred.

### Added

- `path/to/new-file.md`

### Updated

- `path/to/updated-file.md`

### Not done

- What was intentionally not done and why.

### Follow-up

- Next step.
```

## 10. Profile Note

Use this for user background, collaboration preferences, judgment standards, boundaries, and long-term directions.

Confirmed profile notes require explicit human confirmation. Unconfirmed content must remain candidate/evidence only.

```markdown
### Title

Status: confirmed | candidate memory | candidate evidence only | open question

Category: background | collaboration_preference | judgment_standard | boundary | long_term_direction

Content:

- A concise statement of the profile note.

Evidence:

- [[source-or-session-or-candidate-memory]]

Boundaries:

- Where this note does not apply.
- If unconfirmed, explicitly state that it must not be used as confirmed profile context.

Next step:

- confirm | narrow | keep_candidate | reject
```
