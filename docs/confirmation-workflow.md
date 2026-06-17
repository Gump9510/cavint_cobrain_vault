---
type: workflow
status: draft
---

# Confirmation Workflow

This workflow exists to keep human confirmation small, structured, and traceable.

The goal is not to remove human confirmation. The goal is to prevent confirmation from turning into "please read a large pile of notes and decide everything yourself."

## Core Principle

```text
AI prepares the decision.
Human confirms the decision.
System records the decision.
```

The default path should be:

```text
Candidate or proposed action
  -> confirmation card
  -> human decision
  -> execution or rejection
  -> recording
```

## When to Use This Workflow

Use confirmation workflow when a decision would:

- promote Candidate Memory to Confirmed Memory;
- change a durable preference, boundary, identity, or long-term rule;
- resolve a memory conflict;
- approve a project-level decision with downstream impact;
- approve a protocol or policy update;
- approve a risky or broad write that should not be inferred from silence.

Do not use this workflow for every ordinary write. It is for human approval points, not routine summarization.

## Minimal Confirmation Flow

1. AI identifies a decision point.
2. AI produces a confirmation card.
3. Human chooses from explicit options.
4. AI executes only the chosen action.
5. AI records the decision and links the evidence.

## Confirmation Card Schema

```yaml
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
  - key: keep_candidate
    label: ""
    effect: ""
default_recommendation: ""
needs_user_input: true
decision: ""
decision_notes: ""
recording_required: true
```

## Required Fields Explained

### `statement`

One clear thing to confirm. Not a paragraph of analysis.

### `why_now`

Why the system is asking for confirmation at this moment.

### `source_evidence`

Do not dump full documents. Provide only the smallest useful evidence pack:

- where the evidence came from;
- a short excerpt;
- why that excerpt matters.

### `risks`

What goes wrong if this is confirmed too broadly or too early.

### `boundaries`

Where this statement should not apply.

### `options`

Human confirmation should be an explicit choice, not silence or implied acceptance.

## Standard Option Sets

### 1. Candidate Memory Promotion

```text
[Confirm and promote]
[Keep as candidate]
[Narrow and re-review]
[Merge into existing memory]
[Reject]
```

### 2. Memory Conflict Resolution

```text
[Keep old memory]
[Replace with new memory]
[Keep both with narrower boundaries]
[Defer and gather more evidence]
```

### 3. Project Decision Confirmation

```text
[Accept option A]
[Accept option B]
[Record but do not finalize]
[Need more evidence]
[Reject current options]
```

### 4. Protocol Update Confirmation

```text
[Accept update]
[Accept with narrower scope]
[Defer]
[Reject]
```

## OpenCode Interaction Pattern

In OpenCode, this workflow should normally be implemented with a structured interactive question step.

The human should not be asked to read a full session summary unless the evidence pack is still insufficient.

The normal interaction shape is:

```text
What needs confirmation:
- statement

Why now:
- why_now

Evidence:
1. short excerpt
2. short excerpt

Risks / boundaries:
- risk
- boundary

Choose one:
- option 1
- option 2
- option 3
```

See `.opencode/skills/cobrain-vault/references/confirmation-prompt-template.md` for a reusable prompt format.

## Execution Rules

- Never execute more than the confirmed action.
- Never infer Confirmed Memory promotion from a broad “yes.”
- If the human selects “narrow,” revise the statement first and ask again.
- If the human selects “merge,” identify the merge target explicitly.
- If the human rejects the card, record the rejection rather than repeatedly proposing the same candidate unchanged.

## Recording Rules

After a confirmation decision:

- update the candidate / memory / project / protocol object as appropriate;
- record the decision in a session summary or change log;
- keep the evidence trail;
- do not blur candidate and confirmed states.

## What This Workflow Is Not

This workflow is not:

- a replacement for evidence gathering;
- a shortcut that lets AI auto-confirm durable memory;
- a request for the human to manually browse raw vault history;
- a generic chat preference UI for every small decision.

It is a focused layer for high-signal human approval.
