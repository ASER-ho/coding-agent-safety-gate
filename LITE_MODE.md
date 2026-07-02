# 轻量模式 / Lite Mode

如果你不需要完整的七模板工作流，可以只保留三件事。这对小项目、单人项目或第一次尝试已经足够。

If you don't need the full seven-template workflow, keep just three things. This is enough for small projects, solo projects, or a first try.

---

## 只保留三件事 / Keep Only Three Things

### 1. 一个任务 / One Task

在给 Agent 分配工作前，写清楚这一个任务要做什么。口头或写在文件里都可以，但必须明确。

Before assigning work to the agent, write down what this one task should do. Verbally or in a file, but be explicit.

### 2. 两个边界 / Two Boundaries

告诉 Agent / Tell the agent:

- **可以动哪些文件 / Allowed files**：只列这一个任务需要的文件。例如 `README.md`。 / Only list files needed for this task. e.g. `README.md`.
- **禁止做什么 / Forbidden operations**：不要改其他文件、不要读机密、不要 push、不要装依赖、不要加脚本。 / Don't touch other files, don't read secrets, don't push, don't install deps, don't add scripts.

### 3. 一条证据 / One Piece of Evidence

Agent 完成后必须报告 / After finishing, the agent must report:

- 变更了哪些文件 / which files changed
- 做了什么 / what was done
- 怎么验证的 / how it was verified

---

## 最简单的提示词 / The Shortest Prompt

把这个粘贴到 AI 编程助手前 / Paste this into your AI coding agent before assigning a task:

```text
只做当前这一个任务。不要扩大范围。

Allowed files / 允许的文件：
- （列出 1-3 个文件 / list 1-3 files）

Forbidden / 禁止：
- 不要改上面没列出的文件 / Don't edit files not listed above
- 不要读或暴露机密（API key、token、私钥）/ Don't read or expose secrets
- 不要 push、tag、release / Don't push, tag, or release
- 不要加依赖或脚本 / Don't add dependencies or scripts

完成后报告 / After finishing, report：
- 改了什么 / what changed
- 怎么验证的 / how you verified
```

---

## 轻量模式够用吗？/ Is Lite Mode Enough?

对于 / For:

- 小项目 / small projects
- 单人项目 / solo projects
- 快速测试 / quick experiments

→ 够了 / enough。

对于 / For:

- 多人协作 / multi-person projects
- 多 Agent 协作 / multi-agent workflows
- 需要完整审计 / needs full audit trail

→ 用完整的 [templates/](templates/) 和 [QUICKSTART.md](QUICKSTART.md)。

轻量模式不是妥协。它是同一套安全原则的最小实现。

Lite mode is not a compromise. It's the same safety principles, minimally implemented.
