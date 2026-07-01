# Templates / 模板

本目录包含可复制的 Markdown 模板。将它们复制到你自己的项目中，建议放在 `.ai/` 下。

This directory contains copyable Markdown templates. Copy them into your own project, preferably under `.ai/`.

## 模板索引 / Template index

| 模板 / Template | 用途 / Use | 填写频率 / Fill how often |
|---|---|---|
| `PROJECT_RULES.md` | 稳定项目边界、允许操作、安全规则 / Stable project boundaries, allowed actions, safety rules | 每个项目一次 / Once per project |
| `NEXT_TASK.md` | AI Agent 执行的唯一任务 / Exactly one task for the AI agent to perform | 每次 Agent 会话前 / Before each agent session |
| `ACCEPTANCE_CHECKLIST.md` | 用户审查用的证据型验收清单 / Evidence-based completion checklist for human review | 每个任务后 / After each task |
| `AGENT_EXECUTION_REPORT.md` | Agent 的事实报告：变更了什么、验证、安全、风险 / Factual report from the agent: what changed, verification, safety, risks | 每个任务后 / After each task |
| `HANDOFF.md` | 用户或 AI Agent 之间的上下文交接 / Context transfer between humans or AI agents | 会话之间 / Between sessions |
| `GIT_DIFF_REVIEW_CHECKLIST.md` | 任务后 git diff 审查：范围、安全、依赖、证据 / Post-task git diff review: scope, safety, deps, evidence | 每个任务后 / After each task |
| `SAFETY_REDACTION_CHECKLIST.md` | 分享前脱敏：机密、路径、私有数据 / Redact secrets, paths, and private data before sharing | 分享任何输出前 / Before sharing any output |

## 推荐工作流 / Recommended workflow

1. 将 `PROJECT_RULES.md` 复制到 `.ai/` 并填写一次。 / Copy `PROJECT_RULES.md` into `.ai/` and fill it in once.
2. 将 `NEXT_TASK.md` 复制到 `.ai/` 并填写恰好一个任务。 / Copy `NEXT_TASK.md` into `.ai/` and fill in exactly one task.
3. 给 Agent `PROJECT_RULES.md`、`NEXT_TASK.md` 和 `ACCEPTANCE_CHECKLIST.md`。 / Give the agent `PROJECT_RULES.md`, `NEXT_TASK.md`, and `ACCEPTANCE_CHECKLIST.md`.
4. 任务后，Agent 填写 `AGENT_EXECUTION_REPORT.md`。 / After the task, the agent fills `AGENT_EXECUTION_REPORT.md`.
5. 用户用 `GIT_DIFF_REVIEW_CHECKLIST.md` 审查 diff。 / Human reviews the diff with `GIT_DIFF_REVIEW_CHECKLIST.md`.
6. 分享前，用户检查 `SAFETY_REDACTION_CHECKLIST.md`。 / Before sharing, human runs `SAFETY_REDACTION_CHECKLIST.md`.
7. 如果另一个 Agent 或用户继续工作，更新 `HANDOFF.md`。 / Update `HANDOFF.md` if another agent or human continues the work.

最快上手方式见根目录 `QUICKSTART.md` 和 `COPY_PASTE_PROMPT.md`。

See the root `QUICKSTART.md` and `COPY_PASTE_PROMPT.md` for the fastest way to start.
