# Architecture v0.1

## 1. 架构定位

本架构是 research reference architecture（研究参考架构），不是部署架构。唯一落地工件是
`Cell Schema v0.1` 及合成示例。

```text
External Reality Sources
  -> Observation References
    -> Evidence-bound Claims
      -> Reality Cell Record
        -> Synchronization Assessment
          -> Proposed Model Update
            -> External Decision / Authorization
```

## 2. 逻辑组件

### 2.1 Reality Source Boundary

描述观察来自哪里、何时被观察、采用何种方法、来源是否可达。来源本身由外部系统拥有；本项目
只保存引用和摘要，不复制其事实权威。

### 2.2 Observation Set

保存针对有界现实对象的观察。观察必须区分 `OBSERVED`、`REPORTED`、`INFERRED` 和
`UNKNOWN`，并保留时间、来源、顺序、缺失与冲突。

### 2.3 Evidence-bound Claim Set

把可检查的主张与观察或外部材料引用连接起来。主张可以是支持、反对、冲突或未解决状态；
证据引用不自动使主张成为事实。

### 2.4 Reality Cell Record

以研究本地 `cell_id` 组织目标身份、当前状态投影、历史、冲突和不确定性。该记录是认知投影，
不是现实对象、DCell 实例、DBOS Entity 或世界模型本体。

### 2.5 Synchronization Assessment

表达三个候选维度：

- `freshness`：输入是否超过声明时效窗口；
- `divergence`：观察与模型投影是否存在可描述差异；
- `coverage`：当前证据是否足以覆盖待评估字段。

评估结果必须允许 `UNKNOWN`、`CONFLICTED` 和 `NOT_ASSESSED`，并保留输入引用。

### 2.6 Proposed Model Update

只描述候选变更、理由、影响范围和停止条件。它不是 patch、command、permission 或 execution。
任何外部应用需要独立 Decision、Authorization、执行证据和回滚机制。

## 3. 数据与控制边界

| 对象 | 本仓库角色 | 不承担的角色 |
|---|---|---|
| Reality source | 外部引用 | 事实所有者、采集器 |
| Observation | 有来源的研究记录 | 已验证事实 |
| Claim | 可检查陈述 | Truth |
| Evidence reference | 材料定位 | Evidence authority、认证 |
| Cell record | 有界认知投影 | DCell 实例、DBOS Entity |
| Sync assessment | 候选评估 | SAEE 评价、授权 |
| Update proposal | 建议 | 模型更新、现实写入、执行 |

## 4. 失败关闭语义

- 来源不可达：`source_availability=UNAVAILABLE`；不得沿用旧观察为当前事实。
- 时间未知：`freshness=UNKNOWN`；不得声明同步。
- 来源冲突：记录 `conflicts`；不得静默选择有利来源。
- 覆盖不足：`coverage=INSUFFICIENT`；不得输出确定性差异结论。
- 无授权：保留 proposal；`application_authorized=false`。

## 5. 未来实现 gate（当前未开放）

任何实现讨论前至少需要：预注册研究问题、匹配基线、负例、隐私和安全边界、数据 Owner、
失败策略、独立评审，以及新的人工实现授权。当前项目没有进入该 gate。

