# Interactive ZSL Translator

An accessible browser workspace for visualizing hand landmarks and collecting real Zimbabwean Sign Language training examples before a validated recognition model is connected.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

- `artifacts/zsl-translator/` — deployable React/Vite app and the main user experience.
- `attached_assets/` — the capstone proposal that defines the research goals and performance targets.
- `artifacts/api-server/` — shared API service scaffold; the first translator milestone keeps camera processing local in the browser.

## Architecture decisions

- The first milestone is client-side so camera frames and landmark data do not leave the browser.
- Hand tracking and trained sign recognition are separate states; the UI must not present tracking confidence as translation accuracy.
- Dataset capture metadata is stored locally first so the student can collect samples without accounts or a server dependency.

## Product

The app provides a live camera workspace for hand-landmark visualization, a transparent recognition status panel, and a local capture workspace for building the starter ZSL dataset. Later milestones can attach a validated quantized model, speech output, and adaptive streaming.

## User preferences

- Explain the project in plain language so a non-technical person can follow what is happening.

## Gotchas

- Browser camera access requires a secure preview or localhost and explicit user permission.
- Recognition results must remain clearly marked as unavailable until a real trained ZSL model is attached and evaluated.

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
