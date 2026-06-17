---
id: theme-wallet-domain-routing
type: theme
status: active
title: "钱包域名路由与下发机制"
created: 2026-05-26
last_updated: 2026-05-26
related_sources:
  - 10_sources/src-2026-05-26-005.md
  - 10_sources/src-2026-05-26-006.md
  - 10_sources/src-2026-05-26-007.md
  - 10_sources/src-2026-05-26-008.md
related_sessions: []
related_projects: []
related_memories: []
---

# Theme: 钱包域名路由与下发机制

## Scope

钱包业务中"客户端 → 后端"的域名选择、探活、动态下发链路。聚焦机制层面，不替代具体项目实现。

## Current Understanding（基于 src-2026-05-26-005、src-2026-05-26-006，用户口述）

### 1. APP → 后端服务：客户端侧域名优选

- APP 前置配有**多个候选域名**，**候选列表客户端硬编码**（src-006）。
- 客户端在请求前**探活 + 轮询**，从候选中选出"最优域名"。
- 选定后，请求**直达钱包后端服务**（无中间网关层的额外描述）。

### 2. H5 域名下发：通过钱包接口动态获取

- APP 用上面优选出的域名，调用钱包的**某个接口**。
- 该接口**返回一个域名**，供后续 **H5** 访问使用。

### 3. AU / VT：共用机制，但候选不共享（src-006 + src-007 修正）

- AU 与 VT **共用同一套域名优选机制**（探活/轮询/优选/接口下发 H5 域名）。
- 但 AU 与 VT 是**不同品牌，各自使用不同组域名**——硬编码候选**按品牌分组**，互不重叠。
  - AU 候选见 [[au-brand-domains]]
  - VT 候选见 [[vt-brand-domains]]
- 含义：客户端在不同品牌的 binary（或不同打包/配置）中，硬编码各自的候选集合；逻辑层共享。

## Mechanism Map

```
APP 启动（按品牌：AU / VT，逻辑共享）
  ↓
候选域名列表（客户端硬编码，按品牌各自分组）
  ↓
探活 + 轮询 → 选最优域名 (D_app)
  ↓
直达钱包后端：常规请求走 D_app
  ↓
调用钱包接口（走 D_app）
  ↓
接口返回 D_h5
  ↓
H5 后续请求使用 D_h5
```

## Verified Facts（已由用户口述确认）

- 候选域名列表来源：**客户端硬编码**（src-2026-05-26-006）。
- AU 与 VT **共用同一套机制**，但**各自使用不同组域名**（src-2026-05-26-006 + src-2026-05-26-007 修正）。

## Superseded（仅作历史保留）

- ~~"AU 和 VT 共用同一套候选"~~ —— src-2026-05-26-006 表述较宽，被 src-2026-05-26-007 修正为"共用机制，候选按品牌分组"。

## Open Questions

- "探活"的具体协议（HTTP HEAD？专用 ping 接口？）与判定指标（延迟？成功率？地理就近？）。
- "最优"如何打分与选择？是否有降级 / 回退策略？
- 接口下发的 H5 域名是**单次会话有效**还是**持久缓存**？过期/失效如何处理？
- 客户端硬编码 → 域名变更必须随 client 发版？是否存在远程下发的"覆盖"通道？
- ~~AU 与 VT 是同一份 client binary 内置两组按品牌切换？还是两份独立 binary 各自硬编码自己那组？~~ → 已由 src-008 解答："不同套前端代码"⇒ 两份独立。
- [[au-brand-domains]] / [[vt-brand-domains]] 中的 6 个域名是否就是这份硬编码候选的全部 / 一部分？
- 是否与 [[follow-trade-treasury-integration]]、[[flash-exchange-service-design]] 中的服务调用链路有交集？

## Principles / Heuristics

- 此 theme 当前由 3 条 source 支撑，但均为同一信息源（cavint 口述）。结论性表述仍应保守，引用前注明"用户口述"。
- 候选域名既然是客户端硬编码，**任何域名变更都涉及发版**——这条机制约束应进入相关项目的设计 checklist。
- 涉及"换/加/下线域名"的方案设计时，必须按 **AU / VT 分别核对候选**，不可只改一边。

## Contradictions / Risks

- src-2026-05-26-006 中"AU/VT 共用同一套候选"的较宽表述与 src-2026-05-26-007 + 实际两组域名互不重叠的事实冲突。已在 Superseded 中保留历史记录，并以 src-007 为准。

## Related

- Sources: src-2026-05-26-005, src-2026-05-26-006, src-2026-05-26-007, src-2026-05-26-008
- Themes: [[au-vt-brand-architecture]]（"前端不同套"是本 theme 中"候选按品牌分组"的根因）
- Memories: cand-2026-05-26-002（AU/VT 数据严格独立）
- Reference memory: [[vt-consul-prod]] / [[au-consul-prod]] / [[au-brand-domains]] / [[vt-brand-domains]]
