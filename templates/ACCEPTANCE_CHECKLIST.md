# ACCEPTANCE_CHECKLIST

Use this checklist before accepting AI-assisted work.

## Scope

Changed files:

- 

- [ ] Required files exist.
- [ ] Content matches the approved task scope.
- [ ] No unrelated files were modified.
- [ ] No broad formatting churn was introduced.

## Validation

Build result:

- [ ] PASS
- [ ] FAIL
- [ ] Not applicable

Test result:

- [ ] PASS
- [ ] FAIL
- [ ] Not applicable

Validation evidence:

- 

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

- [ ] `git push` executed? No / Yes
- [ ] `git tag` executed? No / Yes
- [ ] Release created? No / Yes
- [ ] Remote added or modified? No / Yes
- [ ] Force push or history rewrite performed? No / Yes

## Known Risks

- 

## Incomplete Items

- 

## Human Review

- [ ] Human review required? No / Yes

Reason:

## Final Acceptance

Choose one:

- [ ] PASS
- [ ] FAIL
- [ ] BLOCKED
- [ ] NEEDS HUMAN REVIEW
