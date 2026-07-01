# Basic AI Project Example

This example shows how a normal project can use `coding-agent-safety-gate` with a minimal `.ai/` directory.

No real secrets, private paths, or real repository remotes are included.

## Example Project Layout

```text
basic-ai-project/
├── README.md
└── .ai/
    ├── PROJECT_RULES.md
    ├── NEXT_TASK.md
    └── ACCEPTANCE_CHECKLIST.md
```

## Example `.ai/PROJECT_RULES.md`

```text
# PROJECT_RULES

Project purpose:
- A small demo project used to test AI-assisted documentation updates.

Allowed:
- Edit README.md when the current task allows it.
- Report changed files and verification evidence.

Not allowed:
- Read or expose real secrets.
- Add dependencies.
- Create scripts.
- Create GitHub Actions.
- Add or modify git remotes.
- Run git push, git tag, or create a release.
- Modify system configuration.
```

## Example `.ai/NEXT_TASK.md`

```text
# NEXT_TASK

Current task:
- Update README.md to make the project introduction clearer.

Background:
- The existing introduction is too vague for new readers.

File scope:
- README.md

Explicitly allowed operations:
- Edit the README introduction.
- Add one short usage example.

Explicitly forbidden operations:
- Do not edit files outside README.md.
- Do not add scripts.
- Do not add dependencies.
- Do not read or expose real secrets.
- Do not introduce full private local paths.
- Do not run git push, git tag, create a release, or add a remote.

Acceptance criteria:
- README.md explains the project in one or two clear paragraphs.
- README.md contains one simple usage example.
- No unrelated files are changed.
- The agent reports verification evidence.
```

## Example `.ai/ACCEPTANCE_CHECKLIST.md`

```text
# ACCEPTANCE_CHECKLIST

- [ ] README.md exists.
- [ ] README.md introduction is clearer.
- [ ] README.md includes one simple usage example.
- [ ] No unrelated files were changed.
- [ ] No real secret or API key appears.
- [ ] No full private local path appears.
- [ ] No system configuration was modified.
- [ ] No git push, tag, release, or remote operation was performed.
- [ ] The agent provided changed files and verification results.
- [ ] The agent listed incomplete items, if any.
```

## Example Agent Request

```text
Please follow the coding-agent-safety-gate skill.
Read .ai/PROJECT_RULES.md and .ai/NEXT_TASK.md.
Complete only the approved README update.
When finished, provide evidence using .ai/ACCEPTANCE_CHECKLIST.md.
```

The human decides whether the result is accepted and what the next task should be.
