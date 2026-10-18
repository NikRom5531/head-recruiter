# Security Policy

## Supported versions

head-recruiter is in early development. Security fixes are applied to the
latest revision of the `main` branch only.

| Version         | Supported |
|-----------------|-----------|
| `main` (latest) | Yes       |

## Reporting a vulnerability

Please do **not** report security vulnerabilities through public GitHub issues,
discussions, or pull requests.

Instead, use GitHub's private vulnerability reporting:

1. Open the [Security Advisories](https://github.com/NikRom5531/head-recruiter/security/advisories/new)
   page for this repository.
2. Click **Report a vulnerability** and fill in the form.

Alternatively, contact the maintainers directly via the email listed on their
GitHub profile.

Please include as much of the following as you can:

- A description of the vulnerability and its impact.
- Steps to reproduce or a proof of concept.
- Affected component/version or commit.
- Any suggested fix or mitigation.

## What to expect

- We will acknowledge your report as soon as possible.
- We will investigate and keep you informed of the progress.
- Once resolved, we will credit you in the release notes unless you prefer to
  stay anonymous.

## Handling secrets

Never commit secrets, credentials, tokens, or environment-specific
configuration. Local secrets belong in a git-ignored `.env` or
`application-local.yaml` file (see [CONTRIBUTING.md](CONTRIBUTING.md)).
