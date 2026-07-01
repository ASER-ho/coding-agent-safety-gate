# PROJECT_RULES / 项目规则

将此文件复制到项目自有位置（如 `.ai/PROJECT_RULES.md`），然后在分配工作给 AI 编程助手之前填写。

Copy this file into a project-owned location such as `.ai/PROJECT_RULES.md`, then fill it in before assigning work to an AI coding agent.

## 项目范围 / Project Scope

项目名称 / Project name:

项目用途 / Project purpose:

范围内 / In scope:

-

范围外 / Out of scope:

-

## 允许的操作 / Allowed Actions

AI Agent 可以 / The AI agent may:

- 读取批准的 `NEXT_TASK.md` 所需的文件 / read files necessary for the approved `NEXT_TASK.md`
- 编辑批准的 `NEXT_TASK.md` 中明确列出的文件 / edit files explicitly listed in the approved `NEXT_TASK.md`
- 运行批准的 `NEXT_TASK.md` 中明确列出的验证命令 / run validation commands explicitly listed in the approved `NEXT_TASK.md`
- 报告证据、风险与未完成工作 / report evidence, risks, and incomplete work

## 禁止的操作 / Forbidden Actions

AI Agent 不得 / The AI agent must not:

- 未经人类批准扩大范围 / expand scope without human approval
- 决定下一个任务 / decide the next task
- 编辑禁止的文件 / edit forbidden files
- 执行禁止的更改 / perform forbidden changes
- 未经明确批准进行大范围重构 / perform broad refactors unless explicitly approved
- 未经明确批准添加依赖、包、插件、MCP server、GitHub Actions、release workflow 或自动化 / add dependencies, packages, plugins, MCP servers, GitHub Actions, release workflows, or automation unless explicitly approved
- 没有证据声称完成 / claim completion without evidence

## 机密安全 / Secret Safety

AI Agent 不得读取、打印、存储、推断或请求真实机密，包括 / The AI agent must not read, print, store, infer, or request real secrets, including:

- API key
- token
- 密码 / passwords
- cookie
- 私钥 / private keys
- SecretStore 机密 / SecretStore secrets
- 生产凭据 / production credentials
- 私有客户数据 / private customer data

使用占位符，如 `YOUR_API_KEY_HERE`、`EXAMPLE_TOKEN` 或 `REDACTED`。

Use placeholders such as `YOUR_API_KEY_HERE`, `EXAMPLE_TOKEN`, or `REDACTED`.

## 路径安全 / Path Safety

AI Agent 不得在项目文档、示例、报告、issue、commit 或公开输出中引入完整的本地私有路径。

The AI agent must not introduce full private local paths into project documents, examples, reports, issues, commits, or public output.

允许的路径风格 / Allowed path style:

- `README.md`
- `.ai/NEXT_TASK.md`
- `src/example.ts`

## Git 安全 / Git Safety

AI Agent 不得运行或配置 / The AI agent must not run or configure:

- `git push`
- `git tag`
- release 创建 / release creation
- remote 创建或修改 / remote creation or modification
- force push
- 历史重写 / history rewrite

这些操作需要明确的人类批准。

These actions require explicit human approval.

## 系统修改安全 / System Modification Safety

AI Agent 不得修改 / The AI agent must not modify:

- 系统环境变量 / system environment variables
- 注册表设置 / registry settings
- shell 配置 / shell profiles
- VS Code 全局配置 / VS Code global configuration
- 全局 IDE 或编辑器设置 / global IDE or editor settings
- 机器级凭据 / machine-level credentials
- 全局 Agent 配置 / global agent configuration

## Agent 启动安全 / Agent Startup Safety

AI Agent 不得 / The AI agent must not:

- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 AI Agent 进程 / start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- 启动另一个 Agent runtime / start another agent runtime
- 点击 Terminal start / click Terminal start
- 启动不相关的后台服务或自动化 / start unrelated background services or automation

## 删除安全 / Deletion Safety

AI Agent 不得删除 / The AI agent must not delete:

- 非 app 管理的文件 / non app-managed files
- 批准任务范围外的文件 / files outside the approved task scope
- 生成的文件，除非任务明确允许清理 / generated files unless the task explicitly permits cleanup

## 证据要求 / Evidence Requirement

声称完成之前，AI Agent 必须提供 / Before claiming completion, the AI agent must provide:

- 变更的文件 / changed files
- 变更摘要 / summary of changes
- 验证命令或手动检查 / validation commands or manual checks
- 验证结果 / validation results
- 已知风险 / known risks
- 未完成事项 / incomplete items
- 最终状态：`PASS`、`FAIL`、`BLOCKED` 或 `NEEDS HUMAN REVIEW` / final status: `PASS`, `FAIL`, `BLOCKED`, or `NEEDS HUMAN REVIEW`

## 人类批准要求 / Human Approval Requirement

在以下情况前需要人类批准 / Human approval is required before:

- 扩大文件范围 / expanding file scope
- 改变任务目标 / changing the task goal
- 添加依赖 / adding dependencies
- 删除文件 / deleting files
- 修改系统配置 / modifying system configuration
- 读取敏感文件 / reading sensitive files
- push、tag、release、deploy 或添加 remote / pushing, tagging, releasing, deploying, or adding a remote
- 启动另一个 AI Agent 或自动化 / starting another AI agent or automation

不确定时，停下来标记工作为 `NEEDS HUMAN REVIEW`。

When uncertain, stop and mark the work `NEEDS HUMAN REVIEW`.
