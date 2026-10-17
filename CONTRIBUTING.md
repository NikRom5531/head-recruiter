# Contributing to head-recruiter

Thanks for your interest in contributing! This document describes how to get
involved.

## Code of Conduct

By participating in this project you agree to abide by our
[Code of Conduct](CODE_OF_CONDUCT.md).

## How can I contribute?

- Report bugs and request features through GitHub Issues.
- Improve documentation.
- Submit pull requests with fixes and new functionality.

Before starting on a large change, please open an issue first so we can discuss
the approach and avoid duplicated work.

## Development setup

1. Fork and clone the repository.
2. Ensure you have JDK 21, PostgreSQL and Redis available (see the
   [README](README.md) and [backend README](backend/README.md)).
3. Create a topic branch off `main`:

   ```bash
   git checkout -b feature/short-description
   ```

## Coding guidelines

- Keep changes focused; one logical change per pull request.
- Follow the existing code style and conventions.
- Add or update tests for any behavior change.
- Keep commit messages clear and in the imperative mood
  (e.g. `Add candidate search endpoint`).
- Do not commit secrets, credentials, or environment-specific configuration.

## Building and testing

All commands are run from the `backend/` directory:

```bash
./mvnw verify
```

Windows:

```powershell
.\mvnw.cmd verify
```

Make sure the build passes before opening a pull request.

## Pull request process

1. Update documentation if needed.
2. Ensure the CI pipeline passes.
3. Fill in the pull request template.
4. A maintainer will review your changes and may request modifications.
5. Once approved, the pull request is merged.

## License

By contributing, you agree that your contributions are licensed under the
project's [Apache License 2.0](LICENSE).
