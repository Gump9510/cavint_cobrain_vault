# CobrainVault

[中文说明](README.zh-CN.md)

CobrainVault is a local-first Markdown vault pattern for working with AI without turning every chat into unreliable long-term memory.

It separates raw evidence, session summaries, candidate memories, confirmed memories, themes, projects, outputs, and retrieval briefings so future AI sessions can resume with traceable context.

> This is a distributable template. The structure, protocols, and skill package are safe to share; real vault data should remain private.

## Core Idea

```text
Source -> Session -> Candidate Memory -> Confirmed Memory -> Retrieval Briefing
```

- **Source** is evidence, not memory.
- **Session** is continuity, not permanent truth.
- **Candidate Memory** is a proposal, not a rule.
- **Confirmed Memory** requires explicit human approval.
- **Retrieval Briefing** is a temporary context pack for the next AI session.

## What Do You Want To Do?

| Goal | Start here | AI should do |
| --- | --- | --- |
| Archive a webpage, PDF, screenshot, recording, or code observation | `10_sources/` | Create a SourceRecord; update theme/project only when useful. |
| Summarize an important conversation or work session | `20_sessions/` | Identify/create a source, write a Session Summary, and run relationship checks. |
| Continue a concrete project | `50_projects/` | Read the project, related themes, sources/sessions, outputs, and briefings. |
| Continue a long-running topic | `40_themes/` | Read the theme, related sessions, memories, projects, and recent briefings. |
| See what the AI is allowed to remember | `00_profile/` + `30_memories/` | Separate confirmed memories from candidates/evidence. |
| Confirm or reject durable memory | `30_memories/` | Use a structured confirmation card before promotion. |
| Find an old AI tool session | `90_indexes/session-registry.md` | Reverse lookup by tool session id or source pointer. |
| See what changed recently | `90_indexes/vault-change-log.md` or `90_indexes/change-log/` | Read semantic change logs, not only Git diff. |
| Produce a reusable artifact | `70_outputs/` | Read context first, then write the output and link sources/themes/projects. |

## Quick Start

1. Clone this repository or copy it as a private vault starter.
2. Open the folder in your Markdown editor, such as Obsidian, VS Code, or any local editor.
3. If your AI tool supports skills, install or copy the CobrainVault skill package:

   - OpenCode project skill: keep `.opencode/skills/cobrain-vault/SKILL.md` in this repository.
   - OpenCode global skill: copy `.opencode/skills/cobrain-vault/` to `~/.config/opencode/skills/cobrain-vault/`.
   - Claude-compatible skill: copy `.opencode/skills/cobrain-vault/` to `.claude/skills/cobrain-vault/` or `~/.claude/skills/cobrain-vault/`.

4. Tell your AI:

```text
Use the cobrain-vault skill for this folder. If skills are not available, read AGENTS.md first and follow the CobrainVault protocol.
```

5. Capture raw material into `10_sources/`.
6. Summarize meaningful work into `20_sessions/`.
7. Propose durable lessons in `30_memories/candidates/`.
8. Promote memory to `30_memories/confirmed/` only after explicit human confirmation.
9. Use `90_indexes/session-registry.md` and `90_indexes/vault-change-log.md` to keep the system auditable.

## Directory Map

| Path | Purpose |
| --- | --- |
| `00_profile/` | Memory policy and stable collaboration rules. |
| `10_sources/` | Raw evidence and source pointers. |
| `20_sessions/` | Summaries of meaningful conversations or work sessions. |
| `30_memories/` | Candidate and confirmed long-term memory objects. |
| `40_themes/` | Long-running domains of inquiry. |
| `50_projects/` | Concrete action units and deliverables. |
| `.opencode/skills/cobrain-vault/` | OpenCode-native CobrainVault skill package. |
| `60_skills-index/` | Optional notes for locally installed AI skills/rules; safe to leave empty. |
| `70_outputs/` | Reusable outputs, drafts, scripts, frameworks, offers. |
| `90_indexes/` | Templates, registries, logs, and retrieval briefings. |

## Privacy Boundary

This repository is intentionally a scaffold.

Do not commit:

- raw AI chats or recordings;
- real session IDs or tool URIs;
- private themes, projects, candidate memories, or outputs;
- `.obsidian/` workspace state;
- local absolute paths such as `/Users/...`.

The `.gitignore` is intentionally strict. If you want to use this as a real personal vault, fork it privately or relax the ignore rules only after you understand the privacy implications.

## Key Files

- `AGENTS.md` — operating protocol for AI agents.
- `.opencode/skills/cobrain-vault/SKILL.md` — OpenCode-native skill entrypoint.
- `.opencode/skills/cobrain-vault/references/confirmation-prompt-template.md` — reusable OpenCode question-style confirmation prompt template.
- `00_profile/memory-policy.md` — rules for memory promotion.
- `90_indexes/core-templates.md` — templates for Source, Session, Candidate Memory, Confirmed Memory, Retrieval Briefing, Session Registry, and Change Log.
- `docs/historical-ai-chat-backfill.md` — workflow for processing old AI tool conversations without polluting long-term memory.
- `docs/confirmation-workflow.md` — workflow for structured human confirmation before durable or high-impact actions.
