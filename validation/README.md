# Validation

当前验证仅限静态工件：

1. 所有 JSON 文件可解析；
2. `schema/cell.schema.json` 是 Draft 2020-12 JSON Schema；
3. 合成示例满足 Cell Schema v0.1；
4. README 与 agent index 引用的本地文件存在；
5. 禁止状态保持 false / not established；
6. Reality Drift Benchmark 必需章节、三组对照、场景和指标可被静态发现；
7. benchmark 目录不包含可执行代码；
8. 不运行网络、Runtime、Agent、模型或真实来源。

静态验证通过不证明语义正确、现实真实性、科学有效性、DCell 分类、DBA 准入、发布或生产就绪。
