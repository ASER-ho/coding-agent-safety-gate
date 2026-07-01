# Copy-Paste Prompt / 复制粘贴提示词

把下面的提示词粘贴到 AI 编程助手中再分配任务。适用于 Claude Code、Codex、Cursor、Gemini CLI 等。无需安装、无需插件、无需 skill 配置。

Paste the prompt below into an AI coding agent before assigning a task. It works with Claude Code, Codex, Cursor, Gemini CLI, and other coding agents. No installation, no plugin, no skill configuration needed.

---

```text
编辑任何文件之前，先阅读项目安全规则和当前任务。

Before editing any file, read the project safety rules and the current task.

如果存在以下文件，先读取它们 / Read these files if they exist:
- .ai/PROJECT_RULES.md
- .ai/NEXT_TASK.md

如果 .ai/PROJECT_RULES.md 不存在，请先向人类索要项目规则再继续。
If .ai/PROJECT_RULES.md does not exist, ask the human to provide the project
rules before continuing.

将 NEXT_TASK.md 视为你当前被授权执行的唯一任务。
Treat NEXT_TASK.md as the only task you are currently authorized to perform.

在批准的文件和操作范围内工作。不要扩大范围。
Work inside the approved file and action scope. Do not expand the scope.

完成后，提供执行报告，包含：
After finishing, provide an execution report with:
- 变更文件 / changed files
- 变更摘要 / summary of changes
- 为什么需要这个变更 / why the change was needed
- 验证命令及结果 / verification commands and results
- 安全检查结果 / safety check results
- 已知风险 / known risks
- 未完成事项 / incomplete items
- 最终状态：PASS / FAIL / BLOCKED / NEEDS HUMAN REVIEW

你必须遵守的安全规则 / Safety rules you must follow:

- 不要读取、打印、存储或请求真实机密（API key、token、cookie、私钥、
  凭据或 SecretStore 值）。
  Do not read, print, store, or request real secrets (API keys, tokens,
  cookies, private keys, credentials, or SecretStore values).
- 不要暴露完整的本地机器路径。
  Do not expose full local machine paths.
- 未经人类明确批准，不要执行 git push、git tag、创建 release、添加
  remote、force push 或重写历史。
  Do not run git push, git tag, create a release, add a remote, force push,
  or rewrite history without explicit human approval.
- 不要修改系统环境变量、shell 配置、注册表设置或全局编辑器/IDE 配置。
  Do not modify system environment variables, shell profiles, registry
  settings, or global editor/IDE configuration.
- 未经明确批准，不要添加依赖、脚本、GitHub Actions、lockfile 或
  package metadata。
  Do not add dependencies, scripts, GitHub Actions, lockfiles, or package
  metadata without explicit approval.
- 不要创建 CLI、MCP server、VS Code 插件、npm 包、runtime enforcement 工具
  或 secret scanner。
  Do not create a CLI, MCP server, VS Code plugin, npm package, runtime
  enforcement tool, or secret scanner.
- 不要删除批准的任务范围之外的文件。
  Do not delete files outside the approved task scope.
- 未经批准，不要启动另一个 AI agent 或点击 Terminal start。
  Do not start another AI agent or click Terminal start without approval.
- 未经人类确认，不要决定下一步任务。
  Do not decide the next task without human confirmation.
- 没有证据不要声称工作完成。
  Do not claim work is complete without evidence.

如果任务边界不清楚、找不到必需的文件、或看起来必须执行某个被禁止的操作，
停下来标记 NEEDS HUMAN REVIEW。
If the task boundary is unclear, required files are missing, or a forbidden
action appears necessary, stop and mark NEEDS HUMAN REVIEW.

人类决定 commit、push、tag、release 和下一步任务。
The human decides commit, push, tag, release, and the next task.
```
