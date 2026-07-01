# 安全脱敏清单 / Safety Redaction Checklist

在分享执行报告、handoff 文档、issue、pull request 或演示前使用此清单。确认敏感信息已被脱敏。

Use this checklist before sharing an execution report, handoff document, issue, pull request, or demo. It helps confirm that sensitive information has been redacted.

---

## Purpose / 用途

在分享执行报告、handoff 文档、issue、PR 或演示前使用此清单。确认敏感信息已脱敏。

Use this checklist before sharing an execution report, handoff document, issue, pull request, or demo. It helps confirm that sensitive information has been redacted.

---

## 审查上下文 / Review Context

- **被审查的材料（文件、报告或输出）/ Material reviewed (file, report, or output):**
- **审查者 / Reviewer:**
- **日期 / Date:**

---

## 机密检查 / Secrets Check

- [ ] 没有可见的 API key。 / No API keys are visible.
- [ ] 没有可见的 token。 / No tokens are visible.
- [ ] 没有可见的 cookie。 / No cookies are visible.
- [ ] 没有可见的私钥。 / No private keys are visible.
- [ ] 没有可见的生产凭据。 / No production credentials are visible.
- [ ] 没有可见的 `.env` 文件内容。 / No `.env` file contents are visible.

---

## 路径 / 身份检查 / Path / Identity Check

- [ ] 没有可见的完整本地机器路径（例如 `/Users/...`、`/home/...`、`C:\Users\...`）。 / No full local machine paths are visible (e.g., `/Users/...`, `/home/...`, `C:\Users\...`).
- [ ] 除非有意公开，否则没有暴露用户名。 / No usernames are exposed unless intentionally public.
- [ ] 除非有意公开，否则没有暴露机器名或主机名。 / No machine names or hostnames are exposed unless intentionally public.
- [ ] 没有可见的私有仓库 URL。 / No private repository URLs are visible.
- [ ] 没有可见的内网主机名或 IP。 / No internal hostnames or IPs are visible.

---

## 日志 / 错误输出检查 / Logs / Error Output Check

- [ ] 已审查堆栈跟踪，如包含路径或机密已脱敏。 / Stack traces have been reviewed and redacted if they contain paths or secrets.
- [ ] 已审查 shell 输出中的路径、机密或主机名。 / Shell output has been reviewed for paths, secrets, or hostnames.
- [ ] 已审查调试日志中的敏感数据。 / Debug logs have been reviewed for sensitive data.
- [ ] 已审查截图中的终端窗口、编辑器标题栏或文件树中的可见路径、token 或凭据。 / Screenshots have been reviewed for visible paths, tokens, or credentials in terminal windows, editor title bars, or file trees.

---

## Agent 报告检查 / Agent Report Check

- [ ] 执行报告不包含真实机密。 / The execution report does not contain real secrets.
- [ ] 执行报告不包含完整本地路径。 / The execution report does not contain full local paths.
- [ ] 执行报告不包含私有 URL。 / The execution report does not contain private URLs.
- [ ] 执行报告没有在缺乏证据的情况下声称完成。 / The execution report does not claim completion without evidence.

---

## 脱敏格式 / Redaction Format

- [ ] 真实机密替换为占位符：`<REDACTED_API_KEY>`、`<REDACTED_TOKEN>`、`<REDACTED_CREDENTIAL>`。 / Real secrets are replaced with placeholders: `<REDACTED_API_KEY>`, `<REDACTED_TOKEN>`, `<REDACTED_CREDENTIAL>`.
- [ ] 真实路径替换为 `<LOCAL_PATH_REDACTED>` 或相对等效形式。 / Real paths are replaced with `<LOCAL_PATH_REDACTED>` or relative equivalents.
- [ ] 保留了足够的上下文供审查者理解被脱敏的内容。 / Enough context is preserved for a reviewer to understand what was redacted.
- [ ] 证据关键细节未被删除——在安全的前提下用脱敏占位符替代。 / Evidence-critical details are not deleted — replaced with redacted placeholders when safe.

---

## 决定 / Decision

选择一项 / Choose one:

- [ ] **可以分享 / Safe to share** — 所有敏感内容已脱敏或未曾出现。 / all sensitive content is redacted or never present.
- [ ] **需要脱敏 / Needs redaction** — 在分享前必须脱敏特定项目（在下方列出）。 / specific items must be redacted before sharing (list below).
- [ ] **Blocked** — 材料无法在保留所需证据的前提下安全脱敏。 / material cannot be safely redacted without losing required evidence.
- [ ] **需要人类审查 / Needs human review** — 模糊性或敏感度需要人类判断。 / ambiguity or sensitivity requires human judgment.

脱敏备注 / Redaction notes:
