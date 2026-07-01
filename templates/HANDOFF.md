# HANDOFF

Use this document to transfer context from one human or AI agent session to the next.

## Project Positioning

Project name:

Project purpose:

This project is:

- 

This project is not:

- 

## Current Status

- 

## Last Completed Task

- 

Evidence:

- 

## Current Risks

- 

## Next Task

Proposed next task:

- 

Human approval status:

- [ ] Approved
- [ ] Not approved
- [ ] Needs discussion

## Acceptance Requirements

The next task is acceptable only if:

- 

## Open Questions

- 

## Do-Not-Do List

The next AI agent must not:

- expand scope without human approval
- decide the next task
- edit files outside the approved task
- edit forbidden files
- perform forbidden changes
- read or expose real secrets, API keys, tokens, credentials, or SecretStore secrets
- introduce full private local paths
- modify system env, registry, shell profile, VS Code global config, or other system configuration
- add dependencies, scripts, packages, plugins, MCP servers, GitHub Actions, release workflows, build outputs, or automation without approval
- start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- click Terminal start
- delete non app-managed files
- run `git push`, `git tag`, create a release, or add or modify a remote
- claim completion without evidence

## Context For The Next AI Agent

Read these files before doing work:

- `PROJECT_RULES.md`
- `NEXT_TASK.md`
- `ACCEPTANCE_CHECKLIST.md`
- `HANDOFF.md`

Follow the current task exactly. If the next step is unclear, stop and mark `NEEDS HUMAN REVIEW`.
