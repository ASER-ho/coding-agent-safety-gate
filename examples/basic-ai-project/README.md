# Basic AI Project Example

This example shows how a normal project can use `coding-agent-safety-gate` with a `.ai/` directory.

No real secrets, private paths, or real repository remotes are included.

## Example Project Layout

```text
basic-ai-project/
├── README.md
└── .ai/
    ├── PROJECT_RULES.md
    ├── NEXT_TASK.md
    ├── ACCEPTANCE_CHECKLIST.md
    ├── AGENT_EXECUTION_REPORT.md
    └── HANDOFF.md
```

The `.ai/` directory in this example contains filled-in copies of all five core templates. Open each file to see what a completed version looks like:

- [PROJECT_RULES.md](.ai/PROJECT_RULES.md)
- [NEXT_TASK.md](.ai/NEXT_TASK.md)
- [ACCEPTANCE_CHECKLIST.md](.ai/ACCEPTANCE_CHECKLIST.md)
- [AGENT_EXECUTION_REPORT.md](.ai/AGENT_EXECUTION_REPORT.md)
- [HANDOFF.md](.ai/HANDOFF.md)

Seven templates are available in `templates/` — the five above plus `GIT_DIFF_REVIEW_CHECKLIST.md` and `SAFETY_REDACTION_CHECKLIST.md`. Copy only the ones you need.

## Suggested workflow

1. Copy `templates/PROJECT_RULES.md` into `.ai/` and fill it in once for your project.
2. Copy `templates/NEXT_TASK.md` into `.ai/` and fill in exactly one task.
3. Give the agent `.ai/PROJECT_RULES.md` and `.ai/NEXT_TASK.md`.
4. The agent performs only the approved task and fills `AGENT_EXECUTION_REPORT.md`.
5. Human reviews the result with `ACCEPTANCE_CHECKLIST.md` and `GIT_DIFF_REVIEW_CHECKLIST.md`.
6. Before sharing, run `SAFETY_REDACTION_CHECKLIST.md`.
7. Update `HANDOFF.md` if another human or agent continues the work.

## Example Agent Request

```text
Read .ai/PROJECT_RULES.md and .ai/NEXT_TASK.md before editing.
Complete only the task in NEXT_TASK.md. Do not expand the scope.
After finishing, fill .ai/AGENT_EXECUTION_REPORT.md with evidence.
Do not push, tag, release, add dependencies, read secrets, or expose full paths.
If the task boundary is unclear, stop and mark NEEDS HUMAN REVIEW.
```

The human decides whether the result is accepted and what the next task should be.
