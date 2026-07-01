# HANDOFF / 工作交接

使用此文档将上下文从一个用户或 AI Agent 会话转移到下一个。

Use this document to transfer context from one human or AI agent session to the next.

## 项目定位 / Project Positioning

项目名称 / Project name:

项目用途 / Project purpose:

本项目是 / This project is:

-

本项目不是 / This project is not:

-

## 当前状态 / Current Status

-

## 上一个完成的任务 / Last Completed Task

-

证据 / Evidence:

-

## 当前风险 / Current Risks

-

## 下一个任务 / Next Task

建议的下一个任务 / Proposed next task:

-

用户批准状态 / Human approval status:

- [ ] 已批准 / Approved
- [ ] 未批准 / Not approved
- [ ] 需要讨论 / Needs discussion

## 验收要求 / Acceptance Requirements

下一个任务可接受的条件 / The next task is acceptable only if:

-

## 未解决的问题 / Open Questions

-

## 禁止事项清单 / Do-Not-Do List

下一个 AI Agent 不得 / The next AI agent must not:

- 未经用户批准扩大范围 / expand scope without human approval
- 决定下一个任务 / decide the next task
- 编辑批准任务之外的文件 / edit files outside the approved task
- 编辑禁止的文件 / edit forbidden files
- 执行禁止的更改 / perform forbidden changes
- 读取或暴露真实机密、API key、token、凭据或 SecretStore 机密 / read or expose real secrets, API keys, tokens, credentials, or SecretStore secrets
- 引入完整的本地私有路径 / introduce full private local paths
- 修改系统 env、注册表、shell 配置、VS Code 全局配置或其他系统配置 / modify system env, registry, shell profile, VS Code global config, or other system configuration
- 未经批准添加依赖、脚本、包、插件、MCP server、GitHub Actions、release workflow、构建输出或自动化 / add dependencies, scripts, packages, plugins, MCP servers, GitHub Actions, release workflows, build outputs, or automation without approval
- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 AI Agent 进程 / start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- 点击 Terminal start / click Terminal start
- 删除非 app 管理的文件 / delete non app-managed files
- 执行 `git push`、`git tag`、创建 release 或添加/修改 remote / run `git push`, `git tag`, create a release, or add or modify a remote
- 没有证据声称完成 / claim completion without evidence

## 给下一个 AI Agent 的上下文 / Context For The Next AI Agent

在做任何工作前先阅读这些文件 / Read these files before doing work:

- `PROJECT_RULES.md`
- `NEXT_TASK.md`
- `ACCEPTANCE_CHECKLIST.md`
- `HANDOFF.md`

严格遵循当前任务。如果下一步不清楚，停下来标记 `NEEDS HUMAN REVIEW`。

Follow the current task exactly. If the next step is unclear, stop and mark `NEEDS HUMAN REVIEW`.
