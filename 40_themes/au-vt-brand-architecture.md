---
id: theme-au-vt-brand-architecture
type: theme
status: active
title: "AU / VT 品牌架构：分离与共用边界"
created: 2026-05-26
last_updated: 2026-05-26
related_sources:
  - 10_sources/src-2026-05-26-008.md
related_sessions: []
related_projects:
  - 50_projects/follow-trade-treasury-integration.md
  - 50_projects/flash-exchange-service-design.md
related_memories: []
---

# Theme: AU / VT 品牌架构：分离与共用边界

## Scope

记录 AU 与 VT 两个品牌在代码、部署、数据层面的"哪里共用、哪里分离"。这是众多其他 theme/project 的前置认知，应作为公共底座引用，避免在每个项目里重复推导。

## Verified Facts（src-2026-05-26-008，用户口述）

| 层面 | AU vs VT |
| --- | --- |
| 前端代码 | **不同套**（独立代码库 / 独立 binary） |
| 后端代码 | **同一套**（共享同一份代码） |
| 机房 / 服务部署 | **不同**（不同机房 + 不同服务实例） |
| 数据 | **严格独立** |

## Implications（直接推论，标注层级）

- **后端代码同一套 + 机房与服务不同** ⇒ 同一份代码以多副本独立部署，按品牌区分实例。任何服务级配置必须区分品牌（DB 连接、密钥、域名候选、缓存命名空间等）。
- **前端不同套** ⇒ 域名硬编码候选自然按品牌分组，与 [[wallet-domain-routing]] 中的"候选按品牌分组"一致。
- **数据严格独立** ⇒
  - 跨品牌的数据查询、聚合、对账、引用必须显式跨域并经合规/审批；
  - 缓存 key、消息队列 topic、文件路径都应内含品牌标识；
  - 不允许"看着像同一张表就直接 join"。

## Open Questions

- "同一套后端代码"在仓库层面是单 repo + 多部署，还是多 repo 同步演进？
- 后端配置是按 namespace（品牌即 namespace）切分，还是单实例多租户？由 Verified Facts 中"不同服务实例"看更像前者，但需证实。
- AU/VT 是否存在"逻辑共用 + 物理隔离"的中台或平台层（例如风控、用户、KYC）？若有，是另一种分离形态，需单独记录。
- [[follow-trade-treasury-integration]] 与 [[flash-exchange-service-design]] 的方案设计在跨品牌动账/资金链路上是否需要双品牌各做一遍？默认按"两份独立部署"理解。

## Contradictions / Risks

- 暂无观察到的矛盾。
- 风险：因为后端代码同一套，**一次发版会同时影响 AU 和 VT 的运行实例**——具体取决于发版策略（逐机房 / 双品牌串行 / 并行），需后续证实。该风险与 [[发车 GitFlow 反向合并规则]] 候选记忆相关：发车流程是否需要双品牌分别确认？

## Related

- Sources: src-2026-05-26-008
- Themes: [[wallet-domain-routing]]（候选域名按品牌分组的根因来自此 theme 的"前端不同套"）
- Projects: [[follow-trade-treasury-integration]] / [[flash-exchange-service-design]]
- Candidate memory: cand-2026-05-26-002（AU/VT 数据严格独立）
- Reference memory: [[au-consul-prod]] / [[vt-consul-prod]] / [[au-brand-domains]] / [[vt-brand-domains]]
