# Project Decision Log

This file records project-level decisions for `coding-agent-safety-gate`.

## 2026-07-01 / v0.1 scope decision

### Decision

Create `ai-workspace-safety-gate` v0.1 as a documentation-and-template-only GitHub repository.

### Reason

The project's first value is to define safe AI coding agent behavior: task boundaries, forbidden actions, evidence-based acceptance, and human-in-the-loop handoff.

A Markdown-first release is lower risk, easier to review, and suitable for open-source validation before adding scripts, CLI, VS Code integration, MCP, or automation.

### Impact Scope

This decision affects:

- README positioning
- Skill instructions
- Project rules
- Task template
- Acceptance checklist
- Execution report
- Handoff document
- Safety boundary documentation
- Basic example

### Safety Boundaries

v0.1 must not include:

- complex scripts
- third-party dependencies
- npm packaging
- VS Code plugins
- MCP server
- GitHub Actions
- push, tag, or release automation
- real secret handling
- real agent startup
- unlicensed external skill code

### Acceptance / Next Actions

Before any public GitHub release, human review must confirm:

- The README does not overclaim.
- The skill file enforces one-task-at-a-time execution.
- Templates are directly usable.
- No real secrets, tokens, API keys, or full local paths are present.
- Future roadmap items are clearly marked as planned, not completed.

## 2026-07-01 / Agent-neutral execution report naming

### Decision

Rename `templates/CLAUDE_EXECUTION_REPORT.md` to `templates/AGENT_EXECUTION_REPORT.md`.

### Reason

`ai-workspace-safety-gate` is designed for Claude Code, Codex, Cursor, Gemini CLI, and other AI coding agents. A Claude-specific report filename could make the project appear narrower than its actual scope.

### Impact scope

This affects the execution report template name and all documentation references to that template.

### Safety boundaries

This change is documentation-only. It must not add scripts, dependencies, automation, GitHub Actions, npm packaging, VS Code integration, MCP, push/tag/release behavior, or real agent startup.

### Acceptance / next actions

All references to `CLAUDE_EXECUTION_REPORT.md` must be replaced with `AGENT_EXECUTION_REPORT.md`. Normal mentions of Claude Code as a supported AI coding agent may remain.

## 2026-07-01 / Rename to Coding Agent Safety Gate

### Decision

Rename the project from `ai-workspace-safety-gate` to `coding-agent-safety-gate`.

### Reason

The project is focused on AI coding agents rather than general AI workspaces. The new name is more precise, easier to understand on GitHub, and less likely to be confused with a general workspace management tool.

The project should not use the crowded `agent-guardrails` name because it may be confused with existing guardrail, runtime enforcement, hook-based, or pre-action authorization projects.

### Impact scope

This affects the project title, repository name recommendation, skill directory name, README references, documentation references, and example references.

### Safety boundaries

This is a documentation-only rename. It must not add scripts, dependencies, npm packaging, GitHub Actions, VS Code integration, MCP, push/tag/release behavior, remote configuration, runtime enforcement, or real agent startup.

### Acceptance / next actions

All active references should use `coding-agent-safety-gate` or `Coding Agent Safety Gate`. Historical references in this decision log may mention the old name only as rename history.
