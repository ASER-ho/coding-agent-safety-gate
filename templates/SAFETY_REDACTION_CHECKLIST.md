# Safety Redaction Checklist

## Purpose

Use this checklist before sharing an execution report, handoff document, issue, pull request, or demo. It helps confirm that sensitive information has been redacted.

---

## Review Context

- **Material reviewed (file, report, or output):**
- **Reviewer:**
- **Date:**

---

## Secrets Check

- [ ] No API keys are visible.
- [ ] No tokens are visible.
- [ ] No cookies are visible.
- [ ] No private keys are visible.
- [ ] No production credentials are visible.
- [ ] No `.env` file contents are visible.

---

## Path / Identity Check

- [ ] No full local machine paths are visible (e.g., `/Users/...`, `/home/...`, `C:\Users\...`).
- [ ] No usernames are exposed unless intentionally public.
- [ ] No machine names or hostnames are exposed unless intentionally public.
- [ ] No private repository URLs are visible.
- [ ] No internal hostnames or IPs are visible.

---

## Logs / Error Output Check

- [ ] Stack traces have been reviewed and redacted if they contain paths or secrets.
- [ ] Shell output has been reviewed for paths, secrets, or hostnames.
- [ ] Debug logs have been reviewed for sensitive data.
- [ ] Screenshots have been reviewed for visible paths, tokens, or credentials in terminal windows, editor title bars, or file trees.

---

## Agent Report Check

- [ ] The execution report does not contain real secrets.
- [ ] The execution report does not contain full local paths.
- [ ] The execution report does not contain private URLs.
- [ ] The execution report does not claim completion without evidence.

---

## Redaction Format

- [ ] Real secrets are replaced with placeholders: `<REDACTED_API_KEY>`, `<REDACTED_TOKEN>`, `<REDACTED_CREDENTIAL>`.
- [ ] Real paths are replaced with `<LOCAL_PATH_REDACTED>` or relative equivalents.
- [ ] Enough context is preserved for a reviewer to understand what was redacted.
- [ ] Evidence-critical details are not deleted — replaced with redacted placeholders when safe.

---

## Decision

Choose one:

- [ ] **Safe to share** — all sensitive content is redacted or never present.
- [ ] **Needs redaction** — specific items must be redacted before sharing (list below).
- [ ] **Blocked** — material cannot be safely redacted without losing required evidence.
- [ ] **Needs human review** — ambiguity or sensitivity requires human judgment.

Redaction notes:
