# dcell-reality-sync

`dcell-reality-sync` 是一个文档与 Schema（结构模式）优先的研究原型，用于研究：

> Reality Synchronization Layer for Agentic World Models
>
> 面向智能体世界模型的现实同步层。

核心研究问题是：当现实世界持续变化时，能否用有边界、可追溯、保留冲突与不确定性的
Cell 记录，帮助智能体识别其世界模型中的陈旧状态和现实偏差？

## Public Research Draft Status

This repository is a sanitized public research draft repository. It contains only the previously
verified sanitized commits plus this public-metadata reconciliation commit. It is public, but it has
no GitHub Release, no tag, no DOI, no Zenodo archive, no executed Benchmark, no scientific validation,
and no implementation authorization.

The repository is `joy7758/dcell-reality-sync`, its visibility is `PUBLIC`, its default branch is `main`,
and its sanitized public history contains exactly four commits. The source internal history and source
private commit email are not included. The current Whitepaper is v0.1.2 and remains a research draft.
The publication pipeline is closed and further push is not authorized. The next research stage is
`REALITY_DRIFT_BENCHMARK_PREREGISTRATION`.

Internal commit hashes retained in historical review files may not resolve in this single-root snapshot.
They record the internal research process only and do not describe this candidate's public Git history.

## 公开研究草案状态

本仓库是经过清理的公开研究草案仓库。它只包含此前验证的经清理提交，以及本次公开元数据对账提交。
仓库已公开，但尚无 GitHub Release、tag、DOI 或 Zenodo 归档，尚未执行 Benchmark，
尚未建立科学验证，也未获得实现授权。

仓库为 `joy7758/dcell-reality-sync`，visibility 为 `PUBLIC`，默认分支为 `main`，经清理的公开历史
恰好包含四笔提交。源内部历史与源私人提交邮箱均未包含。当前 Whitepaper 为 v0.1.2，状态仍为研究
草案。发布流程已经关闭，进一步 push 未获授权。下一研究阶段为
`REALITY_DRIFT_BENCHMARK_PREREGISTRATION`。

历史评审文件中的内部 commit hash 可能无法在本单根快照中解析；这些 hash 只记录内部研究过程，
不表示本候选的公开仓库历史。

## 当前定位

```text
PROJECT_ID=DCELL-REALITY-SYNC
PROJECT_STAGE=RESEARCH_PROTOTYPE_V0_1
ARTIFACT_KIND=DOCUMENTATION_AND_SCHEMA_ONLY
RUNTIME_IMPLEMENTED=false
API_CREATED=false
DATABASE_CREATED=false
PLATFORM_CREATED=false
REAL_WORLD_WRITE_CAPABILITY=false
WORLD_MODEL_IMPLEMENTED=false
REFERENCE_ARCHITECTURE_CREATED=true
WHITEPAPER_CREATED=true
WHITEPAPER_CURRENT_VERSION=0.1.2
WHITEPAPER_STATUS=RESEARCH_DRAFT_EDITORIALLY_CORRECTED_NOT_VALIDATED
IWR_REQUIRED_FINDINGS_CLOSED_COUNT=5
EDITORIAL_CORRECTIONS_APPLIED_COUNT=3
INDEPENDENT_REVISION_VERIFICATION_COMPLETED=true
INDEPENDENT_EDITORIAL_CORRECTION_VERIFICATION_COMPLETED=true
INDEPENDENT_EDITORIAL_CORRECTION_VERIFICATION_DECISION=PASS_FOR_PUBLIC_RESEARCH_RELEASE_REVIEW
PUBLIC_RESEARCH_RELEASE_REVIEW_COMPLETED=true
PUBLIC_RESEARCH_RELEASE_REVIEW_DECISION=PASS_WITH_REQUIRED_PUBLICATION_FIXES
PUBLIC_RELEASE_FIXES_APPLIED=true
LICENSE_STATUS=APACHE-2.0
PUBLIC_RELEASE_MANIFEST_STATUS=PUBLIC_RESEARCH_DRAFT_AVAILABLE_NOT_RELEASED
PUBLIC_SNAPSHOT_STATUS=PUBLIC_RESEARCH_DRAFT_AVAILABLE_NOT_RELEASED
PUBLIC_RESEARCH_DRAFT_AUTHORIZED=true
IMPLEMENTATION_AUTHORIZED=false
REMOTE_CONFIGURED=true
REMOTE_NAME=origin
REMOTE_REPOSITORY_FULL_NAME=joy7758/dcell-reality-sync
REMOTE_REPOSITORY_VISIBILITY=PUBLIC
INITIAL_PRIVATE_STAGING_PUSH_EXECUTED=true
GIT_COMMIT_COUNT=4
PUBLICATION_STATUS=PUBLIC_RESEARCH_DRAFT_AVAILABLE
RELEASE_STATUS=NOT_RELEASED
THIS_CANDIDATE_PUSH_AUTHORIZED=false
PUBLIC_VISIBILITY_SWITCH_AUTHORIZED=true
PUBLIC_VISIBILITY_SWITCH_EXECUTED=true
FINAL_PUBLIC_METADATA_PUSH_AUTHORIZED=true
FINAL_PUBLIC_METADATA_PUSH_EXECUTED=true
CANDIDATE_PUSH_SCOPE_CONSUMED=true
FURTHER_PUSH_AUTHORIZED=false
SOURCE_INTERNAL_HISTORY_INCLUDED=false
SOURCE_PERSONAL_COMMIT_EMAIL_INCLUDED=false
TAG_CREATED=false
RELEASE_CREATED=false
NEXT_GATE=PUBLICATION_PIPELINE_CLOSED
PUBLICATION_PIPELINE_CLOSED=true
NEXT_RESEARCH_STAGE=REALITY_DRIFT_BENCHMARK_PREREGISTRATION
ARCHITECTURE_PHASE_CLOSED=true
CLAIM_BOUNDARY_FROZEN=true
CLAIM_BOUNDARY_VERSION=0.1
WORLD_MODEL_INTERNAL_STATE_ACCESS=false
SEMANTIC_SYNCHRONIZATION_SCOPE_ONLY=true
BENCHMARK_EXECUTED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
```

本仓库当前只提供研究范围、候选架构、`Cell Schema v0.1`、合成示例、研究问题和治理边界。
它不实现自动采集、同步、推理、写回、模型更新、Agent Runtime 或平台。

冻结的限定定位是：

> **DCell explores an evidence-backed, temporally explicit, and governance-bounded semantic reality
> synchronization substrate for long-lived agents and world models.**
>
> **DCell 探索一种面向长期运行智能体和世界模型的、证据支撑、时间显式且具有治理边界的语义现实
> 同步底座。**

这里的 `Reality Synchronization` 仅指跨来源的 semantic state synchronization（语义状态同步），
不是物理现实同步、空间世界模型、传感器同步或动态场景重建的总称。

## Agent-readable 入口

- [Agent 入口与边界](AGENTS.md)
- [当前状态](STATUS.json)
- [机器入口](agent-index.json)
- [Apache License 2.0](LICENSE)
- [引用元数据](CITATION.cff)
- [公开发布清单](PUBLIC_RELEASE_MANIFEST.json)
- [研究来源清单](evidence/source-manifest.json)
- [研究范围](docs/research-scope.md)
- [架构文档](docs/architecture.md)
- [Reality Synchronization Layer Reference Architecture v0.1](docs/reality-synchronization-layer-reference-architecture-v0.1.md)
- [Reality Synchronization Layer Whitepaper v0.1.2](docs/reality-synchronization-layer-whitepaper-v0.1.2.md) — current research draft / 当前研究草案，`RESEARCH_DRAFT_EDITORIALLY_CORRECTED_NOT_VALIDATED`
- [Reality Synchronization Layer Whitepaper v0.1.1](docs/reality-synchronization-layer-whitepaper-v0.1.1.md) — historical reviewed revision / 历史评审修订稿
- [Reality Synchronization Layer Whitepaper v0.1](docs/reality-synchronization-layer-whitepaper-v0.1.md) — historical research draft / 历史研究草案
- [Independent Whitepaper Review v0.1](evaluation/independent-whitepaper-review-v0.1.md) — revision basis / 修订依据
- [Independent Whitepaper Revision Verification v0.1](evaluation/independent-whitepaper-revision-verification-v0.1.md) — editorial correction basis / 编辑修正依据
- [Independent Editorial Correction Verification v0.1](evaluation/independent-editorial-correction-verification-v0.1.md) — `PASS_FOR_PUBLIC_RESEARCH_RELEASE_REVIEW`
- [Public Research Release Review v0.1](evaluation/public-research-release-review-v0.1.md) — `PASS_WITH_REQUIRED_PUBLICATION_FIXES`
- [Independent Publication Fix Verification v0.1](evaluation/independent-publication-fix-verification-v0.1.md) — preparation basis / 准备依据
- [Cell Schema v0.1](schema/cell.schema.json)
- [Schema 语义与边界](schema/README.md)
- [合成示例](examples/synthetic-reality-cell.json)
- [Reality Drift Benchmark v0.1 设计](benchmark/reality-drift-benchmark.md)
- [Reality Drift Dataset Specification v0.1](dataset/reality-drift-dataset-spec.md)
- [DCell Governance Model v0.1](governance/dcell-governance-model-v0.1.md)
- [复用、重叠与所有权审查](governance/reuse-overlap-ownership-review.md)
- [预开发智能体推荐闸门](governance/agent-recommendation-gate.json)
- [声明与非声明](docs/claims-and-nonclaims.md)

本仓库中的 “Independent / 独立” 仅表示项目内部不同 Codex 会话之间的流程独立，不表示外部同行
评审、机构认可、客户验证或生态采用。

## License / 许可证

Unless otherwise stated, the original contents of this repository, including documentation, JSON Schema,
metadata files, and synthetic examples, are licensed under the Apache License, Version 2.0.

除非另有明确说明，本仓库的原创内容，包括文档、JSON Schema、元数据文件和合成示例，均采用
Apache License, Version 2.0 授权。

外部链接及其内容仍受各自权利主体的条款约束。本仓库未复制外部论文或官方文档全文；本许可证不会
把外部来源内容转化为项目自有内容。

## Public history boundary / 公开历史边界

The public repository contains a sanitized history only. The source
internal repository history and personal commit email are not included.
The repository is public, but it remains a research draft: no tag,
GitHub Release, DOI, Zenodo archive, executed Benchmark, scientific
validation, or implementation authorization exists. This metadata
reconciliation closes the publication pipeline. Further push remains
unauthorized unless a new research task requires an exact, separately
approved change.

本公开仓库只包含经过清理的历史，不包含源内部仓库历史和私人提交邮箱。
仓库已经公开，但仍只是研究草案：不存在 tag、GitHub Release、DOI、
Zenodo 归档、已执行 Benchmark、科学验证或实现授权。
本次元数据对账完成后，发布流程关闭。除非新的研究任务确有需要并获得
单独精确授权，否则不再继续 push。

## 候选数据流

```text
现实来源引用
  -> 带时间与来源的 Observation（观察）
    -> Claim / Evidence Link（主张／证据引用）
      -> Cell State Projection（Cell 状态投影）
        -> Staleness / Divergence Assessment（陈旧／偏差评估）
          -> 更新建议
            -> 外部授权决定
```

最后一步只产生建议。任何真实世界写入、世界模型更新或外部行动都不属于本原型。

## 目录结构

```text
.
├── AGENTS.md
├── CITATION.cff
├── LICENSE
├── PUBLIC_RELEASE_MANIFEST.json
├── README.md
├── STATUS.json
├── agent-index.json
├── docs/
│   ├── architecture.md
│   ├── claims-and-nonclaims.md
│   ├── reality-synchronization-layer-reference-architecture-v0.1.md
│   ├── reality-synchronization-layer-whitepaper-v0.1.md
│   ├── reality-synchronization-layer-whitepaper-v0.1.1.md
│   ├── reality-synchronization-layer-whitepaper-v0.1.2.md
│   └── research-scope.md
├── schema/
│   ├── README.md
│   └── cell.schema.json
├── examples/
│   └── synthetic-reality-cell.json
├── benchmark/
│   └── reality-drift-benchmark.md
├── dataset/
│   └── reality-drift-dataset-spec.md
├── research/
│   └── research-questions.md
├── evaluation/
│   ├── README.md
│   ├── independent-editorial-correction-verification-v0.1.md
│   ├── independent-publication-fix-verification-v0.1.md
│   ├── independent-whitepaper-review-v0.1.md
│   ├── independent-whitepaper-revision-verification-v0.1.md
│   └── public-research-release-review-v0.1.md
├── evidence/
│   └── source-manifest.json
├── governance/
│   ├── agent-recommendation-gate.json
│   ├── dcell-governance-model-v0.1.md
│   └── reuse-overlap-ownership-review.md
└── validation/
    └── README.md
```

## 研究边界

- `Cell Schema v0.1` 是研究交换工件，不是 DCell Core 的修改。
- Schema 通过只证明 JSON 结构符合当前候选约束，不证明记录真实、完整或最新。
- `cell_id` 是本仓库的研究标识，不是 DBOS `entity_id`、外部注册标识或真实 Cell 身份。
- `evidence_refs` 是证据材料引用，不是已验证事实、科学证据或认证。
- `synchronization_assessment` 是有来源的评估记录，不会自动更新世界模型或现实系统。
- `world_model_projection` 只表示外部声明且可观察的状态投影，不是神经网络潜变量、模型参数读取、
  模型内部认知状态或自动模型更新接口。
- Reality Drift Benchmark 只研究外部状态表示与更新组织方式，不评价空间理解、物理预测、动作规划
  或世界生成能力。

## 当前研究架构

Reality Synchronization Layer Reference Architecture v0.1 已将 Cell Schema、Reality Drift Benchmark、
Dataset Specification 和 Governance Model 统一到冻结的研究架构。Reality Synchronization Layer
Whitepaper v0.1 原稿保持不变。Whitepaper v0.1.1 以 Independent Whitepaper Review v0.1 为修订依据，
五项 IWR 必要发现已经由独立修订验证确认为关闭。Whitepaper v0.1.2 仅应用 E-01、E-02、E-03 三项
章节编号、来源版本归属和术语限定编辑修正；v0.1 与 v0.1.1 均保留。v0.1.2 状态为
`RESEARCH_DRAFT_EDITORIALLY_CORRECTED_NOT_VALIDATED`。独立编辑修正验证结论为
`PASS_FOR_PUBLIC_RESEARCH_RELEASE_REVIEW`；公开研究发布审查结论为
`PASS_WITH_REQUIRED_PUBLICATION_FIXES`。这些结论不构成公开研究草案、发布或实现授权。

本仓库当前仅是经清理的公开研究草案，未创建 tag、GitHub Release、DOI 或 Zenodo 归档。当前下一
gate 仅为 `INDEPENDENT_PUBLIC_REPOSITORY_POST_SWITCH_VERIFICATION_ONLY`。在新的明确授权前不继续
push、不实现架构组件、不生成 Dataset、不运行 Benchmark、不调用模型，也不形成 DCell 优越性或
科学验证主张；当前状态不是 GitHub Release，scientific validation 仍未建立，实现仍未授权。
