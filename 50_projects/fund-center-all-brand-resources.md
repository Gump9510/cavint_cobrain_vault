---
id: proj-fund-center-all-brand-resources
type: project
status: active
title: "fund-center 全品牌资源确认"
owner: "cavint"
created: 2026-05-28
last_updated: 2026-06-14
related_sources:
  - 10_sources/src-2026-05-28-003.md
  - 10_sources/src-2026-06-14-001.md
  - 10_sources/src-2026-06-14-003.md
related_sessions: []
related_themes:
  - 40_themes/au-vt-brand-architecture.md
---

# Project: fund-center 全品牌资源确认

## Goal

确定 fund-center 服务在全品牌（AU / VT 等）下所需的资源。

## Current State

- **2026-05-28：今天需要确定全品牌资源**。
- **2026-05-28：资源清单初步准备完毕**，等老板们确认后再跟运维推进。
- **2026-06-14：计划于周一（2026-06-15）继续推进 Fund Center 全品牌部署，并跟进转账相关详情**。
- **2026-06-14：OceanBase 运维部署已启动，作为 Fund Center 关联项目需同步跟进**。

## Open Questions

- 全品牌资源具体指什么（部署实例、数据库、配置、域名、consul namespace）？
- 涉及哪些品牌（AU + VT，还有其他）？
- 是否需要按品牌独立部署（参照 AU/VT 数据严格独立的约束）？
- 转账详情跟进具体涉及哪些业务、系统、接口和待确认人？

## Decisions

- 暂无。

## Next Actions

- [x] ~~（今天）确定 fund-center 全品牌资源~~ — 清单已出。
- [ ] 等老板们确认资源清单。
- [ ] **2026-06-03：统计资源使用情况**。
- [ ] **2026-06-03：推进 Fund-Center 全品牌资源部署**。
- [ ] 确认后跟运维推进落地。
- [ ] **2026-06-15：推进 Fund Center 全品牌部署**。
- [ ] **2026-06-15：跟进转账相关详情，并明确业务范围、接口/流程与待确认事项**。
- [ ] **2026-06-15 至 2026-06-21：同步跟进关联项目 OceanBase 的运维部署进展及影响**。

## Related

- [[au-vt-brand-architecture]] — AU/VT 部署与数据严格独立，fund-center 资源规划应遵循此约束。
- [[oceanbase-deployment]] — Fund Center 关联部署项目，需同步跟进部署状态和阻塞。
