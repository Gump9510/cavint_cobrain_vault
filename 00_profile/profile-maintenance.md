---
type: profile_maintenance_protocol
status: active
---

# Profile Maintenance Protocol

This file defines how to extract user background, preferences, boundaries, and long-term directions without turning unconfirmed inferences into durable facts.

## Triggers

Consider profile maintenance when:

1. the human explicitly states background, profession, experience, identity, or long-term direction;
2. the human explicitly states a stable collaboration preference, boundary, or taboo;
3. the same judgment standard appears across multiple sessions or projects;
4. historical backfill reveals a profile clue that would affect future AI collaboration;
5. the human asks what the AI knows about their background, habits, or preferences.

## Non-triggers

Do not write profile notes for:

1. one-off emotions or temporary ideas;
2. project state that belongs in `50_projects/`;
3. AI-only inference without source/session evidence;
4. external opinions unless the human adopts them as their own judgment.

## Flow

```text
Source / Session evidence
-> Candidate Memory or Candidate Profile Note
-> Structured confirmation card
-> Human confirmation
-> Confirmed profile section
-> Change log
```

## File roles

- `user-background.md`: what the human has done, is doing, or has experience with.
- `collaboration-preferences.md`: how the human wants AI collaboration, judgment, and confirmation to work.
- `long-term-directions.md`: long-term themes, career/business hypotheses, and compounding directions.

## Rules

- Confirmed sections require explicit human confirmation.
- Candidate/evidence sections must link to source, session, or candidate memory.
- If evidence is insufficient, write an open question instead of a fact.
