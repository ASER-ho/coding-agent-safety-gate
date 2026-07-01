# Coding Agent Safety Gate / 编程助手安全门禁

面向 AI 编程助手的文档优先安全门禁：任务边界、禁止操作与证据型验收。

A documentation-first safety gate for AI coding agents: task boundaries, forbidden actions, and evidence-based acceptance.

防止 AI 编程助手跑偏、越权修改、泄露敏感信息，或在没有证据时声称完成。

Stop AI coding agents from drifting, over-editing, leaking secrets, or declaring work done without evidence.

本项目提供的是工作流护栏，不是运行时强制执行。

This project provides workflow guardrails, not runtime enforcement.

## Use in 60 Seconds / 60 秒上手

无需安装。无需 CLI。无需依赖。无需 runtime enforcement。用户保留最终决定权。

1. 打开 **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)** — 把提示词复制到 Claude Code、Codex、Cursor、Gemini CLI 或其他 AI 编程助手。
2. 把 **[templates/](templates/)** 中的模板复制到你的项目，建议放在 `.ai/` 下。
3. 填写一次 `PROJECT_RULES.md`，每次任务前填写 `NEXT_TASK.md`。
4. 告诉 Agent 只完成被批准的任务并返回证据。
5. 在 commit、push、tag 或 release 之前审查结果。

更多选项（包括自定义 skill 设置）见 **[QUICKSTART.md](QUICKSTART.md)**。

---

No install. No CLI. No dependencies. No runtime enforcement. Human owns final decisions.

1. Open **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)** — copy the prompt into Claude Code, Codex, Cursor, Gemini CLI, or another AI coding agent.
2. Copy the templates from **[templates/](templates/)** into your project, preferably under `.ai/`.
3. Fill in `PROJECT_RULES.md` once and `NEXT_TASK.md` before each task.
4. Ask the agent to complete only the approved task and return evidence.
5. Review the result before commit, push, tag, or release.

See **[QUICKSTART.md](QUICKSTART.md)** for more options, including custom skill setup.

## First Screen / 首屏

本项目提供一套可复制的 skill 和少量 Markdown 模板，帮助用户在 AI 编程助手开始工作前定义任务边界。v0.1 刻意保持小巧，只包含 Markdown 文档、一个 skill 文件、模板、文档和示例。不运行代码、不安装依赖、不管理 release、不扫描 secret、不替代用户判断。

This project provides a copyable skill and a small set of Markdown templates that help humans define task boundaries before an AI coding agent starts work. v0.1 is intentionally small. It contains only Markdown documentation, a skill file, templates, docs, and examples. It does not run code, install dependencies, manage releases, scan secrets, or replace human judgment.

在以下场景使用 / Use it when you want an AI coding agent to:

- 待在批准的任务范围内 / stay inside an approved task scope
- 避免接触无关文件 / avoid touching unrelated files
- 避免读取或暴露真实机密 / avoid reading or exposing real secrets
- 在决策点请求用户批准 / ask for human approval at decision points
- 声称完成之前提供证据 / provide evidence before claiming completion
- 清晰地将工作交接给下一个人或 Agent / hand off work clearly to the next human or agent

## What Problem It Solves / 解决的问题

AI 编程助手很强大，但可能偏离原始需求、编辑范围过宽、推断从未被授予的权限，或没有证据就报告成功。本项目为团队提供一套轻量级协议：定义项目级安全规则、以窄范围可审查的方式定义下一个任务、要求证据型验收、记录实际变更了什么、支持 human-in-the-loop 多 Agent 工作流。

AI coding agents are powerful, but they can drift from the original request, edit too broadly, infer permission they were never given, or report success without proof. This project gives teams a lightweight protocol for: defining project-level safety rules, defining the next task in a narrow reviewable way, requiring evidence-based acceptance, recording what actually changed, and supporting human-in-the-loop multi-agent workflows.

## What It Is Not / 不是什么

`coding-agent-safety-gate` 不是 Agent runtime、自动化开发平台、代码审查工具、发布工具、机密扫描器、MCP server、Provider Gateway、VS Code 插件、npm 包、Claude Workspace Desktop 主项目、自动化项目管理者、全自动编程 Agent。

`coding-agent-safety-gate` is not: an agent runtime, an automated development platform, a code review tool, a release tool, a secret scanner, an MCP server, a Provider Gateway, a VS Code plugin, an npm package, the Claude Workspace Desktop main project, an automated project manager, or a fully autonomous programming agent.

## Target Users / 目标用户

本项目面向使用 Claude Code、Codex、Cursor、Gemini CLI 等编程助手的开发者、希望 AI 辅助贡献更安全的维护者、实验多 Agent 开发的团队、希望 AI Agent 产出可验证工作而非笼统声称的用户、以及在加自动化之前想先有一套简单安全协议的开源项目。

This project is for: developers using Claude Code, Codex, Cursor, Gemini CLI, or similar coding agents; maintainers who want safer AI-assisted contributions; teams experimenting with multi-agent development; humans who want AI agents to produce verifiable work instead of broad claims; and open source projects that want a simple safety protocol before adding automation.

## Quick Start / 快速开始

1. 将 `skills/coding-agent-safety-gate/SKILL.md` 复制到支持自定义 skills 或指令的 AI 编码环境中。
2. 可选：在项目中创建 `.ai/` 目录作为可读的工作流约定。
3. 将 `templates/` 中的模板复制到该目录。
4. 为项目填写一次 `PROJECT_RULES.md`，每次 Agent 任务前填写 `NEXT_TASK.md`。
5. 让 Agent 遵守 skill 和复制的模板文件。
6. 要求 Agent 在声称完成之前填写 `AGENT_EXECUTION_REPORT.md` 或等效的执行报告。
7. 使用 `ACCEPTANCE_CHECKLIST.md` 验证结果。
8. 当工作需要在另一个会话或与另一个 Agent 继续时，更新 `HANDOFF.md`。

无需安装任何依赖。

---

1. Copy `skills/coding-agent-safety-gate/SKILL.md` into the AI coding agent environment that supports custom skills or instructions.
2. Optionally create a `.ai/` directory inside your project as a human-readable workflow convention.
3. Copy the templates from `templates/` into that directory or another documented location.
4. Fill in `PROJECT_RULES.md` once for the project.
5. Fill in `NEXT_TASK.md` before each agent task.
6. Ask the agent to follow the skill and the copied template files.
7. Require the agent to complete `AGENT_EXECUTION_REPORT.md` or an equivalent execution report before claiming done.
8. Use `ACCEPTANCE_CHECKLIST.md` to verify the result.
9. Update `HANDOFF.md` when work should continue in another session or with another agent.

No dependency installation is required.

## Recommended `.ai/` File Protocol / 推荐的 .ai/ 文件协议

`.ai/` 布局是一个推荐的工作流约定，不实现自动协议、运行时、监控或必需的目录结构。

The `.ai/` layout is a recommended workflow convention. v0.1 does not implement an automatic protocol, runtime, watcher, or required directory structure.

```text
.ai/
├── PROJECT_RULES.md     ← 稳定项目边界和安全规则 / stable project boundaries and safety rules
├── NEXT_TASK.md         ← Agent 当前唯一被允许执行的任务 / the only task currently authorized
├── ACCEPTANCE_CHECKLIST.md ← 证据型完成检查清单 / evidence-based completion checklist
├── AGENT_EXECUTION_REPORT.md ← 实际发生了什么的事实报告 / factual report of what happened
└── HANDOFF.md           ← 下一个用户或 AI Agent 的当前状态 / current state for the next human or AI agent
```

这些文件可用于任何编程 Agent。`AGENT_EXECUTION_REPORT.md` 模板是工具中立的，适用于 Claude Code、Codex、Cursor、Gemini CLI 或其他 AI 编程助手。

The files can be used with any coding agent. The `AGENT_EXECUTION_REPORT.md` template is tool-neutral and works with Claude Code, Codex, Cursor, Gemini CLI, or other AI coding agents.

## Human-In-The-Loop Workflow / 人机协作工作流

本项目假定用户拥有决策权，AI Agent 执行有边界的任务。用户在 `.ai/PROJECT_RULES.md` 中定义项目规则，编写或批准 `.ai/NEXT_TASK.md`。AI Agent 在编辑前读取规则和任务，只在批准的文件和操作范围内工作。当任务需要超出范围的决定时停下来请求批准，提供包括变更文件和验证结果在内的证据。用户审查验收清单后决定下一步任务。

AI Agent 不应自行决定下一步产品方向、扩大任务范围、push 代码、创建 release、添加 remote 或更改系统配置，除非获得用户明确批准。

---

This project assumes humans own decisions and AI agents execute bounded tasks. A human defines project rules in `.ai/PROJECT_RULES.md`, writes or approves `.ai/NEXT_TASK.md`. The AI agent reads the rules and task before editing, works only inside the approved file and action scope, stops and asks for approval when the task requires a decision outside the current scope, and provides evidence including changed files and verification results. A human reviews the acceptance checklist and decides the next task.

AI agents should not decide the next product direction, expand the task scope, push code, create releases, add remotes, or change system configuration without explicit human approval.

## Safety Boundaries / 安全边界

- **机密安全 / Secret-safe**：不读取、打印、推断、存储或请求真实 API key、token、凭据、cookie、私钥或生产机密。
- **路径安全 / Path-safe**：不在项目文档或报告中暴露完整的本地机器路径，除非用户明确要求用于本地调试。
- **Git 安全 / Git-safe**：未经用户明确批准，不执行 `git push`、`git tag`、release 创建、remote 创建、force push 或历史重写。
- **环境安全 / Env-safe**：不修改系统环境变量、shell 配置、注册表设置、IDE 设置或全局配置。
- **执行安全 / Execution-safe**：未经批准，不运行破坏性命令、安装新自动化或启动不相关的 Agent。
- **Agent 启动安全 / Agent-startup-safe**：未经明确批准，不启动真实的 Claude、Codex、Cursor、Gemini CLI 或其他 Agent 进程，不点击 Terminal start。
- **证据型验收 / Evidence-based acceptance**：不列出变更了什么以及如何验证的，不声称完成。

The default safety boundaries are: Secret-safe, Path-safe, Git-safe, Env-safe, Execution-safe, Agent-startup-safe, and Evidence-based acceptance.

## Prior Art and Differentiation / 先行者与差异化

AI 编程助手领域已有 runtime guardrail、hook-based enforcement、pre-action authorization 以及 AGENTS.md security-template 项目。本项目刻意更窄：一个纯粹的 Markdown 工作流层。大多数 guardrail 项目加 hooks、MCP server 或 runtime enforcement，这个项目一个都不加。

`coding-agent-safety-gate` 是文档优先的：不安装 hooks、不在运行时阻塞 shell 命令、不修改编辑器或 Agent 配置、不提供 CLI、不发布 MCP server、不发布 npm 包、不作为 pre-action authorization 层。聚焦于轻量级工作流层：定义边界任务、声明允许和禁止的文件、把禁止的动作写明确、要求提供证据才声称完成、通过 handoff 模板保留用户决策权。

把它当工作流护栏用。如果需要硬性运行时拦截，请结合沙箱、最小权限凭据、hook-based 工具或 pre-action authorization 系统使用。

---

There are already runtime guardrail, hook-based enforcement, pre-action authorization, and AGENTS.md security-template projects for AI coding agents. This project is intentionally narrower: a pure Markdown workflow layer. Most guardrail projects add hooks, MCP servers, or runtime enforcement. This one doesn't.

`coding-agent-safety-gate` is documentation-first. It does not install hooks, block shell commands at runtime, modify editor or agent configuration, provide a CLI, ship an MCP server, publish an npm package, or act as a pre-action authorization layer. It focuses on a lightweight workflow layer: define one bounded task; declare allowed and forbidden files; make forbidden actions explicit; require evidence before claiming completion; preserve human decision-making through handoff templates.

Use it as a workflow guardrail. For hard runtime enforcement, combine it with sandboxing, scoped credentials, hook-based tools, or pre-action authorization systems.

## v0.1 Public Repository Standard / v0.1 公开仓库标准

此仓库包含完整的文档化结构、MIT License、清楚说明范围的 README、可复制的 skill 文件、可复制的任务/规则/验收/执行报告/handoff 模板、示例用法，没有真实机密/token/私有路径/私有仓库 remote，没有 npm 包、VS Code 插件、MCP server、GitHub Actions、runtime enforcement 或 release workflow。本仓库旨在保持文档和模板形态。任何公开发布、tag 或自动化应由用户审查和批准。

This v0.1 repository includes complete documented structure, MIT License, README that clearly explains the scope, copyable skill file, copyable task/rules/acceptance/execution report/handoff templates, and example usage — with no real secrets, tokens, private paths, or private repository remotes, and no npm package, VS Code plugin, MCP server, GitHub Actions, runtime enforcement, or release workflow. This repository is intended to remain documentation-and-template-only. Any public release, tag, or automation should be reviewed and approved by a human.

## Roadmap / 路线图

**已在 v0.2 完成 / Completed in v0.2：** 社区文件（AGENTS、SECURITY、CONTRIBUTING、issue/PR 模板）、审查和脱敏清单、Codex 和 Claude Code 的示例工作流。

**已在 v0.2.1 完成 / Completed in v0.2.1：** 快速入门指南和复制粘贴提示词、`.ai/` 示例目录。

**未来 / 计划中 / Future / planned：** Cursor 和 Gemini CLI 示例、开源维护者团队策略示例、安全敏感仓库的可选清单变体、不同 AI 编程环境的比较指南、多 Agent handoff 模式的轻量示例。

不包含任何自动化、包、插件、MCP server 或 release workflow。No automation, package, plugin, MCP server, or release workflow is included.

## License / 许可证

MIT License。详见 `LICENSE`。
