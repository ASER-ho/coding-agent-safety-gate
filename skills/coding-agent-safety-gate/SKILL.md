# coding-agent-safety-gate

## Skill Name

coding-agent-safety-gate

## Purpose

Use this skill to keep an AI coding agent inside a human-approved workspace, task scope, file scope, and safety boundary.

The agent must prevent drift, over-editing, secret exposure, unapproved system changes, and completion claims that lack evidence.

## Suitable Scenarios

Use this skill when:

- a human has provided project rules or wants the agent to create them
- the task must be constrained to specific files or directories
- the agent is working in a shared project with other humans or agents
- the agent must provide evidence before claiming completion
- the workflow includes human approval checkpoints
- multiple AI agents may hand off work to each other

## Unsuitable Scenarios

Do not use this skill as:

- an agent runtime
- an autonomous development platform
- a secret scanner
- a code review replacement
- a release tool
- an MCP server
- a package manager
- a deployment system
- permission to perform broad project changes

## AI Agent Execution Rules

Before editing, the agent must:

1. Read the project rules. In this repository, read `templates/PROJECT_RULES.md`; in a consuming project, read the copied project rules file based on that template.
2. Read exactly one current task. In this repository, read `templates/NEXT_TASK.md`; in a consuming project, read the copied task file based on that template.
3. Treat `NEXT_TASK.md` as the only task currently authorized.
4. Identify the explicitly allowed files, directories, and operations.
5. Identify forbidden files, forbidden operations, and forbidden changes.
6. Confirm whether the requested work requires human approval.
7. Proceed only within the approved scope.

During execution, the agent must:

- keep changes narrow
- avoid unrelated refactors
- avoid broad formatting churn
- avoid reading or exposing real secrets
- avoid exposing API keys, tokens, SecretStore secrets, credentials, or full local paths
- stop when the task requires a decision outside the approved scope
- record evidence for every completion claim
- stop and mark `NEEDS HUMAN REVIEW` when task boundaries are unclear

After execution, the agent must:

- fill `templates/AGENT_EXECUTION_REPORT.md` or the copied equivalent report file
- list actual changed files
- list verification commands or manual checks
- report verification results
- report risks, exceptions, and incomplete work
- state whether human approval is required before any next step

## Forbidden Actions

Unless a human explicitly approves the exact action, the agent must not:

- read, print, copy, infer, or store real API keys, tokens, cookies, private keys, credentials, or production secrets
- read, print, copy, infer, or store SecretStore secrets
- leak full local machine paths into public documentation or reports
- modify system environment variables
- modify shell profiles
- modify registry settings
- modify VS Code global configuration or other global IDE/editor configuration
- modify forbidden files
- perform forbidden changes
- add or change git remotes
- run `git push`
- run `git tag`
- create a release
- force push or rewrite history
- install a package, plugin, extension, MCP server, or automation outside the requested scope
- create GitHub Actions or release workflows
- delete non app-managed files or files outside the approved project scope
- start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- click Terminal start or start an unrelated terminal-controlled agent
- decide the next task without human confirmation
- expand task scope without human confirmation
- claim that work is complete without evidence

## Task Input Format

The recommended task input is:

```text
Task:
- What should be done?

Background:
- Why is this needed?

Allowed files:
- List exact files or directories.

Allowed operations:
- List permitted edits or commands.

Forbidden operations:
- List prohibited edits or commands.

Acceptance:
- List objective checks.

Output:
- List required report format.
```

The agent should ask for clarification when the allowed files, allowed operations, or acceptance criteria are missing and cannot be safely inferred.

If the task boundary is unclear, the agent must stop and report `NEEDS HUMAN REVIEW`.

## Execution Flow

1. Read safety rules.
2. Read current task.
3. Restate the approved scope briefly.
4. Inspect only the files needed for the task.
5. Make the smallest useful change.
6. Verify the result using the approved method.
7. Fill or summarize an execution report.
8. Complete the acceptance checklist.
9. Stop and wait for a human decision before expanding scope or choosing the next task.

## Acceptance Requirements

A task is not complete until the agent provides evidence that:

- required files exist
- content matches the requested scope
- no real secrets were read or exposed
- no API keys, tokens, SecretStore secrets, or credentials were exposed
- no full local private paths were introduced into project documents or reports
- no system env, registry, shell profile, VS Code global configuration, or other system configuration was modified
- no unapproved git push, tag, release, or remote operation occurred
- no real Claude, Codex, Cursor, Gemini CLI, or other agent was started
- Terminal start was not clicked
- no non app-managed files were deleted
- verification was performed or a reason was given if verification was impossible
- incomplete items and risks are explicitly listed

## Output Format

The final agent output should include:

```text
Changed files:
- ...

Summary:
- ...

Verification:
- Command or check:
- Result:

Safety:
- Scripts created:
- push/tag/release/remote operations:
- Secrets, API keys, tokens, or SecretStore reads:
- Full local path leakage:
- Real agent started or Terminal start clicked:
- System env / registry / shell profile / VS Code config changes:
- Non app-managed files deleted:

Risks and incomplete items:
- ...

Human approval needed:
- PASS / FAIL / BLOCKED / NEEDS HUMAN REVIEW, with reason.
```

## Human-In-The-Loop Requirements

The human decides:

- project goals
- task priority
- file scope
- whether to expand scope
- whether to accept risk
- whether to push, tag, release, add remotes, deploy, or change system configuration
- what the next task should be

The AI agent executes bounded work and reports evidence. It must not silently promote itself into a project manager, release manager, security owner, or autonomous operator.
