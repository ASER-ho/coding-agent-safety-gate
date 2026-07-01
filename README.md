# Coding Agent Safety Gate / 编程助手安全门禁

A documentation-first safety gate for AI coding agents: task boundaries, forbidden actions, and evidence-based acceptance.

面向 AI 编程助手的文档优先安全门禁：任务边界、禁止操作与证据型验收。

Stop AI coding agents from drifting, over-editing, leaking secrets, or declaring work done without evidence.

防止 AI 编程助手跑偏、越权修改、泄露敏感信息，或在没有证据时声称完成。

This project provides workflow guardrails, not runtime enforcement.

本项目提供的是工作流护栏，不是运行时强制执行。

## Use in 60 Seconds / 60 秒上手

No install. No CLI. No dependencies. No runtime enforcement. Human owns final decisions.

无需安装。无需 CLI。无需依赖。无需 runtime enforcement。人类保留最终决定权。

1. 打开 **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)** — 把提示词复制到 Claude Code、Codex、Cursor、Gemini CLI 或其他 AI 编程助手。 / Open **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)** — copy the prompt into Claude Code, Codex, Cursor, Gemini CLI, or another AI coding agent.
2. 把 **[templates/](templates/)** 中的模板复制到你的项目，建议放在 `.ai/` 下。 / Copy the templates from **[templates/](templates/)** into your project, preferably under `.ai/`.
3. 填写一次 `PROJECT_RULES.md`，每次任务前填写 `NEXT_TASK.md`。 / Fill in `PROJECT_RULES.md` once and `NEXT_TASK.md` before each task.
4. 告诉 Agent 只完成被批准的任务并返回证据。 / Ask the agent to complete only the approved task and return evidence.
5. 在 commit、push、tag 或 release 之前审查结果。 / Review the result before commit, push, tag, or release.

更多选项（包括自定义 skill 设置）见 **[QUICKSTART.md](QUICKSTART.md)**。 / See **[QUICKSTART.md](QUICKSTART.md)** for more options, including custom skill setup.

## First Screen / 首屏

本项目提供一套可复制的 skill 和少量 Markdown 模板，帮助人类在 AI 编程助手开始工作前定义任务边界。

This project provides a copyable skill and a small set of Markdown templates that help humans define task boundaries before an AI coding agent starts work.

v0.1 刻意保持小巧。只包含 Markdown 文档、一个 skill 文件、模板、文档和示例。不运行代码、不安装依赖、不管理 release、不扫描 secret、不替代人类判断。

v0.1 is intentionally small. It contains only Markdown documentation, a skill file, templates, docs, and examples. It does not run code, install dependencies, manage releases, scan secrets, or replace human judgment.

在以下场景使用 / Use it when you want an AI coding agent to:

- 待在批准的任务范围内 / stay inside an approved task scope
- 避免接触无关文件 / avoid touching unrelated files
- 避免读取或暴露真实机密 / avoid reading or exposing real secrets
- 在决策点请求人类批准 / ask for human approval at decision points
- 声称完成之前提供证据 / provide evidence before claiming completion
- 清晰地将工作交接给下一个人或 Agent / hand off work clearly to the next human or agent

## What Problem It Solves / 解决的问题

AI 编程助手很强大，但可能偏离原始需求、编辑范围过宽、推断从未被授予的权限，或没有证据就报告成功。

AI coding agents are powerful, but they can drift from the original request, edit too broadly, infer permission they were never given, or report success without proof.

本项目为团队提供一套轻量级协议 / This project gives teams a lightweight protocol for:

- 定义项目级安全规则 / defining project-level safety rules
- 以窄范围、可审查的方式定义下一个任务 / defining the next task in a narrow, reviewable way
- 要求证据型验收 / requiring evidence-based acceptance
- 记录实际变更了什么 / recording what actually changed
- 支持 human-in-the-loop 多 Agent 工作流 / supporting human-in-the-loop multi-agent workflows

## What It Is Not / 不是什么

`coding-agent-safety-gate` 不是 / is not:

- Agent runtime / 代理运行时
- 自动化开发平台 / an automated development platform
- 代码审查工具 / a code review tool
- 发布工具 / a release tool
- 机密扫描器 / a secret scanner
- MCP server
- Provider Gateway
- VS Code 插件 / a VS Code plugin
- v0.1 中的 npm 包 / an npm package in v0.1
- Claude Workspace Desktop 主项目 / the Claude Workspace Desktop main project
- 自动化项目管理者 / an automated project manager
- 全自动编程 Agent / a fully autonomous programming agent

## Target Users / 目标用户

本项目面向 / This project is for:

- 使用 Claude Code、Codex、Cursor、Gemini CLI 等编程助手的开发者 / developers using Claude Code, Codex, Cursor, Gemini CLI, or similar coding agents
- 希望 AI 辅助贡献更安全的维护者 / maintainers who want safer AI-assisted contributions
- 实验多 Agent 开发的团队 / teams experimenting with multi-agent development
- 希望 AI Agent 产出可验证工作而非笼统声称的人类 / humans who want AI agents to produce verifiable work instead of broad claims
- 希望在加自动化之前先有一套简单安全协议的开源项目 / open source projects that want a simple safety protocol before adding automation

## Quick Start / 快速开始

1. 将 `skills/coding-agent-safety-gate/SKILL.md` 复制到支持自定义 skills 或指令的 AI 编码环境中。 / Copy `skills/coding-agent-safety-gate/SKILL.md` into the AI coding agent environment that supports custom skills or instructions.
2. 可选：在项目中创建 `.ai/` 目录作为可读的工作流约定。 / Optionally create a `.ai/` directory inside your project as a human-readable workflow convention.
3. 将 `templates/` 中的模板复制到该目录或其他有文档记录的位置。 / Copy the templates from `templates/` into that directory or another documented location.
4. 为项目填写一次 `PROJECT_RULES.md`。 / Fill in `PROJECT_RULES.md` once for the project.
5. 每次 Agent 任务前填写 `NEXT_TASK.md`。 / Fill in `NEXT_TASK.md` before each agent task.
6. 让 Agent 遵守 skill 和复制的模板文件。 / Ask the agent to follow the skill and the copied template files.
7. 要求 Agent 在声称完成之前填写 `AGENT_EXECUTION_REPORT.md` 或等效的执行报告。 / Require the agent to complete `AGENT_EXECUTION_REPORT.md` or an equivalent execution report before claiming done.
8. 使用 `ACCEPTANCE_CHECKLIST.md` 验证结果。 / Use `ACCEPTANCE_CHECKLIST.md` to verify the result.
9. 当工作需要在另一个会话或与另一个 Agent 继续时，更新 `HANDOFF.md`。 / Update `HANDOFF.md` when work should continue in another session or with another agent.

无需安装任何依赖。 / No dependency installation is required.

## Recommended `.ai/` File Protocol / 推荐的 .ai/ 文件协议

`.ai/` 布局是一个推荐的工作流约定。v0.1 不实现自动协议、运行时、监控或必需的目录结构。

The `.ai/` layout is a recommended workflow convention. v0.1 does not implement an automatic protocol, runtime, watcher, or required directory structure.

一个正常项目可以选择包含 / A normal project can choose to include:

```text
.ai/
├── PROJECT_RULES.md
├── NEXT_TASK.md
├── ACCEPTANCE_CHECKLIST.md
├── AGENT_EXECUTION_REPORT.md
└── HANDOFF.md
```

推荐的角色分工 / Recommended roles:

- `PROJECT_RULES.md`：稳定的项目边界和安全规则 / stable project boundaries and safety rules
- `NEXT_TASK.md`：Agent 当前被允许执行的唯一任务 / the only task the agent is currently allowed to perform
- `ACCEPTANCE_CHECKLIST.md`：证据型完成检查清单 / evidence-based completion checklist
- `AGENT_EXECUTION_REPORT.md`：实际发生了什么的事实报告 / factual report of what happened
- `HANDOFF.md`：下一个人类或 AI Agent 的当前状态 / current state for the next human or AI agent

这些文件可用于任何编程 Agent。`AGENT_EXECUTION_REPORT.md` 模板是工具中立的，适用于 Claude Code、Codex、Cursor、Gemini CLI 或其他 AI 编程助手。

The files can be used with any coding agent. The `AGENT_EXECUTION_REPORT.md` template is tool-neutral and works with Claude Code, Codex, Cursor, Gemini CLI, or other AI coding agents.

## Human-In-The-Loop Workflow / 人机协作工作流

本项目假定人类拥有决策权，AI Agent 执行有边界的任务。

This project assumes humans own decisions and AI agents execute bounded tasks.

推荐流程 / Recommended flow:

1. 人类在 `.ai/PROJECT_RULES.md` 中定义项目规则。 / A human defines project rules in `.ai/PROJECT_RULES.md`.
2. 人类编写或批准 `.ai/NEXT_TASK.md`。 / A human writes or approves `.ai/NEXT_TASK.md`.
3. AI Agent 在编辑前读取规则和任务。 / The AI agent reads the rules and task before editing.
4. AI Agent 只在批准的文件和操作范围内工作。 / The AI agent works only inside the approved file and action scope.
5. 当任务需要在当前范围之外做出决定时，AI Agent 停下来请求批准。 / The AI agent stops and asks for approval when the task requires a decision outside the current scope.
6. AI Agent 提供证据，包括变更文件和验证结果。 / The AI agent provides evidence, including changed files and verification results.
7. 人类审查验收清单。 / A human reviews the acceptance checklist.
8. 人类决定下一步任务。 / A human decides the next task.

AI Agent 不应自行决定下一步产品方向、扩大任务范围、push 代码、创建 release、添加 remote 或更改系统配置，除非获得人类明确批准。

AI agents should not decide the next product direction, expand the task scope, push code, create releases, add remotes, or change system configuration without explicit human approval.

## Safety Boundaries / 安全边界

默认安全边界 / The default safety boundaries are:

- 机密安全 / Secret-safe：不读取、打印、推断、存储或请求真实 API key、token、凭据、cookie、私钥或生产机密。 / do not read, print, infer, store, or request real API keys, tokens, credentials, cookies, private keys, or production secrets.
- 路径安全 / Path-safe：不在项目文档或报告中暴露完整的本地机器路径，除非人类明确要求用于本地调试。 / do not expose full local machine paths in project documents or reports unless the human explicitly requests it for local debugging.
- Git 安全 / Git-safe：未经人类明确批准，不执行 `git push`、`git tag`、release 创建、remote 创建、force push 或历史重写。 / do not run `git push`, `git tag`, release creation, remote creation, force push, or history rewrite without explicit human approval.
- 环境安全 / Env-safe：不修改系统环境变量、shell 配置、注册表设置、IDE 设置或全局配置。 / do not modify system environment variables, shell profiles, registry settings, IDE settings, or global configuration.
- 执行安全 / Execution-safe：未经批准，不运行破坏性命令、安装新自动化或启动不相关的 Agent。 / do not run destructive commands, install new automation, or start unrelated agents without approval.
- Agent 启动安全 / Agent-startup-safe：未经明确批准，不启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 Agent 进程，不点击 Terminal start。 / do not start a real Claude, Codex, Cursor, Gemini CLI, or other agent process, and do not click Terminal start, unless explicitly approved.
- 证据型验收 / Evidence-based acceptance：不列出变更了什么以及如何验证的，不声称完成。 / do not claim done without listing what changed and how it was verified.

## Prior Art and Differentiation / 先行者与差异化

AI 编程助手领域已有 runtime guardrail、hook-based enforcement、pre-action authorization 以及 AGENTS.md security-template 项目。

There are already runtime guardrail, hook-based enforcement, pre-action authorization, and AGENTS.md security-template projects for AI coding agents.

本项目刻意更窄：一个纯粹的 Markdown 工作流层。大多数 guardrail 项目加 hooks、MCP server 或 runtime enforcement。这个项目一个都不加。

This project is intentionally narrower: a pure Markdown workflow layer. Most guardrail projects add hooks, MCP servers, or runtime enforcement. This one doesn't.

`coding-agent-safety-gate` 是文档优先的。不安装 hooks、不在运行时阻塞 shell 命令、不修改编辑器或 Agent 配置、不提供 CLI、不发布 MCP server、不发布 npm 包、不作为 pre-action authorization 层。

`coding-agent-safety-gate` is documentation-first. It does not install hooks, block shell commands at runtime, modify editor or agent configuration, provide a CLI, ship an MCP server, publish an npm package, or act as a pre-action authorization layer.

聚焦于一个轻量级工作流层 / It focuses on a lightweight workflow layer:

- 定义一个边界任务 / define one bounded task;
- 声明允许和禁止的文件 / declare allowed and forbidden files;
- 把禁止的动作写明确 / make forbidden actions explicit;
- 要求提供证据才声称完成 / require evidence before claiming completion;
- 通过 handoff 模板保留人类决策权 / preserve human decision-making through handoff templates.

把它当工作流护栏用。如果需要硬性运行时拦截，请结合沙箱、最小权限凭据、hook-based 工具或 pre-action authorization 系统使用。

Use it as a workflow guardrail. For hard runtime enforcement, combine it with sandboxing, scoped credentials, hook-based tools, or pre-action authorization systems.

## Example Task / 示例任务

`.ai/NEXT_TASK.md` 示例任务 / Example `.ai/NEXT_TASK.md` task:

```text
Update README.md to clarify the project description.
更新 README.md 以使项目描述更清晰。

Allowed files / 允许的文件:
- README.md

Allowed operations / 允许的操作:
- Edit wording in the introduction. / 编辑介绍部分的措辞。
- Add one short usage example. / 添加一个简短的使用示例。

Forbidden operations / 禁止的操作:
- 不要更改包配置。 / Do not change package configuration.
- 不要添加脚本。 / Do not add scripts.
- 不要读取机密。 / Do not read secrets.
- 不要 push、tag、release 或添加 remote。 / Do not push, tag, release, or add a remote.

Acceptance / 验收:
- README 介绍更清晰。 / README introduction is clearer.
- 没有无关文件被更改。 / No unrelated files changed.
- Agent 报告变更文件和验证步骤。 / Agent reports changed files and verification steps.
```

参见 `examples/basic-ai-project/README.md` 获取最小示例。 / See `examples/basic-ai-project/README.md` for a minimal example.

## v0.1 Public Repository Standard / v0.1 公开仓库标准

此 v0.1 仓库包含 / This v0.1 repository includes:

- 完整的文档化结构 / complete documented structure
- MIT License
- 清楚说明范围的 README / README that clearly explains the scope
- 可复制的 skill 文件 / copyable skill file
- 可复制的任务、规则、验收、执行报告和 handoff 模板 / copyable task, rules, acceptance, execution report, and handoff templates
- 示例用法 / example usage
- 没有真实机密、token、私有路径或私有仓库 remote / no real secrets, tokens, private paths, or private repository remotes
- 没有 npm 包、VS Code 插件、MCP server、GitHub Actions、runtime enforcement 或 release workflow / no npm package, VS Code plugin, MCP server, GitHub Actions, runtime enforcement, or release workflow

本仓库旨在保持文档和模板形态。任何公开发布、tag 或自动化应由人类审查和批准。

This repository is intended to remain documentation-and-template-only. Any public release, tag, or automation should be reviewed and approved by a human.

## Roadmap / 路线图

### 已在 v0.2 完成 / Completed in v0.2

- 社区文件：AGENTS.md、SECURITY.md、CONTRIBUTING.md、issue/PR 模板 / community files: AGENTS.md, SECURITY.md, CONTRIBUTING.md, issue templates, PR template
- 审查和脱敏清单：GIT_DIFF_REVIEW_CHECKLIST.md、SAFETY_REDACTION_CHECKLIST.md / review and redaction checklists: GIT_DIFF_REVIEW_CHECKLIST.md, SAFETY_REDACTION_CHECKLIST.md
- Codex 和 Claude Code 的示例工作流 / example workflows for Codex and Claude Code

### 已在 v0.2.1 完成 / Completed in v0.2.1

- 快速入门指南和复制粘贴提示词 / quickstart guide and copy-paste prompt
- `examples/basic-ai-project/` 中的 `.ai/` 示例目录 / filled `.ai/` example directory in `examples/basic-ai-project/`

### 未来 / 计划中 / Future / planned

- Cursor 和 Gemini CLI 的示例工作流 / example workflows for Cursor and Gemini CLI
- 面向开源维护者的团队策略示例 / team policy examples for open source maintainers
- 安全敏感仓库的可选清单变体 / optional checklist variants for security-sensitive repositories
- 不同 AI 编程环境的比较指南 / comparison guide for different AI coding agent environments
- 多 Agent handoff 模式的轻量示例 / lightweight examples for multi-agent handoff patterns

不包含任何自动化、包、插件、MCP server 或 release workflow。

No automation, package, plugin, MCP server, or release workflow is included.

## License / 许可证

MIT License.

详见 `LICENSE`。 / See `LICENSE` for details.
