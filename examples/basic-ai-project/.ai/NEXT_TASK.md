# NEXT_TASK

Copy this file into your own project. Fill in exactly one task before each AI coding agent session.

## Task Title

Update README.md introduction (example)

## Stage

- [x] Planning
- [ ] Implementation
- [ ] Validation
- [ ] Documentation
- [ ] Handoff

## Goal

Make the README introduction clearer for first-time readers. Add one short sentence about what the project does.

## Background

The current README introduction is too short. New visitors need more context to understand the project.

## Allowed Files

The AI agent may read or edit only these files or directories:

- README.md

## Forbidden Files

The AI agent must not read or edit these files or directories:

- .env
- secrets/
- config/production.yaml

## Explicitly Allowed Operations

The AI agent may:

- Edit the README introduction section
- Add one clear sentence describing the project

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
- run git push, git tag, create a release, or add or modify a remote

## Safety Constraints

- Do not read or expose real secrets, API keys, tokens, credentials, or SecretStore secrets.
- Do not introduce full private local paths.
- Do not decide the next task.
- Do not claim completion without evidence.

## Steps

1. Read PROJECT_RULES.md.
2. Confirm this file defines one clear task.
3. Inspect only allowed files needed for the task.
4. Make the smallest useful change.
5. Run only the validation commands listed below.
6. Fill the execution report.
7. Stop for human review.

## Validation Commands

```text
git diff README.md
```

If no command is appropriate, list the manual checks required:

- README.md introduction is clearer
- One sentence was added, not removed
- No other files changed

## Acceptance Criteria

The task is acceptable when:

- README.md contains a clear project introduction
- No unrelated files were changed
- Agent reports evidence

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
- final status: PASS, FAIL, BLOCKED, or NEEDS HUMAN REVIEW

## This Task Does Not Include

- Editing files other than README.md
- Adding dependencies
- Changing the project license
- Publishing or releasing

## Stop Conditions

Stop and mark NEEDS HUMAN REVIEW if:

- task boundaries are unclear
- required files are missing
- requested changes conflict with PROJECT_RULES.md
- a forbidden file or forbidden change appears necessary
- a real secret, SecretStore value, or private credential would need to be read
- full private local paths would need to be disclosed
- git push, tag, release, remote changes, system configuration changes, agent startup, or Terminal start would be required
