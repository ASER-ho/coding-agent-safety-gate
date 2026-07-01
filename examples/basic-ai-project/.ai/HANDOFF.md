# HANDOFF / 工作交接

使用此文档将上下文从一个人类或 AI Agent 会话转移到下一个。复制到你自己的项目中。

Use this document to transfer context from one human or AI agent session to the next. Copy into your own project.

## 项目定位 / Project Positioning

项目名称 / Project name: basic-ai-project (示例 / example)

项目用途 / Project purpose: 一个用于测试安全 AI 辅助文档和代码修改的演示项目。 / A demo project for testing safe AI-assisted documentation and code changes.

本项目是 / This project is:

- 一个练习安全 AI 编程助手工作流的小型演示 / A small demo for practicing safe AI coding agent workflows

本项目不是 / This project is not:

- 一个生产应用 / A production application
- 一个托管服务 / A hosted service
- 一个库或框架 / A library or framework

## 当前状态 / Current Status

- 上一个任务更新了 README 介绍。Diff 已审查并接受。 / README introduction was updated in the last task. Diff reviewed and accepted.

## 上一个完成的任务 / Last Completed Task

- 更新了 README.md 介绍。添加了一句解释项目的句子。 / Updated README.md introduction. Added one sentence explaining the project.

证据 / Evidence:

- git diff README.md 显示精确变更 / git diff README.md shows the exact change
- ACCEPTANCE_CHECKLIST.md 已完成并通过 / ACCEPTANCE_CHECKLIST.md completed and passed
- 没有其他文件被修改 / No other files modified

## 当前风险 / Current Risks

- 无。该项目是一个演示，没有生产依赖或敏感数据。 / None. The project is a demo with no production dependencies or sensitive data.

## 下一个任务 / Next Task

建议的下一个任务 / Proposed next task:

- 在 README.md 中添加"快速开始"部分 / Add a "Getting Started" section to README.md

人类批准状态 / Human approval status:

- [ ] 已批准 / Approved
- [x] 未批准 / Not approved
- [ ] 需要讨论 / Needs discussion

## 验收要求 / Acceptance Requirements

下一个任务可接受的条件 / The next task is acceptable only if:

- NEXT_TASK.md 已填写并由人类审查 / NEXT_TASK.md is filled in and reviewed by a human
- 任务保持在 README.md 范围内 / The task stays within README.md
- 不触碰允许列表之外的文件 / No files outside the allowed list are touched

## 未解决的问题 / Open Questions

- 项目是否应该添加 CONTRIBUTING.md？ / Should the project add a CONTRIBUTING.md?
- README 是否应该添加截图？ / Should screenshots be added to the README?

## 禁止事项清单 / Do-Not-Do List

下一个 AI Agent 不得 / The next AI agent must not:

- 未经人类批准扩大范围 / expand scope without human approval
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
- 执行 git push、git tag、创建 release 或添加/修改 remote / run git push, git tag, create a release, or add or modify a remote
- 没有证据声称完成 / claim completion without evidence

## 给下一个 AI Agent 的上下文 / Context For The Next AI Agent

在做任何工作前先阅读这些文件 / Read these files before doing work:

- PROJECT_RULES.md
- NEXT_TASK.md
- ACCEPTANCE_CHECKLIST.md
- HANDOFF.md

严格遵循当前任务。如果下一步不清楚，停下来标记 NEEDS HUMAN REVIEW。

Follow the current task exactly. If the next step is unclear, stop and mark NEEDS HUMAN REVIEW.
