---
id: proj-biz-domain-split-release
type: project
status: active
title: "业务领域拆分 - 提前上线"
owner: "Wayne"
created: 2026-05-28
last_updated: 2026-05-28
target_completion: 2026-06-02
related_sources:
  - 10_sources/src-2026-05-28-002.md
related_sessions: []
related_themes: []
---

# Project: 业务领域拆分 - 提前上线

## Goal

完成业务领域拆分的上线发布。

## Current State

- **负责人：Wayne**
- **预计下周一（2026-06-02）提前上线**
- **2026-06-02 ~ 2026-06-06：冻结一切常规车需求**

## Key Constraints

- 冻结期内不允许常规发车（常规车仅周二/周四），所有常规需求暂停上线。
- 专车（非周二/周四的单独发版）不受冻结影响。

## Open Questions

- 业务领域拆分的具体范围（哪些服务/模块）？
- 冻结期是否有例外通道（hotfix / 紧急修复）？
- 拆分上线后是否有灰度/回滚计划？
- **（今天确认）fund-backend 服务中，支付部门转账部分是否要跟着业务领域拆分一起上线？**

## Decisions

- 2026-05-28：fund-backend 支付部门转账部分**不跟**业务领域拆分一起上线。

## Risks

- 冻结期与闪兑方案 6/3 交付时间重叠，需确认闪兑是否有常规车发版需求。
- business 服务 6/6（周六）走专车，不受冻结影响。

## Next Actions

- [x] ~~（今天）确认 fund-backend 支付部门转账部分是否跟随本次上线~~ — **已确定：支付不跟上**。
- [ ] 2026-06-02：业务领域拆分提前上线。
- [ ] 2026-06-02 ~ 2026-06-06：冻结常规车需求，监控上线稳定性。
- [ ] 确认冻结期对 [[business-kms-bybit-connectivity]] 6/6 上线是否有影响。

## Related

- [[business-kms-bybit-connectivity]] — 同期 6/6 deadline，需确认是否受冻结影响。
