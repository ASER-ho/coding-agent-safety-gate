# Coding Agent Safety Gate

`coding-agent-safety-gate` is a documentation-first safety gate for AI coding agents: task boundaries, forbidden actions, and evidence-based acceptance.

Stop AI coding agents from drifting, over-editing, leaking secrets, or declaring work done without evidence.

In Chinese: 防止 AI 编程助手跑偏、越权修改、泄露敏感信息，或在没有证据时声称完成。

This project provides workflow guardrails, not runtime enforcement.

## First Screen

This project provides a copyable skill and a small set of Markdown templates that help humans define task boundaries before an AI coding agent starts work.

v0.1 is intentionally small. It contains only Markdown documentation, a skill file, templates, docs, and examples. It does not run code, install dependencies, manage releases, scan secrets, or replace human judgment.

Use it when you want an AI coding agent to:

- stay inside an approved task scope
- avoid touching unrelated files
- avoid reading or exposing real secrets
- ask for human approval at decision points
- provide evidence before claiming completion
- hand off work clearly to the next human or agent

## What Problem It Solves

AI coding agents are powerful, but they can drift from the original request, edit too broadly, infer permission they were never given, or report success without proof.

This project gives teams a lightweight protocol for:

- defining project-level safety rules
- defining the next task in a narrow, reviewable way
- requiring evidence-based acceptance
- recording what actually changed
- supporting human-in-the-loop multi-agent workflows

## What It Is Not

`coding-agent-safety-gate` is not:

- an agent runtime
- an automated development platform
- a code review tool
- a release tool
- a secret scanner
- an MCP server
- a Provider Gateway
- a VS Code plugin
- an npm package in v0.1
- the Claude Workspace Desktop main project
- an automated project manager
- a fully autonomous programming agent

## Target Users

This project is for:

- developers using Claude Code, Codex, Cursor, Gemini CLI, or similar coding agents
- maintainers who want safer AI-assisted contributions
- teams experimenting with multi-agent development
- humans who want AI agents to produce verifiable work instead of broad claims
- open source projects that want a simple safety protocol before adding automation

## Quick Start

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

## Recommended `.ai/` File Protocol

The `.ai/` layout is a recommended workflow convention. v0.1 does not implement an automatic protocol, runtime, watcher, or required directory structure.

A normal project can choose to include:

```text
.ai/
├── PROJECT_RULES.md
├── NEXT_TASK.md
├── ACCEPTANCE_CHECKLIST.md
├── AGENT_EXECUTION_REPORT.md
└── HANDOFF.md
```

Recommended roles:

- `PROJECT_RULES.md`: stable project boundaries and safety rules
- `NEXT_TASK.md`: the only task the agent is currently allowed to perform
- `ACCEPTANCE_CHECKLIST.md`: evidence-based completion checklist
- `AGENT_EXECUTION_REPORT.md`: factual report of what happened
- `HANDOFF.md`: current state for the next human or AI agent

The files can be used with any coding agent. The `AGENT_EXECUTION_REPORT.md` template is tool-neutral and works with Claude Code, Codex, Cursor, Gemini CLI, or other AI coding agents.

## Human-In-The-Loop Workflow

This project assumes humans own decisions and AI agents execute bounded tasks.

Recommended flow:

1. A human defines project rules in `.ai/PROJECT_RULES.md`.
2. A human writes or approves `.ai/NEXT_TASK.md`.
3. The AI agent reads the rules and task before editing.
4. The AI agent works only inside the approved file and action scope.
5. The AI agent stops and asks for approval when the task requires a decision outside the current scope.
6. The AI agent provides evidence, including changed files and verification results.
7. A human reviews the acceptance checklist.
8. A human decides the next task.

AI agents should not decide the next product direction, expand the task scope, push code, create releases, add remotes, or change system configuration without explicit human approval.

## Safety Boundaries

The default safety boundaries are:

- Secret-safe: do not read, print, infer, store, or request real API keys, tokens, credentials, cookies, private keys, or production secrets.
- Path-safe: do not expose full local machine paths in project documents or reports unless the human explicitly requests it for local debugging.
- Git-safe: do not run `git push`, `git tag`, release creation, remote creation, force push, or history rewrite without explicit human approval.
- Env-safe: do not modify system environment variables, shell profiles, registry settings, IDE settings, or global configuration.
- Execution-safe: do not run destructive commands, install new automation, or start unrelated agents without approval.
- Agent-startup-safe: do not start a real Claude, Codex, Cursor, Gemini CLI, or other agent process, and do not click Terminal start, unless explicitly approved.
- Evidence-based acceptance: do not claim done without listing what changed and how it was verified.

## Prior Art and Differentiation

There are already runtime guardrail, hook-based enforcement, pre-action authorization, and AGENTS.md security-template projects for AI coding agents.

This project is intentionally narrower.

`coding-agent-safety-gate` is documentation-first. It does not install hooks, block shell commands at runtime, modify editor or agent configuration, provide a CLI, ship an MCP server, publish an npm package, or act as a pre-action authorization layer.

It focuses on a lightweight workflow layer:

- define one bounded task;
- declare allowed and forbidden files;
- make forbidden actions explicit;
- require evidence before claiming completion;
- preserve human decision-making through handoff templates.

Use it as a workflow guardrail. For hard runtime enforcement, combine it with sandboxing, scoped credentials, hook-based tools, or pre-action authorization systems.

## Example Task

Example `.ai/NEXT_TASK.md` task:

```text
Update README.md to clarify the project description.

Allowed files:
- README.md

Allowed operations:
- Edit wording in the introduction.
- Add one short usage example.

Forbidden operations:
- Do not change package configuration.
- Do not add scripts.
- Do not read secrets.
- Do not push, tag, release, or add a remote.

Acceptance:
- README introduction is clearer.
- No unrelated files changed.
- Agent reports changed files and verification steps.
```

See `examples/basic-ai-project/README.md` for a minimal example.

## v0.1 Public Repository Standard

This v0.1 repository includes:

- complete documented structure
- MIT License
- README that clearly explains the scope
- copyable skill file
- copyable task, rules, acceptance, execution report, and handoff templates
- example usage
- no real secrets, tokens, private paths, or private repository remotes
- no npm package, VS Code plugin, MCP server, GitHub Actions, runtime enforcement, or release workflow in v0.1

This repository is intended to remain documentation-and-template-only in v0.1. Any public release, tag, or automation should be reviewed and approved by a human.

## Roadmap

The following items are future / planned ideas, not completed features:

- future / planned: more example workflows for Codex, Claude Code, Cursor, and Gemini CLI
- future / planned: team policy examples for open source maintainers
- future / planned: optional checklist variants for security-sensitive repositories
- future / planned: comparison guide for different AI coding agent environments
- future / planned: lightweight examples for multi-agent handoff patterns

No automation, package, plugin, MCP server, or release workflow is included in this first version.

## License

MIT License.

See `LICENSE` for details.
