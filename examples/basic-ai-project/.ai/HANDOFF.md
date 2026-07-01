# HANDOFF

Use this document to transfer context from one human or AI agent session to the next. Copy into your own project.

## Project Positioning

Project name: basic-ai-project (example)

Project purpose: A demo project for testing safe AI-assisted documentation and code changes.

This project is:

- A small demo for practicing safe AI coding agent workflows

This project is not:

- A production application
- A hosted service
- A library or framework

## Current Status

- README introduction was updated in the last task. Diff reviewed and accepted.

## Last Completed Task

- Updated README.md introduction. Added one sentence explaining the project.

Evidence:

- git diff README.md shows the exact change
- ACCEPTANCE_CHECKLIST.md completed and passed
- No other files modified

## Current Risks

- None. The project is a demo with no production dependencies or sensitive data.

## Next Task

Proposed next task:

- Add a "Getting Started" section to README.md

Human approval status:

- [ ] Approved
- [x] Not approved
- [ ] Needs discussion

## Acceptance Requirements

The next task is acceptable only if:

- NEXT_TASK.md is filled in and reviewed by a human
- The task stays within README.md
- No files outside the allowed list are touched

## Open Questions

- Should the project add a CONTRIBUTING.md?
- Should screenshots be added to the README?

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
- run git push, git tag, create a release, or add or modify a remote
- claim completion without evidence

## Context For The Next AI Agent

Read these files before doing work:

- PROJECT_RULES.md
- NEXT_TASK.md
- ACCEPTANCE_CHECKLIST.md
- HANDOFF.md

Follow the current task exactly. If the next step is unclear, stop and mark NEEDS HUMAN REVIEW.
