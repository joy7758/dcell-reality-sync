---
specification_id: REALITY-DRIFT-DATASET-SPEC-v0.1
title: Reality Drift Dataset Specification v0.1
title_zh: 现实漂移数据集规范 v0.1
artifact_kind: RESEARCH_DATASET_SPECIFICATION
status: RESEARCH_DRAFT_NOT_IMPLEMENTED
created_at: 2026-08-11T17:33:01Z
dataset_implemented: false
dataset_generated: false
dataset_executed: false
benchmark_executed: false
scientific_validation: NOT_ESTABLISHED
---

# Reality Drift Dataset Specification v0.1

## 1. Purpose

本规范定义 Reality Drift Benchmark v0.1 的标准化研究数据契约，用于研究：当现实对象随时间
发生变化时，不同知识组织方式如何帮助 AI Agent（人工智能智能体）保持其状态表示与可观察现实
的一致性，并识别陈旧、冲突、缺失和更正。

“标准化”在本文件中只表示项目内部的统一字段、时间语义、可见性规则和评分边界，不表示正式标准、
已发布数据集、行业采纳或科学有效性。本规范不预设 Frozen LLM、RAG 或 DCell research condition
中任何一组表现更好。

```text
SPECIFICATION_ID=REALITY-DRIFT-DATASET-SPEC-v0.1
SPECIFICATION_ROLE=RESEARCH_DESIGN_ONLY
DATASET_IMPLEMENTED=false
DATASET_GENERATED=false
BENCHMARK_EXECUTED=false
```

## 2. Dataset Scope

### In scope

- 研究对象是 Reality Drift：现实对象的可观察状态与既有模型状态投影随时间出现差异；
- 描述有边界的 entity identity、初始状态、现实更新、事件顺序和状态迁移；
- 保存来源、时间戳、证据类型、置信表达、provenance（来源沿袭）、冲突和不确定性；
- 为 Frozen LLM、RAG 和 DCell research condition 提供可比较的场景输入边界；
- 为离线状态重建、漂移检测、溯源和冲突保留评分提供隐藏参考记录。

### Out of scope

- 不是真实世界自动控制系统、实时监控服务或 Reality Synchronization Runtime；
- 不包含个人敏感数据、真实凭据、私密客户数据或可识别个人的信息；
- 不用于医疗、法律、金融、安全、就业、执法或其他高风险决策；
- 不用于自动修改现实对象、世界模型、Agent memory、数据库或外部系统；
- 不创建 Truth、Evidence、Authorization、Certification 或状态裁决权威；
- 不修改 DCell Core，也不创建真实 DCell 或 DBOS Entity。

v0.1 只定义未来合成数据的结构和治理边界，不包含任何 scenario instance（场景实例）。

## 3. Scenario Packet Specification

### 3.1 规范结构

一个 `ScenarioPacket` 必须由以下顶层字段构成：

```text
ScenarioPacket =
  scenario_id
  + entity_identity
  + initial_snapshot
  + updates
  + event_sequence
  + source_metadata
  + timestamp_metadata
  + query_set
  + hidden_reference_ledger
```

本节是概念数据契约，不是 JSON Schema、数据库 Schema、API payload 或已生成记录。

| field | 研究语义 | 最小约束 |
|---|---|---|
| `scenario_id` | 场景包的研究本地稳定标识 | 在一个 dataset version 内唯一；不包含答案标签 |
| `entity_identity` | 被观察对象的身份与边界 | 明确对象类型、作用域和不可混同的邻接对象 |
| `initial_snapshot` | 时间 `t0` 的基线状态投影 | 字段有界、版本固定、来源可追溯 |
| `updates` | `t1...tn` 可见的变化材料 | 每项更新绑定事件、来源、时间和证据引用 |
| `event_sequence` | 声明的事件顺序或乱序关系 | 区分事件顺序、观察顺序和摄取顺序 |
| `source_metadata` | 所有来源的类型、标识与可用性 | 来源身份稳定；不可达、冲突和撤回必须保留 |
| `timestamp_metadata` | 时间字段的语义与精度 | 区分 event、observation、ingestion 和 publication time |
| `query_set` | 对三组条件提出的统一任务 | 问题核心语义一致；不得包含 hidden labels |
| `hidden_reference_ledger` | 仅供离线评分的参考状态与标签 | 与三组实验输入物理和逻辑隔离 |

### 3.2 `entity_identity`

未来记录至少需要描述：

- 稳定的研究本地实体引用；
- entity type（实体类型）；
- 声明范围内的状态字段；
- identity boundary（身份边界）；
- 明确排除的相似或相邻对象。

实体引用不是外部注册标识、DBOS `entity_id` 或真实身份权威。

### 3.3 `initial_snapshot`

`initial_snapshot` 是时间 `t0` 的有界状态投影，必须包含字段值、来源引用、观察时间和未知项。
它是实验基线，不等于现实真相。后续更新不得静默覆盖该快照。

### 3.4 `updates` 与 `event_sequence`

`updates` 保存候选变化材料；`event_sequence` 保存它们在事件时间、观察时间和摄取时间上的关系。
同一事件可以延迟到达或乱序到达，且二者不得被压缩成单一“最新时间”。

### 3.5 `query_set`

`query_set` 应与 Reality Drift Benchmark v0.1 的任务族一致：当前状态、漂移状态、变化历史、
来源依据、冲突状态和更新建议。所有条件接收相同核心问题和输出语义。

## 4. Reality Event Model

Reality Event（现实事件）采用以下研究结构：

```text
Event = Actor + Action + Target + Time + Evidence
```

| component | 含义 | 边界 |
|---|---|---|
| `Actor` | 执行、报告或观察行动的主体引用 | 不自动证明身份、权限或可信度 |
| `Action` | 导致或声称导致状态变化的动作类型 | 必须结构化，不以自由文本替代事件类型 |
| `Target` | 被动作影响或被观察的目标对象与字段 | 必须符合 entity boundary |
| `Time` | 事件时间及相关观察／摄取时间 | 时间未知或精度不足必须显式保留 |
| `Evidence` | 支撑事件记录的材料引用 | Evidence reference 不等于 Truth 或 verification |

事件不是普通文本片段，而是导致候选状态变化的结构化观察。自由文本可以作为来源材料或摘要，
但不能单独替代 Actor、Action、Target、Time 和 Evidence 的显式绑定。

一个 Event 可以为 `OBSERVED`、`REPORTED`、`INFERRED`、`CORRECTED`、`RETRACTED` 或
`UNKNOWN`。事件类型描述记录语义，不自动决定事件为真或允许执行任何变化。

## 5. State Transition Model

状态迁移采用以下概念模型：

```text
Before State
    ↓
Transition Event
    ↓
After State
```

每条 `StateTransition` 必须描述：

- `before_state`：迁移前的有界状态与版本；
- `transition_event_ref`：触发或支持迁移判断的 Event 引用；
- `after_state`：迁移后的候选状态与版本；
- `changed_fields`：发生变化的字段及未变化字段边界；
- `change_reason`：变化原因、来源更正或未知原因；
- `supporting_evidence_refs`：支撑变化的证据材料引用；
- `uncertainty`：未知、冲突、覆盖不足和时间不确定性；
- `transition_status`：`CANDIDATE`、`SUPPORTED_FOR_DECLARED_SCOPE`、`CONFLICTED`、
  `RETRACTED` 或 `UNKNOWN`。

`after_state` 不得无痕覆盖 `before_state`。更正和撤回必须形成新的迁移记录，并保留原状态、
原依据和更正来源。State Transition 是研究记录，不是自动更新命令。

## 6. Evidence and Provenance Model

每个候选状态变化必须关联以下字段：

| field | 要求 |
|---|---|
| `source` | 稳定来源引用、来源类型和可用性状态 |
| `timestamp` | 至少区分 event time 与 observation time；其他时间缺失时显式标记 |
| `evidence_type` | 例如 structured observation、versioned document、external report、correction 或 retraction |
| `confidence` | 有界研究表达；允许 `UNKNOWN`，不得伪装成真实概率或 Truth score |
| `provenance` | 从来源材料到 Event、Transition、State 和 query expectation 的连续引用链 |

建议的 provenance 链为：

```text
source_ref
  -> evidence_ref
    -> event_ref
      -> state_transition_ref
        -> state_version_ref
```

来源冲突时必须保留多条 provenance 链，不得为构造干净标签而静默删除不利来源。无法复核的来源
必须标记 `UNAVAILABLE` 或 `UNKNOWN`，而不是沿用旧结论。

## 7. Hidden Reference Ledger

`hidden_reference_ledger` 只用于离线评分，记录声明范围内的参考状态、漂移标签、事件顺序、
预期冲突／未知状态以及指标所需的 provenance reference。

严格规则：

- 不进入 Frozen LLM 的初始输入或 prompt；
- 不进入 RAG corpus、chunk、index、retrieval metadata 或 reranker；
- 不进入 DCell record、Cell builder 输入、同步评估或 update proposal；
- 不用于人工补写模型答案；
- 与可见材料分别存储、版本化和校验 digest；
- 只有离线 scorer 或获授权的独立评分者可以读取；
- 用于判断状态重建、漂移检测、冲突保留、时序恢复和来源引用；
- ledger 的存在不表示其代表现实 Truth，只表示冻结的实验参考答案。

如果 hidden ledger 或其派生标签泄漏到任一条件，相关场景和受影响比较必须标记
`INVALIDATED_DATA_LEAKAGE`，不得继续计分。

## 8. Data Leakage Prevention

### 8.1 禁止评分信息进入输入

expected answer、漂移标签、正确状态、评分规则中的答案提示和 hidden provenance target 不得出现在
prompt、文件名、字段描述、RAG metadata、Cell record 或输出示例中。

### 8.2 禁止未来事件泄漏

在时间 `ti` 的查询中，只能看到 `visibility_time <= ti` 的材料。`ti+1...tn` 的事件、修正、
撤回和来源状态不得通过排序、摘要、版本号或 metadata 提前暴露。

### 8.3 禁止人工补充有利信息

不得在执行中人工挑选检索片段、修正 DCell record、补写来源或删除失败输出。预处理、检索失败、
缺失记录和格式错误必须按预注册规则保留。

### 8.4 三组条件公平性

- Frozen LLM、RAG 和 DCell research condition 使用同一基础模型、核心任务、输出格式和 token 上限；
- RAG 与 DCell 条件在同一时间点只能看到相同的原始来源集合；
- DCell 表示不得加入 RAG 不可获得的事实；
- Frozen LLM 只看到 `t0`，其用途是不可更新的陈旧基线，不能与两个更新条件混成单一公平性结论；
- scenario author、condition builder、executor 和 scorer 应尽可能角色分离；
- 任何可见性、模型、prompt、Schema 或 scoring 变化都需要新版本或 `REASSESSMENT_REQUIRED`。

## 9. Synthetic Scenario Generation Principles

未来生成合成场景时，每个发布候选集合应覆盖：

- **时间变化**：对象状态跨多个时间点演化；
- **状态迁移**：至少包含可追踪的 before/event/after 关系；
- **来源冲突**：同等级或不同等级来源提供不一致状态；
- **信息缺失**：关键字段、时间或来源不可用；
- **更正事件**：已有主张被 correction 或 retraction 替代；
- **无漂移负控**：新材料确认旧状态，测试假阳性更新；
- **乱序事件**：事件时间与摄取顺序不同；
- **身份干扰**：相邻对象变化不得错误归并到目标对象。

生成原则：

1. 只使用低风险合成对象，不映射真实个人或高影响系统；
2. 先冻结 scenario template 和 hidden ledger，再构造三组可见输入；
3. 同一语义应有多个表面变体，避免只测关键词匹配；
4. 保留 `UNKNOWN`、`CONFLICTED`、`UNAVAILABLE`、negative control 和失败样例；
5. 不为提高某组结果而增加额外事实、更多时间可见性或人工解释；
6. 场景数量、领域分层、随机化和统计功效必须在 v0.2 或后续预注册中另行决定。

本节不生成任何合成样例，也不授权进入 v0.2。

## 10. Dataset Versioning

| version | 目标 | 当前边界 |
|---|---|---|
| `v0.1` | 规范设计 | 当前阶段；只有本文档，无 Dataset、样例、Schema 实现或执行 |
| `v0.2` | 少量人工验证样例 | 未来阶段；需要独立授权、review、来源／标签审计和小规模边界 |
| `v1.0` | 正式实验数据集 | 未来候选；需要数据治理、统计计划、版本冻结、独立复核和发布决定 |

每个未来版本必须记录：

- specification revision 与 digest；
- scenario packet manifest 与数量；
- 可见材料和 hidden ledger 的分离 digest；
- 字段、标签、场景和评分规则的 change log；
- 已知限制、冲突、删除、撤回和不兼容变化；
- `implemented`、`generated`、`validated`、`executed`、`released` 的独立状态。

版本号不自动表示 Dataset 已创建、Benchmark 已执行、科学验证成立或获得外部采用。

## 11. Current Status

```text
DATASET_SPECIFICATION_CREATED=true
DATASET_SPECIFICATION_VERSION=0.1
DATASET_SPECIFICATION_STATUS=RESEARCH_DRAFT
SCENARIO_PACKET_SPECIFIED=true
REALITY_EVENT_MODEL_SPECIFIED=true
STATE_TRANSITION_MODEL_SPECIFIED=true
EVIDENCE_PROVENANCE_MODEL_SPECIFIED=true
HIDDEN_REFERENCE_LEDGER_SPECIFIED=true
DATA_LEAKAGE_CONTROLS_SPECIFIED=true
SYNTHETIC_GENERATION_PRINCIPLES_SPECIFIED=true
DATASET_IMPLEMENTED=false
DATASET_GENERATED=false
DATASET_EXECUTED=false
FIXTURES_CREATED=false
RUNNER_IMPLEMENTED=false
MODEL_API_CALLED=false
BENCHMARK_EXECUTED=false
RESULTS_AVAILABLE=false
DCELL_SUPERIORITY_CLAIMED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
RUNTIME_EFFECT=NONE
AUTHORIZATION_EFFECT=NONE
```

当前顺序保持：

```text
Cell Schema
    ↓
Benchmark Design
    ↓
Dataset Specification  ← 当前
    ↓
Small Fixture          ← 未授权、未创建
    ↓
Benchmark Runner       ← 未授权、未实现
    ↓
Experiment             ← 未授权、未执行
```

下一阶段 `Reality Drift Dataset v0.2` 需要新的明确任务与授权。本规范不授权生成样例、实现代码、
调用模型、运行 Benchmark、发布数据集或形成比较结论。
