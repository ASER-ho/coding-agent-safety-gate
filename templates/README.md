# Templates

This directory contains copyable Markdown templates. Copy them into your own project, preferably under `.ai/`.

## Template index

| Template | Use | Fill how often |
|---|---|---|
| `PROJECT_RULES.md` | Stable project boundaries, allowed actions, safety rules | Once per project |
| `NEXT_TASK.md` | Exactly one task for the AI agent to perform | Before each agent session |
| `ACCEPTANCE_CHECKLIST.md` | Evidence-based completion checklist for human review | After each task |
| `AGENT_EXECUTION_REPORT.md` | Factual report from the agent: what changed, verification, safety, risks | After each task |
| `HANDOFF.md` | Context transfer between humans or AI agents | Between sessions |
| `GIT_DIFF_REVIEW_CHECKLIST.md` | Post-task git diff review: scope, safety, deps, evidence | After each task |
| `SAFETY_REDACTION_CHECKLIST.md` | Redact secrets, paths, and private data before sharing | Before sharing any output |

## Recommended workflow

1. Copy `PROJECT_RULES.md` into `.ai/` and fill it in once.
2. Copy `NEXT_TASK.md` into `.ai/` and fill in exactly one task.
3. Give the agent `PROJECT_RULES.md`, `NEXT_TASK.md`, and `ACCEPTANCE_CHECKLIST.md`.
4. After the task, the agent fills `AGENT_EXECUTION_REPORT.md`.
5. Human reviews the diff with `GIT_DIFF_REVIEW_CHECKLIST.md`.
6. Before sharing, human runs `SAFETY_REDACTION_CHECKLIST.md`.
7. Update `HANDOFF.md` if another agent or human continues the work.

See the root `QUICKSTART.md` and `COPY_PASTE_PROMPT.md` for the fastest way to start.
