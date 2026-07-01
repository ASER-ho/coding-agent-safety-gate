# NEXT_TASK

Copy this file into a project-owned location such as `.ai/NEXT_TASK.md`. This file defines exactly one task.

## Task Title


## Stage

- [ ] Planning
- [ ] Implementation
- [ ] Validation
- [ ] Documentation
- [ ] Handoff

## Goal


## Background


## Allowed Files

The AI agent may read or edit only these files or directories:

- 

## Forbidden Files

The AI agent must not read or edit these files or directories:

- 

## Explicitly Allowed Operations

The AI agent may:

- 

## Forbidden Changes

The AI agent must not:

- edit files outside the allowed file list
- edit forbidden files
- expand the task goal
- perform broad refactors
- add dependencies
- create scripts, packages, plugins, MCP servers, GitHub Actions, release workflows, build outputs, or automation unless explicitly listed above
- modify system env, registry, shell profile, VS Code global config, or other system configuration
- start a real Claude, Codex, Cursor, Gemini CLI, or other AI agent process
- click Terminal start
- delete non app-managed files
- run `git push`, `git tag`, create a release, or add or modify a remote

## Safety Constraints

- Do not read or expose real secrets, API keys, tokens, credentials, or SecretStore secrets.
- Do not introduce full private local paths.
- Do not decide the next task.
- Do not claim completion without evidence.

## Steps

1. Read `PROJECT_RULES.md`.
2. Confirm this file defines one clear task.
3. Inspect only allowed files needed for the task.
4. Make the smallest useful change.
5. Run only the validation commands listed below.
6. Fill the execution report.
7. Stop for human review.

## Validation Commands

```text

```

If no command is appropriate, list the manual checks required:

- 

## Acceptance Criteria

The task is acceptable when:

- 

## Expected Output

The AI agent must report:

- changed files
- summary
- why this change was needed
- validation commands
- validation results
- build result, if applicable
- test result, if applicable
- known risks
- incomplete work
- final status: `PASS`, `FAIL`, `BLOCKED`, or `NEEDS HUMAN REVIEW`

## This Task Does Not Include

- 

## Stop Conditions

Stop and mark `NEEDS HUMAN REVIEW` if:

- task boundaries are unclear
- required files are missing
- requested changes conflict with `PROJECT_RULES.md`
- a forbidden file or forbidden change appears necessary
- a real secret, SecretStore value, or private credential would need to be read
- full private local paths would need to be disclosed
- git push, tag, release, remote changes, system configuration changes, agent startup, or Terminal start would be required
