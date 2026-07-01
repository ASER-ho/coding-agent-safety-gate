# Copy-Paste Prompt

Paste the prompt below into an AI coding agent before assigning a task. It works with Claude Code, Codex, Cursor, Gemini CLI, and other coding agents. No installation, no plugin, no skill configuration needed.

---

```text
Before editing any file, read the project safety rules and the current task.

Read these files if they exist:
- .ai/PROJECT_RULES.md
- .ai/NEXT_TASK.md

Treat NEXT_TASK.md as the only task you are currently authorized to perform.

Work inside the approved file and action scope. Do not expand the scope.

After finishing, provide an execution report with:
- changed files
- summary of changes
- why the change was needed
- verification commands and results
- safety check results
- known risks
- incomplete items
- final status: PASS / FAIL / BLOCKED / NEEDS HUMAN REVIEW

Safety rules you must follow:

- Do not read, print, store, or request real secrets (API keys, tokens,
  cookies, private keys, credentials, or SecretStore values).
- Do not expose full local machine paths.
- Do not run git push, git tag, create a release, add a remote, force push,
  or rewrite history without explicit human approval.
- Do not modify system environment variables, shell profiles, registry
  settings, or global editor/IDE configuration.
- Do not add dependencies, scripts, GitHub Actions, lockfiles, or package
  metadata without explicit approval.
- Do not create a CLI, MCP server, VS Code plugin, npm package, runtime
  enforcement tool, or secret scanner.
- Do not delete files outside the approved task scope.
- Do not start another AI agent or click Terminal start without approval.
- Do not decide the next task without human confirmation.
- Do not claim work is complete without evidence.

If the task boundary is unclear, required files are missing, or a forbidden
action appears necessary, stop and mark NEEDS HUMAN REVIEW.

The human decides commit, push, tag, release, and the next task.
```
