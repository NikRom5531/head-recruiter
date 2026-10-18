# head-recruiter

[![Backend CI](https://github.com/NikRom5531/head-recruiter/actions/workflows/backend-ci.yml/badge.svg)](https://github.com/NikRom5531/head-recruiter/actions/workflows/backend-ci.yml)
[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

An open-source platform for head recruiting: managing vacancies, candidates and
the hiring pipeline.

> **Project status:** early development. The backend is a Spring Boot
> application scaffold; the frontend and infrastructure are planned.

## Repository layout

| Path        | Description                                                  |
|-------------|--------------------------------------------------------------|
| `backend/`  | Spring Boot backend (REST API, persistence, security)        |
| `frontend/` | Web client (work in progress)                                |
| `infra/`    | Infrastructure as code, local environment (work in progress) |
| `doc/`      | Project documentation and design decisions                   |

## Technology stack

- **Backend:** Java 21, Spring Boot, Spring Web MVC, Spring Data JPA,
  Spring Security, Spring Validation, Liquibase, Redis
- **Database:** PostgreSQL
- **Build:** Maven (wrapper included)

## Getting started (backend)

### Requirements

- JDK 21+
- PostgreSQL
- Redis

The Maven Wrapper is bundled, so a local Maven installation is not required.

```bash
cd backend
./mvnw spring-boot:run
```

On Windows:

```powershell
cd backend
.\mvnw.cmd spring-boot:run
```

Configuration lives in `backend/src/main/resources/application.yaml`. Use the
`local` Spring profile (or environment variables) for machine-specific values —
never commit secrets.

### Running tests

```bash
cd backend
./mvnw verify
```

## Local infrastructure

PostgreSQL and Redis for local development are provided as a Docker Compose
stack:

```bash
cd infra
docker compose up -d
```

See [infra/README.md](infra/README.md) for details.

## Documentation

- [Architecture overview](doc/architecture.md)
- [Architecture Decision Records](doc/adr/)
- [Contributing](CONTRIBUTING.md)
- [Security policy](SECURITY.md)

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and the
[Code of Conduct](CODE_OF_CONDUCT.md) before opening an issue or a pull request.

## License

Licensed under the [Apache License 2.0](LICENSE).
