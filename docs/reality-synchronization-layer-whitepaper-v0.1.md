---
whitepaper_id: REALITY-SYNCHRONIZATION-LAYER-WHITEPAPER-v0.1
title: Reality Synchronization Layer for Long-Lived Agents and World Models
title_zh: 面向长期运行智能体和世界模型的现实同步层
artifact_kind: RESEARCH_WHITEPAPER
status: RESEARCH_DRAFT_NOT_VALIDATED
version: "0.1"
created_at: 2026-08-11T19:11:44Z
claim_boundary_version: "0.1"
architecture_phase_closed: true
synthesis_only: true
runtime: false
api: false
database: false
benchmark_executed: false
scientific_validation: NOT_ESTABLISHED
---

# Reality Synchronization Layer for Long-Lived Agents and World Models

# 面向长期运行智能体和世界模型的现实同步层

## 1. Abstract / 摘要

**English.** Long-lived agents may continue to rely on an externally declared state after the observable semantic state of an object has changed, been corrected, conflicted, retracted, or become unavailable. This whitepaper synthesizes a candidate Reality Synchronization Layer（现实同步层）for studying that bounded problem. The candidate uses a DCell Research Representation（DCell研究表示）to retain identity, sources, observations, evidence references, state history, conflicts, uncertainties, and a non-executable synchronization assessment.

**中文。** 长期运行智能体可能在现实对象的可观察语义状态已经变化、被更正、发生冲突、被撤回或变得不可达之后，仍继续依赖外部声明的旧状态。本白皮书综合一个用于研究该有界问题的候选 Reality Synchronization Layer（现实同步层）。该候选层使用 DCell Research Representation（DCell研究表示）保留身份、来源、观察、证据引用、状态历史、冲突、不确定性以及不可执行的同步评估。

**English.** The frozen research package consists of [Cell Schema v0.1](../schema/cell.schema.json), [Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md), [Reality Drift Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md), [DCell Governance Model v0.1](../governance/dcell-governance-model-v0.1.md), and the [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md). No Runtime, API, database, dataset instance, Runner, model call, Benchmark execution, comparison result, or scientific validation exists.

**中文。** 冻结的研究包由 [Cell Schema v0.1](../schema/cell.schema.json)、[Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md)、[Reality Drift Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md)、[DCell Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) 和 [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md) 构成。当前不存在 Runtime、API、数据库、数据集实例、Runner、模型调用、Benchmark 执行、比较结果或科学验证。

## 2. Research Status and Claim Boundary / 研究状态与主张边界

**English.** This repository remains a documentation-and-schema-only research prototype. The architecture phase is closed, claim boundary v0.1 is frozen, and this whitepaper is synthesis only. Its status is `RESEARCH_DRAFT_NOT_VALIDATED`; creation of the document does not validate the hypothesis or authorize implementation, experiment, publication, or external adoption. These boundaries follow [STATUS.json](../STATUS.json), [Research Scope v0.1](research-scope.md), and [Claims and Nonclaims](claims-and-nonclaims.md).

**中文。** 本仓库仍是仅包含文档与 Schema 的研究原型。架构阶段已经关闭，主张边界 v0.1 已冻结，本白皮书仅作综合整理。其状态为 `RESEARCH_DRAFT_NOT_VALIDATED`；文档创建不验证研究假设，也不授权实现、实验、发布或外部采用。这些边界遵循 [STATUS.json](../STATUS.json)、[Research Scope v0.1](research-scope.md) 和 [Claims and Nonclaims](claims-and-nonclaims.md)。

> DCell explores an evidence-backed, temporally explicit,
> and governance-bounded semantic reality synchronization substrate
> for long-lived agents and world models.
>
> DCell探索一种面向长期运行智能体和世界模型的、
> 证据支撑、时间显式且具有治理边界的语义现实同步底座。

**English.** The operative verb is `explores`. This whitepaper does not say that DCell implements, establishes, solves, proves, or standardizes the candidate substrate. There is no Runtime, API, database, model call, Benchmark execution, superiority claim, or scientific validation.

**中文。** 有效动词是 `探索`。本白皮书不声称 DCell 已实现、建立、解决、证明或标准化该候选底座。当前没有 Runtime、API、数据库、模型调用、Benchmark 执行、优越性主张或科学验证。

## 3. Motivation: Long-Lived Agents and Semantic Reality Drift / 研究动机：长期运行智能体与语义现实漂移

**English.** The motivating case is deliberately narrow. At time `t0`, an external system declares an observable state projection for a bounded object. During `t1...tn`, reality sources may report changes, corrections, conflicts, retractions, missing information, or loss of availability. A long-lived agent may then face a stale or uncertain external semantic state. This paper calls the resulting research phenomenon Reality Drift（现实漂移）, following the [Benchmark definition](../benchmark/reality-drift-benchmark.md).

**中文。** 研究动机被刻意限定在较窄范围。时间 `t0`，外部系统为一个有界对象声明可观察状态投影；在 `t1...tn`，现实来源可能报告变化、更正、冲突、撤回、信息缺失或不可达。长期运行智能体随后可能面对陈旧或不确定的外部语义状态。依照 [Benchmark 定义](../benchmark/reality-drift-benchmark.md)，本文将这一研究现象称为 Reality Drift（现实漂移）。

**English.** This formulation is conditional, not universal. It does not assert that every World Model has this problem, that existing World Models lack update mechanisms, or that DCell has solved reality synchronization. It asks whether an evidence-bounded external representation can make a particular class of semantic state changes more inspectable.

**中文。** 该形式化是条件性的，不是普遍性断言。它不声称所有 World Model 都存在这一问题，不声称现有 World Model 缺乏更新机制，也不声称 DCell 已经解决现实同步。它只询问：有证据边界的外部表示，能否让一类特定的语义状态变化更易检查。

## 4. Current World-Model Boundary / 当前世界模型边界

**English.** Official sources show that adjacent work already addresses persistence, temporal consistency, physical planning, dynamic scene reconstruction, tracking, and interactive simulation. The table records only the scope supported by those official descriptions; it is not a performance comparison.

**中文。** 官方来源表明，相邻工作已经覆盖持久性、时间一致性、物理规划、动态场景重建、追踪和交互模拟。下表只记录这些官方描述能够支持的范围，不构成性能比较。

| Official work / 官方工作 | Supported adjacent scope / 可支持的相邻范围 | Boundary in this paper / 本文边界 |
|---|---|---|
| [World Labs Marble](https://docs.worldlabs.ai/index) | Persistent 3D worlds<br>持久 3D 世界 | Spatial world creation is acknowledged, not evaluated.<br>承认空间世界生成，不作评价。 |
| [World Labs World API](https://www.worldlabs.ai/blog/announcing-the-world-api) | Programmable generation of explorable 3D worlds<br>可编程生成可探索 3D 世界 | An external product API, not this repository's API.<br>属于外部产品 API，不是本仓库 API。 |
| [Meta FAIR V-JEPA 2.1](https://github.com/facebookresearch/vjepa2) | Temporally consistent dense representations<br>时间一致的稠密表示 | Internal learned representations are outside DCell v0.1.<br>内部学习表示不属于 DCell v0.1。 |
| [Meta FAIR JEPA-WMs](https://github.com/facebookresearch/jepa-wms) | Environment prediction and physical planning<br>环境预测与物理规划 | Planning capability is not measured by this project.<br>本项目不测量规划能力。 |
| [Google DeepMind D4RT](https://deepmind.google/blog/d4rt-teaching-ai-to-see-the-world-in-four-dimensions/) | Dynamic 4D reconstruction and tracking<br>动态 4D 重建与追踪 | Physical scene reconstruction is out of scope.<br>物理场景重建不在范围内。 |
| [Google DeepMind Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) | Interactive environment simulation and action-conditioned evolution<br>交互环境模拟与动作条件演化 | Generated-world capability is not evaluated here.<br>本文不评价生成世界能力。 |

**English.** The bounded differentiation hypothesis is that adjacent routes principally study spatial or physical scenes, environment prediction, planning, and simulation, while this project studies how an auditable semantic state of a reality-linked object might be updated across heterogeneous sources. This is an inference from the cited public scopes, not a complete system review, uniqueness proof, global-gap claim, or claim that DCell is a missing infrastructure layer.

**中文。** 有界差异化假设是：相邻路线主要研究空间或物理场景、环境预测、规划与模拟，而本项目研究与现实关联对象的可审计语义状态可能如何跨异构来源持续更新。这是从所引公开范围形成的推断，不是完整系统综述、唯一性证明、全球空白声明，也不声称 DCell 是某个缺失基础设施层。

## 5. Problem Formulation: Semantic Reality Drift / 问题形式化：语义现实漂移

**English.** Reality Drift is defined in the frozen Benchmark as a describable difference between a model-state projection established at `t0` and source-linked observations at `t1...tn`. The difference may arise from reality change, source correction, missing observation, out-of-order events, source conflict, or state staleness. It does not by itself prove that a source is true, that a model is wrong, or that an update must occur.

**中文。** 冻结 Benchmark 将 Reality Drift 定义为：在 `t0` 建立的模型状态投影，与 `t1...tn` 的有来源观察之间出现可描述差异。该差异可能来自现实变化、来源更正、观察缺失、事件乱序、来源冲突或状态陈旧。它本身不证明来源为真、模型错误或必须执行更新。

```text
initial_snapshot
  + ordered_or_unordered_updates
    (frozen Benchmark form: ordered_or_declared_unordered_updates)
  + source_and_timestamp_metadata
  + query_set
  + hidden_reference_ledger
  + expected_conflict_or_unknown_state
```

**English.** A scenario packet therefore preserves the initial snapshot, ordered or declared-unordered updates, source and timestamp metadata, a query set, and expected conflict or unknown state. The `hidden_reference_ledger` is isolated for offline scoring. It is a frozen experimental reference, not reality Truth, and leakage into any condition invalidates the affected comparison. The detailed contract is defined by the [Dataset Specification](../dataset/reality-drift-dataset-spec.md).

**中文。** 因而，场景包保留初始快照、有序或声明为无序的更新、来源与时间戳元数据、查询集，以及预期冲突或未知状态。`hidden_reference_ledger` 与实验输入隔离，仅用于离线评分；它是冻结的实验参考，不是现实 Truth，泄漏到任何条件都会使受影响比较失效。详细契约由 [Dataset Specification](../dataset/reality-drift-dataset-spec.md) 定义。

## 6. Proposed Candidate Layer / 候选现实同步层

**English.** The frozen candidate architecture contains exactly the following mainline from the [Reference Architecture](reality-synchronization-layer-reference-architecture-v0.1.md). No additional layer is introduced by this whitepaper.

**中文。** 冻结的候选架构只包含以下来自 [Reference Architecture](reality-synchronization-layer-reference-architecture-v0.1.md) 的主线。本白皮书不引入任何附加层。

```text
Reality Sources
    ↓
Observation / Event
    ↓
DCell Research Representation
    ↓
Synchronization Assessment
    ↓
External World Model / Agent Consumer
```

**English.** The arrows express conceptual reference and interpretation relationships. They are not implemented data flows, service calls, write permissions, automatic migrations, or model-update operations. Reality sources, model computation, authorization, and execution remain external.

**中文。** 箭头表达概念上的引用与解释关系。它们不是已实现的数据流、服务调用、写权限、自动迁移或模型更新操作。现实来源、模型计算、授权和执行仍位于外部。

**English.** The five frozen research artifacts have distinct, non-executing roles.

**中文。** 五项冻结研究工件具有彼此不同且不可执行的作用。

| Frozen artifact / 冻结工件 | Synthesis role / 综合中的作用 | Nonclaim / 非声明 |
|---|---|---|
| [Cell Schema v0.1](../schema/cell.schema.json) | Record structure<br>记录结构 | Schema, not Runtime<br>Schema，不是 Runtime |
| [Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md) | Evaluation design<br>评价设计 | Design, not execution<br>设计，不是执行 |
| [Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md) | Scenario and leakage contract<br>场景与泄漏契约 | Specification, not Dataset<br>规范，不是数据集 |
| [Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) | Responsibility and evidence boundary<br>责任与证据边界 | Roles, not permissions<br>角色，不是权限 |
| [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md) | Frozen integration view<br>冻结综合视图 | Candidate architecture, not implementation<br>候选架构，不是实现 |

## 7. DCell Research Representation / DCell研究表示

**English.** The DCell Research Representation is a versioned research record constrained by [Cell Schema v0.1](../schema/cell.schema.json) and its [schema semantics](../schema/README.md). It organizes identity, reality target, sources, observations, claims, evidence references, state projections, history, conflicts, uncertainties, synchronization assessment, update proposal, truth boundaries, and authorization fields. Schema conformance does not establish semantic correctness or reality truth.

**中文。** DCell Research Representation 是由 [Cell Schema v0.1](../schema/cell.schema.json) 及其 [Schema 语义](../schema/README.md) 约束的版本化研究记录。它组织 identity、reality target、sources、observations、claims、evidence references、state projections、history、conflicts、uncertainties、synchronization assessment、update proposal、truth boundaries 和 authorization 字段。Schema 合规不建立语义正确性或现实真值。

```text
world_model_projection = externally declared and observable state projection
world_model_projection = 外部声明且可观察的状态投影
```

**English.** `world_model_projection` is limited to an externally declared and observable state projection, such as an explicit structured state, versioned declaration, or inspectable output supplied by an external system. It is not neural latent state（神经潜在状态）, model parameter access（模型参数访问）, internal cognition（内部认知状态）, or an automatic model update interface（自动模型更新接口）. `reality_projection` is likewise a source-bounded candidate projection, not reality itself.

**中文。** `world_model_projection` 仅指外部声明且可观察的状态投影，例如外部系统提供的显式结构化状态、版本化声明或可检查输出。它不是 neural latent state（神经潜在状态）、model parameter access（模型参数访问）、internal cognition（内部认知状态）或 automatic model update interface（自动模型更新接口）。`reality_projection` 同样只是有来源边界的候选投影，不是现实本身。

**English.** A synchronization assessment may express freshness, divergence, coverage, basis references, and uncertainty. A non-executable update proposal may record proposed changes and reasons, but `application_authorized=false` is invariant in v0.1. Assessment and proposal do not authorize model writes or reality actions.

**中文。** 同步评估可以表达 freshness、divergence、coverage、依据引用和不确定性。不可执行的更新提议可以记录候选变化与理由，但在 v0.1 中 `application_authorized=false` 保持不变。评估和提议不授权模型写入或现实行动。

## 8. Observation, Event and State Transition / 观察、事件与状态迁移

**English.** The [Dataset Specification](../dataset/reality-drift-dataset-spec.md) defines an event as a structured observation rather than an unqualified text fragment.

**中文。** [Dataset Specification](../dataset/reality-drift-dataset-spec.md) 将事件定义为结构化观察，而不是没有约束的文本片段。

```text
Event = Actor + Action + Target + Time + Evidence
```

**English.** `Actor` identifies the acting, reporting, or observing subject; `Action` describes the action; `Target` binds the affected object and field; `Time` preserves available temporal semantics; and `Evidence` links supporting material. Identity, authority, and truth cannot be inferred merely from the presence of these fields. An Observation is not a fact, and an Event does not directly modify a Cell.

**中文。** `Actor` 标识行动、报告或观察主体；`Action` 描述动作；`Target` 绑定受影响对象和字段；`Time` 保留可用时间语义；`Evidence` 连接支撑材料。不能仅因这些字段存在就推导身份、权限或真值。Observation 不等于事实，Event 也不直接修改 Cell。

```text
Before State
    ↓
Transition Event
    ↓
After State
```

**English.** `After State` is a candidate state for a declared scope, not reality Truth. The old state must not be silently overwritten. Correction, retraction, conflict, unknown, changed fields, reasons, and supporting evidence remain traceable through transition and history records.

**中文。** `After State` 是声明范围内的候选状态，不是现实 Truth。旧状态不得被无痕覆盖。更正、撤回、冲突、未知、变化字段、原因和支撑证据必须通过迁移与历史记录保持可追溯。

## 9. Evidence and Provenance Boundary / 证据与来源沿袭边界

**English.** Evidence handling preserves a stable source reference, evidence reference, provenance chain, event time, observation time, publication time, ingestion time, uncertainty, and source availability. Missing times or unavailable sources remain explicit rather than being replaced with inferred certainty. Conflicting sources retain separate provenance paths.

**中文。** 证据处理保留稳定的 source reference、evidence reference、provenance chain、event time、observation time、publication time、ingestion time、不确定性和来源可用性。时间缺失或来源不可达时必须显式保留，不能用推断出的确定性替代。冲突来源保留各自独立的 provenance 路径。

```text
source_ref
  -> evidence_ref
    -> event_ref
      -> state_transition_ref
        -> state_version_ref
```

**English.** `Evidence ≠ Truth` and `Provenance ≠ Correctness`. Evidence is inspectable supporting material within a declared scope; provenance records derivation and custody relationships. Neither creates truth, verification, certification, authority, or correctness. These limits follow the [Dataset Specification](../dataset/reality-drift-dataset-spec.md) and [Governance Model](../governance/dcell-governance-model-v0.1.md).

**中文。** `证据不等于真值`，`来源沿袭不等于正确性`。Evidence 是声明范围内可检查的支撑材料；provenance 记录派生和保管关系。二者都不创建真值、验证、认证、权威或正确性。这些限制遵循 [Dataset Specification](../dataset/reality-drift-dataset-spec.md) 和 [Governance Model](../governance/dcell-governance-model-v0.1.md)。

## 10. Governance Boundary / 治理边界

**English.** Governance v0.1 uses exactly five core research roles. They describe responsibility relationships and do not implement accounts, access control, voting, scores, incentives, an economic model, or a Marketplace.

**中文。** Governance v0.1 只使用五个核心研究角色。它们描述责任关系，不实现账号、访问控制、投票、评分、激励、经济模型或 Marketplace。

- **Cell Owner（Cell责任主体）:** Maintains the declared lifecycle responsibility boundary; does not own the represented reality object.<br>维护声明的生命周期责任边界；不拥有被表示的现实对象。
- **Evidence Provider（证据提供者）:** Supplies traceable materials or observations; does not become an evidence or truth authority.<br>提供可追溯材料或观察；不因此成为证据或真值权威。
- **Cell Maintainer（Cell维护者）:** Organizes state, history, conflicts, uncertainty, and proposals; cannot authorize execution.<br>整理状态、历史、冲突、不确定性和提议；不能授权执行。
- **Agent Consumer（智能体消费者）:** Reads and uses bounded state and evidence; use does not establish correctness or adoption.<br>读取并使用有界状态与证据；使用不建立正确性或外部采用。
- **Evaluator（评价者）:** Produces assessment or recommendation; cannot directly modify a Cell or create authority.<br>产生评价或建议；不能直接修改 Cell 或创建权威。

```text
Role ≠ Permission
角色不等于权限

Ownership ≠ Reality Object Ownership
维护责任不等于现实对象所有权

Evaluation ≠ Authority
评价不等于权威
```

**English.** The frozen update-governance sequence remains Observation → Evidence → Update Proposal → Review / Assessment → State Transition. It is a responsibility and traceability model, not an autonomous governance mechanism or permission system.

**中文。** 冻结的状态更新治理顺序仍是 Observation → Evidence → Update Proposal → Review / Assessment → State Transition。它是责任与可追溯关系模型，不是自治治理机制或权限系统。

## 11. Evaluation Framework / 评价框架

**English.** The evaluation design combines the [Reality Drift Benchmark](../benchmark/reality-drift-benchmark.md) with the [Dataset Specification](../dataset/reality-drift-dataset-spec.md). It compares external knowledge organization under a frozen base-model context; it does not compare the intrinsic capabilities of Marble, V-JEPA, JEPA-WMs, D4RT, Genie 3, or any spatial World Model.

**中文。** 评价设计综合 [Reality Drift Benchmark](../benchmark/reality-drift-benchmark.md) 与 [Dataset Specification](../dataset/reality-drift-dataset-spec.md)，在冻结的基础模型上下文中比较外部知识组织方式；它不比较 Marble、V-JEPA、JEPA-WMs、D4RT、Genie 3 或任何空间 World Model 的本体能力。

| Condition / 条件 | Visible update organization / 可见更新组织方式 | Boundary / 边界 |
|---|---|---|
| Frozen LLM<br>冻结语言模型 | `t0` snapshot only<br>仅 `t0` 快照 | Staleness baseline; no updates after `t0`.<br>陈旧基线；`t0` 后无更新。 |
| RAG<br>检索增强生成 | Versioned document retrieval<br>版本化文档检索 | Same source set as DCell; no persistent Cell record.<br>与 DCell 使用相同来源集；无持续 Cell record。 |
| DCell research condition<br>DCell研究条件 | Versioned Cell research record<br>版本化 Cell 研究记录 | Representation condition only; no extra facts or real DCell classification.<br>仅为表示条件；无额外事实或真实 DCell 分类。 |

**English.** Primary metrics are Drift Detection Macro-F1, Current State Exactness, Unsupported Claim Rate, Provenance Recall, and Conflict Preservation Rate. Secondary checks include false update proposals, correction recovery, temporal ordering, appropriate unknown or abstention behavior, silent overwrite, identity-boundary error, update lag, and separately reported resource costs. No composite leaderboard is defined, and no DCell win is presumed.

**中文。** 主要指标包括 Drift Detection Macro-F1、Current State Exactness、Unsupported Claim Rate、Provenance Recall 和 Conflict Preservation Rate。次要检查包括错误更新提议、更正恢复、时间排序、适当的未知或拒答、静默覆盖、身份边界错误、更新延迟，以及单独报告的资源成本。不定义综合排行榜，也不预设 DCell 获胜。

**English.** A comparison fails or stops if model or input conditions are not comparable, revisions or data digests cannot be frozen, the hidden ledger leaks, failures are deleted or silently retried, or execution requires real-world writes, automatic model updates, a Runtime, service, database, or external authority. The Benchmark does not evaluate spatial understanding, physical prediction, action planning, or world generation.

**中文。** 如果模型或输入条件不可比、revision 或数据 digest 无法冻结、hidden ledger 泄漏、失败输出被删除或静默重试，或者执行需要现实写入、自动模型更新、Runtime、服务、数据库或外部权威，则比较失败或必须停止。Benchmark 不评价空间理解、物理预测、动作规划或世界生成。

## 12. Falsifiability and Rejection Conditions / 可证伪性与拒绝条件

**English.** The frozen Benchmark specifies outcomes that would weaken or reject the DCell research hypothesis rather than protect it from adverse evidence.

**中文。** 冻结 Benchmark 指定了会削弱或拒绝 DCell 研究假设的结果，而不是让该假设免受不利证据影响。

1. RAG reaches the same or better primary outcomes at lower cost.<br>RAG 以更低成本达到相同或更好的主要结果。
2. Any DCell benefit comes from extra facts, more tokens, or manual correction rather than representation structure.<br>DCell 的任何收益来自额外事实、更多 token 或人工修正，而不是表示结构。
3. The DCell condition cannot reliably preserve sources, conflicts, unknowns, temporal order, or change history.<br>DCell 条件不能可靠保留来源、冲突、未知、时间顺序或变化历史。
4. Maintenance and governance cost exceeds the declared measurable benefit.<br>维护与治理成本超过声明的可测收益。
5. Results are unstable across prompt wording, scenario wording, or model revision.<br>结果对 prompt 表述、场景表述或模型 revision 不稳定。

**English.** Any such observation must be reported with execution context and failure records. It would weaken or reject the DCell research hypothesis for the tested scope; it must not be removed to preserve a favorable narrative.

**中文。** 任何此类观察都必须连同执行上下文和失败记录一起报告。它会在被测范围内削弱或拒绝 DCell 研究假设；不得为了保留有利叙事而删除。

## 13. Limitations and Threats to Validity / 局限与有效性威胁

**English.** The present artifact set has the following limitations and validity threats.

**中文。** 当前工件集合具有以下局限与有效性威胁。

- No Runtime, API, database, service, platform, Registry, or real Cell exists.<br>不存在 Runtime、API、数据库、服务、平台、Registry 或真实 Cell。
- No dataset instance, fixture, Runner, model call, Benchmark execution, or result exists.<br>不存在数据集实例、fixture、Runner、模型调用、Benchmark 执行或结果。
- The scope is semantic state synchronization only; physical reality synchronization, sensors, localization, and 4D reconstruction are excluded.<br>范围仅限语义状态同步；不覆盖物理现实同步、传感器、定位和 4D 重建。
- The project does not access a World Model's latent state, parameters, or internal cognition.<br>本项目不访问 World Model 的潜在状态、参数或内部认知。
- Schema conformance cannot establish source truth, semantic correctness, completeness, freshness, or safety.<br>Schema 合规不能建立来源真值、语义正确性、完整性、时效性或安全性。
- No external replication, statistical plan, comparative result, or scientific validation exists.<br>不存在外部复现、统计计划、比较结果或科学验证。
- The adjacent-work discussion is bounded by selected official sources and is not a systematic literature review.<br>相邻工作讨论受所选官方来源限制，不是系统性文献综述。

**English.** These limitations prevent claims of effectiveness, superiority, deployment readiness, standardization, certification, external adoption, or scientific validity. Whitepaper completeness is not implementation evidence.

**中文。** 这些限制阻止关于有效性、优越性、部署就绪、标准化、认证、外部采用或科学有效性的主张。白皮书完整性不是实现证据。

## 14. Bounded Research Agenda / 有界研究议程

**English.** The bounded agenda below compresses questions already present in [Research Questions v0.1](../research/research-questions.md), the [Reference Architecture](reality-synchronization-layer-reference-architecture-v0.1.md), the [Governance Model](../governance/dcell-governance-model-v0.1.md), and the [Benchmark](../benchmark/reality-drift-benchmark.md). It does not create a new architecture or protocol.

**中文。** 以下有界议程压缩自 [Research Questions v0.1](../research/research-questions.md)、[Reference Architecture](reality-synchronization-layer-reference-architecture-v0.1.md)、[Governance Model](../governance/dcell-governance-model-v0.1.md) 和 [Benchmark](../benchmark/reality-drift-benchmark.md) 中已有的问题，不创建新架构或协议。

- What minimum fields let an Agent recognize stale, conflicted, or unknown state without excessive structure?<br>哪些最小字段能让 Agent 识别陈旧、冲突或未知状态，同时避免过度结构化？
- Can independent reviewers reconstruct the basis of an assessment from observations, evidence references, time, and provenance?<br>独立复核者能否从观察、证据引用、时间和来源沿袭中重建评估依据？
- Under matched information and token budgets, does a Cell record differ measurably from versioned retrieval?<br>在匹配的信息量和 token 预算下，Cell record 与版本化检索是否存在可测差异？
- Can conflicts, unknowns, corrections, retractions, and identity boundaries be preserved consistently?<br>冲突、未知、更正、撤回和身份边界能否被一致保留？
- How should the five core roles remain separable and disclose role overlap without creating permissions?<br>五个核心角色如何保持可分离并披露角色重合，同时不创建权限？
- Does representation and governance cost exceed any measured benefit?<br>表示与治理成本是否超过任何可测收益？

**English.** This agenda excludes Cell economics, Cell evolution or reproduction, a Cell Marketplace, claims that billions of Cells form a World Model, artificial-life generalization, new protocols, and new platforms.

**中文。** 该议程排除 Cell 经济、Cell 进化或繁殖、Cell Marketplace、“亿万个 Cell 形成 World Model”的主张、人工生命泛化、新协议和新平台。

## 15. Current Status and Nonclaims / 当前状态与非声明

**English.** The following machine-readable block is the whitepaper's bounded status summary. Repository-wide current status remains governed by [STATUS.json](../STATUS.json).

**中文。** 以下机器可读区块是白皮书的有界状态摘要。仓库级当前状态仍由 [STATUS.json](../STATUS.json) 管理。

```text
WHITEPAPER_CREATED=true
WHITEPAPER_VERSION=0.1
WHITEPAPER_STATUS=RESEARCH_DRAFT
ARCHITECTURE_PHASE_CLOSED=true
SYNTHESIS_ONLY=true
CLAIM_BOUNDARY_FROZEN=true
CLAIM_BOUNDARY_VERSION=0.1
WORLD_MODEL_INTERNAL_STATE_ACCESS=false
SEMANTIC_SYNCHRONIZATION_SCOPE_ONLY=true
RUNTIME=false
API=false
DATABASE=false
RUNNER_IMPLEMENTED=false
MODEL_API_CALLED=false
BENCHMARK_EXECUTED=false
DCELL_SUPERIORITY_CLAIMED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
```

**English.** `WHITEPAPER_CREATED=true` means only that this synthesis document exists. It does not mean the candidate layer is implemented, the architecture is validated, a Benchmark was run, a result was obtained, a release was published, or an external party adopted the work.

**中文。** `WHITEPAPER_CREATED=true` 只表示本综合文档存在。它不表示候选层已经实现、架构已经验证、Benchmark 已运行、结果已获得、release 已发布或外部主体已经采用该工作。

## References / 参考文献

### Internal frozen artifacts / 内部冻结工件

1. [README.md](../README.md) — human entry and scope / 人类入口与范围。
2. [AGENTS.md](../AGENTS.md) — agent-readable rules and truth boundaries / 智能体可读规则与真值边界。
3. [STATUS.json](../STATUS.json) — only current repository status source / 唯一当前仓库状态源。
4. [agent-index.json](../agent-index.json) — machine discovery index / 机器发现索引。
5. [Research Scope v0.1](research-scope.md) — research scope and stop conditions / 研究范围与停止条件。
6. [Claims and Nonclaims](claims-and-nonclaims.md) — supported and unsupported claims / 可支持与不可支持主张。
7. [Architecture v0.1](architecture.md) — earlier bounded architecture description / 早期有界架构说明。
8. [Reference Architecture v0.1](reality-synchronization-layer-reference-architecture-v0.1.md) — frozen integration and claim boundary / 冻结综合与主张边界。
9. [Cell Schema v0.1](../schema/cell.schema.json) and [schema semantics](../schema/README.md) — record contract and interpretation boundary / 记录契约与解释边界。
10. [Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md) — comparison design and rejection conditions / 比较设计与拒绝条件。
11. [Reality Drift Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md) — scenario, event, transition, provenance, and leakage contract / 场景、事件、迁移、来源沿袭与泄漏契约。
12. [DCell Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) — five core roles and governance boundaries / 五个核心角色与治理边界。
13. [Research Questions v0.1](../research/research-questions.md) — questions and falsification criteria / 研究问题与可证伪条件。
14. [Research Source Manifest](../evidence/source-manifest.json) — source-relationship record / 来源关系记录。

### External official sources / 外部官方来源

1. World Labs. [Welcome to Marble](https://docs.worldlabs.ai/index) — official documentation for persistent 3D worlds / 持久 3D 世界的官方文档。
2. World Labs. [Announcing the World API](https://www.worldlabs.ai/blog/announcing-the-world-api) — official announcement of an API for explorable 3D worlds / 可探索 3D 世界 API 的官方公告。
3. Meta FAIR. [V-JEPA 2 official repository](https://github.com/facebookresearch/vjepa2) — official repository including V-JEPA 2.1 temporally consistent dense features / 包含 V-JEPA 2.1 时间一致稠密特征说明的官方仓库。
4. Meta FAIR. [JEPA-WMs official repository](https://github.com/facebookresearch/jepa-wms) — official implementation and pretrained models for physical-planning research / 面向物理规划研究的官方实现与预训练模型。
5. Google DeepMind. [D4RT: Teaching AI to see the world in four dimensions](https://deepmind.google/blog/d4rt-teaching-ai-to-see-the-world-in-four-dimensions/) — official research page for dynamic 4D reconstruction and tracking / 动态 4D 重建与追踪的官方研究页面。
6. Google DeepMind. [Genie 3: A new frontier for world models](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) — official page for interactive environment simulation / 交互环境模拟的官方页面。

**English.** The external set is intentionally limited to the six official sources required for the current boundary comparison. It is not a complete bibliography or evidence of uniqueness, superiority, adoption, or scientific validation.

**中文。** 外部来源集合被刻意限制为当前边界比较所需的六项官方来源。它不是完整参考文献，也不构成唯一性、优越性、外部采用或科学验证的证据。
