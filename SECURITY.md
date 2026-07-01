# Security Policy

## Reporting a security concern

This project welcomes reports about documentation safety issues. Examples:

- Unsafe or misleading instructions in templates or docs
- Risk of secret exposure in example content
- Risk of full local path exposure
- Guidance that could be interpreted as authorizing unapproved git push, tag, release, or remote changes
- Language that could be mistaken for runtime enforcement claims

Open an issue with the label `security` or `documentation-safety`, or contact the maintainers directly.

## What to avoid in public reports

Do not post real secrets in issues, pull requests, or discussions. This includes:

- API keys
- tokens
- cookies
- private keys
- production credentials
- full local machine paths
- private repository URLs

Use placeholders such as `YOUR_API_KEY_HERE`, `EXAMPLE_TOKEN`, or `REDACTED`.

## Scope

This project is **documentation-and-template-only**. It does not accept, verify, scan, or store real secrets. It does not run code, install dependencies, or execute commands.

If you discover a security issue in a dependency, runtime, or external tool used alongside this project, report it to that tool's maintainers.
