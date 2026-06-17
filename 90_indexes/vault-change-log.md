---
type: vault_change_log
status: active
---

# Vault Change Log

Use this file to record substantive vault writes: what changed, why it changed, which files were added/updated, and whether Confirmed Memory was created.

Do not add private activity history to a template repository.

## 2026-06-15 — 记录 Bybit KYT 资料交付

~~~yaml
operator: "Codex"
trigger: "用户口述：今天下班前向 Brandon 提供并修改 Bybit KYT 资料"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

用户明确了一项带当天截止时间的 Bybit 相关交付，需要加入现有 Bybit Custody 项目的优先行动。

### Added

- `10_sources/src-2026-06-15-002.md`

### Updated

- `50_projects/business-kms-bybit-connectivity.md`
- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次是单点任务登记。
- 未创建 Candidate 或 Confirmed Memory：这是短期项目行动。
- 未推断 KYT 资料的具体清单和修改内容。

### Follow-up

- 2026-06-15 下班前完成资料修改并提供给 Brandon，之后回填交付状态。

## 2026-06-15 — 记录 VF 和 NS 部署架构沟通

~~~yaml
operator: "Codex"
trigger: "用户口述：VF 和 NS 部署今天需要跟架构沟通"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

用户明确了当天需要推进的部署沟通事项，且 vault 中没有对应项目，需要建立最小项目上下文以便后续回填结论。

### Added

- `10_sources/src-2026-06-15-001.md`
- `50_projects/vf-ns-deployment.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次是单点任务登记。
- 未创建 Candidate 或 Confirmed Memory：这是短期项目行动。
- 未推断 VF、NS 的全称、部署范围或目标环境。

### Follow-up

- 2026-06-15 与架构沟通后，回填部署方案、依赖、负责人和排期。

## 2026-06-14 — 生成 CobrainVault 小黑风格正文配图

~~~yaml
operator: "Codex"
trigger: "用户要求为 vault 生成 3 张 16:9 小黑风格正文配图"
mode:
  - output production
confirmed_memory_created: false
~~~

### Why

将 CobrainVault 的记忆分层、关联项目和检索续接三个核心概念转化为可复用的正文插图。

### Added

- `assets/cobrain-vault-illustrations/01-memory-layers.png`
- `assets/cobrain-vault-illustrations/02-linked-projects.png`
- `assets/cobrain-vault-illustrations/03-retrieval-briefing.png`
- `70_outputs/cobrain-vault-xiaohei-illustrations.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次目标是直接产出图片。
- 未创建 Candidate 或 Confirmed Memory：没有形成需长期记忆的新规则。

### Follow-up

- 在介绍 CobrainVault 的文章或文档中按主题选用对应配图。

## 2026-06-14 — OceanBase 进入部署并关联 Fund Center

~~~yaml
operator: "Codex"
trigger: "用户口述：OceanBase 运维已在部署，下周持续跟进，并与 Fund Center 关联"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

OceanBase 已解除等待运维确认的 pending 状态并进入部署过程；同时需要将其与 Fund Center 项目建立双向关联，以便同步跟进依赖和阻塞。

### Added

- `10_sources/src-2026-06-14-003.md`

### Updated

- `50_projects/oceanbase-deployment.md`
- `50_projects/fund-center-all-brand-resources.md`
- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次是单点项目状态更新。
- 未创建 Candidate 或 Confirmed Memory：这是当前项目状态和关系。
- OceanBase 的目标环境、部署完成日期及具体承载范围仍待明确。

### Follow-up

- 2026-06-15 至 2026-06-21 持续跟进部署进展，并同步记录对 Fund Center 的影响。

## 2026-06-14 — Bybit Custody 进入联调阶段

~~~yaml
operator: "Codex"
trigger: "用户口述：Bybit Custody 已进入联调阶段，下周启动"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

Bybit Custody 已解除等待 Tony 确认的 pending 状态，项目进入联调阶段，需要更新状态和下周行动计划。

### Added

- `10_sources/src-2026-06-14-002.md`

### Updated

- `50_projects/business-kms-bybit-connectivity.md`
- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次是单点项目进展更新。
- 未创建 Candidate 或 Confirmed Memory：这是当前项目状态。
- 尚未设定新的联调完成和上线日期。

### Follow-up

- 2026-06-15 至 2026-06-21 启动联调，并根据结果重排上线时间。

## 2026-06-14 — 记录周一 Fund Center 部署与转账跟进事项

~~~yaml
operator: "Codex"
trigger: "用户口述：周一推进 Fund Center 全品牌部署，并跟进转账相关详情"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

用户明确了 2026-06-15 的两项项目行动，需要追加到现有 Fund Center 项目以便后续跟进。

### Added

- `10_sources/src-2026-06-14-001.md`

### Updated

- `50_projects/fund-center-all-brand-resources.md`
- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未创建 Session Summary：本次是单点任务登记。
- 未创建 Candidate 或 Confirmed Memory：这些是短期项目行动。
- 转账事项的具体业务范围和对接对象尚未明确，保留为待跟进问题。

### Follow-up

- 2026-06-15 推进后，回填部署进展和转账详情结论。

## 2026-06-08 — 记录今日修复任务：日志噪音 + 订单号重复

~~~yaml
operator: "Cobrain"
trigger: "用户口述：今天要修复日志噪音问题，还要修复订单号重复问题"
mode:
  - session capture
confirmed_memory_created: false
~~~

### Why

用户告知当天两个修复任务，需要落地为可追溯的 source + session，避免今天工作内容丢失。

### Added

- `10_sources/src-2026-06-08-001.md`
- `20_sessions/session-2026-06-08-001.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 所属服务/模块未明确，未关联具体 project。
- 未提名 Candidate Memory：属于当日任务，不是长期偏好。

### Follow-up

- 修复完成后，更新 session-2026-06-08-001 的 Current State，补充服务/模块信息。
- 若涉及已有项目（如跟单-资金中台、闪兑等），在对应 project 文件中关联。

## 2026-05-26 — 首次启用 vault：记录第一条 source + session

~~~yaml
operator: "Claude Code"
trigger: "用户问'我最近在干嘛'，发现 vault 为空后同意把本次会话作为第一条记录"
mode:
  - session capture
confirmed_memory_created: false
~~~

### Why

vault 此前仅有 scaffold（2 个 commit、所有目录均为空 README）。用户决定从这次 Claude Code 会话开始正式使用，需要建立第一条可追溯的 source/session 记录。

### Added

- `10_sources/src-2026-05-26-001.md`
- `20_sessions/session-2026-05-26-001.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未登记 session-registry：本次 Claude Code 会话无稳定 session id 可追溯。
- 未提名任何 Candidate Memory：信号偏低，等持续使用后再判断。
- 未写 profile note：尚未出现稳定偏好/边界等需要登记的内容。

### Follow-up

- 用户开始具体项目时，在 `50_projects/` 创建对应文件。
- 出现稳定偏好/边界/长期方向时，走 `00_profile/profile-maintenance.md` 流程。

## 2026-05-26 — 跟单-资金中台对接项目首次落地

~~~yaml
operator: "Claude Code"
trigger: "用户转述与 Wilson 沟通：确认无循环调用，meti 动账调用方式待 2026-05-27 答复"
mode:
  - session capture
  - project maintenance
confirmed_memory_created: false
~~~

### Why

用户给出具体项目进展（已确认事项 + 明日待办），需要登记为可追溯的 project + session，避免明天信息回流时丢失今天的状态。

### Added

- `10_sources/src-2026-05-26-002.md`
- `20_sessions/session-2026-05-26-002.md`
- `50_projects/follow-trade-treasury-integration.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未登记 session-registry：信息源是用户转述，无 AI tool session id。
- 未提名 Candidate Memory：属于项目状态而非长期偏好。
- meti 与跟单系统的精确职责边界未在 vault 中固化，等下一轮信息回流再补。

### Follow-up

- 2026-05-27：对方答复后更新 `50_projects/follow-trade-treasury-integration.md` 的 Current State / Decisions。
- 若答复触发接口/时序设计，再考虑在 `70_outputs/` 起草草案。

## 2026-05-26 — 闪兑服务项目立项

~~~yaml
operator: "Claude Code"
trigger: "用户转述：Rocket 和 Selina 仍在决定闪兑服务归属；cavint 2026-05-27 介入技术方案设计"
mode:
  - session capture
  - project maintenance
confirmed_memory_created: false
~~~

### Why

明日要介入闪兑服务技术方案设计，需要在 vault 中先建立项目骨架与今日已知状态，明日开场可直接读取上下文。

### Added

- `10_sources/src-2026-05-26-003.md`
- `20_sessions/session-2026-05-26-003.md`
- `50_projects/flash-exchange-service-design.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未登记 session-registry：用户转述，无 AI tool session id。
- 未提名 Candidate Memory：项目状态，不是长期偏好。
- 未在 `40_themes/` 立 theme：现有信息只构成具体项目，尚不足以支撑长期主题。

### Follow-up

- 2026-05-27 介入后：更新闪兑项目的 Current State / Decisions；判断是否需要在 `70_outputs/` 起草方案草案。
- 留意闪兑与 [[follow-trade-treasury-integration]] 是否产生依赖或链路复用。

## 2026-05-26 — 新建 theme au-vt-brand-architecture + Candidate（数据严格独立）

~~~yaml
operator: "Claude Code"
trigger: "用户：AU 和 VT 是不同的品牌，他们使用不同套的前端代码，但是是使用同一套后端代码，但是部署到的是不同的机房，不同的服务。他们的数据严格独立"
mode:
  - session capture
  - theme maintenance
  - memory proposal
confirmed_memory_created: false
~~~

### Why

用户一次性给出 AU/VT 在前端代码 / 后端代码 / 部署 / 数据 4 个层面的分离-共用关系。这是众多其他 theme/project 的前置底座，需要单独立 theme（避免在每个项目里重复推导）。"数据严格独立"是硬约束，单独提名 Candidate Memory（建议升 Confirmed）。

### Added

- `10_sources/src-2026-05-26-008.md`
- `40_themes/au-vt-brand-architecture.md`
- `30_memories/candidates/cand-2026-05-26-002.md`

### Updated

- `40_themes/wallet-domain-routing.md`：related_sources 加 src-008；解决"AU/VT 是否同 binary"开放问题（划掉并标注答案）；Related 加 [[au-vt-brand-architecture]] 与 cand-2026-05-26-002。
- `90_indexes/vault-change-log.md`（本条目）。

### Not done

- 未直接升 cand-2026-05-26-002 到 Confirmed：等用户显式确认。建议在 2026-05-27 介入闪兑方案设计前升格，AI 可主动应用此约束。
- au-vt-brand-architecture 的"单 repo vs 多 repo""中台/平台层是否存在"等问题保留为 Open Questions，等下一条证据再补。

## 2026-05-26 — wallet-domain-routing 修正：AU/VT 共用机制但候选分组

~~~yaml
operator: "Claude Code"
trigger: "用户：AU 和 VT 是不同的品牌，它们使用不同组的域名"
mode:
  - theme maintenance
confirmed_memory_created: false
~~~

### Why

src-006 当时被解读为"AU/VT 共用同一份候选"，与 src-007 + 实际两组域名互不重叠的事实冲突。按协议保留历史表述（Superseded 段），用 src-007 修正 Verified Facts、Mechanism Map、Open Questions、Principles。

### Added

- `10_sources/src-2026-05-26-007.md`

### Updated

- `40_themes/wallet-domain-routing.md`：
  - related_sources 加 src-007；
  - 第 3 段重写（"共用机制，候选按品牌分组"）；
  - Mechanism Map 调整候选行措辞；
  - Verified Facts 第 2 条改写；新增 Superseded 段保留历史表述；
  - Open Questions 把"AU/VT 是否同 binary"重写、6 个域名改为"全部/一部分"追问；
  - Principles 加"换/加/下线域名必须 AU/VT 分别核对"；
  - Contradictions / Risks 记录 src-006 与 src-007 的冲突解决路径；
  - Related 同步 sources + reference memory。
- `~/.claude/.../memory/au-brand-domains.md`、`vt-brand-domains.md`：把"AU/VT 共用一份"的措辞改为"按品牌分组"。
- `90_indexes/vault-change-log.md`（本条目）。

### Not done

- 仍未将这 6 个域名直接断言为"硬编码候选的全部/一部分"——证据强度不够。

## 2026-05-26 — wallet-domain-routing 推进：硬编码 + 双环境共用

~~~yaml
operator: "Claude Code"
trigger: "用户：域名是客户端硬编码，AU 和 VT 使用同一套机制和候选"
mode:
  - session capture
  - theme maintenance
confirmed_memory_created: false
~~~

### Why

用户回答了 wallet-domain-routing 中两条核心 Open Question（候选来源 + 双环境是否共用），把"推断"升级为"用户口述已确认"。同时补一条机制约束（硬编码 → 域名变更必须随发版）方便未来项目设计引用。

### Added

- `10_sources/src-2026-05-26-006.md`

### Updated

- `40_themes/wallet-domain-routing.md`：related_sources 加 src-006；Current Understanding 增第 3 段（AU/VT 共用）；Mechanism Map 标注硬编码；新增 Verified Facts 段；Open Questions 移除两条已解答、增加 4 条新追问；Principles 加"硬编码=变更随发版"；Related 加 [[au-brand-domains]]。
- `~/.claude/.../memory/au-brand-domains.md`：用 wallet-domain-routing 已知信息收紧"可能用途"段。
- `90_indexes/vault-change-log.md`（本条目）。

### Not done

- 未直接断言三个 AU 品牌域名就是硬编码候选——证据强度不够，仅在 Open Questions 中并列追问。
- 未提名 Candidate Memory：仍是机制描述，不是规则。

## 2026-05-26 — 新建 theme：wallet-domain-routing

~~~yaml
operator: "Claude Code"
trigger: "用户口述钱包域名探活 + 接口下发 H5 域名的机制理解"
mode:
  - session capture
  - theme maintenance
confirmed_memory_created: false
~~~

### Why

用户描述的是机制层认知（探活/轮询/动态下发），不是稳定规则，不适合 Candidate Memory；属于长期主题，需要按 source-driven 的方式持续累积。先建 theme 骨架并把开放问题登记下来，避免后续被"补一句改一句"地稀释。

### Added

- `10_sources/src-2026-05-26-005.md`
- `40_themes/wallet-domain-routing.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未提名 Candidate Memory：当前只有 1 条 source，机制理解尚未稳定。
- 未关联具体 project：没有正在进行的"域名路由"专项工作。
- 未建立与 `vt-consul-prod` / `au-consul-prod` 之间的强关联，仅在 theme Open Questions 中标注待证。

### Follow-up

- 出现第二条独立证据时，更新 Mechanism Map 并把推断转为"已验证"。
- 若机制涉及具体项目（如闪兑或资金对接），把 theme 互链到对应 project。

## 2026-05-26 — Candidate cand-2026-05-26-001 补充 st 并发性

~~~yaml
operator: "Claude Code"
trigger: "用户：全局只有一个 st"
mode:
  - memory proposal
confirmed_memory_created: false
~~~

### Why

把"相关 st"语义锁死为"当前那一个 st-YYYYMMDD"，消除"多 st 并存如何选"的潜在歧义；Proposed Statement 改为更精确的措辞。

### Updated

- `10_sources/src-2026-05-26-004.md`：补用户原文 + processing log。
- `30_memories/candidates/cand-2026-05-26-001.md`：Terminology 强化 st（全局唯一）；Proposed Statement 改为引用具体分支名；Notes 移除已解答的两条精确化追问。
- `90_indexes/vault-change-log.md`（本条目）。

## 2026-05-26 — Candidate cand-2026-05-26-001 补充 st 分支定义

~~~yaml
operator: "Claude Code"
trigger: "用户：st 分支指的是冒烟测试分支，他是在发车前，把 au-uat 切出来的一个新分支，根据日期命名..."
mode:
  - memory proposal
confirmed_memory_created: false
~~~

### Why

用户给出 st 分支的来源（从 au-uat 切出）、命名规则（st-YYYYMMDD）和用途（UAT 回归 + 冒烟测试），把"反向合并到相关 st 分支"这条规则的对象具体化。

### Updated

- `10_sources/src-2026-05-26-004.md`：补 st 分支用户原文 + processing log。
- `30_memories/candidates/cand-2026-05-26-001.md`：Terminology 加 au-uat / st 定义；Notes "已澄清"扩展；新增 3 条精确化追问。
- `90_indexes/vault-change-log.md`（本条目）。

### Not done

- 仍未升 Confirmed：等用户显式确认。

## 2026-05-26 — Candidate cand-2026-05-26-001 补充适用范围与主车分支

~~~yaml
operator: "Claude Code"
trigger: "用户：这个规则是团队需要遵守的规则，主车对应的分支是 release"
mode:
  - memory proposal
confirmed_memory_created: false
~~~

### Why

用户进一步澄清适用范围（团队规约）与主车对应分支（`release`），消除"个人 vs 团队"歧义并把"主车"绑定到具体分支名，可显著降低未来 AI 在协助合并/发版时的误判风险。

### Updated

- `10_sources/src-2026-05-26-004.md`：补两条用户原文 + processing log。
- `30_memories/candidates/cand-2026-05-26-001.md`：Terminology 中 release 分支映射；新增 Applicability 段（团队规约）；Notes "已澄清"扩展。
- `90_indexes/vault-change-log.md`（本条目）。

### Not done

- 仍未升 Confirmed：等用户显式说"升 Confirmed"。剩余仅"st 分支命名规则"与"例外场景"两点待澄清，不阻塞升格。

## 2026-05-26 — Candidate cand-2026-05-26-001 补充术语澄清

~~~yaml
operator: "Claude Code"
trigger: "用户主动澄清：主车 = 周二/周四统一发版，发车 = 发版"
mode:
  - memory proposal
confirmed_memory_created: false
~~~

### Why

用户在同一会话中主动展开术语，构成第二次表达，promotion check 全部通过。置信度从 medium 调到 high；保持 Candidate，等用户显式确认升格。

### Updated

- `10_sources/src-2026-05-26-004.md`：补术语澄清原文 + processing log。
- `30_memories/candidates/cand-2026-05-26-001.md`：加 Terminology 段、置信度 → high、勾选第三项 promotion check、Notes 区分"已澄清/待澄清"。
- `90_indexes/vault-change-log.md`（本条目）。

## 2026-05-26 — 提名发车 GitFlow 反向合并规则（Candidate）

~~~yaml
operator: "Claude Code"
trigger: "用户：记录一下发车的 GitFlow 流程..."
mode:
  - session capture
  - memory proposal
confirmed_memory_created: false
~~~

### Why

用户口述发版分支反向合并规则，符合 long-term memory whitelist 的"verified workflows or methods"，但仅 1 次陈述、且术语颗粒度（如"相关 st 分支""主车"）未充分澄清，按协议先入 Candidate。

### Added

- `10_sources/src-2026-05-26-004.md`
- `30_memories/candidates/cand-2026-05-26-001.md`

### Updated

- `90_indexes/vault-change-log.md`（本条目）

### Not done

- 未直接升 Confirmed Memory：等用户显式确认（参见 candidate 文件 Notes 中的 4 个澄清点）。
- 未写 session summary：本次互动是单点登记，不是工作会话。

### Follow-up

- 用户确认或补充澄清后，升格到 `30_memories/confirmed/`，或合并到既有 memory。

## 2026-05-26 — 闪兑项目设定目标完成日期

~~~yaml
operator: "Claude Code"
trigger: "用户：预计下周三能把闪兑方案设计完毕"
mode:
  - project maintenance
confirmed_memory_created: false
~~~

### Why

为闪兑项目设定明确目标完成日期（2026-06-03），并补充时间风险。

### Updated

- `50_projects/flash-exchange-service-design.md`：新增 `target_completion: 2026-06-03`、Current State 增加预计完成日期、Risks 增加时间风险、Next Actions 增加交付节点。
- `90_indexes/vault-change-log.md`（本条目）。
