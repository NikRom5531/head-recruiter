# Infrastructure

Local development infrastructure for head-recruiter, provided as a Docker
Compose stack.

## Services

| Service    | Image                | Port | Purpose          |
|------------|----------------------|------|------------------|
| `postgres` | `postgres:17-alpine` | 5432 | Primary database |
| `redis`    | `redis:7-alpine`     | 6379 | Cache / sessions |

## Usage

```bash
cd infra
cp .env.example .env   # adjust values if needed
docker compose up -d
```

Stop the stack:

```bash
docker compose down
```

Stop the stack and remove volumes (deletes all data):

```bash
docker compose down -v
```

On Windows, use `Copy-Item .env.example .env` instead of `cp`.

## Configuration

All values are read from the `.env` file with sensible defaults. Default
credentials match the backend defaults, so a freshly started stack works out of
the box for local development.

> Do not commit the `.env` file — it is git-ignored. Use `.env.example` as the
> template.
