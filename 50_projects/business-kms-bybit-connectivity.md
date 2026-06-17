---
id: proj-business-kms-bybit-connectivity
type: project
status: active
title: "Business 服务上线 - KMS & Bybit 连通性验证"
owner: "cavint"
created: 2026-05-28
last_updated: 2026-06-15
target_completion: ""
related_sources:
  - 10_sources/src-2026-05-28-001.md
  - 10_sources/src-2026-06-14-002.md
  - 10_sources/src-2026-06-15-002.md
related_sessions: []
related_themes: []
---

# Project: Business 服务上线 - KMS & Bybit 连通性验证

## Goal

完成 Bybit Custody 联调，验证 business 服务、KMS 与 Bybit 的连通性，并据此确定上线计划。

## Current State

- **2026-05-28：立项**，目标 6/6 前上线。
- **2026-05-28：需提前准备 Bybit Custody 接入的运维资源**——域名、IP 白名单、KMS 配置。这是当前插入的紧急前置任务。
- ~~**2026-06-08：Custody 进度暂时 pending**，等 Tony（老板）确认后再推进。~~
- **2026-06-14：等待确认状态已结束，Bybit Custody 已进入联调阶段；计划于下周（2026-06-15 至 2026-06-21）启动联调**。
- **2026-06-15：需要在今天下班前整理或修改 Bybit KYT 相关资料，并提供给 Brandon**。

## Milestones

- [ ] ~~2026-06-06：business 服务上线，KMS + Bybit 连通性测通~~ — 原目标日期已过，待按联调计划重排。
- [ ] 2026-06-15 至 2026-06-21：启动 Bybit Custody 联调

## Open Questions

- business 服务的具体范围 / 模块？
- KMS 用于什么场景（签名、密钥托管）？
- Bybit 连通性指的是哪些接口（交易、资金、行情）？
- 部署环境（AU / VT / 独立）？
- Brandon 需要的 Bybit KYT 资料具体包含哪些内容，需修改哪些部分？

## Decisions

- 暂无。

## Risks

- 联调依赖 Bybit API 权限、KMS 配置、域名和 IP 白名单等外部资源；任一项未就绪都可能阻塞进度。
- 原定 2026-06-06 上线目标已过期，新的完成日期尚未确定。

## Next Actions

- [x] ~~（今天）确定 Bybit Custody 的对接形式~~ — 已解决。
- [x] ~~等待 Tony 确认后恢复 Custody 推进~~ — 2026-06-14 已解除 pending，进入联调阶段。
- [ ] 配合联调推进以下事项：
  - [ ] 了解 Fireblocks 的作用和 API
  - [ ] 与 Bybit 了解整个 Custody 流程
  - [ ] 准备 Custody 物料 + 催产品出对账文档
  - [ ] 准备 Bybit Custody 运维资源（域名、IP 白名单、KMS 配置）
- [ ] **2026-06-15 至 2026-06-21：启动 Bybit Custody 联调**。
- [ ] **【今天下班前】整理或修改 Bybit KYT 相关资料，并提供给 Brandon**。
- [ ] 明确 business 服务边界与部署目标环境。
- [ ] 确认 Bybit API 凭证等前置条件。
- [ ] 根据联调结果重新确定上线与连通性验证完成日期。

## Related

- 暂无已知关联项目。
