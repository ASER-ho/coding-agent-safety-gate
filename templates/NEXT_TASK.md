# NEXT_TASK / 下一个任务

将此文件复制到项目自有位置（如 `.ai/NEXT_TASK.md`）。本文件只定义恰好一个任务。

Copy this file into a project-owned location such as `.ai/NEXT_TASK.md`. This file defines exactly one task.

## 任务标题 / Task Title


## 阶段 / Stage

- [ ] 规划 / Planning
- [ ] 实现 / Implementation
- [ ] 验证 / Validation
- [ ] 文档 / Documentation
- [ ] 交接 / Handoff

## 目标 / Goal


## 背景 / Background


## 允许的文件 / Allowed Files

AI Agent 只能读取或编辑这些文件或目录 / The AI agent may read or edit only these files or directories:

-

## 禁止的文件 / Forbidden Files

AI Agent 不得读取或编辑这些文件或目录 / The AI agent must not read or edit these files or directories:

-

## 明确允许的操作 / Explicitly Allowed Operations

AI Agent 可以 / The AI agent may:

-

## 禁止的更改 / Forbidden Changes

AI Agent 不得 / The AI agent must not:

- 编辑允许文件列表之外的文件 / edit files outside the allowed file list
- 编辑禁止的文件 / edit forbidden files
- 扩大任务目标 / expand the task goal
- 进行大范围重构 / perform broad refactors
- 添加依赖 / add dependencies
- 创建脚本、包、插件、MCP server、GitHub Actions、release workflow、构建输出或自动化，除非上面明确列出 / create scripts, packages, plugins, MCP servers, GitHub Actions, release workflows, build outputs, or automation unless explicitly listed above
- 修改系统 env、注册表、shell 配置、VS Code 全局配置或其他系统配置 / modify system env, registry, shell profile, VS Code global config, or other system configuration
- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 AI Agent 进程 / start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- 点击 Terminal start / click Terminal start
- 删除非 app 管理的文件 / delete non app-managed files
- 执行 `git push`、`git tag`、创建 release 或添加/修改 remote / run `git push`, `git tag`, create a release, or add or modify a remote

## 安全约束 / Safety Constraints

- 不要读取或暴露真实机密、API key、token、凭据或 SecretStore 机密。 / Do not read or expose real secrets, API keys, tokens, credentials, or SecretStore secrets.
- 不要引入完整的本地私有路径。 / Do not introduce full private local paths.
- 不要决定下一个任务。 / Do not decide the next task.
- 没有证据不要声称完成。 / Do not claim completion without evidence.

## 步骤 / Steps

1. 阅读 `PROJECT_RULES.md`。 / Read `PROJECT_RULES.md`.
2. 确认本文件定义了一个清晰的任务。 / Confirm this file defines one clear task.
3. 只检查任务需要的允许文件。 / Inspect only allowed files needed for the task.
4. 做最小的有用改动。 / Make the smallest useful change.
5. 只运行下面列出的验证命令。 / Run only the validation commands listed below.
6. 填写执行报告。 / Fill the execution report.
7. 停下来等待用户审查。 / Stop for human review.

## 验证命令 / Validation Commands

```text

```

如果不适合用命令，列出需要的手动检查 / If no command is appropriate, list the manual checks required:

-

## 验收标准 / Acceptance Criteria

任务可接受的条件 / The task is acceptable when:

-

## 期望输出 / Expected Output

AI Agent 必须报告 / The AI agent must report:

- 变更文件 / changed files
- 摘要 / summary
- 为什么需要这个变更 / why this change was needed
- 验证命令 / validation commands
- 验证结果 / validation results
- 构建结果（如适用） / build result, if applicable
- 测试结果（如适用） / test result, if applicable
- 已知风险 / known risks
- 未完成工作 / incomplete work
- 最终状态：`PASS`、`FAIL`、`BLOCKED` 或 `NEEDS HUMAN REVIEW` / final status: `PASS`, `FAIL`, `BLOCKED`, or `NEEDS HUMAN REVIEW`

## 本任务不包括 / This Task Does Not Include

-

## 停止条件 / Stop Conditions

以下情况停下来标记 `NEEDS HUMAN REVIEW` / Stop and mark `NEEDS HUMAN REVIEW` if:

- 任务边界不清楚 / task boundaries are unclear
- 必需文件缺失 / required files are missing
- 请求的更改与 `PROJECT_RULES.md` 冲突 / requested changes conflict with `PROJECT_RULES.md`
- 似乎必须动到禁止的文件或执行禁止的更改 / a forbidden file or forbidden change appears necessary
- 需要读取真实机密、SecretStore 值或私有凭据 / a real secret, SecretStore value, or private credential would need to be read
- 需要披露完整的本地私有路径 / full private local paths would need to be disclosed
- 需要执行 git push、tag、release、remote 更改、系统配置更改、Agent 启动或 Terminal start / git push, tag, release, remote changes, system configuration changes, agent startup, or Terminal start would be required
