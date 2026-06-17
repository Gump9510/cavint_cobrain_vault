---
type: prompt_template
status: draft
tool: opencode-question
---

# OpenCode Confirmation Prompt Template

Use this template when OpenCode should ask the human for a structured confirmation instead of forcing the human to read large amounts of source material.

## Purpose

This prompt format is designed for:

- Candidate Memory promotion;
- memory conflict resolution;
- project decision confirmation;
- protocol update confirmation;
- other high-signal approval points.

## Required Structure

Every confirmation prompt should contain these sections:

1. **What needs confirmation**
2. **Why now**
3. **Evidence**
4. **Risks / boundaries**
5. **Decision options**
6. **Recommended default** (optional but useful)

## Minimal Prompt Skeleton

```text
I need your confirmation before taking a durable or high-impact action.

What needs confirmation:
- {statement}

Why now:
- {why_now}

Evidence:
1. {excerpt_1} — {reason_1}
2. {excerpt_2} — {reason_2}

Risks / boundaries:
- {risk_1}
- {boundary_1}

Choose one:
1. {option_1}
2. {option_2}
3. {option_3}
4. {option_4}

Recommended default:
- {default_recommendation}
```

## OpenCode `question` Mapping

Recommended mapping:

- `header`: short decision label
- `question`: the full structured prompt
- `options`: explicit actions only
- `multiple`: `false` by default

## Example: Candidate Memory Promotion

```text
Header:
Confirm durable memory?

Question:
What needs confirmation:
- When the system needs human confirmation, it should prefer structured interactive confirmation over asking the human to read large amounts of vault history.

Why now:
- This would affect future memory promotion, conflict review, and project decision confirmation.

Evidence:
1. The workflow repeatedly hits high reading overhead during candidate review. — shows repeated friction.
2. The same pattern appears across memory, project, and protocol decisions. — shows cross-context relevance.

Risks / boundaries:
- Too broad a statement could over-template cases that still need open discussion.
- This does not apply when evidence is still missing.

Choose one:
1. Confirm and promote
2. Keep as candidate
3. Narrow and re-review
4. Reject

Recommended default:
- Keep as candidate until used in a few more real cases.
```

## Example: Project Decision Confirmation

```text
Header:
Confirm project direction?

Question:
What needs confirmation:
- Use Qdrant single-node as the first production vector store.

Why now:
- This choice affects deployment, implementation cost, and operational complexity.

Evidence:
1. Milvus was previously too heavy to maintain. — operational constraint.
2. The scale is only hundreds of thousands of images. — scale does not justify heavier infrastructure.

Risks / boundaries:
- Qdrant still introduces a service dependency.
- This recommendation assumes MySQL remains the source of truth.

Choose one:
1. Accept Qdrant
2. Prefer LanceDB first
3. Defer and gather more evidence
4. Reject current options
```

## Decision Rules

- Do not ask for open-ended approval when clear options are possible.
- Do not hide the action effect behind vague labels like “OK” or “continue.”
- Do not infer durable-memory approval from approval of a summary or a theme update.
- If the answer is “narrow,” rewrite the statement and ask again.
- If the answer is “merge,” identify the target object explicitly before executing.

## Codex Fallback Pattern

If the environment does not support interactive choice UI, fall back to a strict text protocol:

```text
Reply with one action only:
- action=confirm
- action=keep_candidate
- action=narrow
- action=merge
- action=reject

If action=narrow, also provide:
- rewrite="..."
```

## Post-Decision Action Checklist

After the human chooses:

1. Execute only the chosen action.
2. Update candidate / memory / project / protocol state.
3. Record the result in session summary or change log.
4. Keep evidence and final decision linked.
