# Codex — 安全门示例 / Safety Gate Example

## Purpose / 用途

本示例展示如何在 Codex（或其他类似编码助手）中使用 `coding-agent-safety-gate`。它是一层文档优先的工作流——不是 runtime enforcement，不是插件，不是包。

This example shows how to use `coding-agent-safety-gate` with Codex (or another coding agent with similar capabilities). It is a documentation-first workflow layer — not runtime enforcement, not a plugin, not a package.

## 推荐给 Agent 的文件 / Recommended files to give the agent

在开始 Codex 会话前，从 `templates/` 复制这些文件到你的项目中并填写：

Copy these files from `templates/` into your project and fill them in before starting a Codex session:

- `PROJECT_RULES.md` — 稳定项目边界和安全规则 / stable project boundaries and safety rules
- `NEXT_TASK.md` — Agent 当前被允许执行的唯一任务 / the one task the agent is currently allowed to perform
- `ACCEPTANCE_CHECKLIST.md` — 证据型完成清单 / evidence-based completion checklist
- `AGENT_EXECUTION_REPORT.md` — 实际发生了什么的事实报告 / factual report of what happened
- `HANDOFF.md` — 下一个用户或 Agent 的上下文 / context for the next human or agent
- `GIT_DIFF_REVIEW_CHECKLIST.md` — 任务后 diff 审查 / post-task diff review
- `SAFETY_REDACTION_CHECKLIST.md` — 分享前脱敏检查 / redaction check before sharing

## 建议工作流 / Suggested workflow

1. **用户** 编写或审查 `PROJECT_RULES.md`。 / **Human** writes or reviews `PROJECT_RULES.md`.
2. **用户** 编写恰好一个 `NEXT_TASK.md`。 / **Human** writes exactly one `NEXT_TASK.md`.
3. **Agent** 阅读项目规则、任务和清单文件。 / **Agent** reads the project rules, task, and checklist files.
4. **Agent** 只执行 `NEXT_TASK.md` 中描述的任务。 / **Agent** performs only the task described in `NEXT_TASK.md`.
5. **Agent** 填写 `AGENT_EXECUTION_REPORT.md`，包含变更文件和验证证据。 / **Agent** fills `AGENT_EXECUTION_REPORT.md` with changed files and verification evidence.
6. **用户** 使用 `GIT_DIFF_REVIEW_CHECKLIST.md` 审查 diff。 / **Human** reviews the diff using `GIT_DIFF_REVIEW_CHECKLIST.md`.
7. **用户** 在分享或发布前使用 `SAFETY_REDACTION_CHECKLIST.md` 检查输出。 / **Human** checks the output using `SAFETY_REDACTION_CHECKLIST.md` before sharing or publishing.
8. **用户** 决定是否 commit、push、tag 或 release。 / **Human** decides whether to commit, push, tag, or release.

Agent 不决定下一个任务。

The agent does not decide the next task.

## 禁止的 Agent 行为 / Forbidden agent behavior

使用 Codex 或其他编程 Agent 时，Agent 不得 / When using Codex or another coding agent, the agent must not:

- push、tag 或 release / push, tag, or release
- 添加或修改 remote / add or modify a remote
- force push 或重写历史 / force push or rewrite history
- 添加依赖、包或脚本 / add dependencies, packages, or scripts
- 创建 CLI、MCP server、VS Code 插件、npm 包、runtime enforcement 工具或 secret scanner / create a CLI, MCP server, VS Code plugin, npm package, runtime enforcement tool, or secret scanner
- 读取、打印或存储真实机密（API key、token、凭据） / read, print, or store real secrets (API keys, tokens, credentials)
- 暴露完整本地机器路径 / expose full local machine paths
- 未经用户批准继续进入下一个任务 / continue into the next task without human approval
- 没有证据声称完成 / claim completion without evidence

## 示例提示词 / Example prompt

在设置好项目文件后，将此复制到 Codex 会话中。 / Copy this into a Codex session after setting up your project files:

```text
编辑任何文件前，先读取 .ai/PROJECT_RULES.md 和 .ai/NEXT_TASK.md。
只完成 NEXT_TASK.md 中描述的任务。不要扩大范围。
完成后填写 .ai/AGENT_EXECUTION_REPORT.md，包含变更文件、变更摘要、验证命令及结果、安全检查结果。
不要 push、tag、release、添加依赖、读取机密或暴露完整路径。
如果任务边界不清楚，停下来标记 NEEDS HUMAN REVIEW。

Read .ai/PROJECT_RULES.md and .ai/NEXT_TASK.md before editing any file.
Complete only the task described in NEXT_TASK.md. Do not expand the scope.
After finishing, fill .ai/AGENT_EXECUTION_REPORT.md with changed files, summary, verification and results, safety check results.
Do not push, tag, release, add dependencies, read secrets, or expose full paths.
If the task boundary is unclear, stop and mark NEEDS HUMAN REVIEW.
```

## 用户审查 / Human review

用户审查者拥有所有最终决定权。Agent 的执行报告是支持审查的证据——不是声称工作正确、安全或可以发布的证明。在 commit、push、tag 或 release 之前审查每个变更。

The human reviewer owns all final decisions. The agent's execution report is evidence to support review — it is not a claim that the work is correct, safe, or ready to publish. Review every change before committing, pushing, tagging, or releasing.
