# Docs / 文档

本目录包含 `coding-agent-safety-gate` 的文档。如果你是新手，按以下顺序阅读。

This directory contains documentation for `coding-agent-safety-gate`. Read in this order if you are new to the project.

## 阅读顺序 / Reading order

| 顺序 / Order | 文件 / File | 内容 / What it covers |
|---|---|---|
| 1 | `safety-boundaries.md` | 默认安全规则：机密安全、路径安全、Git 安全、环境安全、执行安全、证据型验收 / The default safety rules |
| 2 | `human-in-the-loop.md` | 用户与 AI Agent 的责任分工、多 Agent 协作流程、必须由用户决策的节点 / Division of responsibility, multi-agent flow, human decision points |
| 3 | `../LIMITATIONS.md` | 诚实说明本项目能做什么、不能做什么——无 runtime enforcement、无 secret scan、依赖 Agent 诚实 / Honest explanation of what this project can and cannot do |
| 4 | `../LITE_MODE.md` | 只保留三件事的最小用法：一个任务、两个边界、一条证据 / Minimal usage: one task, two boundaries, one piece of evidence |

## 阅读后 / After reading

- 回到根目录 `README.md` 查看总览。 / Return to the root `README.md` for the overview.
- 打开 `QUICKSTART.md` 开始使用本项目。 / Open `QUICKSTART.md` to start using the project.
- 从 `templates/` 复制模板到你自己的项目。 / Copy templates from `templates/` into your own project.
