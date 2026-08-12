---
review_id: INDEPENDENT-WHITEPAPER-REVIEW-v0.1
review_target: REALITY-SYNCHRONIZATION-LAYER-WHITEPAPER-v0.1
artifact_kind: INDEPENDENT_RESEARCH_REVIEW
status: COMPLETED
created_at: 2026-08-11T19:32:24Z
review_mode: FRESH_CONTEXT_INDEPENDENT_REVIEW
whitepaper_modified: false
architecture_modified: false
benchmark_executed: false
scientific_validation: NOT_ESTABLISHED
---

# Independent Review of Reality Synchronization Layer Whitepaper v0.1

# 现实同步层白皮书 v0.1 独立评审

## 1. Review Scope and Independence

## 评审范围与独立性

本评审在一个新的 Codex 会话中完成。评审者未参与本轮白皮书修改，不预设 DCell 成立、具有创新性，
也不接受“现实同步层是缺失层”作为前提。作者期状态文件、推荐门和架构说明均被视为待核验工件，
不作为独立结论的替代品。

评审对象仅为当前 `v0.1`、当前仓库工件和本报告列出的外部官方／原始来源。评审不评价尚不存在的
Runtime、Dataset instance、Fixture、Runner、模型调用或实验结果；未执行 Benchmark，未修改白皮书、
参考架构、Schema、Benchmark、Dataset Specification 或 Governance Model。

评审问题是：白皮书是否提出一个可独立重建、可被不利结果削弱、值得实验的问题；以及当前工件是否
足以把它与 versioned RAG、temporal knowledge graph、event sourcing、provenance-aware systems、
digital twin 和 agent memory 区分开。文档数量、双语配对数量、静态检查通过和边界声明严格程度均不
被当作研究贡献或科学证据。

## 2. Reviewed Artifact Inventory

## 已审工件清单

审查基线为 Git `24ec4c114cc36560866be7f9cc6470b07029d574`。下表列出所有完整读取的仓库工件；
digest 为审查开始时文件内容的 SHA-256。

| artifact | SHA-256 |
|---|---|
| [AGENTS.md](../AGENTS.md) | `5a6f7da49e01d71f7dfff6f651665a004b3ecd4fa7ab2ad166d2d6093e83c7fd` |
| [STATUS.json](../STATUS.json) | `bb823834ed69b24dd71a4d79d050fe40b731cac6bb569e99ddd49f37d0b8421b` |
| [README.md](../README.md) | `a28e01d7f0c4fc2a50e4263017e745f179c13d96e62df5e4c66229934d32a024` |
| [agent-index.json](../agent-index.json) | `982fb9c12aeadf440a6a1313304ffa9d4a6aa8ecbf1820e9a7834c5ff156a5a3` |
| [docs/research-scope.md](../docs/research-scope.md) | `88ab76fdf7f03c989328b1b9af3147e2ce9b3fc174cf2fc419e369cde9c96f4b` |
| [docs/architecture.md](../docs/architecture.md) | `5b21d2dbbb6b982471e7268d82fa4385f615bec0b78b131a062402f6527ea19e` |
| [governance/reuse-overlap-ownership-review.md](../governance/reuse-overlap-ownership-review.md) | `75e0f5c67aca4e579e1b7d9648461ca7ca71ccea068038812811858ecd15d9c7` |
| [governance/agent-recommendation-gate.json](../governance/agent-recommendation-gate.json) | `382fae969e559119682e928f966ccbec609b82ae65e5513182aa66899cfbe911` |
| [schema/README.md](../schema/README.md) | `7ec4ba286642a7e22d2756791d035e3e71cde2e4a6cde17191941e763fc581f3` |
| [schema/cell.schema.json](../schema/cell.schema.json) | `4f3625a3b47a3230c27a29026e32228315d61763eed357abeec09e3f3e614fe1` |
| [docs/claims-and-nonclaims.md](../docs/claims-and-nonclaims.md) | `485249a0e8d4f8a183ddb23c4747f2cea2aa870397a99892ab86c0612a222286` |
| [evidence/source-manifest.json](../evidence/source-manifest.json) | `5471e5d6dd9c281de2131704478f5eef4aacb90cf7489400813c8097be720c26` |
| `governance/dba-filing-candidate.json` (excluded internal candidate; not included in the sanitized public snapshot / 已排除的内部候选工件；不包含于经清理的公开快照) | `9ed62c6e2f1cbc5b0455d03dc16e2595a18ff83d67d5c81046a7b30a86c9ef1c` |
| [whitepaper v0.1](../docs/reality-synchronization-layer-whitepaper-v0.1.md) | `dcacec7115798988c27501edf9b9a4ddd36e35eb36a7675eb803ce2cef46078e` |
| [reference architecture v0.1](../docs/reality-synchronization-layer-reference-architecture-v0.1.md) | `2a6e64a14595257d1260db4b528059126da42b2b9b71c5ff6c582fdcbeb4d17e` |
| [Reality Drift Benchmark v0.1](../benchmark/reality-drift-benchmark.md) | `e268a8c4a9d0503d138c4bf8f5546930306a2ee2b0148ea901c45e8ad0896be2` |
| [Reality Drift Dataset Specification v0.1](../dataset/reality-drift-dataset-spec.md) | `0882596d42f68b2064fec5f46ca6dfcca5225f6bf32262eb9b072fa51fd5733b` |
| [DCell Governance Model v0.1](../governance/dcell-governance-model-v0.1.md) | `97fdc077af59208f924e7c56e202f2ff04b39ffd4957dfd6fcf41ed9afb7886b` |
| [research/research-questions.md](../research/research-questions.md) | `1b055a5f5978aca02ad735ed618aee4e6a8e23e728631077e90dca68fe225681` |

白皮书审查前 Git blob 为 `f75835bb2aab44e18bd9f95bf9d5383d30398a90`；参考架构审查前 Git blob
为 `73a1681a6414214443b9870bcfde9242d8795e58`。

## 3. Whitepaper Contribution Reconstruction

## 白皮书贡献重建

### 3.1 研究问题

在基础模型、可见来源、时间点、问题和 token budget 匹配的条件下，一个显式保存对象身份、来源、
时间、状态历史、冲突、未知和同步评估的版本化记录，是否比版本化文档检索更可靠地识别外部可观察
语义状态的陈旧、变化与冲突，并允许独立复核其依据？

### 3.2 候选解释或假设

候选解释是：相对于只检索文档，预先把同一批可见材料组织为持续对象记录，可能降低错误对象归并、
旧结论复用、冲突丢失、无来源主张和无痕覆盖，同时代价是额外的构建、维护和治理成本。

### 3.3 新增的研究表示

当前新增工件是一个项目本地、版本化的 JSON record profile：identity、reality target、sources、
observations、claims、evidence references、两个外部状态投影、history、conflicts、uncertainties、
synchronization assessment、non-executable update proposal、truth boundaries 和全部为 `false` 的
authorization 字段。

这是一项可检查的领域组合，但当前证据不能证明这些字段或其组合构成新的通用数据模型。最可信的
候选贡献是围绕该组合形成的有界研究问题、失败模式和比较设计，而不是字段集合本身。

### 3.4 如何被证伪

白皮书列出的拒绝方向包括：RAG 以更低成本达到相同或更好结果；DCell 收益来自额外事实、更多 token
或人工修正；记录不能稳定保留来源、冲突、未知、时序和历史；维护成本超过收益；结果随 prompt、
场景或模型 revision 不稳定。

这些方向具有可证伪意图，但尚未形成完全可执行的 decision rule，因为“相同或更好”“成本更低”
和“不稳定”缺少预注册阈值、效应量、样本量和跨指标裁决规则。当前只能称为 candidate rejection
conditions，而不能称为已经操作化的证伪协议。

### 3.5 当前有什么证据

- 白皮书、参考架构、Schema、Benchmark、Dataset Specification 和 Governance Model 的定义性与
  设计性证据；
- 可检查的 JSON Schema 约束和静态状态边界；
- 六项官方来源对相邻空间／物理 world-model 能力边界的支持；
- 明确的不利结果保留、hidden-ledger 隔离和信息可见性约束。

### 3.6 当前没有什么证据

- 没有 Dataset、Fixture、Runner、模型调用、Benchmark 结果、统计计划或独立复现；
- 没有 DCell 相对 RAG、temporal knowledge graph、event sourcing、provenance-aware system、
  digital twin 或 agent memory 的实证优势；
- 没有证明 `Semantic Reality Drift` 是新发现的科学现象或 `DCell Research Representation` 是新的
  通用结构；
- 没有与 World Model 的实际集成、内部状态访问或长期 Agent 使用证据；
- 没有科学验证、外部采用、DBA 准入、发布、部署或实现授权。

## 4. Claim-to-Artifact Traceability

## 主张到工件的可追溯性

| claim_id | 白皮书主张 | 支撑内部工件 | 支撑类型 | 是否充分 | 问题 |
|---|---|---|---|---|---|
| C-01 | Reality Drift 是 `t0` 投影与 `t1...tn` 有来源观察的可描述差异 | Benchmark §2；Dataset §3 | DEFINITIONAL_SUPPORT | 是，仅对项目定义 | 没有证据证明术语或现象新颖 |
| C-02 | Reality Synchronization Layer 是来源与外部 consumer 之间的候选层 | Reference Architecture §§3-4 | DESIGN_SUPPORT | 是，仅对概念架构 | 不是已实现数据流或必要基础设施 |
| C-03 | DCell Research Representation 组织身份、来源、观察、主张、状态、历史、冲突和评估 | Cell Schema；schema README | DESIGN_SUPPORT | 部分 | Schema 未显式实现 Dataset 中的完整 Event 和 StateTransition |
| C-04 | `world_model_projection` 只指外部声明且可观察的投影 | Cell Schema `state`；Reference Architecture §9 | DEFINITIONAL_SUPPORT | 是 | 不支持任何内部模型状态或集成主张 |
| C-05 | Evidence 不等于 Truth，Provenance 不等于 Correctness | Schema `truth_boundaries`；Dataset §6；Governance §6 | DEFINITIONAL_SUPPORT | 是 | 属边界定义，不是效果证据 |
| C-06 | 旧状态、更正、撤回、冲突和未知可通过迁移与历史保留 | Dataset §§4-6；Governance §5 | DESIGN_SUPPORT | 部分 | Dataset 是概念契约；Schema 没有 first-class transition record |
| C-07 | 五个治理角色描述责任，不创建权限 | Governance §§3-5 | DESIGN_SUPPORT | 是，仅对角色词汇 | 未验证多主体治理可行性 |
| C-08 | Benchmark 以 Frozen LLM、RAG、DCell research 三组检验表示差异 | Benchmark §§3-10 | DESIGN_SUPPORT | 部分 | Frozen LLM 只是陈旧负控；RAG/DCell builder parity 尚未冻结 |
| C-09 | 研究假设可由不利结果削弱或拒绝 | Benchmark §11；Whitepaper §12 | DESIGN_SUPPORT | 部分 | 缺少可执行阈值、统计计划与跨指标裁决规则 |
| C-10 | 当前无 Runtime、模型调用、Benchmark 结果或科学验证 | STATUS；Claims and Nonclaims；Whitepaper §§2,13,15 | DEFINITIONAL_SUPPORT | 是 | 状态边界清楚，不构成贡献证据 |
| C-11 | 六项外部工作主要覆盖 3D persistence、dense temporal features、planning、4D tracking 和 simulation | Whitepaper §4；source manifest | EXTERNAL_SOURCE_SUPPORT | 是，对表内有限描述 | 不能据此推导语义状态同步的全球空白 |
| C-12 | DCell 表示能帮助检测漂移和改善可审计性 | Research Questions；Benchmark | UNSUPPORTED | 否 | 当前是待测假设，没有 EMPIRICAL_SUPPORT |

当前没有任何白皮书实质性效果主张获得 `EMPIRICAL_SUPPORT`。

## 5. Novelty and Differentiation Assessment

## 新颖性与差异化评估

### 5.1 Semantic Reality Drift 是否构成独立、可测研究问题

构成一个独立、可测的任务定义，但尚不构成已证明的新科学现象。它把陈旧状态、来源更正、冲突、
不可达、乱序和未知放入一个统一的外部语义状态评估任务；这些现象分别早已存在于版本控制、事件溯源、
provenance 和知识图谱系统中。研究价值在于：对长期 Agent 使用同一基础模型时，显式记录结构是否在
匹配信息条件下改变失败率。术语 `Reality Drift` 本身没有得到新颖性证据。

### 5.2 与六类相邻方向的差异

| 相邻方向 | 当前 DCell 候选增量 | 独立评审判断 |
|---|---|---|
| versioned RAG | 持续对象身份、显式状态投影、冲突对象、历史和非执行 assessment | 可形成消融条件；但 versioned corpus 也可携带相同字段，差异可能来自预处理而不是新机制 |
| temporal knowledge graph | 显式 truth/authorization 边界、同步评估和角色责任 | 时间限定实体、声明、引用和 unknown/deprecated 不是 DCell 独有；当前没有直接相关工作对照 |
| event sourcing | 来源／证据绑定、unknown/conflicted 状态和外部投影比较 | 事件序列、历史重建、更正、乱序处理与 temporal query 已是 event sourcing 核心能力 |
| provenance-aware systems | task-specific drift assessment、coverage/freshness 和 update proposal | entities、agents、responsibility、derivation、generation/invalidation 和版本来源沿袭已有成熟模型 |
| digital twin | 强制非物理、非控制、非 Truth 的语义记录边界 | 白皮书未给出原始来源对照，无法证明对象状态投影和现实关联表示的增量 |
| agent memory | 外部、可审计、治理有界且不访问内部 memory | 白皮书未给出原始来源对照，也未测试 Agent 是否能更好使用该记录 |

三项直接削弱“字段组合天然新颖”的高相关来源是：

1. [W3C PROV-DM](https://www.w3.org/TR/prov-dm/) 已定义 Entity、Activity、Agent、responsibility、
   derivation、generation、invalidation、版本与 provenance-of-provenance；它还明确处理随时间变化的
   对象描述和不同来源观点。
2. [Wikidata Data Model](https://www.wikidata.org/wiki/Wikidata%3AData_model/en) 已提供稳定实体、
   statements、qualifiers、references、normal/preferred/deprecated rank、unknown/no value 和时间限定。
3. [Martin Fowler 的 Event Sourcing 原始说明](https://martinfowler.com/eaaDev/EventSourcing.html) 已把
   状态变化保存为事件序列，并支持完整重建、temporal query、错误事件修正和乱序事件重放。

这些来源不证明 DCell“没有价值”，但表明 `identity + time + evidence + state + governance` 更像
对已有模式的领域组合。当前最可能成立的原创贡献，是一个面向长期 Agent 外部语义状态的、强调冲突／
未知保留和不利结果的评价问题；最容易被现有研究吸收的，是 Cell Schema 的字段集合、事件历史和
provenance 链。

即使结构是组合，该组合仍产生了：

- 一个可检验问题：结构化外部对象记录与 versioned retrieval 是否在匹配条件下不同；
- 一个候选实验条件：DCell record versus versioned documents；
- 一组明确失败模式：silent overwrite、identity-boundary error、conflict loss、unsupported claim、
  correction failure；
- 一组有方向的不利预测：RAG 同等或更好且更便宜、收益来自额外信息、结果对 revision 不稳定。

但最后一项尚未操作化为可执行阈值，因此只能支持 `PASS_WITH_REQUIRED_REVISIONS`，不能支持未经修订
的公开研究草案或创新性主张。

### 5.3 六项指定外部来源核验

| 来源 | 核验结果 | 对白皮书定位的影响 |
|---|---|---|
| [World Labs Marble](https://docs.worldlabs.ai/index) | `PASS`：官方描述 high-fidelity persistent 3D worlds，并说明 reconstruct/generate/simulate 3D worlds | 白皮书“persistent 3D worlds”准确；不支持语义同步唯一性 |
| [World Labs World API](https://www.worldlabs.ai/blog/announcing-the-world-api) | `PASS`：官方描述从文本、图像、视频生成可探索 3D worlds 的公共 API | 白皮书没有把该产品 API 误写成本项目能力 |
| [Meta FAIR V-JEPA 2.1](https://github.com/facebookresearch/vjepa2) | `PASS`：官方仓库明确 high-quality and temporally consistent dense features | 白皮书准确限制为 learned representation 边界；该仓库同时覆盖 understanding/prediction/planning，但未直接主张跨来源语义同步 |
| [Meta FAIR JEPA-WMs](https://github.com/facebookresearch/jepa-wms) | `PASS`：官方仓库和论文标题明确 physical planning with Joint-Embedding Predictive World Models | 白皮书“environment prediction and physical planning”未被提升为语义同步结论 |
| [Google DeepMind D4RT](https://deepmind.google/blog/d4rt-teaching-ai-to-see-the-world-in-four-dimensions/) | `PASS`：官方页明确 unified 4D scene reconstruction and tracking across space and time | 官方也使用 persistent representation of reality 的动机语言，但技术对象仍是动态 4D 物理场景；白皮书不应据此声称“persistence”是空白 |
| [Google DeepMind Genie 3](https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/) | `PASS`：官方页明确 interactive world simulation、action-conditioned evolution、数分钟一致性和 promptable world events | 白皮书的 simulation 边界准确；promptable events 说明“event/state change”也非 DCell 独有，但不等于现实来源同步 |

未发现六项来源被重大误述，也未发现产品能力被写成白皮书的实证结论。关键缺口不是这六项表述错误，
而是它们与白皮书真正要主张的 semantic/provenance/temporal record contribution 不同轴。

## 6. World-Model Positioning Review

## 世界模型定位审查

白皮书在实质边界上保持一致：DCell 不是 World Model，不访问 latent state、参数或 internal cognition，
不评价空间理解、物理预测、规划和世界生成，只研究外部声明且可观察的语义状态投影。未发现与这些
边界直接矛盾的句子。

| 表述 | 潜在隐性扩张 | 当前缓解 | 评审 |
|---|---|---|---|
| `for long-lived agents and world models` | 可能暗示已经与 World Model 集成 | 摘要、§§2,7,13,15 明确无 model call 或 integration | 边界保持，但公开版宜在标题附近加 `candidate external record framework` |
| `world_model_projection` | 可能暗示读取内部表示 | §7 明确定义为 externally declared and observable | 无实质突破 |
| `Reality Synchronization Layer` | 可能覆盖物理／传感器同步 | §4、局限与 README 明确 semantic only | 无实质突破，但名称仍需要紧邻限定词 |
| `substrate` | 可能暗示必要基础设施或已建立底座 | 有效动词限定为 `explores`，并否定 missing-layer claim | 风险未完全消失；应避免把候选记录 profile 写成既成底座 |
| `World Model Interface` | 可能暗示 API 或协议 | 参考架构 §9 明确 conceptual read/proposal boundary | 无实质突破 |

结论：world-model 边界在正文中合格；风险来自标题和 `substrate` 的读者第一印象，而不是内部状态访问
或能力冒领。

## 7. Benchmark and Falsifiability Review

## 基准与可证伪性审查

- **Frozen LLM：**它只是没有 `t1...tn` 更新通道的陈旧负控，不是与两个更新条件公平竞争的方法。
  Benchmark 已明确分层报告，因此该点不是阻断。
- **事实和时间可见性：**RAG 与 DCell 被要求使用相同原始来源和时间点，方向正确；Frozen LLM
  故意只见 `t0`。
- **Token budget：**三组上限相同，但“相同上限”不保证信息表达等价。结构化 Cell 可能把人工解析、
  冲突识别或状态标签预先编码进输入；RAG 可能为原始片段支付额外 token。
- **Builder leakage：**hidden ledger 明确禁止进入 Cell builder，但 builder 的确定性规则、作者隔离、
  字段推导审计和与 RAG 的 transformation parity 尚未冻结。仅记录 builder version 不足以排除标签
  泄漏或人工语义增益。
- **指标偏向：**Conflict Preservation、Provenance Recall、Silent Overwrite 和 Identity Boundary
  正好对应 Cell 的显式字段；这些是合理任务指标，但必须允许 RAG 使用同一输出结构，并报告字段化
  预处理成本，否则会把 representation availability 当成模型能力。
- **维护成本：**已列 token、存储、预处理、人工标注、冲突裁决和延迟，但没有统一计量方案或拒绝阈值。
- **Prompt/model drift：**设计要求冻结 provider、resolved ID、prompt、参数和 digest，并在无法冻结时
  标记 `EXECUTION_CONTEXT_DRIFT`；该控制合理，但尚未执行。
- **拒绝条件：**方向上允许保留不利结果，但缺少 non-inferiority margin、成本阈值、样本量、统计检验
  和多指标冲突裁决，因此尚未“真实可执行”。
- **不利结果：**文档明确要求保留失败、错误、重试和 exclusions，不允许为有利叙事删除，边界合格。

**Benchmark 尚未实现和执行。** 当前没有 Fixture、Runner、model call、score、winner 或 scientific
validation。

## 8. Governance and Authority Boundary Review

## 治理与权威边界审查

下列关系在白皮书、Governance Model、Schema 和 STATUS 中保持一致：

```text
Role != Permission
Ownership != Reality Object Ownership
Evidence != Truth
Provenance != Correctness
Evaluation != Authority
```

未发现其他章节把 Owner 写成现实对象所有者，把 Evidence Provider 写成 Evidence authority，把
Evaluator 写成决策者，或把 assessment/proposal 写成授权或执行。`application_authorized=false` 在
Schema v0.1 中为常量；所有执行授权字段为 `false`。

需要澄清的一点是：Governance Model 的 `Review / Assessment -> State Transition` 只表示本地研究记录
的候选版本变化，不是外部模型或现实写入。正文已有这一限制，但公开版本应继续保留在流程图附近，
避免读者把“review 后迁移”误读为自动权限链。

## 9. Bilingual Semantic Equivalence

## 双语语义等价性

抽查覆盖摘要、核心定位、Reality Drift、candidate layer、world-model projection、Evidence/Truth、
governance、Benchmark、falsifiability、limitations 和 status。关键限定词对应稳定：

| English | 中文 | 评审 |
|---|---|---|
| explores | 探索 | 强度等价 |
| candidate | 候选 | 强度等价 |
| representation | 表示 | 未被提升为实现 |
| assessment | 评估 | 未被提升为决定 |
| proposal | 建议／提议 | 未被提升为命令 |
| observable | 可观察 | 范围保留 |
| governance-bounded | 具有治理边界 | 范围保留 |
| semantic state synchronization | 语义状态同步 | 未扩张为物理同步 |

未发现中文比英文更强、英文比中文更强、关键否定丢失或 `candidate/explores` 限定词消失。

```text
NO_MATERIAL_BILINGUAL_SEMANTIC_DRIFT_FOUND
```

## 10. Substance-versus-Guardrail Assessment

## 实质贡献与边界声明比例评估

1. **两分钟内能否知道研究问题：**能。摘要、§3 和 §5 足以识别“长期 Agent 使用陈旧外部语义状态”
   的问题。
2. **能否说出候选机制：**能，但只能说出高层机制：版本化对象记录加 freshness/divergence/coverage
   assessment；不能说出已验证机制。
3. **能否知道怎样实验：**能知道三组条件和主要指标，但不能得到可执行的 builder protocol、统计计划
   和判定阈值。
4. **边界是否多于实质论证：**是。§§2,4,6,7,9,10,13,15 重复 Runtime/API/model-write/
   scientific-validation 非声明，降低了正面贡献的可见度。
5. **可压缩内容：**保留摘要附近的一次核心非声明、§13 limitations 和 §15 machine status；将其他章节
   的重复状态列表压缩为局部、与该章节风险直接相关的边界。不能删除 Evidence/Truth、assessment/
   authorization 和 internal/external model state 三个核心区分。

当前读者能找到研究问题，但很可能先记住“它不是什么”，而不是“它提出了哪一个可区分预测”。公开
修订版应在前两节增加一个短的 `Claimed contribution / Not claimed` 对照，并把原创候选明确限制为研究
问题、评价条件和失败模式。

## 11. Findings

## 评审发现

### FINDING_ID: IWR-001

**SEVERITY:** MAJOR

**LOCATION:** Whitepaper §§4-5, §14 and References; Research Questions RQ1

**OBSERVATION:** 六项外部来源只覆盖空间／物理 World Model 边界，而白皮书的新增结构主张位于
versioned RAG、temporal knowledge graph、event sourcing、provenance-aware systems、digital twin
和 agent memory 的交叉区。当前没有同轴相关工作定位。

**WHY_IT_MATTERS:** 不能从“六个 spatial/physical 项目没有明确描述 DCell”推导 DCell 表示新增了
独立结构。W3C PROV、Wikidata 和 Event Sourcing 已直接覆盖身份、时间、来源沿袭、版本、废弃／未知、
事件历史与重建等主要元素。

**SUPPORTED_BY:** Whitepaper §4；W3C PROV-DM；Wikidata Data Model；Event Sourcing。

**REQUIRED_ACTION:** 在白皮书 v0.1.1 中加入有界、同轴的相关工作定位，把潜在贡献收窄为可检验问题、
评价条件和失败模式；不得声称字段集合、Reality Drift 术语或“同步底座”具有已证明的唯一性。

### FINDING_ID: IWR-002

**SEVERITY:** MAJOR

**LOCATION:** Whitepaper §12; Benchmark §§9,11

**OBSERVATION:** 拒绝条件有方向但没有可执行阈值；`same or better`、`lower cost`、`significantly` 和
`unstable` 未绑定效应量、置信区间、样本量、成本计量或跨指标 decision rule。

**WHY_IT_MATTERS:** 没有预先可执行的拒绝规则，未来任何结果都可能被事后解释为“仍值得继续”，这会
削弱白皮书最重要的可证伪性主张。

**SUPPORTED_BY:** Benchmark §§8-11 明确统计计划尚待预注册；STATUS 标记 Benchmark 未执行。

**REQUIRED_ACTION:** 公开修订版必须把现状表述为 `candidate rejection conditions pending
preregistration`；若不在本轮定义阈值，不得声称已有完全操作化的 falsification protocol。

### FINDING_ID: IWR-003

**SEVERITY:** MAJOR

**LOCATION:** Whitepaper §11; Benchmark §§4-5,10; Dataset §§7-8

**OBSERVATION:** RAG 和 DCell 的原始来源／时间可见性约束相同，但 DCell builder 如何从来源生成显式
state、conflict、uncertainty 和 assessment 尚未冻结。builder version 与 hidden-ledger 禁令不能单独
证明 transformation parity，也不能排除人工标签增益。

**WHY_IT_MATTERS:** 如果 DCell 输入提前包含由场景作者解释的正确状态或冲突标签，实验测到的是额外
人工结构化信息，而不是 representation 的独立价值。

**SUPPORTED_BY:** Benchmark §4 的公平矩阵、§5 builder version 要求、§10 leakage controls；Dataset
§8 的角色分离仍为 `should`。

**REQUIRED_ACTION:** 白皮书 v0.1.1 必须把 builder parity 和 label-enrichment 写成明确的未决有效性
威胁，并声明在 blind/deterministic transformation contract 冻结前不能形成公平比较结论。具体 builder
实现与审计留待未来独立授权。

### FINDING_ID: IWR-004

**SEVERITY:** MAJOR

**LOCATION:** Whitepaper §§7-8; Cell Schema; Dataset §§4-5

**OBSERVATION:** 白皮书用 `Event = Actor + Action + Target + Time + Evidence` 和
`Before State -> Transition Event -> After State` 重建表示，但当前 Cell Schema 没有 first-class Event
或 StateTransition 对象。`historyEvent` 只有 kind、time、basis refs 和 summary；Observation 也没有完整
Actor/Action/Target/Evidence 绑定。

**WHY_IT_MATTERS:** 读者可能把 Dataset 的概念契约误认为 Schema 已强制的 DCell record 结构，导致
claim-to-artifact traceability 高估当前工件能力。

**SUPPORTED_BY:** `schema/cell.schema.json` 与 Dataset §§4-5 的逐字段比较。

**REQUIRED_ACTION:** 只修订白皮书 v0.1.1，明确 Event/StateTransition 当前属于 Dataset/architecture
conceptual contract，而非 Cell Schema v0.1 已实现字段；本评审不授权修改 Schema。

### FINDING_ID: IWR-005

**SEVERITY:** MINOR

**LOCATION:** Whitepaper §§2,4,6,7,9,10,13,15

**OBSERVATION:** 大量重复的“不是、没有、未实现”边界降低正面研究命题和候选增量的可见度。

**WHY_IT_MATTERS:** 严格边界是优点，但重复会让读者难以在早期区分“可检验贡献”与“合规状态”。

**SUPPORTED_BY:** Substance-versus-Guardrail review in §10 of this report.

**REQUIRED_ACTION:** 在不删除三项核心语义边界的前提下，压缩重复状态声明，并在前两节加入简短的
贡献／非贡献对照。

### FINDING_ID: IWR-006

**SEVERITY:** NOTE

**LOCATION:** Whitepaper §4 and external references

**OBSERVATION:** 六项指定官方来源的能力复述基本准确，未发现重大误述或把产品能力提升为学术结论。

**WHY_IT_MATTERS:** 外部来源问题是 coverage mismatch，不是 source fidelity failure。

**SUPPORTED_BY:** 本报告 §5.3 的逐项核验。

**REQUIRED_ACTION:** 无独立修复；随 IWR-001 补足同轴定位。

### FINDING_ID: IWR-007

**SEVERITY:** NOTE

**LOCATION:** Whitepaper bilingual paragraphs and status blocks

**OBSERVATION:** 未发现实质性双语语义漂移。

**WHY_IT_MATTERS:** 中英文核心主张、限定词和否定边界方向一致。

**SUPPORTED_BY:** 本报告 §9。

**REQUIRED_ACTION:** 保持当前术语映射。

## 12. Decision

## 评审结论

```text
PASS_WITH_REQUIRED_REVISIONS
```

白皮书提出了一个可独立重建、值得有界实验的问题，边界一致，六项指定外部来源复述准确，也明确允许
不利结果。但是，当前相关工作与核心结构贡献不同轴，证伪规则尚未操作化，builder parity 未冻结，且
Event/StateTransition 的概念契约与当前 Schema 表达不一致。因此必须完成 v0.1.1 文稿修订后，才可
再次判断是否适合作为公开研究草案。

本 Decision 不等于科学验证、创新性证明、论文接收、外部采用、实验成功、Runtime 可行、发布授权
或实现授权。

```text
BLOCKER_COUNT=0
MAJOR_COUNT=4
MINOR_COUNT=1
PUBLIC_RESEARCH_DRAFT_AUTHORIZED=false
```

## 13. Required Revision Set

## 必要修订集合

1. **IWR-001 / MAJOR：**加入同轴、有界的相关工作定位；把原创候选限制为研究问题、评价条件和失败
   模式，不把字段组合或名称写成已证明的新结构。
2. **IWR-002 / MAJOR：**将 §12 的拒绝条件明确标记为待预注册的 candidate conditions；在决策规则
   冻结前不声称已有完全操作化的证伪协议。
3. **IWR-003 / MAJOR：**把 builder transformation parity、label enrichment 和 role separation 写成
   明确有效性威胁，并声明冻结协议前不能形成公平比较结论。
4. **IWR-004 / MAJOR：**明确 Event 和 StateTransition 是 Dataset/architecture 概念契约，不是当前
   Cell Schema v0.1 已强制的 first-class fields。
5. **IWR-005 / MINOR：**压缩重复 guardrails，在前两节加入正面贡献／非贡献对照，同时保留
   Evidence/Truth、assessment/authorization、external/internal model state 三项核心边界。

该修订集合不授权新架构、新角色、新协议、新 Schema、Fixture、Runner 或实验。

## 14. Deferred Questions

## 延后问题

以下问题只能由未来单独授权的 Fixture、Runner 和实验回答，不应伪装成当前文稿修复：

- RAG 与 DCell 在匹配事实、时间、token 和 transformation cost 后是否存在可复现差异；
- blind/deterministic builder 是否能在不读取 hidden ledger 的情况下稳定构造 Cell record；
- 需要多少场景、语义变体、领域分层和随机种子才能支持预注册统计结论；
- primary metrics 之间冲突时采用何种 decision rule，以及维护成本的拒绝阈值；
- prompt wording、retriever、model revision 和 hosted-model drift 对结果有多大影响；
- temporal knowledge graph、event-sourced state 或 agent-memory baseline 是否应成为后续 matched
  condition；
- 独立标注者能否一致区分 Observation、Claim、Evidence、Event、Transition 和 Truth；
- 外部 Agent 或 World Model 是否能正确消费 uncertainty、conflict 和 proposal，而不把它们当成权限；
- 不利结果是否会在完整执行记录中被保留并复现。

## 15. Review Status

## 评审状态

```text
INDEPENDENT_WHITEPAPER_REVIEW_COMPLETED=true
REVIEW_VERSION=0.1
FRESH_CONTEXT_REVIEW=true
WHITEPAPER_MODIFIED=false
REFERENCE_ARCHITECTURE_MODIFIED=false
BENCHMARK_EXECUTED=false
MODEL_API_CALLED=false
SCIENTIFIC_VALIDATION=NOT_ESTABLISHED
PUBLICATION_AUTHORIZED=false
IMPLEMENTATION_AUTHORIZED=false
```

唯一允许的下一分支是：

```text
PASS_WITH_REQUIRED_REVISIONS
  -> Whitepaper Revision v0.1.1 Only
```

本评审不授权生成 Fixture、实现 Runner、调用模型、创建 Runtime、建立 remote、push、tag、release、
publication 或 DBA submission。
