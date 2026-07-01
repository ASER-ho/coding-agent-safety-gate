# AGENTS.md

This file is read by AI coding agents (Claude Code, Codex, Cursor, Gemini CLI, and others) when they enter this repository. It defines the safety constraints they must follow.

## Repository type

This repository is **documentation-first**. It contains only Markdown files: a skill definition, templates, docs, and examples. There is no runtime code, no package.json, no dependencies, and no automation.

## Rules for AI coding agents

When working in this repository:

- Prefer small, Markdown-only changes.
- Do not add a CLI, MCP server, VS Code plugin, npm package, runtime enforcement tool, secret scanner, GitHub Actions workflow, release automation, or any dependency.
- Do not read, print, infer, request, or store real secrets (API keys, tokens, cookies, private keys, credentials, or SecretStore values).
- Do not expose full local machine paths in any file.
- Do not run `git push`, `git tag`, create a release, add a remote, force push, or rewrite history without explicit human approval.
- Do not decide the next task without human confirmation.
- Provide evidence before claiming work is complete.
- If task scope is unclear, stop and mark `NEEDS HUMAN REVIEW`.
