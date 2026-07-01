# ACCEPTANCE_CHECKLIST

Use this checklist before accepting AI-assisted work. Copy into your own project.

## Scope

Changed files:

- README.md

- [ ] Required files exist.
- [ ] Content matches the approved task scope.
- [ ] No unrelated files were modified.
- [ ] No broad formatting churn was introduced.

## Validation

Build result:

- [ ] PASS
- [ ] FAIL
- [x] Not applicable

Test result:

- [ ] PASS
- [ ] FAIL
- [x] Not applicable

Validation evidence:

- git diff README.md shows only the introduction change

## Secret And Path Safety

- [ ] Full path leaked? No / Yes
- [ ] Secret leaked? No / Yes
- [ ] Real API key or token leaked? No / Yes
- [ ] SecretStore read? No / Yes
- [ ] Examples use placeholders only.

## Execution Safety

- [ ] Real Agent started? No / Yes
- [ ] Terminal command executed? No / Yes
- [ ] Terminal start clicked? No / Yes
- [ ] Only approved validation commands were executed.

## System Safety

- [ ] System env modified? No / Yes
- [ ] Registry modified? No / Yes
- [ ] Shell profile modified? No / Yes
- [ ] VS Code config modified? No / Yes
- [ ] Non app-managed files deleted? No / Yes

## Git Safety

- [ ] git push executed? No / Yes
- [ ] git tag executed? No / Yes
- [ ] Release created? No / Yes
- [ ] Remote added or modified? No / Yes
- [ ] Force push or history rewrite performed? No / Yes

## Known Risks

- None identified. This is a documentation-only change.

## Incomplete Items

- None

## Human Review

- [ ] Human review required? No / Yes

Reason:

## Final Acceptance

Choose one:

- [ ] PASS
- [ ] FAIL
- [ ] BLOCKED
- [ ] NEEDS HUMAN REVIEW
