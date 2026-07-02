# 局限性 / Limitations

本文档诚实地说明 `coding-agent-safety-gate` 能做什么、不能做什么。坦诚比完美重要。

This document honestly explains what `coding-agent-safety-gate` can and cannot do. Honesty matters more than perfection.

---

## 它是什么 / What It Is

一个**文档优先的工作流护栏**。通过 Markdown 文件帮用户和 AI Agent 明确任务边界、禁止操作和证据要求，然后靠用户审查来确认 Agent 是否遵守。

A **documentation-first workflow guardrail**. It uses Markdown files to help humans and AI agents agree on task boundaries, forbidden actions, and evidence requirements — then relies on human review to confirm the agent followed them.

## 它不是 / What It Is Not

这不是一个**安全系统**。它是一个**协议**。

It is not a **security system**. It is a **protocol**.

---

## 当前限制 / Current Limitations

### 1. 没有运行时拦截 / No Runtime Enforcement

Agent 可以选择忽略 SKILL.md 里的任何规则。本项目没有 hook、sandbox、pre-tool-use approval 或任何自动拦截机制。它依赖 Agent 自愿遵守和用户事后审查。

如果你的场景需要硬拦截——例如阻止 Agent 删除 `.env`、执行 `rm -rf`、force push 到 main——你必须另外使用沙箱环境、hook 系统、pre-action 授权工具或 CI gate。

An agent can choose to ignore any rule in SKILL.md. This project has no hooks, sandbox, pre-tool-use approval, or automatic blocking. It relies on voluntary compliance by the agent and post-hoc human review.

If you need hard blocking — e.g., prevent an agent from deleting `.env`, running `rm -rf`, or force-pushing to main — you must additionally use a sandbox, hook system, pre-action authorization tool, or CI gate.

### 2. 没有机密扫描 / No Secret Scanning

模板要求 Agent 不读取和暴露机密，但本项目不会自动扫描 Agent 的输出中是否包含了 API key、token 或完整路径。SAFETY_REDACTION_CHECKLIST.md 是给你手动检查用的——它不自带扫描器。

如果你的场景要求自动检测输出中的机密泄露，你需要另外使用 secret scanner 或 pre-commit hook。

Templates ask the agent not to read or expose secrets, but this project does not automatically scan agent output for API keys, tokens, or full paths. SAFETY_REDACTION_CHECKLIST.md is for manual review — it does not include a scanner.

If your scenario requires automatic detection of secrets in output, you need a separate secret scanner or pre-commit hook.

### 3. 依赖 Agent 诚实 / Depends on Agent Honesty

Agent 声称"没有读取机密"时，我们只能相信它——或者事后审查 diff、日志和系统状态来验证。目前主流 AI 编程助手不会主动欺骗，但从安全工程角度看，"相信 Agent"不等于"Agent 值得相信"。

如果你的场景需要独立验证 Agent 的行为，你需要审计日志、沙箱监控或 hook 系统。

When an agent claims "I did not read secrets," we can only trust it — or verify afterward by reviewing diffs, logs, and system state. Mainstream AI coding agents today don't actively deceive, but from a security engineering perspective, "trust the agent" is not the same as "the agent is trustworthy."

If your scenario requires independent verification of agent behavior, you need audit logs, sandbox monitoring, or a hook system.

### 4. 对新手有配置成本 / Configuration Cost for Beginners

QUICKSTART.md 和 COPY_PASTE_PROMPT.md 尽力降低了门槛——LITE_MODE.md 只需要三件事——但完整的七模板工作流仍然需要用户在首次使用时理解每个模板的用途。

这不是 bug，是协议类项目的固有特点。但它意味着：一个只想要"帮我管住 Agent 别乱改文件"的用户，可能会觉得七模板太多了。

QUICKSTART.md, COPY_PASTE_PROMPT.md, and LITE_MODE.md try to lower the barrier, but the full seven-template workflow still requires first-time setup. This is inherent to protocol-style projects, but it means a user who just wants "stop my agent from editing random files" may find seven templates to be too many.

---

## 推荐的安全组合 / Recommended Safety Stack

`coding-agent-safety-gate` 是一层。要构建更强的安全姿态，和以下工具配合使用：

`coding-agent-safety-gate` is one layer. For a stronger security posture, combine it with:

| 层级 / Layer | 做什么 / Does What | 建议工具 / Suggested Tools |
|---|---|---|
| 工作流护栏 / Workflow guardrail | 定义任务边界和证据要求 / Defines task boundaries and evidence | **这个项目 / This project** |
| Runtime enforcement | 实时拦截危险操作 / Blocks dangerous actions in real time | Sandbox, hooks, pre-tool approval |
| Secret scanning | 自动检测输出中的机密 / Auto-detects secrets in output | Secret scanner, pre-commit hooks |
| CI gate | 阻止不安全的代码进入主分支 / Blocks unsafe code from main | GitHub Actions, linting, tests |
| Audit logging | 记录 Agent 做了什么 / Records what the agent did | Session logs, diff history |

---

## 为什么在没有硬拦截的情况下还要用它 / Why Use It Without Hard Enforcement

1. **协议本身就有价值。** 在 Agent 工作前强迫用户想清楚"到底让它改哪个文件、不准做什么"，已经减少了大部分 AI drift 问题。
2. **它不依赖任何平台。** 今天用在 Claude Code，明天用在 Codex，不需要装东西、不需要权限。
3. **它是往上堆硬安全的起点。** 先定义好规则，再加 hook；先养成审查习惯，再加 CI gate。

The protocol itself has value. Forcing the human to decide "exactly which files and what's forbidden" before the agent starts already eliminates most AI drift problems. It's platform-independent. And it's the foundation you can build hard enforcement on top of later.
