---
id: proj-follow-trade-treasury-integration
type: project
status: active
title: "跟单-资金中台对接"
owner: "cavint"
stakeholders:
  - Wilson（跟单方）
  - 资金中台团队
  - meti 团队
created: 2026-05-26
last_updated: 2026-06-08
related_themes: []
related_sources:
  - 10_sources/src-2026-05-26-002.md
  - 10_sources/src-2026-06-08-002.md
related_sessions:
  - 20_sessions/session-2026-05-26-001.md
---

# Project: 跟单-资金中台对接

## Goal

打通"跟单系统 ↔ 资金中台 ↔ meti"三方对接链路，使资金中台能够对跟单账户进行动账操作。

## Current State

- 已与跟单方 Wilson 确认：**链路上不存在循环调用问题**（2026-05-26）。
- 待确认：**资金中台如何调用 meti 来对跟单账户动账**——等 Wilson / 对方团队 2026-05-27 给答复。
- **2026-05-28：Rocket 不同意接入 MTS，称后续会打掉 MTS**。但 MTS 已接入 meti，可直接调用 meti → MT5 实现跟单动账，不依赖 MTS 接口层。
- **MTS 底层是 MT5**；MTS 已接入 meti，意味着 meti 已具备直连 MT5 的能力，链路可行。

## Key Entities

- **跟单系统**：业务侧，Wilson 对接。
- **资金中台**：发起动账请求的一方。
- **meti**：与跟单系统并列的另一个独立系统，承担动账落账的角色（具体职责待对方明确）。

## Open Questions

- 资金中台调用 meti 的具体接口/协议/触发方式？
- meti 与跟单系统之间在动账场景下的边界与数据一致性如何保证？

## Decisions

- 2026-05-26：确认无循环调用问题（与 Wilson 一致）。
- 2026-05-28：Rocket 否决接入 MTS（理由：MTS 后续会被打掉）。

## Risks

- meti 调用方式未定，可能影响接口设计与排期。
- MTS 接口层后续会被打掉——但 meti 已具备直连 MT5 能力，风险在于 MTS 下线时是否有其他调用方仍依赖旧路径。

## Next Actions

- [x] ~~确定跟单的查询资产怎么查~~ — **已确认：等效接口为 `queryAccountByUserIds`**（2026-06-08）。
- [ ] 2026-05-27：等 Wilson / 对方答复"资金中台 → meti 动账"的具体方案。
- [ ] 答复到位后，更新本文件 Decisions 与 Current State，并视情况起草接口/时序草案。
- [ ] **2026-06-03：100U 紧急上账问题处理**。
