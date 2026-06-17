---
id: proj-flash-exchange-service-design
type: project
status: active
title: "闪兑服务 - 技术方案设计"
owner: "cavint"
stakeholders:
  - Rocket（服务归属决策方）
  - Selina（服务归属决策方）
  - cavint（技术方案介入）
created: 2026-05-26
last_updated: 2026-05-26
target_completion: 2026-06-03
related_themes: []
related_sources:
  - 10_sources/src-2026-05-26-003.md
related_sessions:
  - 20_sessions/session-2026-05-26-003.md
---

# Project: 闪兑服务 - 技术方案设计

## Goal

参与闪兑服务的技术方案设计，输出可落地的技术方案。

## Current State

- **服务归属未定**：Rocket 和 Selina 仍在决定闪兑服务放在哪里。
- **cavint 已于 2026-05-27 介入技术方案设计阶段**。
- **预计 2026-06-03（下周三）完成方案设计**。
- **预计 2026-05-28 给出闪兑相关的细节排期** — ✅ 已完成。
- **2026-05-28：已通过 AI 生成初步技术方案**，目前还在探索 AI 辅助方案设计的用法。
- **2026-05-28：闪兑对账不齐问题已解决** — 原因：精度问题。

## Open Questions

- 闪兑服务最终的归属（哪个团队 / 哪个域 / 哪个模块）？这会直接影响技术方案的落点。
- 闪兑服务的输入/输出边界、上下游依赖、是否复用既有动账链路（参见 [[follow-trade-treasury-integration]]）？
- 性能 / 资金安全 / 一致性的硬性约束？

## Decisions

- 暂无。

## Risks

- 服务归属未定时进入技术方案设计，可能出现"先设计后归属"导致的返工。需在 2026-05-27 介入时主动核对归属是否影响关键设计选择。
- 预计 2026-06-03 完成方案——只有 6 个工作日（含明日）。若归属决定迟于 2026-05-29，完成日期可能滑动，需提前预警。

## Next Actions

- [ ] 2026-05-27：介入技术方案设计——开场先确认服务归属现状与是否影响今天要谈的设计点。
- [ ] 收集上下游、SLA、资金安全要求等关键约束，回填到本文件 Open Questions 与 Decisions。
- [ ] 进入设计后，把方案草案放到 `70_outputs/`，本文件保持指向最新草案。
- [ ] 2026-06-03：交付方案设计；若有滑动，更新 target_completion 并在 vault-change-log 中记录原因。

## Related

- [[follow-trade-treasury-integration]] — 资金动账相关项目，可能与闪兑链路有重叠或复用关系。
