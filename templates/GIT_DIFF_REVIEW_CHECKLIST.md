# Git Diff Review Checklist

## Purpose

Use this checklist to review a git diff after an AI coding agent completes a task. It helps confirm the change stayed within scope, did not introduce unrelated files, and meets evidence-based acceptance.

---

## Review Context

- **Task file (NEXT_TASK.md):**
- **Expected changed files:**
- **Actual changed files (git diff --name-only):**
- **Human reviewer:**
- **Date:**

---

## Scope Match

- [ ] Changed files match the approved file list in `NEXT_TASK.md`.
- [ ] No unrelated files were edited.
- [ ] No generated files, build artifacts, or noise were included.
- [ ] No formatting-only churn was introduced unless explicitly allowed.

---

## Safety Boundary Check

- [ ] No CLI was added.
- [ ] No MCP server was added.
- [ ] No VS Code plugin was added.
- [ ] No npm package or package metadata was added.
- [ ] No runtime enforcement tool was added.
- [ ] No secret scanner was added.
- [ ] No GitHub Actions workflow was added.
- [ ] No release automation was added.

---

## Git / Release Check

- [ ] No `git push` was performed without authorization.
- [ ] No `git tag` was created without authorization.
- [ ] No release was created without authorization.
- [ ] No remote was added or modified without authorization.
- [ ] No force push or history rewrite was performed.

---

## Dependency / Script Check

- [ ] No new dependency was added.
- [ ] No lockfile was created or modified.
- [ ] No package metadata (`package.json`, `Cargo.toml`, etc.) was changed.
- [ ] No new script was introduced.

---

## Evidence Check

- [ ] Verification commands were run and results recorded.
- [ ] Changed files were inspected in the diff.
- [ ] Screenshots or logs are attached if applicable.
- [ ] Remaining uncertainty or incomplete items are listed.

---

## Decision

Choose one:

- [ ] **Approved** — diff is clean, scope matched, evidence complete.
- [ ] **Needs changes** — list required changes below.
- [ ] **Blocked** — safety boundary or scope violation detected.
- [ ] **Needs human review** — ambiguity or risk requires human judgment.

Notes:
