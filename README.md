# specs-phase-sync

一个用于在实现任务完成后同步项目规格文档的 Codex skill。

## 用途

在任务已经完成、需要把最终决策和验证结果记录回仓库时使用。它会：

1. 先预览将要同步的 specs、phase 文档和 `CHANGELOG.md`；
2. 等待用户确认文件清单与变更摘要；
3. 仅在确认后执行文档同步；
4. 验证文件完整性、phase 状态、变更范围和 `git diff --check`。

## 使用

将此目录安装为 Codex skill 后，在任务完成时调用：

```text
$specs-phase-sync
```

## 目录

- `specs-phase-sync/SKILL.md`：完整工作流程与约束。
- `specs-phase-sync/agents/openai.yaml`：Codex skill 的显示信息与默认提示词。

## 范围约束

此 skill 默认只同步 `specs/` 和 `CHANGELOG.md` 等已批准的文档，不修改源代码、测试、依赖或 CI 配置。除非用户明确要求提交或外部上传，否则不会执行 git commit 或上传操作。

## 执行步骤
1、@specs-phase-sync 由该技能负责 preview、同步 specs、创建日期任务、更新 CHANGELOG 和按授权执行 Git 操作
2、确认，按刚才的文件清单执行。 不要修改代码。 验证通过后提交本次文档变更。这是现在的提示词，可以把这个skills传到我的github上吗
