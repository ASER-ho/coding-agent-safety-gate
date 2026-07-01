# 人类参与的工作流 / Human-In-The-Loop Workflow

AI 编程助手不应自行决定下一步，因为它们不拥有产品意图、风险容忍度、发布时机、安全姿态或团队优先级。

AI coding agents should not decide the next step by themselves because they do not own product intent, risk tolerance, release timing, security posture, or team priorities.

一个 Agent 可以在执行边界任务方面非常出色，但当它默默扩大使命时就变得不安全。Human-in-the-loop 工作流将权力保留在人类手中，让 Agent 负责窄范围执行加证据。

An agent can be excellent at executing a bounded task and still be unsafe when it silently expands the mission. Human-in-the-loop workflow keeps authority with the human and makes the agent responsible for narrow execution plus evidence.

## 推荐的责任分工 / Recommended Division Of Responsibility

ChatGPT 或规划助手 / ChatGPT or a planning assistant:

- 帮助澄清目标 / helps clarify goals
- 起草任务描述 / drafts task descriptions
- 比较选项 / compares options
- 准备 `.ai/NEXT_TASK.md` / prepares `.ai/NEXT_TASK.md`
- 识别人类审查的决策点 / identifies decision points for human review

Codex、Claude Code、Cursor、Gemini CLI 或其他编程 Agent / Codex, Claude Code, Cursor, Gemini CLI, or another coding agent:

- 读取 `.ai/PROJECT_RULES.md` / reads `.ai/PROJECT_RULES.md`
- 读取 `.ai/NEXT_TASK.md` / reads `.ai/NEXT_TASK.md`
- 只在批准的文件范围内工作 / works only inside the approved file scope
- 范围不清晰时停下来 / stops when scope is unclear
- 验证工作 / verifies work
- 报告变更文件、结果、风险和未完成事项 / reports changed files, results, risks, and incomplete items

人类 / Human:

- 决定项目方向 / decides the project direction
- 批准任务范围 / approves task scope
- 批准风险 / approves risk
- 批准依赖变更 / approves dependency changes
- 批准 push、tag、release、deploy、remote 或系统配置变更 / approves push, tag, release, deploy, remote, or system configuration changes
- 决定下一个任务 / decides the next task

## 多 Agent 协作流程 / Multi-Agent Collaboration Flow

1. 人类编写或批准项目规则。 / Human writes or approves project rules.
2. 人类或规划助手起草下一个任务。 / Human or planning assistant drafts the next task.
3. 人类批准任务范围和禁止操作。 / Human approves the task scope and forbidden operations.
4. 编程 Agent 在批准边界内执行任务。 / Coding agent performs the task inside the approved boundary.
5. 编程 Agent 生成带证据的执行报告。 / Coding agent produces an execution report with evidence.
6. 人类审查验收清单。 / Human reviews the acceptance checklist.
7. 人类决定是否由另一个 Agent 继续。 / Human decides whether another agent should continue.
8. 在下一个 Agent 开始前更新 handoff 记录。 / Handoff notes are updated before the next agent starts.

## 必须由人类决策的节点 / Required Human Decision Points

在 AI Agent 执行以下操作前，人类必须确认 / A human must confirm before an AI agent:

- 将任务扩大到当前文件范围之外 / expands the task beyond the current file scope
- 改变产品方向 / changes the product direction
- 改变安全姿态 / changes security posture
- 添加依赖 / adds dependencies
- 删除重要文件 / deletes important files
- 读取敏感文件 / reads sensitive files
- 修改环境或系统配置 / modifies environment or system configuration
- 启动另一个 Agent 或自动化 / starts another agent or automation
- 启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 Agent 进程 / starts a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- 点击 Terminal start / clicks Terminal start
- push、tag、release、deploy 或添加 remote / pushes, tags, releases, deploys, or adds a remote

## 证据型验收 / Evidence-Based Acceptance

Agent 永远不应只说"完成了"作为赤裸的声称。

The agent should never say "done" as a bare claim.

可接受的完成报告包括 / Acceptable completion includes:

- 变更文件列表 / changed file list
- 实际变更摘要 / summary of actual changes
- 验证命令或手动检查 / verification commands or manual checks
- 验证结果 / verification results
- 已知风险 / known risks
- 未完成事项 / incomplete items
- 下一步是否需要人类批准 / whether human approval is required for the next step

人类决定证据是否充分。

The human decides whether the evidence is sufficient.
