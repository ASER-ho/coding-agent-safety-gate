# Safety Boundaries

This document defines the default safety boundaries for `coding-agent-safety-gate`.

## Secret-Safe

AI agents must not read, print, copy, store, infer, or request real secrets.

Secrets include:

- API keys
- tokens
- passwords
- cookies
- private keys
- SecretStore secrets
- production credentials
- private customer data

Documentation must use placeholders such as `YOUR_API_KEY_HERE`, `EXAMPLE_TOKEN`, or `REDACTED`.

## Path-Safe

AI agents should avoid writing full private local paths into public project documents, examples, or reports.

Prefer relative paths:

- `.ai/NEXT_TASK.md`
- `README.md`
- `src/example.ts`

Avoid machine-specific paths that reveal a user name, home directory, private workspace, or organization structure.

## Git-Safe

AI agents must not perform git operations that publish, rewrite, or connect a repository without human approval.

Explicitly forbidden without human approval:

- `git push`
- `git tag`
- release creation
- adding a remote
- modifying a remote
- force push
- history rewrite

The agent may inspect local status or diffs when needed for an approved task, but it must not publish or release.

## Env-Safe

AI agents must not modify:

- system environment variables
- shell profiles
- registry settings
- VS Code global configuration
- global editor settings
- machine-level credentials
- global agent configuration

If an environment change appears necessary, the agent must stop and ask the human.

## Execution-Safe

AI agents must not run destructive or broad execution steps without explicit approval.

Examples requiring approval:

- deleting files outside the approved scope
- deleting non app-managed files
- installing packages
- starting background services
- starting another AI agent
- starting a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- clicking Terminal start
- creating automation
- creating GitHub Actions
- creating release workflows
- modifying system configuration

## Evidence-Based Acceptance

AI agents must provide evidence before declaring work complete.

Evidence should include:

- files changed
- files intentionally left unchanged when relevant
- commands or checks used for verification
- verification results
- risks
- incomplete work
- required human approvals
- final status: `PASS`, `FAIL`, `BLOCKED`, or `NEEDS HUMAN REVIEW`

## Explicitly Forbidden Autonomous Actions

The AI agent must not independently:

- push
- tag
- release
- add a remote
- modify a remote
- deploy
- change system configuration
- read real secrets
- expose real secrets
- read SecretStore secrets
- expose full private local paths
- start another agent
- start a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- click Terminal start
- invent the next task

When a decision is needed, the agent should stop and ask the human.

## One Layer, Not the Whole Safety System

This project provides one layer of a workflow safety stack. It is not a complete safety system on its own.

It does not replace:

- sandboxing
- least-privilege credentials
- backup and rollback
- runtime command blocking
- secret scanning
- human code review

Its job is narrower: make task boundaries, forbidden actions, evidence requirements, and human handoff explicit and reviewable before and after each AI-assisted change.

If you need hard runtime interception of dangerous commands, pair this project with dedicated runtime enforcement tools, pre-action authorization middleware, or sandboxed execution environments.
