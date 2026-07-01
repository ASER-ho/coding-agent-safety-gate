# Contributing

Thank you for considering a contribution to `coding-agent-safety-gate`.

## What we welcome

This project is documentation-first. Contributions are welcome in these areas:

- documentation improvements
- template improvements
- checklist improvements
- examples for coding-agent workflows (Claude Code, Codex, Cursor, Gemini CLI, and others)
- clearer safety boundaries and guardrail language

## What we do not accept in v0.1

To keep the project focused, we are not accepting contributions for:

- CLI tools
- MCP servers
- VS Code plugins
- npm packages
- runtime enforcement
- secret scanners
- GitHub Actions
- release automation
- dependency additions
- autonomous push, tag, or release workflows

These may be considered for future versions after community discussion.

## Pull request requirements

Every pull request should include:

- **Changed files** — list every file modified or added
- **Purpose** — why the change is needed
- **Scope check** — does the change stay within documentation-and-template-only?
- **Safety boundary check** — does the change involve secrets, full paths, environment variables, system configuration, git remotes, push, tag, release, or dependencies?
- **Redaction check** — confirm no real API keys, tokens, credentials, full local paths, or private URLs appear
- **Verification evidence** — how was the change tested or reviewed?
- **Human review** — is human approval required before merge?

## Before you start

Read `AGENTS.md` for the safety rules that apply to all AI coding agents working in this repository.
