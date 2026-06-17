---
name: cobrain-vault
description: Use when organizing AI conversations, sources, sessions, candidate memory, confirmed memory, projects, themes, outputs, and retrieval briefings in a local-first Markdown vault.
license: MIT
compatibility: opencode
metadata:
  system: cobrain-vault
  storage: markdown
---

# CobrainVault Skill

Use this skill to operate a CobrainVault: a local-first Markdown vault that separates evidence, session continuity, candidate memory, confirmed memory, projects, themes, outputs, and retrieval briefings.

This skill is the tool-native launcher. It does not replace the vault's own `AGENTS.md`; it tells the AI how to enter the vault correctly.

## When to use this skill

Use this skill when the human asks to:

- read, continue, search, summarize, or maintain a CobrainVault;
- organize an AI conversation, recording, document, webpage, code observation, or work session;
- create or update Source, Session, Candidate Memory, Confirmed Memory, Theme, Project, Output, Registry, Change Log, or Retrieval Briefing files;
- extract stable profile context, collaboration preferences, boundaries, or long-term directions;
- confirm, reject, narrow, merge, or promote durable memory;
- improve the vault protocol, templates, routing notes, or skill packaging.

Do not use this skill for ordinary one-off questions that do not need future continuity.

## Required startup sequence

Before doing substantive vault work:

1. Identify the vault root. If the human does not provide an absolute path, use the current repository root when it contains `AGENTS.md`.
2. Read `<VAULT_PATH>/AGENTS.md` and follow it strictly.
3. Read `<VAULT_PATH>/README.md` to understand the current directory structure.
4. If memory, profile, preference, boundary, or durable behavior is involved, read `<VAULT_PATH>/00_profile/memory-policy.md`.
5. If writing Source, Session, Candidate Memory, Confirmed Memory, Retrieval Briefing, Session Registry, or Change Log files, read `<VAULT_PATH>/90_indexes/core-templates.md`.
6. Search/read relevant existing source, session, theme, project, memory, output, registry, and briefing files before creating new ones.
7. Write only the smallest useful set of files that preserves traceability.

If `AGENTS.md` is unavailable, stop and report the missing file. Do not guess the protocol.

## Memory and confirmation rules

- Source is evidence, not long-term memory.
- Session Summary is continuity, not permanent truth.
- Candidate Memory is a proposal, not a rule.
- Confirmed Memory requires explicit human confirmation.
- Never infer Confirmed Memory promotion from approval of a summary, theme update, or broad “yes.”
- Keep evidence, interpretation, candidate memory, and confirmed memory separate.

For durable or high-impact approval points, follow `<VAULT_PATH>/docs/confirmation-workflow.md` and use `references/confirmation-prompt-template.md` as the OpenCode-style prompt reference.

## Relationship integrity check

Before finishing a substantive vault write, verify whether the smallest useful set needs:

- SourceRecord: evidence or stable pointer preserved.
- Session Summary: meaningful conversation, reading, or work block captured for continuity.
- Theme update: long-running domain understanding changed.
- Project update: concrete initiative advanced or changed state.
- Candidate Memory: durable lesson, preference, boundary, workflow, or decision proposed.
- Profile note: background, preference, boundary, or long-term direction appeared.
- Retrieval Briefing: next session should resume from this context.
- Session registry: stable AI tool session id exists.
- Change log: substantive vault write happened.

Do not perform every step mechanically. Choose the smallest set that preserves continuity without polluting memory.

## Output standard

When reporting back to the human, include:

- which key protocol files were read;
- which operating mode was used;
- which files were created or updated;
- whether any Candidate Memory or Confirmed Memory was created;
- where the next session should resume.
