# Cell Schema v0.1

`cell.schema.json` 是 JSON Schema Draft 2020-12 格式的研究草案，用于描述一个
Reality-linked Cognitive Cell record（现实关联认知 Cell 记录）。

## 结构目的

Schema 强制记录：

- 研究本地身份和现实目标边界；
- 来源与观察的时间、方式和可用性；
- 主张与证据材料引用；
- 世界模型投影与现实状态投影；
- 陈旧度、偏差、覆盖率、冲突与不确定性；
- 更新建议的非执行、未授权状态；
- 明确 truth/authorization 边界。

## 解释限制

```text
SCHEMA_VALID_NE_SEMANTICALLY_CORRECT=true
SCHEMA_VALID_NE_REALITY_VERIFIED=true
CELL_ID_NE_DBOS_ENTITY_ID=true
OBSERVATION_NE_FACT=true
EVIDENCE_REF_NE_EVIDENCE_AUTHORITY=true
DIVERGENCE_ASSESSMENT_NE_MODEL_UPDATE=true
PROPOSAL_NE_AUTHORIZATION_OR_EXECUTION=true
```

本项目没有 validator Runtime。`validation/README.md` 只记录静态检查范围。

