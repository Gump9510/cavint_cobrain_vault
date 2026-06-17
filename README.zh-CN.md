# CobrainVault

[English](README.md)

CobrainVault 是一套本地优先的 Markdown vault 模板，用来和 AI 长期协作，同时避免把每一次聊天都变成不可靠的长期记忆。

它把原始证据、会话摘要、候选记忆、确认记忆、长期主题、具体项目、可复用输出和续接 briefing 分开管理，让未来的 AI 会话可以带着可追溯上下文继续工作。

> 这是一个可分发模板。仓库里的结构、协议和 skill 包可以安全分享；你自己的真实 vault 数据应保持私有。

## 核心思路

```text
Source -> Session -> Candidate Memory -> Confirmed Memory -> Retrieval Briefing
```

- **Source** 是证据，不是记忆。
- **Session** 用于续接，不是永久真理。
- **Candidate Memory** 是提案，不是规则。
- **Confirmed Memory** 必须经过人的明确确认。
- **Retrieval Briefing** 是下一次会话使用的临时上下文包。

## 我现在想做什么？

| 目标 | 从哪里开始 | AI 应该做什么 |
| --- | --- | --- |
| 归档网页、PDF、截图、录音或代码观察 | `10_sources/` | 创建 SourceRecord；必要时再更新 theme/project。 |
| 整理一次重要对话或工作会话 | `20_sessions/` | 识别或创建 source，写 Session Summary，并做关系完整性检查。 |
| 继续一个具体项目 | `50_projects/` | 读取 project、相关 themes、sources/sessions、outputs 和 briefings。 |
| 继续一个长期主题 | `40_themes/` | 读取 theme、相关 sessions、memories、projects 和最近 briefings。 |
| 查看 AI 可以记住什么 | `00_profile/` + `30_memories/` | 区分 confirmed memories、candidates 和 evidence。 |
| 确认或拒绝长期记忆 | `30_memories/` | 在升格前使用结构化 confirmation card。 |
| 查找旧 AI 工具会话 | `90_indexes/session-registry.md` | 通过 tool session id 或 source pointer 反查。 |
| 查看最近改动 | `90_indexes/vault-change-log.md` | 看语义化 change log，而不只依赖 Git diff。 |
| 生成可复用产物 | `70_outputs/` | 先读上下文，再写 output，并链接 source/theme/project。 |

## 快速开始

1. Clone 这个仓库，或复制为你自己的私人 vault 起点。
2. 用 Obsidian、VS Code 或任何本地 Markdown 编辑器打开该文件夹。
3. 如果你的 AI 工具支持 skills，可以安装或复制 CobrainVault skill 包：

   - OpenCode 项目级 skill：保留 `.opencode/skills/cobrain-vault/SKILL.md` 在本仓库中。
   - OpenCode 全局 skill：复制 `.opencode/skills/cobrain-vault/` 到 `~/.config/opencode/skills/cobrain-vault/`。
   - Claude-compatible skill：复制 `.opencode/skills/cobrain-vault/` 到 `.claude/skills/cobrain-vault/` 或 `~/.claude/skills/cobrain-vault/`。

4. 对你的 AI 说：

```text
Use the cobrain-vault skill for this folder. If skills are not available, read AGENTS.md first and follow the CobrainVault protocol.
```

5. 把原始材料放入 `10_sources/`。
6. 把有续接价值的工作整理到 `20_sessions/`。
7. 把可能长期有用的经验先提名到 `30_memories/candidates/`。
8. 只有在你明确确认后，才把记忆升格到 `30_memories/confirmed/`。
9. 使用 `90_indexes/session-registry.md` 和 `90_indexes/vault-change-log.md` 保持系统可审计。

## 目录说明

| 路径 | 用途 |
| --- | --- |
| `00_profile/` | 记忆政策和稳定协作规则。 |
| `10_sources/` | 原始证据和 source pointers。 |
| `20_sessions/` | 重要对话或工作会话摘要。 |
| `30_memories/` | 候选与已确认长期记忆。 |
| `40_themes/` | 长期主题和认知地图。 |
| `50_projects/` | 具体行动单元和交付物。 |
| `.opencode/skills/cobrain-vault/` | OpenCode 原生 CobrainVault skill 包。 |
| `60_skills-index/` | 本地安装的 AI skills/rules 备注；可以保持为空。 |
| `70_outputs/` | 可复用输出、草稿、脚本、框架、offer。 |
| `90_indexes/` | 模板、注册表、change log 和 retrieval briefings。 |

## 隐私边界

这个仓库本身是 scaffold。

不要提交：

- 原始 AI 聊天记录或录音；
- 真实 session id 或 tool URI；
- 私人 themes、projects、candidate memories 或 outputs；
- `.obsidian/` 工作区状态；
- `/Users/...` 这样的本地绝对路径。

`.gitignore` 默认较严格。如果你要把它变成真实私人 vault，请先 fork 成私有仓库，或在理解隐私影响后再调整 ignore 规则。

## 关键文件

- `AGENTS.md` — AI agent 操作协议。
- `.opencode/skills/cobrain-vault/SKILL.md` — OpenCode 原生 skill 入口。
- `.opencode/skills/cobrain-vault/references/confirmation-prompt-template.md` — OpenCode question-style confirmation prompt 模板。
- `00_profile/memory-policy.md` — 记忆升格规则。
- `90_indexes/core-templates.md` — Source、Session、Candidate Memory、Confirmed Memory、Retrieval Briefing、Session Registry 和 Change Log 模板。
- `docs/historical-ai-chat-backfill.md` — 整理历史 AI 工具会话的流程。
- `docs/confirmation-workflow.md` — 对长期或高影响动作做人类确认的流程。
