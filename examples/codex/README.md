# Codex — Safety Gate Example

## Purpose

This example shows how to use `coding-agent-safety-gate` with Codex (or another coding agent with similar capabilities). It is a documentation-first workflow layer — not runtime enforcement, not a plugin, not a package.

## Recommended files to give the agent

Copy these files from `templates/` into your project and fill them in before starting a Codex session:

- `PROJECT_RULES.md` — stable project boundaries and safety rules
- `NEXT_TASK.md` — the one task the agent is currently allowed to perform
- `ACCEPTANCE_CHECKLIST.md` — evidence-based completion checklist
- `AGENT_EXECUTION_REPORT.md` — factual report of what happened
- `HANDOFF.md` — context for the next human or agent
- `GIT_DIFF_REVIEW_CHECKLIST.md` — post-task diff review
- `SAFETY_REDACTION_CHECKLIST.md` — redaction check before sharing

## Suggested workflow

1. **Human** writes or reviews `PROJECT_RULES.md`.
2. **Human** writes exactly one `NEXT_TASK.md`.
3. **Agent** reads the project rules, task, and checklist files.
4. **Agent** performs only the task described in `NEXT_TASK.md`.
5. **Agent** fills `AGENT_EXECUTION_REPORT.md` with changed files and verification evidence.
6. **Human** reviews the diff using `GIT_DIFF_REVIEW_CHECKLIST.md`.
7. **Human** checks the output using `SAFETY_REDACTION_CHECKLIST.md` before sharing or publishing.
8. **Human** decides whether to commit, push, tag, or release.

The agent does not decide the next task.

## Forbidden agent behavior

When using Codex or another coding agent, the agent must not:

- push, tag, or release
- add or modify a remote
- force push or rewrite history
- add dependencies, packages, or scripts
- create a CLI, MCP server, VS Code plugin, npm package, runtime enforcement tool, or secret scanner
- read, print, or store real secrets (API keys, tokens, credentials)
- expose full local machine paths
- continue into the next task without human approval
- claim completion without evidence

## Example prompt

Copy this into a Codex session after setting up your project files:

```text
Read .ai/PROJECT_RULES.md and .ai/NEXT_TASK.md before editing any file.

Complete only the task described in NEXT_TASK.md. Do not expand the scope.

After finishing, fill .ai/AGENT_EXECUTION_REPORT.md with:
- changed files
- summary of changes
- verification commands and results
- safety check results

Do not push, tag, release, add dependencies, read secrets, or expose full paths.
If the task boundary is unclear, stop and mark NEEDS HUMAN REVIEW.
```

## Human review

The human reviewer owns all final decisions. The agent's execution report is evidence to support review — it is not a claim that the work is correct, safe, or ready to publish. Review every change before committing, pushing, tagging, or releasing.
