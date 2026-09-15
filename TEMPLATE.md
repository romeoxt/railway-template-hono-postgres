# Railway Template Composer Setup

## Marketplace listing

- **Title:** Deploy and Host Hono Postgres API with Railway
- **Short description:** Lightweight TypeScript API with Hono, Drizzle ORM, and PostgreSQL.
- **Category:** Starters
- **Overview:** paste `README.md`

## Services

| Service | Source | Volume | Public HTTP |
| --- | --- | --- | --- |
| Hono Postgres API | GitHub repo (this folder) | — | Yes |
| Postgres | Railway PostgreSQL plugin | `/var/lib/postgresql/data` | No |

## Variables — Hono Postgres API

| Variable | Value | Secret | Description |
| --- | --- | --- | --- |
| `DATABASE_URL` | `${{Postgres.DATABASE_URL}}` | Yes | Postgres connection |
| `API_KEY` | `${{secret(32)}}` | Yes | `X-API-Key` except `/health` |

## Settings — Hono Postgres API

- Healthcheck: `/health`
- Start command: `npm start` (from `Procfile`)
