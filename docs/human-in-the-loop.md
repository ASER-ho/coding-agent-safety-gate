# Human-In-The-Loop Workflow

AI coding agents should not decide the next step by themselves because they do not own product intent, risk tolerance, release timing, security posture, or team priorities.

An agent can be excellent at executing a bounded task and still be unsafe when it silently expands the mission. Human-in-the-loop workflow keeps authority with the human and makes the agent responsible for narrow execution plus evidence.

## Recommended Division Of Responsibility

ChatGPT or a planning assistant:

- helps clarify goals
- drafts task descriptions
- compares options
- prepares `.ai/NEXT_TASK.md`
- identifies decision points for human review

Codex, Claude Code, Cursor, Gemini CLI, or another coding agent:

- reads `.ai/PROJECT_RULES.md`
- reads `.ai/NEXT_TASK.md`
- works only inside the approved file scope
- stops when scope is unclear
- verifies work
- reports changed files, results, risks, and incomplete items

Human:

- decides the project direction
- approves task scope
- approves risk
- approves dependency changes
- approves push, tag, release, deploy, remote, or system configuration changes
- decides the next task

## Multi-Agent Collaboration Flow

1. Human writes or approves project rules.
2. Human or planning assistant drafts the next task.
3. Human approves the task scope and forbidden operations.
4. Coding agent performs the task inside the approved boundary.
5. Coding agent produces an execution report with evidence.
6. Human reviews the acceptance checklist.
7. Human decides whether another agent should continue.
8. Handoff notes are updated before the next agent starts.

## Required Human Decision Points

A human must confirm before an AI agent:

- expands the task beyond the current file scope
- changes the product direction
- changes security posture
- adds dependencies
- deletes important files
- reads sensitive files
- modifies environment or system configuration
- starts another agent or automation
- starts a real Claude, Codex, Cursor, Gemini CLI, or other agent process
- clicks Terminal start
- pushes, tags, releases, deploys, or adds a remote

## Evidence-Based Acceptance

The agent should never say "done" as a bare claim.

Acceptable completion includes:

- changed file list
- summary of actual changes
- verification commands or manual checks
- verification results
- known risks
- incomplete items
- whether human approval is required for the next step

The human decides whether the evidence is sufficient.
