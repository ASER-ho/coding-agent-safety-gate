# 基础 AI 项目示例 / Basic AI Project Example

本示例展示一个普通项目如何使用 `coding-agent-safety-gate` 和 `.ai/` 目录。

This example shows how a normal project can use `coding-agent-safety-gate` with a `.ai/` directory.

不包含真实机密、私有路径或真实仓库 remote。

No real secrets, private paths, or real repository remotes are included.

## 示例项目布局 / Example Project Layout

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

本示例中的 `.ai/` 目录包含全部五个核心模板的填写版本。打开每个文件查看完成版的样式：

The `.ai/` directory in this example contains filled-in copies of all five core templates. Open each file to see what a completed version looks like:

- [PROJECT_RULES.md](.ai/PROJECT_RULES.md)
- [NEXT_TASK.md](.ai/NEXT_TASK.md)
- [ACCEPTANCE_CHECKLIST.md](.ai/ACCEPTANCE_CHECKLIST.md)
- [AGENT_EXECUTION_REPORT.md](.ai/AGENT_EXECUTION_REPORT.md)
- [HANDOFF.md](.ai/HANDOFF.md)

`templates/` 中有七个模板——以上五个外加 `GIT_DIFF_REVIEW_CHECKLIST.md` 和 `SAFETY_REDACTION_CHECKLIST.md`。只复制你需要的。

Seven templates are available in `templates/` — the five above plus `GIT_DIFF_REVIEW_CHECKLIST.md` and `SAFETY_REDACTION_CHECKLIST.md`. Copy only the ones you need.

## 建议工作流 / Suggested workflow

1. 把 `templates/PROJECT_RULES.md` 复制到 `.ai/`，为你的项目填写一次。 / Copy `templates/PROJECT_RULES.md` into `.ai/` and fill it in once for your project.
2. 把 `templates/NEXT_TASK.md` 复制到 `.ai/`，填写恰好一个任务。 / Copy `templates/NEXT_TASK.md` into `.ai/` and fill in exactly one task.
3. 给 Agent `.ai/PROJECT_RULES.md` 和 `.ai/NEXT_TASK.md`。 / Give the agent `.ai/PROJECT_RULES.md` and `.ai/NEXT_TASK.md`.
4. Agent 只执行批准的任务，填写 `AGENT_EXECUTION_REPORT.md`。 / The agent performs only the approved task and fills `AGENT_EXECUTION_REPORT.md`.
5. 人类用 `ACCEPTANCE_CHECKLIST.md` 和 `GIT_DIFF_REVIEW_CHECKLIST.md` 审查结果。 / Human reviews the result with `ACCEPTANCE_CHECKLIST.md` and `GIT_DIFF_REVIEW_CHECKLIST.md`.
6. 分享前检查 `SAFETY_REDACTION_CHECKLIST.md`。 / Before sharing, run `SAFETY_REDACTION_CHECKLIST.md`.
7. 如果另一个人类或 Agent 继续工作，更新 `HANDOFF.md`。 / Update `HANDOFF.md` if another human or agent continues the work.

## 示例 Agent 请求 / Example Agent Request

```text
编辑前先读取 .ai/PROJECT_RULES.md 和 .ai/NEXT_TASK.md。
只完成 NEXT_TASK.md 中的任务。不要扩大范围。
完成后填写 .ai/AGENT_EXECUTION_REPORT.md 提供证据。
不要 push、tag、release、添加依赖、读取机密或暴露完整路径。
如果任务边界不清楚，停下来标记 NEEDS HUMAN REVIEW。

Read .ai/PROJECT_RULES.md and .ai/NEXT_TASK.md before editing.
Complete only the task in NEXT_TASK.md. Do not expand the scope.
After finishing, fill .ai/AGENT_EXECUTION_REPORT.md with evidence.
Do not push, tag, release, add dependencies, read secrets, or expose full paths.
If the task boundary is unclear, stop and mark NEEDS HUMAN REVIEW.
```

人类决定结果是否被接受以及下一步任务。

The human decides whether the result is accepted and what the next task should be.
