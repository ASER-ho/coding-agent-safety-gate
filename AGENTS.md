# AGENTS / 代理规则

本文件由 AI 编程助手（Claude Code、Codex、Cursor、Gemini CLI 等）进入仓库时读取，定义它们必须遵守的安全约束。

This file is read by AI coding agents (Claude Code, Codex, Cursor, Gemini CLI, and others) when they enter this repository. It defines the safety constraints they must follow.

## 仓库类型 / Repository type

本仓库是**文档优先**的。只包含 Markdown 文件：一个 skill 定义、模板、文档和示例。没有运行时代码、没有 package.json、没有依赖、没有自动化。

This repository is **documentation-first**. It contains only Markdown files: a skill definition, templates, docs, and examples. There is no runtime code, no package.json, no dependencies, and no automation.

## AI 代理规则 / Rules for AI coding agents

在本仓库工作时：

- **规则 #1 — 在违反本文件任何规则之前，必须先停下来，获得用户的明确批准。**
- 优先做小的、仅 Markdown 的改动。
- 不要新增 CLI、MCP server、VS Code 插件、npm 包、runtime enforcement 工具、secret scanner、GitHub Actions 工作流、release 自动化或任何依赖。
- 不要读取、打印、推断、请求或存储真实机密（API key、token、cookie、私钥、凭据或 SecretStore 值）。
- 不要在任何文件中暴露完整的本地机器路径。
- 未经用户明确批准，不要执行 `git push`、`git tag`、创建 release、添加 remote、force push 或重写历史。
- 未经用户确认，不要决定下一步任务。
- 在声称完成工作之前提供证据。
- 如果任务范围不清晰，停止并标记 `NEEDS HUMAN REVIEW`。

When working in this repository:

- **Rule #1 — stop and get explicit human approval before breaking any rule in this file.**
- Prefer small, Markdown-only changes.
- Do not add a CLI, MCP server, VS Code plugin, npm package, runtime enforcement tool, secret scanner, GitHub Actions workflow, release automation, or any dependency.
- Do not read, print, infer, request, or store real secrets (API keys, tokens, cookies, private keys, credentials, or SecretStore values).
- Do not expose full local machine paths in any file.
- Do not run `git push`, `git tag`, create a release, add a remote, force push, or rewrite history without explicit human approval.
- Do not decide the next task without human confirmation.
- Provide evidence before claiming work is complete.
- If task scope is unclear, stop and mark `NEEDS HUMAN REVIEW`.
