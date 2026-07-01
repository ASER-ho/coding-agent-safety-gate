# 安全边界 / Safety Boundaries

本文档定义 `coding-agent-safety-gate` 的默认安全边界。

This document defines the default safety boundaries for `coding-agent-safety-gate`.

## Secret-Safe / 机密安全

AI Agent 不得读取、打印、复制、存储、推断或请求真实机密。

AI agents must not read, print, copy, store, infer, or request real secrets.

机密包括 / Secrets include:

- API key
- token
- 密码 / passwords
- cookie
- 私钥 / private keys
- SecretStore 机密 / SecretStore secrets
- 生产凭据 / production credentials
- 私有客户数据 / private customer data

文档必须使用占位符，如 `YOUR_API_KEY_HERE`、`EXAMPLE_TOKEN` 或 `REDACTED`。

Documentation must use placeholders such as `YOUR_API_KEY_HERE`, `EXAMPLE_TOKEN`, or `REDACTED`.

## Path-Safe / 路径安全

AI Agent 应避免在公开项目文档、示例或报告中写入完整的本地私有路径。

AI agents should avoid writing full private local paths into public project documents, examples, or reports.

优先使用相对路径 / Prefer relative paths:

- `.ai/NEXT_TASK.md`
- `README.md`
- `src/example.ts`

避免暴露用户名、主目录、私有工作空间或组织结构的机器特定路径。

Avoid machine-specific paths that reveal a user name, home directory, private workspace, or organization structure.

## Git-Safe / Git 安全

AI Agent 未经用户批准不得执行会发布、重写或连接仓库的 git 操作。

AI agents must not perform git operations that publish, rewrite, or connect a repository without human approval.

未经用户批准明确禁止 / Explicitly forbidden without human approval:

- `git push`
- `git tag`
- release 创建 / release creation
- 添加 remote / adding a remote
- 修改 remote / modifying a remote
- force push
- 历史重写 / history rewrite

Agent 可以在批准任务需要时查看本地状态或 diff，但不得发布或 release。

The agent may inspect local status or diffs when needed for an approved task, but it must not publish or release.

## Env-Safe / 环境安全

AI Agent 不得修改 / AI agents must not modify:

- 系统环境变量 / system environment variables
- shell 配置 / shell profiles
- 注册表设置 / registry settings
- VS Code 全局配置 / VS Code global configuration
- 全局编辑器设置 / global editor settings
- 机器级凭据 / machine-level credentials
- 全局 Agent 配置 / global agent configuration

如果环境变更看起来必要，Agent 必须停下来询问用户。

If an environment change appears necessary, the agent must stop and ask the human.

## Execution-Safe / 执行安全

AI Agent 未经明确批准不得运行破坏性或大范围的执行步骤。

AI agents must not run destructive or broad execution steps without explicit approval.

需要批准的示例 / Examples requiring approval:

- 删除批准范围外的文件 / deleting files outside the approved scope
- 删除非 app 管理的文件 / deleting non app-managed files
- 安装包 / installing packages
- 启动后台服务 / starting background services
- 启动另一个 AI Agent / starting another AI agent
- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 Agent 进程 / starting a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- 点击 Terminal start / clicking Terminal start
- 创建自动化 / creating automation
- 创建 GitHub Actions / creating GitHub Actions
- 创建 release workflow / creating release workflows
- 修改系统配置 / modifying system configuration

## Evidence-Based Acceptance / 证据型验收

AI Agent 在声称工作完成前必须提供证据。

AI agents must provide evidence before declaring work complete.

证据应包括 / Evidence should include:

- 变更的文件 / files changed
- 有意保持不变的文件（当相关时） / files intentionally left unchanged when relevant
- 用于验证的命令或检查 / commands or checks used for verification
- 验证结果 / verification results
- 风险 / risks
- 未完成工作 / incomplete work
- 需要的用户批准 / required human approvals
- 最终状态：`PASS`、`FAIL`、`BLOCKED` 或 `NEEDS HUMAN REVIEW` / final status: `PASS`, `FAIL`, `BLOCKED`, or `NEEDS HUMAN REVIEW`

## 明确禁止的自主行为 / Explicitly Forbidden Autonomous Actions

AI Agent 不得自行 / The AI agent must not independently:

- push
- tag
- release
- 添加 remote / add a remote
- 修改 remote / modify a remote
- deploy
- 更改系统配置 / change system configuration
- 读取真实机密 / read real secrets
- 暴露真实机密 / expose real secrets
- 读取 SecretStore 机密 / read SecretStore secrets
- 暴露完整本地私有路径 / expose full private local paths
- 启动另一个 Agent / start another agent
- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 Agent 进程 / start a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- 点击 Terminal start / click Terminal start
- 自行决定下一个任务 / invent the next task

当需要做出决定时，Agent 应停下来询问用户。

When a decision is needed, the agent should stop and ask the human.

## 一层，不是整个安全系统 / One Layer, Not the Whole Safety System

本项目提供工作流安全栈中的一层。它本身不是一个完整的安全系统。

This project provides one layer of a workflow safety stack. It is not a complete safety system on its own.

它不替代 / It does not replace:

- 沙箱 / sandboxing
- 最小权限凭据 / least-privilege credentials
- 备份与回滚 / backup and rollback
- 运行时命令拦截 / runtime command blocking
- 机密扫描 / secret scanning
- 用户代码审查 / human code review

它的职责更窄：在每次 AI 辅助变更前后，让任务边界、禁止动作、证据要求和用户 handoff 变得明确且可审查。

Its job is narrower: make task boundaries, forbidden actions, evidence requirements, and human handoff explicit and reviewable before and after each AI-assisted change.

如果你需要硬性实时拦截危险命令，请将本项目与专门的运行时拦截工具、pre-action 授权中间件或沙箱执行环境配合使用。

If you need hard runtime interception of dangerous commands, pair this project with dedicated runtime enforcement tools, pre-action authorization middleware, or sandboxed execution environments.
