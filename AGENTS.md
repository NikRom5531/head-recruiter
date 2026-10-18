# AGENTS.md

## Repo shape

- Not a multi-module build: only `backend/` has a build. `frontend/` is an empty placeholder.
- `backend/` — Spring Boot 4.1.1 (Java 21) scaffold, package root `ru.pride.headrecruiter`. Currently just the application class + one context test; no controllers, entities, or Liquibase changelogs yet.
- Lombok is included and wired via explicit `annotationProcessorPaths` executions in `backend/pom.xml` — keep those when touching the compiler plugin or Lombok-generated code stops compiling.
- `infra/` — Docker Compose for local Postgres 17 + Redis 7.
- `doc/` — architecture doc (`doc/architecture.md`) and ADRs (`doc/adr/`).

## Commands (all Maven commands run from `backend/`)

- Full verification gate (matches CI): `./mvnw -B -ntp verify` — Windows: `.\mvnw.cmd -B -ntp verify`
- Run app: `./mvnw spring-boot:run` — needs a reachable Postgres; the main `application.yaml` has no datasource config, so pass env vars or add a git-ignored `application-local.yaml`.
- Single test: `./mvnw test -Dtest=ClassName`
- No separate lint/typecheck step exists (no Checkstyle/Spotless); `verify` is the whole gate.

## Testing

- `./mvnw verify` works with **no Docker/services**: tests use the `test` Spring profile with H2 in-memory and Liquibase disabled (`backend/src/test/resources/application-test.yaml`).
- New `@SpringBootTest` classes must carry `@ActiveProfiles("test")` or they will try to auto-configure a real datasource and fail.

## Spring Boot 4 gotcha

- Boot 4 renamed starters: use `spring-boot-starter-webmvc` (not `-web`) and per-module test starters (`spring-boot-starter-webmvc-test`, `spring-boot-starter-security-test`, ...). Do not copy Spring Boot 3 snippets or dependency names.

## Local infra

- `cd infra && cp .env.example .env` (Windows: `Copy-Item .env.example .env`), then `docker compose up -d`.
- Compose defaults (`headrecruiter`/`headrecruiter`, ports 5432/6379) are meant to match backend local config.

## Conventions & constraints

- Secrets never committed: `.env.*` (except `.env.example`) and `*.local.yaml` are git-ignored.
- Significant architectural decisions get an ADR in `doc/adr/`; template in `doc/adr/0001-record-architecture-decisions.md`.
- Backend CI (`.github/workflows/backend-ci.yml`) is path-filtered to `backend/**` — infra/doc/frontend-only PRs skip the build. Its single job is named `Build and test`; branch protection references that name, so renaming it breaks the required status check.
- Line endings: LF enforced via `.gitattributes`; `.cmd`/`.bat` stay CRLF. Indent 4 spaces (2 for yaml/json/md) per `.editorconfig`.
- Per `CONTRIBUTING.md`: imperative-mood commit messages, one logical change per PR, tests for behavior changes.
