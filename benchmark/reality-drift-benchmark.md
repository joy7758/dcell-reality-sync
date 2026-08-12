---
benchmark_id: REALITY-DRIFT-BENCHMARK-v0.1
title: Reality Drift Benchmark v0.1
title_zh: 现实漂移基准 v0.1
artifact_kind: RESEARCH_BENCHMARK_DESIGN
status: RESEARCH_DRAFT_NOT_IMPLEMENTED
created_at: 2026-08-11T17:26:46Z
implementation_status: NOT_IMPLEMENTED
execution_status: NOT_EXECUTED
result_status: NOT_ASSESSED
scientific_validation: NOT_ESTABLISHED
---

# Reality Drift Benchmark v0.1

## 1. 研究定位

Reality Drift Benchmark（现实漂移基准）用于研究：当可观察现实在时间序列中发生变化时，
不同知识组织条件是否能帮助同一个基础语言模型识别陈旧状态、重建当前状态、保留冲突与未知，
并给出有来源的更新建议。

本文件只是 benchmark design（基准设计），不是实现、数据集、runner、模型调用、实验记录、
排行榜或科学结果。

```text
BENCHMARK_ID=REALITY-DRIFT-BENCHMARK-v0.1
DESIGN_STATUS=RESEARCH_DRAFT
FROZEN_LLM_CONDITION_DEFINED=true
RAG_CONDITION_DEFINED=true
DCELL_RESEARCH_CONDITION_DEFINED=true
FIXTURES_CREATED=false
RUNNER_IMPLEMENTED=false
MODEL_INVOKED=false
BENCHMARK_EXECUTED=false
WINNER_DECLARED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
```

## 2. Reality Drift 定义

本设计中的 Reality Drift 是以下研究现象：

> 在时间 `t0` 建立的模型状态投影，与时间 `t1...tn` 的有来源观察之间出现可描述差异。

该差异可能来自现实变化、来源更正、观察缺失、事件乱序、来源冲突或模型状态陈旧。
它不自动表示现实来源为真、模型错误、必须更新，或 DCell 条件优于其他条件。

研究单位是一个 `scenario packet`（场景包）：

```text
initial_snapshot
  + ordered_or_declared_unordered_updates
  + source_and_timestamp_metadata
  + query_set
  + hidden_reference_ledger
  + expected_conflict_or_unknown_state
```

`hidden_reference_ledger` 只用于离线评分；不得进入任何对照组的模型输入。

## 3. 研究问题

### Primary research question

**RQ1 — Drift detection:** 在相同基础模型、问题、原始来源和时间序列下，Frozen LLM、RAG
和 DCell research condition 对现实漂移的检测能力是否存在可复现差异？

### Secondary research questions

- **RQ2 — Current-state reconstruction:** 三组能否在多个更新后重建声明范围内的当前状态？
- **RQ3 — Provenance:** 三组能否把回答中的关键主张绑定到正确来源和观察时间？
- **RQ4 — Conflict and unknown preservation:** 三组能否保留冲突、缺失、不可达与未知，而不静默选边？
- **RQ5 — Correction recovery:** 来源撤回或更正后，三组能否停止复用旧结论并恢复到新状态？
- **RQ6 — Temporal consistency:** 三组能否区分事件时间、观察时间和摄取时间，处理乱序变化？
- **RQ7 — Cost and complexity:** 任何准确性收益是否足以抵偿上下文、存储、检索和治理成本？

这些问题均保持 `NOT_ASSESSED`。本设计不预注册 DCell 必然优胜的方向性结论。

## 4. 三组对照

### 4.1 Group A — Frozen LLM

```text
CONDITION_ID=FROZEN_LLM
BASE_MODEL=SAME_AS_OTHER_GROUPS
REALITY_UPDATE_ACCESS=NONE_AFTER_T0
RETRIEVAL=false
PERSISTENT_MUTABLE_STATE=false
```

模型只获得 `t0` 的初始快照和统一任务说明。`t1...tn` 的现实更新不进入上下文。每次查询使用
同一冻结 prompt、模型 revision、解码参数和初始材料；不允许 Web、工具、外部记忆或跨轮写入。

该组测量“没有现实更新通道时的自然陈旧基线”，不是对基础模型总体能力的评价。

### 4.2 Group B — RAG

```text
CONDITION_ID=RAG
BASE_MODEL=SAME_AS_OTHER_GROUPS
REALITY_UPDATE_ACCESS=VERSIONED_DOCUMENT_RETRIEVAL
PERSISTENT_OBJECT_STATE=false
CELL_RECORD=false
```

RAG 条件使用与 DCell 条件完全相同的原始来源材料和可见时间点。每个时间步只检索当时允许可见的
版本化文档片段。它可以返回来源标识和时间，但不额外维护持续 Cell identity、显式状态投影、
变更历史、冲突对象或 update proposal。

检索器、分块、排序、`top-k`、索引版本和重建策略必须在未来执行前冻结。检索失败必须保留，
不得人工补选有利片段。

### 4.3 Group C — DCell research condition

```text
CONDITION_ID=DCELL_RESEARCH
BASE_MODEL=SAME_AS_OTHER_GROUPS
REALITY_UPDATE_ACCESS=VERSIONED_CELL_RECORD
CELL_SCHEMA=../schema/cell.schema.json
REAL_DCELL_CLASSIFICATION=false
```

DCell research condition 使用与 RAG 组相同的原始来源和可见时间点，但将材料组织为版本化研究记录：
identity、observations、claims、evidence references、state projection、history、conflicts、
uncertainties 和 synchronization assessment。

该条件只是对 `Cell Schema v0.1` 表达方式的研究性消融条件，不是已实现 DCell、DCell Core
修改、DBOS Entity、Runtime 或现实同步服务。它不能获得 RAG 组不可获得的额外事实。

### 4.4 公平性冻结矩阵

| 变量 | Frozen LLM | RAG | DCell research |
|---|---|---|---|
| 基础模型及 revision | 相同 | 相同 | 相同 |
| system/task prompt | 相同核心文本 | 相同核心文本 | 相同核心文本 |
| 解码参数与输出格式 | 相同 | 相同 | 相同 |
| `t0` 初始事实 | 相同 | 相同 | 相同 |
| `t1...tn` 原始来源 | 不可见 | 相同可见集合 | 相同可见集合 |
| 输入 token 上限 | 相同 | 相同 | 相同 |
| 外部 Web/工具 | 禁止 | 禁止 | 禁止 |
| 跨场景记忆 | 禁止 | 禁止 | 禁止 |
| 更新表示方式 | 无 | 文档检索 | Cell 记录 |

核心比较不是“有更新组对无更新组谁更强”，而是分两层报告：

1. Frozen LLM 提供不可更新的陈旧基线；
2. RAG 与 DCell 在相同更新材料下比较表示方式及其成本。

## 5. Frozen execution context

未来任何执行必须冻结并记录：

- 模型 provider、resolved model ID、weights/snapshot 或可验证 revision；
- tokenizer、system prompt、task prompt、解码参数、随机种子和最大 token；
- RAG embedding model、chunking、index revision、`top-k` 和 tie-breaking；
- DCell Schema digest、record builder version 和输入序列；
- 场景包、来源材料、hidden ledger 和评分规范的 digest；
- 执行时间、网络状态、工具状态、错误、重试与缺失输出。

如果 hosted model 无法证明 revision 稳定，应将条件标记为 `EXECUTION_CONTEXT_DRIFT`，不得把跨时段
差异归因于知识组织方式。`temperature=0` 也不等于确定性。

## 6. 测试场景

所有 v0.1 场景应为低风险合成对象，不使用真实个人数据、实时控制系统或高影响决策。

| scenario_id | 场景 | 时间变化 | 预期研究压力 |
|---|---|---|---|
| `RD-01` | 单一属性变化 | 对象状态从 A 变为 B | 基本漂移检测与当前状态重建 |
| `RD-02` | 多次连续变化 | A → B → C | 防止停留在中间状态，检查历史顺序 |
| `RD-03` | 来源更正／撤回 | `t1` 主张在 `t2` 被撤回 | 旧结论失效与 correction recovery |
| `RD-04` | 同时来源冲突 | 两个同等级来源给出不同状态 | 冲突保留、拒绝静默选边 |
| `RD-05` | 来源不可达 | 最新来源在查询时不可访问 | 陈旧标记、未知与失败关闭 |
| `RD-06` | 乱序事件 | 摄取顺序与事件时间不同 | event/observation/ingestion time 区分 |
| `RD-07` | 部分字段更新 | 只更新对象的一部分属性 | 覆盖率与未更新字段保护 |
| `RD-08` | 无漂移负控 | 新材料重复确认旧状态 | 假阳性漂移和无必要更新建议 |
| `RD-09` | 无关干扰更新 | 同域但非目标对象发生变化 | 身份边界和错误归并 |
| `RD-10` | 多轮回归查询 | 在多个时间点重复同一问题 | 时间一致性与旧答案复用风险 |

每类场景至少应在未来生成多个语义等价但表面不同的实例。实例数量、领域分层和功效分析尚未定义，
因此 v0.1 不能声称统计充分性。

## 7. 查询任务

每个场景应包含相同的结构化查询：

1. `CURRENT_STATE`：声明范围内当前状态是什么？
2. `DRIFT_STATUS`：相对 `t0` 是否出现漂移？
3. `CHANGE_HISTORY`：发生了哪些变化，顺序是什么？
4. `SOURCE_BASIS`：哪些来源支持当前回答？
5. `CONFLICT_STATUS`：是否存在冲突、缺失或未知？
6. `UPDATE_RECOMMENDATION`：是否建议更新模型投影，理由和停止条件是什么？

统一输出必须允许 `UNKNOWN`、`CONFLICTED`、`INSUFFICIENT_EVIDENCE` 和 `NO_UPDATE_NEEDED`。
建议字段不得被解释为授权或执行。

## 8. 评价指标

### 8.1 Primary metrics

| metric_id | 指标 | 定义 |
|---|---|---|
| `M-01` | Drift Detection Macro-F1 | 对 `DRIFT` / `NO_DRIFT` / `UNKNOWN_OR_CONFLICTED` 三类逐类计算 F1 后宏平均 |
| `M-02` | Current State Exactness | 当前状态字段与 hidden ledger 在声明范围内完全一致的比例 |
| `M-03` | Unsupported Claim Rate | 无允许来源支持或超出来源含义的实质主张数 / 实质主张总数；越低越好 |
| `M-04` | Provenance Recall | 应引用的关键来源中被正确引用的比例 |
| `M-05` | Conflict Preservation Rate | 要求保留冲突的样例中明确输出冲突且未静默裁决的比例 |

### 8.2 Secondary metrics

| metric_id | 指标 | 定义 |
|---|---|---|
| `M-06` | False Update Proposal Rate | 无漂移负控中错误建议更新的比例 |
| `M-07` | Correction Recovery Rate | 撤回／更正后停止复用旧结论并输出新状态或未知的比例 |
| `M-08` | Temporal Order Accuracy | 正确重建事件顺序的场景比例 |
| `M-09` | Unknown/Abstention Appropriateness | 证据不足时正确保留未知，证据充分时不过度拒答的平衡表现 |
| `M-10` | Silent Overwrite Rate | 输出新状态但未保留被替代状态、依据或变化记录的比例；越低越好 |
| `M-11` | Identity Boundary Error Rate | 把其他对象更新错误归并到目标对象的比例；越低越好 |
| `M-12` | Update Lag | 从允许看到有效更新到首次正确当前状态输出的时间步数 |

### 8.3 Resource and complexity metrics

- 输入／输出 token；
- 检索调用次数与返回片段数；
- Cell record 或索引存储字节数；
- 每次场景的预处理步骤和失败数；
- 人工标注、冲突裁决和维护时间；
- 端到端延迟（若未来实现）。

资源指标必须与准确性指标分开报告，避免通过无限上下文或人工处理获得不可比较优势。

## 9. 评分与统计计划边界

- v0.1 不定义单一综合分数，也不创建 leaderboard；
- 三组结果按场景、时间步和 metric 分开展示，保留均值、分布、置信区间与失败样例；
- 同一 scenario instance 应采用配对比较；
- 多重比较、样本量、随机化、功效分析和统计检验必须在执行前另行预注册；
- 缺失输出、超时、检索失败和格式错误不得从分母中删除；
- 不因初步结果不利而改变 primary metrics、场景或 hidden ledger。

在统计计划未冻结前，任何结果只能是 exploratory observation（探索性观察）。

## 10. 数据泄漏与审计控制

- hidden ledger、评分标签和 expected answer 不得进入 prompt、索引或 Cell record；
- RAG 与 DCell 条件只能使用相同时间点允许可见的原始材料；
- DCell record builder 不得增加来源中不存在的事实；
- 场景作者、执行者和评分者角色应尽可能分离；
- 所有输入、输出、错误、重试和 exclusions 必须保留 digest 与原因；
- prompt、模型、索引、Schema 或评分规则变化会触发 `REASSESSMENT_REQUIRED`。

## 11. 成功、失败与停止条件

本设计不预设哪个组成功。未来只有在匹配输入、执行上下文和独立评分成立时，才可形成有界结论。

削弱或拒绝 DCell research hypothesis 的条件包括：

1. RAG 在 primary metrics 上达到相同或更好结果，且成本更低；
2. DCell 条件的收益来自额外事实、更多 token 或人工修正，而不是表示结构；
3. DCell 条件仍无法可靠保留来源、冲突、未知或变化历史；
4. 维护成本显著高于可测量收益；
5. 结果对 prompt、场景表述或模型 revision 不稳定。

以下条件触发执行停止或结果失效：

- 三组基础模型、输入材料或 token 上限不可比；
- model revision、数据 digest、评分规范或 source visibility 无法冻结；
- hidden ledger 泄漏；
- 为改善结果删除失败、静默重试或修改标签；
- 执行需要现实写入、自动模型更新、真实个人数据或高影响系统控制；
- 需要本仓库建立 Runtime、平台、数据库、服务或外部 Authority。

## 12. 当前状态与非声明

```text
RESEARCH_QUESTIONS_DEFINED=true
CONTROL_GROUPS_DEFINED=true
TEST_SCENARIOS_DEFINED=true
METRICS_DEFINED=true
DATASET_CREATED=false
FIXTURES_CREATED=false
SCORING_IMPLEMENTED=false
RUNNER_IMPLEMENTED=false
MODEL_CALLS_EXECUTED=0
BENCHMARK_EXECUTED=false
RESULTS_AVAILABLE=false
COMPARISON_INTERPRETATION=NOT_ASSESSED
DCELL_SUPERIORITY_CLAIMED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
RUNTIME_EFFECT=NONE
AUTHORIZATION_EFFECT=NONE
```

下一 gate 只能是对设计进行独立评审并冻结场景包、数据治理、统计计划和执行上下文；本文件不授权
实现、模型调用、Benchmark 执行、发布或对外结论。

