# CobrainVault Agent Operating Protocol

This vault is a local-first human-AI cobrain system. Treat it as a memory operating system, not as a dumping ground for notes.

## Prime Directive

Preserve human agency and memory quality. AI may capture, summarize, connect, and propose memory updates, but long-term memory must stay narrow, traceable, and explicitly confirmed by the human.

Core loop:

```text
Source -> Session -> Candidate Memory -> Confirmed Memory -> Retrieval Briefing
```

## When This Protocol Applies

Use this protocol whenever the user asks to read, write, continue, summarize, search, maintain, or reason from this vault.

Strong trigger phrases include:

- "read CobrainVault"
- "follow AGENTS.md"
- "continue this theme/project"
- "organize this conversation"
- "write into the vault"
- "create session summary / candidate memory / retrieval briefing"
- "update theme / update project"
- "save this lesson for later"

## When Not To Use This Protocol

Do not write into the vault for every ordinary chat.

Skip vault writes when:

- the user asks a one-off factual question;
- the answer is short-lived and will not affect future work;
- no source, session, project, theme, memory, output, or briefing would be useful later;
- the user explicitly asks not to save or record anything.

## Operating Modes

Classify the user's request before acting:

| Mode | User intent | Minimum action |
| --- | --- | --- |
| Context retrieval | Continue a topic/project | Read protocol + relevant theme/project/session/memory; produce or update Retrieval Briefing when useful. |
| Session capture | Summarize a meaningful conversation | Create SourceRecord pointer if possible, then Session Summary. |
| Memory proposal | Extract durable lessons/preferences | Read memory policy, create Candidate Memory only. |
| Memory confirmation | User explicitly confirms a candidate | Promote/create Confirmed Memory with source, scope, status, and review date. |
| Profile maintenance | Extract or update user background, preferences, boundaries, or long-term directions | Read `00_profile/profile-maintenance.md`; write confirmed facts only after explicit confirmation; otherwise add candidate/evidence notes. |
| Theme maintenance | Long-running domain changed | Update relevant `40_themes/` file with sourced, non-final wording. |
| Project maintenance | Concrete initiative advanced | Update or create relevant `50_projects/` file. |
| Output production | Create reusable article/script/offer/framework | Read relevant context, write output in `70_outputs/`, link sources/context. |
| Historical backfill | Organize old AI tool conversations | Build a backfill queue, deduplicate, triage, then create Source/Session/Candidate records only for useful sessions. |
| Confirmation workflow | Ask for durable or high-impact human approval | Build a structured confirmation card, ask explicit options, then record the decision. |
| Protocol maintenance | Improve vault rules, templates, or installed-skill notes | Update `AGENTS.md`, `90_indexes/`, or `60_skills-index/`; record rationale when substantial. |

If multiple modes apply, execute the smallest set that preserves continuity and traceability.

## Required Startup Sequence

Before reading or writing substantive content in this vault:

1. Read this `AGENTS.md`.
2. Read `README.md` to understand the current directory structure.
3. Read `00_profile/memory-policy.md` before creating or changing any memory object.
4. Read `90_indexes/core-templates.md` before writing Source, Session, Candidate Memory, Confirmed Memory, or Retrieval Briefing files.
5. Search/read relevant existing theme, project, session, and memory files before proposing new entries, to avoid duplicates and contradictions.
6. If the current interaction itself is a substantive AI chat, create or identify a SourceRecord pointer before writing a Session Summary.
7. If a project is named or implied, verify that a corresponding file exists in `50_projects/`; create a project context file when the work is active and concrete.

If you cannot access one of these required files, stop and clearly report the missing file instead of guessing the protocol.

## Search Protocol

When the user asks whether something has been organized already:

1. Search `90_indexes/session-registry.md` for the tool session id, source id, or title.
2. Search `10_sources/` for source pointers or raw evidence references.
3. Search `20_sessions/` for session summaries.
4. Search `40_themes/` and `50_projects/` for theme/project continuity.
5. If still not found, report that no organized record exists yet and propose the smallest useful write.

Do not rely only on conversation memory when a relevant vault file exists.

## Historical AI Chat Backfill

When organizing historical AI tool conversations, follow `docs/historical-ai-chat-backfill.md`.

Do not treat historical chat import as memory import. Historical conversations should be processed as:

```text
Raw Tool History -> Source -> Session or Phase Summary -> Candidate Memory -> Confirmed Memory -> Retrieval Briefing
```

Before summarizing, create or update a backfill queue using the Backfill Queue Entry template in `90_indexes/core-templates.md`.

Rules:

- Process chronologically when possible, but triage before deep summarization.
- Register low-signal sessions without forcing a Session Summary.
- Split long, multi-topic, or multi-day sessions into phases.
- Preserve rejected options and reasons, not just final conclusions.
- Propose Candidate Memories narrowly and link them to source sessions.
- Never promote historical content to Confirmed Memory without explicit human confirmation.

## Confirmation Workflow

When a durable or high-impact decision needs human approval, follow `docs/confirmation-workflow.md`.

Do not turn confirmation into a reading task. The default path should be:

```text
candidate or proposed action
-> confirmation card
-> explicit human choice
-> execution or rejection
-> recording
```

For OpenCode-style interaction, use the reusable prompt format in `.opencode/skills/cobrain-vault/references/confirmation-prompt-template.md`.

Rules:

- provide a clear statement, why now, evidence, risks, boundaries, and explicit options;
- never infer Confirmed Memory promotion from a broad or ambiguous “yes”;
- if the human narrows the statement, rewrite first and ask again;
- execute only the confirmed action, not adjacent actions.

## Profile Maintenance

Use `00_profile/profile-maintenance.md` when a conversation or historical session reveals stable user background, collaboration preferences, boundaries, judgment standards, or long-term directions.

Default flow:

```text
Source/Session evidence -> Candidate Memory or Candidate Profile Note -> Confirmation Card -> Confirmed Profile section
```

Rules:

- do not write identity, background, preference, boundary, or long-term direction into a confirmed profile section without explicit human confirmation;
- candidate/evidence notes must link to source, session, theme, project, or candidate memory;
- keep profile files narrow: background in `user-background.md`, collaboration behavior in `collaboration-preferences.md`, long-term direction in `long-term-directions.md`;
- if evidence is only inferred by AI, keep it as an open question instead of a candidate fact.

## Directory Contract

- `00_profile/`: Memory policies, stable collaboration rules, user background, preferences, boundaries, and long-term directions. Read carefully; write conservatively.
- `10_sources/`: Raw or lightly processed evidence. Broad capture is allowed, but keep provenance.
- `20_sessions/`: Session summaries and event summaries. Use this to preserve continuity. A session summary is not permanent truth.
- `30_memories/`: Candidate and confirmed long-term memory objects. Candidate is proposal; confirmed is human-approved durable memory.
- `40_themes/`: Long-running domains of inquiry and evolving cognitive maps.
- `50_projects/`: Concrete action units with goals, state, deliverables, decisions, and next actions.
- `60_skills-index/`: Optional maps and explanations for locally installed AI skills, commands, rules, or workflows. CobrainVault must still work when this directory is empty.
- `70_outputs/`: Reusable outputs such as articles, scripts, offers, frameworks, and finished deliverables.
- `90_indexes/`: Indexes, templates, retrieval briefings, and navigation layers. These are rebuildable maps, not the knowledge body itself.

## Default Routing

Use this as a default path, not as a rigid one-file-only rule. Route by input type first, then run the completeness check below.

| User input / intent | Default location | Also check |
| --- | --- | --- |
| URL, webpage, article, web clip | `10_sources/` | Related theme/project; whether it deserves a session summary. |
| PDF, document, report | `10_sources/` | Citation/pointer, key excerpts, related theme/project. |
| Recording, transcript, interview, meeting | `10_sources/` | Whether to create a session/event summary. |
| AI tool conversation | `10_sources/` + `20_sessions/` | `90_indexes/session-registry.md`, theme/project, candidate memory. |
| Screenshot, video frame, visual QA evidence | `10_sources/` or a supporting evidence index | Parent project/theme; avoid deep-backfilling low-signal visual checks. |
| Codebase/repository observation | `10_sources/` or project-linked source note | Do not copy full repositories; record path/commit/pointer and key files. |
| User background, preference, boundary, long-term direction | `00_profile/` candidate/evidence note | Candidate/Confirmed memory boundary; explicit confirmation before durable memory. |
| Long-running domain understanding changed | `40_themes/` | Source/session links; candidate memories if durable. |
| Concrete initiative advanced | `50_projects/` | Related theme/source/session/output links. |
| Reusable deliverable created | `70_outputs/` | Link context sources, theme, and project. |
| Index, template, registry, briefing, change log | `90_indexes/` | Keep it navigational and rebuildable, not the knowledge body. |

## After Routing, Check Completeness

Before finishing a vault write, ask which of these are needed and write only the smallest useful set:

- SourceRecord: is there evidence or a stable pointer to preserve?
- Session Summary: did a meaningful conversation, reading, or work block need continuity?
- Theme update: did understanding of a long-running domain change?
- Project update: did a concrete initiative advance or change state?
- Candidate Memory: did a durable lesson/preference/decision emerge?
- Profile note: did user background, preference, boundary, or long-term direction appear?
- Retrieval Briefing: should the next session resume from this context?
- Session registry: is there a stable AI tool session id?
- Change log: did any substantive vault write happen?

## Read/Write Rules

### Default Access

- Read before writing.
- Prefer appending clearly dated notes over silently overwriting history.
- Keep evidence, interpretation, and confirmed memory separate.
- Use Markdown with YAML frontmatter when templates provide it.
- Prefer relative links within the vault.

### Allowed Without Explicit Confirmation

- Create or update Source records in `10_sources/` when preserving evidence or pointers.
- Create Session Summary files in `20_sessions/` after a meaningful conversation or work session.
- Create Candidate Memory files in `30_memories/candidates/` when a possible long-term memory emerges.
- Create Retrieval Briefings in `90_indexes/` for a specific future task.
- Update Theme or Project files with clearly marked session-derived updates, provided they do not pretend to be confirmed long-term memory.

### Requires Explicit Human Confirmation

- Create a Confirmed Memory in `30_memories/confirmed/`.
- Promote a Candidate Memory to Confirmed Memory.
- Mark a user preference, boundary, identity claim, or long-term decision as durable.
- Delete, archive, supersede, or materially rewrite an existing Confirmed Memory.
- Change this `AGENTS.md` or `00_profile/memory-policy.md` in a way that weakens safety or promotion rules.

### Forbidden

- Do not turn raw chat content directly into Confirmed Memory.
- Do not treat one-off emotions, temporary drafts, or speculative claims as durable memory.
- Do not store secrets, credentials, private keys, tokens, or sensitive personal data unless the user explicitly instructs how to handle them.
- Do not bulk-import unrelated files into the vault just because they exist.
- Do not overwrite source evidence to fit a later interpretation.

## Required Relationship Integrity

For any substantial session summary, verify these relationships before finishing:

- It links at least one SourceRecord or clearly explains why no source exists.
- If it references an AI tool conversation, it records the tool name and stable session pointer when available.
- Every named active project has a corresponding file in `50_projects/`.
- Every named theme either links to an existing theme file or is marked as a candidate/new theme.
- Topic switches are captured in a timeline when the conversation covers more than one major topic.
- Lessons learned are separated from confirmed memory; durable lessons should be proposed as Candidate Memory first.
- Any Retrieval Briefing generated from the session links the session in `sessions_used`.
- The session is listed in `90_indexes/session-registry.md` when it comes from a tool with a stable session id.
- Any substantive vault write is recorded in `90_indexes/vault-change-log.md`.

## Memory Promotion Rules

Follow `00_profile/memory-policy.md` as the source of truth.

A Candidate Memory may be proposed when it plausibly matches at least one long-term category:

- stable collaboration preference;
- repeated judgment standard;
- explicit boundary or taboo;
- core principle of a long-term theme;
- verified workflow or method;
- decision that will keep affecting future AI behavior.

Promotion from Candidate to Confirmed requires explicit human confirmation and should normally satisfy at least two of these checks:

- it will repeatedly affect future judgment;
- it holds across multiple contexts;
- the user has expressed it more than once;
- without remembering it, the user would need to explain it repeatedly;
- it changes how AI should behave in later sessions.

## Theme vs Project

Use this distinction consistently:

- Theme: a long-running domain of inquiry. It has no fixed end date and accumulates principles, mechanisms, examples, contradictions, and judgment frameworks.
- Project: a concrete action unit. It has goals, current status, deliverables, constraints, decisions, and next actions.

Decision rule:

```text
If it answers “how do we understand this class of problem over time?”, write/update a Theme.
If it answers “what are we trying to make, ship, test, or finish now?”, write/update a Project.
```

Projects may reference Themes. Themes may absorb lessons from Projects.

## Privacy Guard

If this repository is used as a template or shared with others:

- never include real names, private project titles, private session IDs, or internal URIs in template files;
- do not commit files under data directories unless they are explicitly fictional examples;
- replace local absolute paths with placeholders such as `<VAULT_PATH>`;
- keep `.obsidian/` workspace state out of version control.

## Session-End Ritual

After a substantial conversation or work session involving this vault, consider producing:

1. A Session Summary in `20_sessions/`.
2. Candidate Memories in `30_memories/candidates/` only for high-signal durable candidates.
3. Theme Updates in `40_themes/` when a long-running domain changed.
4. Project Updates in `50_projects/` when a concrete initiative advanced.
5. A Retrieval Briefing in `90_indexes/` if the next session should resume from specific context.
6. Session registry update when a stable tool session id exists.
7. Vault change log entry when any substantive write occurred.

Do not perform all seven mechanically. Choose the smallest set that preserves continuity without polluting memory.
