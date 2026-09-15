# Deploy and Host Hono Postgres API with Railway

Lightweight TypeScript API with Hono, Drizzle ORM, and PostgreSQL.

## About Hono Postgres API

A minimal TypeScript backend built with Hono and postgres.js. Includes a task API example (create, list, mark done) and optional API-key protection — fast cold starts and a small footprint compared to heavier frameworks.

## About Hosting Hono Postgres API

Railway builds from your GitHub repo, connects the API to Postgres over the private network, and exposes HTTPS with health checks — no manual container orchestration.

## Environment Variables

| Variable | Description | Secret | Example/Notes |
| --- | --- | --- | --- |
| `DATABASE_URL` | PostgreSQL connection string | Yes | `${{Postgres.DATABASE_URL}}` |
| `API_KEY` | Protects routes except `/health` | Yes | `${{secret(32)}}` — send as `X-API-Key` |
| `PORT` | HTTP port (Railway sets automatically) | No | `$PORT` |

## Deploy and Host

1. Deploy this repo from GitHub on Railway.
2. Add **PostgreSQL** with a **volume**.
3. Set `DATABASE_URL` and `API_KEY` on the API service.
4. Enable **public HTTP** and deploy.
5. Confirm `/health` returns OK.

## Common Use Cases

- Edge-friendly TypeScript APIs
- Serverless-style backends with Postgres
- Small services that need low overhead
- Node.js teams preferring Hono over Express

## Dependencies for Hono Postgres API Hosting

The Railway template includes:

- **Hono Postgres API** — this GitHub repo (Node.js)
- **PostgreSQL** — Railway PostgreSQL plugin

## Deployment Dependencies

- [Hono documentation](https://hono.dev/)
- [Drizzle ORM docs](https://orm.drizzle.team/)
- [Railway PostgreSQL docs](https://docs.railway.com/databases/postgresql)

## Why Deploy Hono Postgres API on Railway?

Fast Node builds, private Postgres references, and a `/health` endpoint wired into Railway deploys — ship a TypeScript API without managing servers.

## Template Content

| Service | Source |
| --- | --- |
| Hono Postgres API | GitHub repo (this template) |
| Postgres | Railway PostgreSQL plugin |

## Run locally

```bash
npm install
copy .env.example .env
npm run dev
```

## Author

romeoxt — herbylegall9@gmail.com

## License

MIT
