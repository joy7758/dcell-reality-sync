# Research Scope v0.1

## 研究对象

本项目研究一个候选 Reality Synchronization Layer（现实同步层）：它位于现实来源与
Agentic World Model（智能体世界模型）之间，用带来源、时间、状态、不确定性和冲突的
Cell 记录描述“当前模型认知与可观察现实之间可能存在什么差异”。

研究构想：

> World Model 可以作为可互操作 Cognitive Cell 的动态生态系统来研究；每个 Cell 维护
> 对一个有界现实对象的、证据支持且可演化的表征。

该表述是候选研究框架，不是 World Model 的正式定义、DCell Core 修改或科学结论。

## In scope

- 现实对象的研究身份与边界；
- 带时间、来源和获取方式的观察引用；
- 主张与证据材料的显式绑定；
- 当前状态、历史变化、冲突和不确定性；
- 陈旧度与偏差的候选评估表达；
- 只读、可审计、可失败关闭的更新建议；
- 用 JSON Schema 表达候选 Cell 记录结构；
- 设计未来可证伪的评估协议。

## Out of scope

- 传感器、爬虫、消息总线或自动采集；
- 世界模型、基础模型、Agent 或 Agent framework；
- 自动事实判定、Truth Store（真理存储）或认证；
- 写回现实系统或自动更新模型；
- Runtime、API、数据库、Registry、平台和控制平面；
- DCell Core、DBOS、SAEE、Agent Evidence 或 DBA 的实现替代；
- 生产、商业服务、标准或外部发布声明。

## 停止条件

满足任一条件时停止扩展，只记录问题：

1. 需求可以由普通版本化记录、RAG、知识图谱或现有 DCell 工件以更低复杂度满足；
2. 不能明确 Reality source、时间边界、证据引用或不确定性；
3. 设计要求本仓库成为 Truth、Authorization、Runtime 或外部写入权威；
4. 需要新增平台、服务、数据库或自动执行逻辑才能继续；
5. 研究指标、匹配基线或反例尚未定义，却准备提出效果声明。

