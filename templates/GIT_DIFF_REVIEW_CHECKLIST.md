# Git Diff 审查清单 / Git Diff Review Checklist

在 AI 编程助手完成任务后，使用此清单审查 git diff。它帮助确认变更保持在范围内、没有引入无关文件，并满足证据型验收。

Use this checklist to review a git diff after an AI coding agent completes a task. It helps confirm the change stayed within scope, did not introduce unrelated files, and meets evidence-based acceptance.

---

## Purpose / 用途

在 AI 编程助手完成任务后，使用此清单审查 git diff。确认变更在范围内、没有无关文件，并满足证据型验收。

Use this checklist to review a git diff after an AI coding agent completes a task. It helps confirm the change stayed within scope, did not introduce unrelated files, and meets evidence-based acceptance.

---

## 审查上下文 / Review Context

- **任务文件（NEXT_TASK.md）/ Task file (NEXT_TASK.md):**
- **预期变更文件 / Expected changed files:**
- **实际变更文件（git diff --name-only）/ Actual changed files (git diff --name-only):**
- **人类审查者 / Human reviewer:**
- **日期 / Date:**

---

## 范围匹配 / Scope Match

- [ ] 变更文件与 `NEXT_TASK.md` 中批准的文件列表匹配。 / Changed files match the approved file list in `NEXT_TASK.md`.
- [ ] 没有无关文件被编辑。 / No unrelated files were edited.
- [ ] 没有生成文件、构建产物或噪声被包含。 / No generated files, build artifacts, or noise were included.
- [ ] 没有引入仅格式化的扰动，除非明确允许。 / No formatting-only churn was introduced unless explicitly allowed.

---

## 安全边界检查 / Safety Boundary Check

- [ ] 没有添加 CLI。 / No CLI was added.
- [ ] 没有添加 MCP server。 / No MCP server was added.
- [ ] 没有添加 VS Code 插件。 / No VS Code plugin was added.
- [ ] 没有添加 npm 包或 package metadata。 / No npm package or package metadata was added.
- [ ] 没有添加 runtime enforcement 工具。 / No runtime enforcement tool was added.
- [ ] 没有添加 secret scanner。 / No secret scanner was added.
- [ ] 没有添加 GitHub Actions 工作流。 / No GitHub Actions workflow was added.
- [ ] 没有添加 release 自动化。 / No release automation was added.

---

## Git / Release 检查 / Git / Release Check

- [ ] 没有未经授权执行 `git push`。 / No `git push` was performed without authorization.
- [ ] 没有未经授权创建 `git tag`。 / No `git tag` was created without authorization.
- [ ] 没有未经授权创建 release。 / No release was created without authorization.
- [ ] 没有未经授权添加或修改 remote。 / No remote was added or modified without authorization.
- [ ] 没有执行 force push 或历史重写。 / No force push or history rewrite was performed.

---

## 依赖 / 脚本检查 / Dependency / Script Check

- [ ] 没有新增依赖。 / No new dependency was added.
- [ ] 没有创建或修改 lockfile。 / No lockfile was created or modified.
- [ ] 没有修改 package metadata（`package.json`、`Cargo.toml` 等）。 / No package metadata (`package.json`, `Cargo.toml`, etc.) was changed.
- [ ] 没有引入新脚本。 / No new script was introduced.

---

## 证据检查 / Evidence Check

- [ ] 验证命令已运行并记录了结果。 / Verification commands were run and results recorded.
- [ ] 变更文件在 diff 中已检查。 / Changed files were inspected in the diff.
- [ ] 如适用，截图或日志已附上。 / Screenshots or logs are attached if applicable.
- [ ] 剩余的不确定性或未完成事项已列出。 / Remaining uncertainty or incomplete items are listed.

---

## 决定 / Decision

选择一项 / Choose one:

- [ ] **批准 / Approved** — diff 干净，范围匹配，证据完整。 / diff is clean, scope matched, evidence complete.
- [ ] **需要修改 / Needs changes** — 在下方列出需要的修改。 / list required changes below.
- [ ] **Blocked** — 检测到安全边界或范围违反。 / safety boundary or scope violation detected.
- [ ] **需要人类审查 / Needs human review** — 模糊性或风险需要人类判断。 / ambiguity or risk requires human judgment.

备注 / Notes:
