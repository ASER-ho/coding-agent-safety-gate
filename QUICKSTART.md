# Quickstart

## No Installation Required

`coding-agent-safety-gate` is documentation-only. There is nothing to install.

No `npm install`. No CLI. No MCP server. No VS Code plugin. No package manager.

You only need Markdown files and an AI coding agent (Claude Code, Codex, Cursor, Gemini CLI, or another coding agent).

## Option A: Copy-Paste Prompt

The fastest way to get started.

1. Open **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)**.
2. Copy the prompt inside the fenced code block.
3. Paste it into your AI coding agent before assigning a task.
4. The prompt tells the agent to respect task boundaries, avoid secrets, avoid full paths, and return evidence.

Works with any AI coding agent — no custom skill support needed.

## Option B: Project Template Files

Set up a `.ai/` directory in your own project.

1. Create `.ai/` in your project root.
2. Copy these files from `templates/` into `.ai/`:

   - `templates/PROJECT_RULES.md`
   - `templates/NEXT_TASK.md`
   - `templates/ACCEPTANCE_CHECKLIST.md`
   - `templates/AGENT_EXECUTION_REPORT.md`
   - `templates/HANDOFF.md`
   - `templates/GIT_DIFF_REVIEW_CHECKLIST.md`
   - `templates/SAFETY_REDACTION_CHECKLIST.md`

3. Fill in `PROJECT_RULES.md` once for your project.
4. Fill in `NEXT_TASK.md` before each agent task.
5. Ask the agent to read `.ai/PROJECT_RULES.md` and `.ai/NEXT_TASK.md` before editing.

This approach keeps safety rules inside your repo, reviewable by your team.

## Option C: Custom Skill or Instruction

If your AI coding environment supports custom instructions, skills, rules, or project-level system prompts:

1. Copy **[skills/coding-agent-safety-gate/SKILL.md](skills/coding-agent-safety-gate/SKILL.md)**.
2. Paste it into the custom instruction or skill configuration for your environment.
3. The skill defines the same safety rules — one task at a time, no secret exposure, no push without approval, evidence before claiming done.

This project does not claim that any agent automatically enforces these rules. The skill sets expectations; human review confirms they were followed.

## Human Review Required

This project provides workflow guardrails, not runtime enforcement. The human reviewer remains responsible for:

- deciding what the next task should be
- reviewing changed files and diffs
- confirming no secrets or full paths were exposed
- deciding whether to commit, push, tag, or release

The agent's execution report is evidence to support review — not a claim that the work is correct or safe to publish.
