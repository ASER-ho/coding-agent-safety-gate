# Quickstart / 快速入门

## 无需安装 / No Installation Required

`coding-agent-safety-gate` 是纯文档项目。没有任何需要安装的东西。不需要 `npm install`。不需要 CLI。不需要 MCP server。不需要 VS Code 插件。不需要包管理器。你只需要 Markdown 文件和一个 AI 编程助手（Claude Code、Codex、Cursor、Gemini CLI 等）。

`coding-agent-safety-gate` is documentation-only. There is nothing to install. No `npm install`. No CLI. No MCP server. No VS Code plugin. No package manager. You only need Markdown files and an AI coding agent (Claude Code, Codex, Cursor, Gemini CLI, or another coding agent).

## 方案 A：复制粘贴提示词 / Option A: Copy-Paste Prompt

最快上手的方式。打开 **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)**，复制 fenced code block 里的提示词，在给 AI 编程助手分配任务之前粘贴给它。这段提示词告诉 Agent 遵守任务边界、避免泄露机密、避免暴露完整路径，并返回证据。适用于任何 AI 编程助手——不需要 custom skill 支持。

The fastest way to get started. Open **[COPY_PASTE_PROMPT.md](COPY_PASTE_PROMPT.md)**, copy the prompt inside the fenced code block, and paste it into your AI coding agent before assigning a task. The prompt tells the agent to respect task boundaries, avoid secrets, avoid full paths, and return evidence. Works with any AI coding agent — no custom skill support needed.

## 方案 B：项目模板文件 / Option B: Project Template Files

在你自己的项目中建一个 `.ai/` 目录。在项目根目录创建 `.ai/`，把 `templates/` 中的文件复制到 `.ai/` 下（共七个模板：PROJECT_RULES、NEXT_TASK、ACCEPTANCE_CHECKLIST、AGENT_EXECUTION_REPORT、HANDOFF、GIT_DIFF_REVIEW_CHECKLIST、SAFETY_REDACTION_CHECKLIST）。为你的项目填写一次 `PROJECT_RULES.md`，每次 Agent 任务前填写 `NEXT_TASK.md`，告诉 Agent 在编辑前先读取这些文件。这种方式把安全规则放在你的仓库里，团队可以一起审查。

Set up a `.ai/` directory in your own project. Create `.ai/` in your project root, copy the seven templates from `templates/`, fill in `PROJECT_RULES.md` once for your project, fill in `NEXT_TASK.md` before each agent task, and ask the agent to read `.ai/PROJECT_RULES.md` and `.ai/NEXT_TASK.md` before editing. This approach keeps safety rules inside your repo, reviewable by your team.

## 方案 C：自定义 Skill 或指令 / Option C: Custom Skill or Instruction

如果你的 AI 编程环境支持自定义指令、skills、rules 或项目级系统提示词，复制 **[skills/coding-agent-safety-gate/SKILL.md](skills/coding-agent-safety-gate/SKILL.md)** 并粘贴到你的环境的自定义指令或 skill 配置中。该 skill 定义了同样的安全规则——一次一个任务、不暴露机密、未经批准不 push、有证据才声称完成。本项目不声称任何 Agent 会自动执行这些规则。Skill 设定期望；用户审查确认是否被遵守。

If your AI coding environment supports custom instructions, skills, rules, or project-level system prompts, copy **[skills/coding-agent-safety-gate/SKILL.md](skills/coding-agent-safety-gate/SKILL.md)** and paste it into the custom instruction or skill configuration for your environment. The skill defines the same safety rules — one task at a time, no secret exposure, no push without approval, evidence before claiming done. This project does not claim that any agent automatically enforces these rules. The skill sets expectations; human review confirms they were followed.

## 用户审查必须保留 / Human Review Required

本项目提供的是工作流护栏，不是运行时强制执行。用户审查者仍然负责：决定下一步任务是什么、审查变更文件和 diff、确认没有机密或完整路径被暴露、决定是否 commit、push、tag 或 release。Agent 的执行报告是支持审查的证据——不是声称工作正确或可以发布的证明。

This project provides workflow guardrails, not runtime enforcement. The human reviewer remains responsible for: deciding what the next task should be, reviewing changed files and diffs, confirming no secrets or full paths were exposed, and deciding whether to commit, push, tag, or release. The agent's execution report is evidence to support review — not a claim that the work is correct or safe to publish.
