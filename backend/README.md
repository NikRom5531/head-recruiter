# head-recruiter — backend

Spring Boot service that powers the head-recruiter platform.

## Stack

- Java 21
- Spring Boot
- Spring Web MVC, Spring Data JPA, Spring Security, Spring Validation
- Liquibase (database migrations)
- PostgreSQL, Redis
- Lombok
- Tests: JUnit 5, Spring Boot Test

## Requirements

- JDK 21+
- PostgreSQL
- Redis

## Build & run

Use the bundled Maven Wrapper.

```bash
./mvnw spring-boot:run
```

Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

## Tests

```bash
./mvnw verify
```

## Configuration

Application configuration is in `src/main/resources/application.yaml`.

Do not commit secrets. Provide machine-specific values through environment
variables or a local profile (e.g. `application-local.yaml`, which is
git-ignored).

## Packaging

```bash
./mvnw clean package
```

The executable jar is produced in `target/`.

See the top-level [README](../README.md) for the project overview and
[CONTRIBUTING](../CONTRIBUTING.md) for the contribution process.
