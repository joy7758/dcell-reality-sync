# Reuse, Overlap, and Ownership Review v0.1

## 结论

本项目可以作为独立的、文档与 Schema 范围的研究原型存在；不应成为新的 Cell Framework、
Runtime、平台、世界模型或执行系统。当前处置为：

```text
REUSE_REVIEW=PASS_WITH_STRICT_BOUNDARY
DUPLICATE_RUNTIME_JUSTIFIED=false
NEW_PLATFORM_JUSTIFIED=false
NEW_SCHEMA_RESEARCH_ARTIFACT_JUSTIFIED=true
PRIMARY_REPOSITORY=DCELL-REALITY-SYNC
CROSS_REPOSITORY_WRITES=false
```

## 复用与所有权矩阵

| 表面 | canonical owner / 参考来源 | 本项目可做 | 本项目不得做 |
|---|---|---|---|
| DCell Core 定义 | `dcell-framework` 作者与治理 | 引用边界 | 修改核心、分类真实 DCell |
| Cognitive Cell 研究 | `dcell-framework` 的 Future Research 工件 | 细化 reality-sync 研究问题 | 宣称扩展已获验证或成为 core |
| TITMAS-CELL-001 实验 | `dcell-lab` | 只读参考失败与观察纪律 | 新建 Cell Runtime、干预实验 |
| 项目群治理与架构准入 | DBA cockpit + Human Decision | 准备本地报备候选 | 宣称已提交或已准入 |
| Entity 身份与运行历史 | DBOS 或未来明确 owner | 声明未来接口边界 | 注册 Entity、创建运行历史 |
| Evaluation | SAEE 或独立 evaluator | 定义未来评估输入要求 | 签发评分、选择或演化决定 |
| Evidence | Agent Evidence、DBOS 或其他明确 owner | 保存材料引用 | 成为证据/真理/认证权威 |
| Agent / World Model Runtime | 现有模型或 Agent framework | 描述外部消费边界 | 重新实现 framework 或模型 |

## 差异化研究对象

相邻 DCell 工件研究“受治理持续软件实体”与“持续认知对象”的结构。本项目只聚焦一个更窄问题：
如何把现实来源、观察时间、冲突、不确定性、模型投影与候选偏差放入同一可审计记录，并明确
“评估不等于更新”。

这项差异只支持独立研究工件，不证明需要独立 Runtime 或平台。

## 数据与权力边界

- Reality source 事实由外部来源拥有；
- 本项目只拥有其本地研究文档、Schema 与合成样例；
- `cell_id` 不映射为 DBOS `entity_id`；
- sync assessment 不映射为 SAEE 结论；
- evidence reference 不映射为 Agent Evidence 或 DBOS canonical Evidence；
- update proposal 不映射为 Permission、Decision、Command 或 Execution。

## 处置

没有复制相邻仓库的代码、Schema、Git 历史、运行状态或评价结果。概念字段采用独立重述，
并通过 source manifest 保留来源关系。未来若需要实现，必须先重新执行 duplicate capability
review，指定 Owner、契约和 gate，再获得新的人工授权。

