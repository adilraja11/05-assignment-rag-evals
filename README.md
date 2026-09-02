# RAG Agent Evals

pnpm workspace containing:

- `apps/platform` — React, Vite, and TanStack Router
- `apps/api` — Hono on Node.js with Prisma and PostgreSQL
- `packages/agents` — shared agent code

## Setup

```sh
pnpm install
cp .env.example .env
docker compose -f docker-compose.dev.yml up -d db qdrant
pnpm db:generate
pnpm db:migrate
pnpm dev
```

All workspace commands load the single root `.env` file through `dotenv-cli`.
Set `OPENAI_API_KEY` in `.env`. `TAVILY_API_KEY` is optional because Tavily supports keyless usage with lower limits.

## Commands

```sh
pnpm dev           # run the platform and API together
pnpm dev:platform  # run the Vite app on port 3000
pnpm dev:api       # run the Hono API (PORT, default 8000)
pnpm build
pnpm typecheck
pnpm db:generate
pnpm db:migrate
pnpm db:studio
pnpm ingest:handbook
pnpm eval
```
