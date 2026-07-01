# PROJECT_RULES

Copy this file into your own project. Fill in your project details. Review with your team.

## Project Scope

Project name: basic-ai-project (example)

Project purpose: A demo project for testing safe AI-assisted documentation and code changes.

In scope:

- Edit README.md when approved by NEXT_TASK.md
- Edit documentation files under docs/
- Report evidence after every task

Out of scope:

- Production deployment
- Database schema changes
- Adding third-party services

## Allowed Actions

The AI agent may:

- read files necessary for the approved NEXT_TASK.md
- edit files explicitly listed in the approved NEXT_TASK.md
- run validation commands explicitly listed in the approved NEXT_TASK.md
- report evidence, risks, and incomplete work

## Forbidden Actions

The AI agent must not:

- expand scope without human approval
- decide the next task
- edit forbidden files
- perform forbidden changes
- perform broad refactors unless explicitly approved
- add dependencies, packages, plugins, MCP servers, GitHub Actions, release workflows, or automation unless explicitly approved
- claim completion without evidence

## Secret Safety

The AI agent must not read, print, store, infer, or request real secrets, including:

- API keys
- tokens
- passwords
- cookies
- private keys
- SecretStore secrets
- production credentials
- private customer data

Use placeholders such as YOUR_API_KEY_HERE, EXAMPLE_TOKEN, or REDACTED.

## Path Safety

The AI agent must not introduce full private local paths into project documents, examples, reports, issues, commits, or public output.

Allowed path style:

- README.md
- .ai/NEXT_TASK.md
- src/example.ts

## Git Safety

The AI agent must not run or configure:

- git push
- git tag
- release creation
- remote creation or modification
- force push
- history rewrite

These actions require explicit human approval.

## System Modification Safety

The AI agent must not modify:

- system environment variables
- registry settings
- shell profiles
- VS Code global configuration
- global IDE or editor settings
- machine-level credentials
- global agent configuration

## Agent Startup Safety

The AI agent must not:

- start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- start another agent runtime
- click Terminal start
- start unrelated background services or automation

## Deletion Safety

The AI agent must not delete:

- non app-managed files
- files outside the approved task scope
- generated files unless the task explicitly permits cleanup

## Evidence Requirement

Before claiming completion, the AI agent must provide:

- changed files
- summary of changes
- validation commands or manual checks
- validation results
- known risks
- incomplete items
- final status: PASS, FAIL, BLOCKED, or NEEDS HUMAN REVIEW

## Human Approval Requirement

Human approval is required before:

- expanding file scope
- changing the task goal
- adding dependencies
- deleting files
- modifying system configuration
- reading sensitive files
- pushing, tagging, releasing, deploying, or adding a remote
- starting another AI agent or automation

When uncertain, stop and mark the work NEEDS HUMAN REVIEW.
