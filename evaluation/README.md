# Evaluation Boundary

本目录只冻结未来评估原则，不实现 evaluator 或 Benchmark。具体设计草案见
[`Reality Drift Benchmark v0.1`](../benchmark/reality-drift-benchmark.md)。

“Independent” in this repository means fresh-session process independence within the project. It does not
mean external peer review, institutional endorsement, customer validation, or ecosystem adoption.

本仓库中的“独立”表示项目内部不同会话之间的流程独立，不表示外部同行评审、机构认可、客户验证
或生态采用。

未来协议至少应包含：

- 匹配的版本化文档、RAG、知识图谱或 Agent Memory 基线；
- 陈旧输入、乱序事件、来源冲突、来源不可达和证据缺失负例；
- 预先声明的陈旧识别率、冲突保留率、依据重建率、误更新建议率和维护成本；
- 盲化或独立复核；
- 全部失败、未知和未完成结果保留；
- 精确执行上下文和数据来源锁。

```text
EVALUATION_PROTOCOL_DESIGN=REALITY_DRIFT_BENCHMARK_V0_1_RESEARCH_DRAFT
MATCHED_CONTROL_GROUPS_DEFINED=true
NEGATIVE_SCENARIOS_DEFINED=true
BENCHMARK_IMPLEMENTED=false
BENCHMARK_EXECUTED=false
RESULT_STATUS=NOT_ASSESSED
SAEE_EVALUATION_REQUESTED=false
```

设计完成不等于 executable protocol（可执行协议）已经冻结；样本量、数据集、评分实现、统计计划、
执行上下文和独立评审仍未完成。
