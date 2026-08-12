---
whitepaper_id: REALITY-SYNCHRONIZATION-LAYER-WHITEPAPER-v0.1.1
supersedes_for_review: REALITY-SYNCHRONIZATION-LAYER-WHITEPAPER-v0.1
title: Reality Synchronization Layer for Long-Lived Agents and World Models
title_zh: 面向长期运行智能体和世界模型的现实同步层
artifact_kind: RESEARCH_WHITEPAPER_REVISION
status: RESEARCH_DRAFT_REVISED_NOT_VALIDATED
version: "0.1.1"
created_at: 2026-08-11T19:51:40Z
claim_boundary_version: "0.1"
revision_basis: INDEPENDENT-WHITEPAPER-REVIEW-v0.1
architecture_phase_closed: true
synthesis_only: true
runtime: false
api: false
database: false
benchmark_executed: false
scientific_validation: NOT_ESTABLISHED
public_research_draft_authorized: false
---

# Reality Synchronization Layer for Long-Lived Agents and World Models

# 面向长期运行智能体和世界模型的现实同步层

## 1. Abstract

## 1. 摘要

**English.** Long-lived agents may continue to rely on an externally declared state after the observable semantic state of an object has changed, been corrected, conflicted, retracted, or become unavailable. This whitepaper explores a candidate external record and evaluation framework for studying that bounded problem. The phrase “for Long-Lived Agents and World Models” denotes a candidate external record and evaluation framework; it does not imply an existing interface, integration, or adoption.

**中文。** 长期运行智能体可能在现实对象的可观察语义状态已经变化、被更正、发生冲突、被撤回或变得不可达之后，仍继续依赖外部声明的旧状态。本白皮书探索一个用于研究该有界问题的候选外部记录与评价框架。“面向长期运行智能体和世界模型”表示候选外部记录与评价框架；它不暗示已经存在接口、集成或采用。

**English.** The framework compares versioned retrieval with a versioned DCell Research Representation under matched source, temporal-visibility, model, and budget conditions. The present package contains documents and a Schema research draft only: there is no Runtime, API, database, dataset instance, Fixture, Runner, model call, Benchmark execution, comparison result, or scientific validation.

**中文。** 该框架在来源、时间可见性、模型和预算匹配的条件下，比较版本化检索与版本化 DCell Research Representation（DCell研究表示）。当前工件包只包含文档与 Schema 研究草案：不存在 Runtime、API、数据库、数据集实例、Fixture、Runner、模型调用、Benchmark 执行、比较结果或科学验证。

| Candidate contribution / 候选贡献 | Not claimed / 不作主张 |
|---|---|
| Semantic Reality Drift as a bounded evaluation problem / 将语义现实漂移定义为有边界评价问题 | A newly discovered scientific phenomenon / 新发现的科学现象 |
| Matched comparison design / 匹配比较设计 | A proven superior architecture / 已证明优越的架构 |
| Failure taxonomy / 失败模式分类 | A novel universal data model / 新的通用数据模型 |
| Evidence- and time-explicit research record / 证据与时间显式研究记录 | First identity/time/provenance/state representation / 首次身份、时间、来源沿袭和状态表示 |
| Candidate falsification conditions / 候选证伪条件 | Fully operationalized falsification protocol / 已完全操作化的证伪协议 |

## 2. Research Status and Claim Boundary

## 2. 研究状态与主张边界

**English.** This repository remains a documentation-and-schema-only research prototype. Whitepaper v0.1.1 is a revised candidate public research draft based on [Independent Whitepaper Review v0.1](../evaluation/independent-whitepaper-review-v0.1.md). Its status is RESEARCH_DRAFT_REVISED_NOT_VALIDATED. Revision does not authorize implementation, experiment, publication, or external adoption, and independent revision verification remains incomplete.

**中文。** 本仓库仍是仅包含文档与 Schema 的研究原型。白皮书 v0.1.1 是根据 [Independent Whitepaper Review v0.1（独立白皮书评审 v0.1）](../evaluation/independent-whitepaper-review-v0.1.md)修订的候选公开研究草案。其状态为 RESEARCH_DRAFT_REVISED_NOT_VALIDATED。文稿修订不授权实现、实验、发布或外部采用，独立修订验证仍未完成。

> DCell explores an evidence-backed, temporally explicit, and governance-bounded
> candidate research substrate for semantic reality synchronization for long-lived
> agents and world models.
>
> DCell 探索一种面向长期运行智能体和世界模型的、证据支撑、时间显式且具有治理边界的
> 候选语义现实同步研究底座。

**English.** The operative terms are explores, candidate, and research. Novelty not established.

**中文。** 有效限定词是探索、候选和研究。新颖性尚未成立。

## 3. Motivation: Long-Lived Agents and Semantic Reality Drift

## 3. 研究动机：长期运行智能体与语义现实漂移

**English.** At time t0, an external system may declare an observable state projection for a bounded object. During t1...tn, sources may report changes, corrections, conflicts, retractions, missing information, or loss of availability. A long-lived agent may then face a stale or uncertain external semantic state. Following the [Benchmark definition](../benchmark/reality-drift-benchmark.md), this paper calls that bounded evaluation problem Semantic Reality Drift.

**中文。** 时间 t0，外部系统可能为一个有界对象声明可观察状态投影；在 t1...tn，来源可能报告变化、更正、冲突、撤回、信息缺失或不可达。长期运行智能体随后可能面对陈旧或不确定的外部语义状态。依照 [Benchmark 定义](../benchmark/reality-drift-benchmark.md)，本文将这一有边界评价问题称为 Semantic Reality Drift（语义现实漂移）。

**English.** The formulation is conditional. It asks whether an evidence-bounded external representation may make a particular class of semantic state changes more inspectable. It does not treat every World Model as having the same problem, and the terminology itself has no established novelty.

**中文。** 该形式化是条件性的。它询问：有证据边界的外部表示，是否可能让一类特定的语义状态变化更易检查。它不把所有 World Model 都视为存在同一问题，该术语本身也没有已经成立的新颖性。

## 4. Current World-Model Boundary

## 4. 当前世界模型边界

**English.** Official sources show that adjacent work already addresses persistence, temporal consistency, physical planning, dynamic scene reconstruction, tracking, and interactive simulation. This table records only the cited public scope and is not a performance comparison.

**中文。** 官方来源表明，相邻工作已经覆盖持久性、时间一致性、物理规划、动态场景重建、追踪和交互模拟。下表只记录所引公开范围，不构成性能比较。

| Official work / 官方工作 | Supported adjacent scope / 可支持的相邻范围 | Boundary here / 本文边界 |
|---|---|---|
| [World Labs Marble](https://docs.worldlabs.ai/index) | Persistent 3D worlds / 持久 3D 世界 | Spatial world creation acknowledged, not evaluated / 承认空间世界生成，不作评价 |
| [World Labs World API](https://www.worldlabs.ai/blog/announcing-the-world-api) | Explorable 3D world generation API / 可探索 3D 世界生成 API | External product API, not an interface of this work / 外部产品 API，不是本研究的接口 |
| [Meta FAIR V-JEPA 2](https://github.com/facebookresearch/vjepa2) | Temporally consistent dense features / 时间一致的稠密特征 | Internal learned representations are out of scope / 内部学习表示不在范围内 |
| [Meta FAIR JEPA-WMs](https://github.com/facebookresearch/jepa-wms) | Environment prediction and physical planning / 环境预测与物理规划 | Planning is not evaluated / 不评价规划能力 |
| [Google DeepMind D4RT](https://deepmind.google/blog/d4rt-teaching-ai-to-see-the-world-in-four-dimensions/) | Dynamic 4D reconstruction and tracking / 动态 4D 重建与追踪 | Physical reconstruction is out of scope / 物理重建不在范围内 |
| [Google DeepMind Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) | Interactive environment simulation / 交互环境模拟 | World generation is not evaluated / 不评价世界生成 |

**English.** DCell is not a World Model. This research does not access latent variables, model parameters, or internal cognitive state; it does not evaluate spatial understanding, physical prediction, planning, or world generation; and it does not claim integration with a World Model. The world-model projection in this paper is only an externally declared and observable state projection.

**中文。** DCell 不是 World Model。本研究不访问潜变量、模型参数或内部认知状态；不评价空间理解、物理预测、规划或世界生成；也不声称已经与 World Model 集成。本文中的 world-model projection 只表示外部声明且可观察的状态投影。

## Related Data and State Representation Patterns

## 相邻数据与状态表示模式

**English.** The candidate research representation overlaps substantially with established data and state representation patterns. The sources below are aligned with the identity, provenance, version, state, uncertainty, and event-history axis of this work; they narrow the candidate contribution instead of supporting a uniqueness claim.

**中文。** 候选研究表示与既有数据和状态表示模式存在大量重叠。下列来源与本研究的身份、来源沿袭、版本、状态、不确定性和事件历史轴直接同轴；它们用于收窄候选贡献，而不支持唯一性主张。

| Source and type / 来源与类型 | Structures already covered / 已覆盖结构 | Boundary for this research / 本研究边界 |
|---|---|---|
| [W3C PROV-DM](https://www.w3.org/TR/prov-dm/), W3C Recommendation / W3C 推荐标准 | Entity, Activity, Agent, generation, invalidation, derivation, revision, responsibility, temporal information, provenance of provenance, and domain extensibility / 实体、活动、责任主体、生成、失效、派生、修订、责任、时间信息、来源沿袭的来源沿袭和领域扩展 | DCell does not originate or replace these provenance structures / DCell 不创设或替代这些来源沿袭结构 |
| [Wikidata Data Model](https://www.wikidata.org/wiki/Wikidata:Data_model/en), official Wikidata/Wikibase data-model description / Wikidata/Wikibase 官方项目数据模型说明 | Stable entity identity, statements, qualifiers, references, preferred, normal, and deprecated ranks, unknown value, no value, and time qualifiers / 稳定实体身份、陈述、限定符、引用、优选、普通和废弃等级、未知值、无值及时间限定 | DCell does not originate or replace these knowledge-representation patterns / DCell 不创设或替代这些知识表示模式 |
| [Martin Fowler, Event Sourcing](https://martinfowler.com/eaaDev/EventSourcing.html), architecture pattern draft / 架构模式草案 | Event sequence, current-state reconstruction, complete rebuild, temporal query, event replay, correction of past events, and out-of-order events / 事件序列、当前状态重建、完整重建、时间查询、事件重放、过去事件更正和乱序事件 | The page explicitly describes draft material; it is not treated here as a standard, peer-reviewed paper, or formal specification / 该页面明确说明属于草案材料；本文不把它视为标准、同行评议论文或正式规范 |

**English.** Current evidence cannot establish that the DCell field set is novel, that the term Reality Drift is novel, that the Reality Synchronization Layer fills a global gap, or that DCell is a new general-purpose data model. DCell does not replace PROV, Wikidata, Event Sourcing, temporal knowledge graphs, digital twins, or agent memory.

**中文。** 当前证据不能证明 DCell 字段集合具有新颖性，不能证明 Reality Drift 术语具有新颖性，不能证明 Reality Synchronization Layer 填补全球空白，也不能证明 DCell 是新的通用数据模型。DCell 不替代 PROV、Wikidata、Event Sourcing、temporal knowledge graph（时态知识图谱）、digital twin（数字孪生）或 agent memory（智能体记忆）。

**English.** The most plausible candidate contributions are strictly narrowed to four items: Semantic Reality Drift as a research problem for long-lived agents; a matched comparison between versioned retrieval and a versioned object-state record under the same facts, temporal visibility, model, and budget; a failure taxonomy covering silent overwrite, identity-boundary error, conflict loss, unsupported claim, and correction failure; and rejection of the DCell research hypothesis when RAG reaches the same or better result at lower cost.

**中文。** 当前最可能成立的候选贡献被严格收窄为四项：面向长期运行智能体的 Semantic Reality Drift（语义现实漂移）研究问题；在相同事实、时间可见性、模型和预算条件下，对 versioned retrieval（版本化检索）与 versioned object-state record（版本化对象状态记录）进行匹配比较；覆盖 silent overwrite（静默覆盖）、identity-boundary error（身份边界错误）、conflict loss（冲突丢失）、unsupported claim（无支持主张）和 correction failure（更正恢复失败）的失败分类；以及当 RAG 以更低成本达到相同或更好结果时拒绝 DCell research hypothesis（DCell研究假设）。

## 6. Problem Formulation: Semantic Reality Drift

## 6. 问题形式化：语义现实漂移

**English.** Semantic Reality Drift is a describable difference between a model-state projection established at t0 and source-linked observations at t1...tn. It may arise from change, correction, missing observation, out-of-order events, source conflict, or staleness. A difference does not by itself show that a source is true, a model is wrong, or an update is required.

**中文。** Semantic Reality Drift 是在 t0 建立的模型状态投影与 t1...tn 的有来源观察之间出现的可描述差异。它可能来自变化、更正、观察缺失、事件乱序、来源冲突或状态陈旧。差异本身不表明来源为真、模型错误或必须更新。

    initial_snapshot
      + ordered_or_declared_unordered_updates
      + source_and_timestamp_metadata
      + query_set
      + hidden_reference_ledger
      + expected_conflict_or_unknown_state

**English.** The hidden reference ledger is isolated for offline scoring. It is a frozen experimental reference rather than reality Truth, and leakage into a condition invalidates the affected comparison. The detailed scenario contract remains in the frozen [Dataset Specification](../dataset/reality-drift-dataset-spec.md).

**中文。** hidden reference ledger（隐藏参考账本）与实验输入隔离，仅用于离线评分。它是冻结的实验参考，而不是现实 Truth；一旦泄漏到某个条件，受影响比较即失效。详细场景契约仍由冻结的 [Dataset Specification（数据集规范）](../dataset/reality-drift-dataset-spec.md)定义。

## 7. Proposed Candidate Layer

## 7. 候选现实同步层

**English.** The candidate architecture uses the frozen mainline from the [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md). The arrows express conceptual reference and interpretation relationships.

**中文。** 候选架构沿用 [Reference Architecture v0.1（参考架构 v0.1）](reality-synchronization-layer-reference-architecture-v0.1.md)的冻结主线。箭头表达概念上的引用与解释关系。

    Reality Sources
        ↓
    Observation / Event
        ↓
    DCell Research Representation
        ↓
    Synchronization Assessment
        ↓
    External World Model / Agent Consumer

**English.** The five frozen research artifacts retain distinct roles: Cell Schema defines a record structure; the Benchmark defines an evaluation design; the Dataset Specification defines scenario and leakage contracts; the Governance Model defines responsibility boundaries; and the Reference Architecture gives the integration view. This whitepaper changes none of them.

**中文。** 五项冻结研究工件保留不同作用：Cell Schema 定义记录结构；Benchmark 定义评价设计；Dataset Specification 定义场景与泄漏契约；Governance Model 定义责任边界；Reference Architecture 提供综合视图。本白皮书不修改其中任何一项。

## 8. DCell Research Representation

## 8. DCell研究表示

**English.** The DCell Research Representation is a versioned research record constrained by [Cell Schema v0.1](../schema/cell.schema.json) and its [schema semantics](../schema/README.md). It organizes identity, reality target, sources, observations, claims, evidence references, state projections, history, conflicts, uncertainties, synchronization assessment, update proposal, truth boundaries, and authorization fields. Schema conformance does not establish semantic correctness or reality truth.

**中文。** DCell Research Representation 是由 [Cell Schema v0.1](../schema/cell.schema.json) 及其 [Schema 语义](../schema/README.md)约束的版本化研究记录。它组织身份、现实目标、来源、观察、主张、证据引用、状态投影、历史、冲突、不确定性、同步评估、更新提议、真值边界和授权字段。Schema 合规不建立语义正确性或现实真值。

**English.** Cell Schema v0.1 has no first-class Event object and no first-class StateTransition object. Its observations, history, evidence references, and summaries express only part of the related information. Therefore, the Schema does not enforce the complete event or state-transition contracts used in the Dataset Specification and Reference Architecture.

**中文。** Cell Schema v0.1 当前没有第一类 Event 对象，也没有第一类 StateTransition 对象。其 observations、history、evidence references 和 summaries 只能表达部分相关信息。因此，该 Schema 不强制约束 Dataset Specification 与 Reference Architecture 使用的完整事件或状态迁移契约。

**English.** A synchronization assessment may express freshness, divergence, coverage, basis references, and uncertainty. A non-executable update proposal may record candidate changes and reasons. Assessment or proposal is not authorization, a model write, or a reality action.

**中文。** 同步评估可以表达 freshness、divergence、coverage、依据引用和不确定性。不可执行的更新提议可以记录候选变化与理由。评估或提议不等于授权、模型写入或现实行动。

## 9. Observation, Event and State Transition

## 9. 观察、事件与状态迁移

**English.** The following structures belong to the conceptual contract of the [Dataset Specification](../dataset/reality-drift-dataset-spec.md) and the [Reference Architecture](reality-synchronization-layer-reference-architecture-v0.1.md):

**中文。** 以下结构属于 [Dataset Specification（数据集规范）](../dataset/reality-drift-dataset-spec.md)与 [Reference Architecture（参考架构）](reality-synchronization-layer-reference-architecture-v0.1.md)的概念契约：

    Event = Actor + Action + Target + Time + Evidence

    Before State
        ↓
    Transition Event
        ↓
    After State

**English.** Actor, Action, Target, Time, and Evidence describe the intended event semantics. Before State, Transition Event, and After State describe the intended transition trace. Observation is not fact, and the after state is a source-bounded candidate state rather than reality Truth. Corrections, retractions, conflicts, unknowns, and prior states should remain traceable.

**中文。** Actor、Action、Target、Time 和 Evidence 描述预期事件语义；Before State、Transition Event 和 After State 描述预期迁移轨迹。Observation 不等于事实，after state 是有来源边界的候选状态，而不是现实 Truth。更正、撤回、冲突、未知和先前状态应保持可追溯。

**English.** The conceptual event and transition contracts exceed the current enforcement scope of Cell Schema v0.1.

**中文。** 事件与状态迁移的概念契约超出了当前 Cell Schema v0.1 的强制约束范围。

## 10. Evidence and Provenance Boundary

## 10. 证据与来源沿袭边界

**English.** Evidence handling retains source references, evidence references, available temporal information, uncertainty, source availability, and separate provenance paths for conflicts. Missing time or unavailable sources remain explicit.

**中文。** 证据处理保留来源引用、证据引用、可用时间信息、不确定性、来源可用性，以及冲突来源各自独立的来源沿袭路径。时间缺失或来源不可达保持显式。

    Evidence != Truth
    Provenance != Correctness

    证据不等于真值
    来源沿袭不等于正确性

**English.** Evidence is inspectable supporting material within a declared scope; provenance records derivation and custody relationships. Neither creates verification, certification, authority, or correctness.

**中文。** Evidence 是声明范围内可检查的支撑材料；provenance 记录派生和保管关系。二者都不创建验证、认证、权威或正确性。

## 11. Governance Boundary

## 11. 治理边界

**English.** [Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) uses five research roles: Cell Owner, Evidence Provider, Cell Maintainer, Agent Consumer, and Evaluator. They describe responsibility relationships. The frozen sequence Observation → Evidence → Update Proposal → Review / Assessment → State Transition records a candidate local research-record change.

**中文。** [Governance Model v0.1（治理模型 v0.1）](../governance/dcell-governance-model-v0.1.md)使用五个研究角色：Cell Owner、Evidence Provider、Cell Maintainer、Agent Consumer 和 Evaluator。它们描述责任关系。冻结顺序 Observation → Evidence → Update Proposal → Review / Assessment → State Transition 记录候选的本地研究记录变化。

    Role != Permission
    Assessment / Proposal != Authorization

    角色不等于权限
    评估 / 提议不等于授权

**English.** A review or assessment does not authorize an external model update or a real-world write. Responsibility, decision, authorization, and execution remain separate.

**中文。** review 或 assessment 不授权外部模型更新或现实写入。责任、决定、授权和执行保持分离。

## 12. Evaluation Framework

## 12. 评价框架

**English.** The [Reality Drift Benchmark](../benchmark/reality-drift-benchmark.md) compares three external knowledge-organization conditions under a frozen base-model context.

**中文。** [Reality Drift Benchmark（现实漂移基准）](../benchmark/reality-drift-benchmark.md)在冻结的基础模型上下文中比较三种外部知识组织条件。

| Condition / 条件 | Visible organization / 可见组织方式 | Evaluation role / 评价作用 |
|---|---|---|
| Frozen LLM / 冻结语言模型 | t0 snapshot only / 仅 t0 快照 | Staleness negative control / 陈旧负控 |
| RAG / 检索增强生成 | Versioned document retrieval / 版本化文档检索 | Updated-material baseline / 更新材料基线 |
| DCell research condition / DCell研究条件 | Versioned object-state research record / 版本化对象状态研究记录 | Representation condition / 表示条件 |

**English.** Primary metrics are Drift Detection Macro-F1, Current State Exactness, Unsupported Claim Rate, Provenance Recall, and Conflict Preservation Rate. Secondary checks include false update proposals, correction recovery, temporal ordering, appropriate unknown or abstention behavior, silent overwrite, identity-boundary error, update lag, and separately reported resource costs. No winner is presumed.

**中文。** 主要指标包括 Drift Detection Macro-F1、Current State Exactness、Unsupported Claim Rate、Provenance Recall 和 Conflict Preservation Rate。次要检查包括错误更新提议、更正恢复、时间排序、适当的未知或拒答、静默覆盖、身份边界错误、更新延迟，以及单独报告的资源成本。不预设获胜者。

### Builder Transformation Parity

### 构建器转换对等性

**English.** Giving RAG and DCell the same raw sources and temporal visibility is necessary but insufficient for a fair comparison. A DCell builder may pre-encode current state, conflict labels, uncertainty, identity boundaries, temporal order, or synchronization assessments.

**中文。** 为 RAG 与 DCell 提供相同原始来源和时间可见性是公平比较的必要条件，但并不充分。DCell builder 可能预先编码当前状态、冲突标签、不确定性、身份边界、时间顺序或同步评估。

**English.** If an author or hidden ledger derives those semantics, the experiment would measure additional human labeling or preprocessing advantage rather than the value of the representation itself.

**中文。** 如果这些语义由作者或 hidden ledger 派生，实验测到的将是额外人工标签或预处理优势，而不是表示方式本身的价值。

**English.** No fair-comparison conclusion may be formed until the following are frozen:

**中文。** 在以下条件冻结前，不得形成公平比较结论：

- Blind transformation / 盲化转换；
- Deterministic or auditable transformation contract / 确定性或可审计的转换契约；
- Builder-hidden-ledger isolation / 构建器与隐藏账本隔离；
- Equivalent output task schema / 等价输出任务结构；
- Transformation labor and token accounting / 转换人工与 Token 成本核算；
- Role separation among scenario author, builder, executor, and scorer / 场景作者、构建者、执行者和评分者角色分离。

**English.** Builder transformation parity remains an unresolved threat to validity. This revision records the threat without implementing a builder or creating a Fixture or Runner.

**中文。** 构建器转换对等性仍是未决的有效性威胁。本次修订只记录该威胁，不实现 builder，也不创建 Fixture 或 Runner。

## 13. Falsifiability and Rejection Conditions

## 13. 可证伪性与拒绝条件

**English.** The current status is candidate rejection conditions pending preregistration.

**中文。** 当前状态是待预注册的候选拒绝条件。

**English.** The present design lacks an effect-size threshold, non-inferiority margin, sample size, confidence-interval rule, cost threshold, cross-metric decision rule, and multiple-comparison plan. It is not an executable falsification protocol; preregistration has not been completed; and statistical decision criteria have not been frozen.

**中文。** 当前设计缺少 effect-size threshold（效应量阈值）、non-inferiority margin（非劣界值）、sample size（样本量）、confidence interval rule（置信区间规则）、cost threshold（成本阈值）、cross-metric decision rule（跨指标裁决规则）和 multiple-comparison plan（多重比较计划）。它不是可执行证伪协议；尚未完成预注册；统计判定标准也尚未冻结。

**English.** The existing rejection directions remain: RAG may reach the same or better primary outcomes at lower cost; an apparent DCell benefit may come from extra facts, more tokens, manual labels, or correction; the DCell condition may fail to preserve sources, conflicts, unknowns, temporal order, or history; maintenance cost may exceed measurable benefit; and results may be unstable across prompt wording, scenario wording, or model revision.

**中文。** 现有拒绝方向保持不变：RAG 可能以更低成本达到相同或更好的主要结果；表面上的 DCell 收益可能来自额外事实、更多 Token、人工标签或修正；DCell 条件可能无法保留来源、冲突、未知、时间顺序或历史；维护成本可能超过可测收益；结果可能对 prompt 表述、场景表述或模型 revision 不稳定。

**English.** Until the missing rules are frozen, any future result can only be an exploratory observation. This revision introduces no numerical threshold.

**中文。** 在缺失规则冻结前，任何未来结果只能是 exploratory observation（探索性观察）。本次修订不引入任何数值阈值。

## 14. Limitations and Threats to Validity

## 14. 局限与有效性威胁

**English.** The present artifact set has no Runtime, API, database, service, platform, Registry, real Cell, dataset instance, Fixture, Runner, model call, Benchmark execution, result, statistical plan, external replication, or scientific validation. The scope is semantic state synchronization only. Schema conformance cannot establish source truth, semantic correctness, completeness, freshness, or safety.

**中文。** 当前工件集合不存在 Runtime、API、数据库、服务、平台、Registry、真实 Cell、数据集实例、Fixture、Runner、模型调用、Benchmark 执行、结果、统计计划、外部复现或科学验证。范围仅限语义状态同步。Schema 合规不能建立来源真值、语义正确性、完整性、时效性或安全性。

**English.** External observable projection is not internal model state. The project neither reads internal cognition nor evaluates the intrinsic capabilities of a World Model. The adjacent-work discussion is bounded by selected sources and is not a systematic literature review. Builder transformation parity is unresolved.

**中文。** 外部可观察投影不等于模型内部状态。本项目既不读取内部认知，也不评价 World Model 的本体能力。相邻工作讨论受所选来源限制，不是系统性文献综述。构建器转换对等性仍未解决。

**English.** These limitations prevent claims of effectiveness, superiority, deployment readiness, standardization, certification, external adoption, scientific validity, or publication readiness. Whitepaper revision is not implementation evidence or publication authorization.

**中文。** 这些限制阻止关于有效性、优越性、部署就绪、标准化、认证、外部采用、科学有效性或发布就绪的主张。白皮书修订不是实现证据，也不是发布授权。

## 15. Bounded Research Agenda

## 15. 有界研究议程

**English.** The agenda remains limited to existing questions: whether a minimal record helps identify stale, conflicted, or unknown state; whether independent reviewers can reconstruct an assessment basis; whether a versioned object-state record differs measurably from matched versioned retrieval; whether conflicts, unknowns, corrections, retractions, and identity boundaries remain intact; and whether representation and governance cost exceeds any measured benefit.

**中文。** 研究议程仍限于已有问题：最小记录是否有助于识别陈旧、冲突或未知状态；独立复核者能否重建评估依据；版本化对象状态记录与匹配的版本化检索是否存在可测差异；冲突、未知、更正、撤回和身份边界能否保持完整；表示与治理成本是否超过任何测得收益。

**English.** Questions about experimental thresholds, builder behavior, scenario counts, additional baselines, model drift, and downstream consumption remain deferred. They require separate authorization and cannot be answered by this document revision.

**中文。** 关于实验阈值、builder 行为、场景数量、附加基线、模型漂移和下游消费的问题保持延后。它们需要单独授权，不能由本次文稿修订回答。

## 16. Current Status and Nonclaims

## 16. 当前状态与非声明

**English.** The following block is a bounded summary. Repository-wide current status remains governed by [STATUS.json](../STATUS.json).

**中文。** 以下区块是有界摘要。仓库级当前状态仍由 [STATUS.json](../STATUS.json) 管理。

    WHITEPAPER_REVISION_CREATED=true
    WHITEPAPER_CURRENT_VERSION=0.1.1
    WHITEPAPER_REVISION_STATUS=RESEARCH_DRAFT_REVISED_NOT_VALIDATED
    WHITEPAPER_V0_1_PRESERVED=true
    REVISION_BASIS=INDEPENDENT-WHITEPAPER-REVIEW-v0.1
    REQUIRED_REVISION_MAJOR_ADDRESSED_COUNT=4
    REQUIRED_REVISION_MINOR_ADDRESSED_COUNT=1
    INDEPENDENT_REVISION_VERIFICATION_COMPLETED=false
    PUBLIC_RESEARCH_DRAFT_AUTHORIZED=false
    ARCHITECTURE_PHASE_CLOSED=true
    SYNTHESIS_ONLY=true
    CLAIM_BOUNDARY_FROZEN=true
    CLAIM_BOUNDARY_VERSION=0.1
    WORLD_MODEL_INTERNAL_STATE_ACCESS=false
    SEMANTIC_SYNCHRONIZATION_SCOPE_ONLY=true
    RUNTIME=false
    API=false
    DATABASE=false
    FIXTURE_CREATED=false
    RUNNER_IMPLEMENTED=false
    MODEL_API_CALLED=false
    BENCHMARK_EXECUTED=false
    SCIENTIFIC_VALIDATION=NOT_ESTABLISHED

**English.** The block means only that a review-driven candidate revision exists. It does not record independent revision verification, implementation, experiment, publication, release, or external adoption.

**中文。** 该区块只表示评审驱动的候选修订稿存在。它不记录独立修订验证、实现、实验、发布、release 或外部采用。

## References

## 参考文献

### Internal frozen artifacts

### 内部冻结工件

1. [STATUS.json](../STATUS.json) — only current repository status source / 唯一当前仓库状态源。
2. [Research Scope v0.1](research-scope.md) — scope and stop conditions / 范围与停止条件。
3. [Claims and Nonclaims](claims-and-nonclaims.md) — claim boundary / 主张边界。
4. [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md) — frozen integration view / 冻结综合视图。
5. [Cell Schema v0.1](../schema/cell.schema.json) and [schema semantics](../schema/README.md) — current record enforcement boundary / 当前记录强制约束边界。
6. [Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md) — comparison design / 比较设计。
7. [Reality Drift Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md) — conceptual event, transition, and leakage contracts / 事件、迁移和泄漏概念契约。
8. [DCell Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) — responsibility and authority boundary / 责任与权威边界。
9. [Research Questions v0.1](../research/research-questions.md) — existing research questions / 既有研究问题。
10. [Independent Whitepaper Review v0.1](../evaluation/independent-whitepaper-review-v0.1.md) — revision basis / 修订依据。
11. [Research Source Manifest](../evidence/source-manifest.json) — source relationship record / 来源关系记录。

### External sources

### 外部来源

1. World Wide Web Consortium. [PROV-DM: The PROV Data Model](https://www.w3.org/TR/prov-dm/) — W3C Recommendation / W3C 推荐标准。
2. Wikidata. [Wikidata Data Model](https://www.wikidata.org/wiki/Wikidata:Data_model/en) — official Wikidata/Wikibase data-model description / Wikidata/Wikibase 官方项目数据模型说明。
3. Martin Fowler. [Event Sourcing](https://martinfowler.com/eaaDev/EventSourcing.html) — architecture pattern draft / 架构模式草案。
4. World Labs. [Welcome to Marble](https://docs.worldlabs.ai/index) — persistent 3D worlds / 持久 3D 世界。
5. World Labs. [Announcing the World API](https://www.worldlabs.ai/blog/announcing-the-world-api) — explorable 3D world API / 可探索 3D 世界 API。
6. Meta FAIR. [V-JEPA 2 official repository](https://github.com/facebookresearch/vjepa2) — temporally consistent dense features / 时间一致的稠密特征。
7. Meta FAIR. [JEPA-WMs official repository](https://github.com/facebookresearch/jepa-wms) — environment prediction and physical planning / 环境预测与物理规划。
8. Google DeepMind. [D4RT](https://deepmind.google/blog/d4rt-teaching-ai-to-see-the-world-in-four-dimensions/) — dynamic 4D reconstruction and tracking / 动态 4D 重建与追踪。
9. Google DeepMind. [Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) — interactive environment simulation / 交互环境模拟。

**English.** These sources bound the related-work positioning. They do not establish novelty, superiority, adoption, scientific validation, or publication authorization.

**中文。** 这些来源限定相关工作定位。它们不建立新颖性、优越性、外部采用、科学验证或发布授权。
