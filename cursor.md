# AyshaCanada — Cursor instructions

This is the project playbook for Cursor in this folder. Follow it on every task unless the user overrides it.

## Project

- **Name:** AyshaCanada
- **Root:** `d:\New AyshaCanada`
- **Status:** New workspace. Scaffold and code against the stack below.

## Tech stack

- **Runtime:** Node.js
- **Language:** TypeScript (strict). No new `.js` / `.jsx` app files.
- **Framework:** Next.js (App Router)
- **UI:** React Server Components by default. Use `"use client"` only when browser APIs, event handlers, or client state are required.
- **Styling:** CSS Modules or Tailwind if already in the repo. Do not mix a new styling system without being asked.
- **Package manager:** Use whatever lockfile exists (`package-lock.json` → npm, `pnpm-lock.yaml` → pnpm, `yarn.lock` → yarn). If none exists yet, use **npm**.
- **Env:** `NEXT_PUBLIC_*` for browser-safe values only. Secrets stay in server-only env (never import them in Client Components).

## Next.js / TypeScript conventions

- Routes live under `app/`. Shared UI under `components/`. Server logic under `lib/` (or `server/`).
- Data fetching and mutations: Server Components, Route Handlers (`app/api/.../route.ts`), or Server Actions — not ad-hoc client `fetch` unless needed.
- Prefer `async` Server Components over `useEffect` for initial data.
- Types: explicit props and API payloads. Avoid `any`. Use `unknown` + narrowing when the shape is unsure.
- Path aliases: follow `tsconfig.json` (`@/` if configured).
- Images: `next/image`. Links: `next/link`. Fonts: `next/font`.
- Keep server and client boundaries clean. Do not pass non-serializable values from Server to Client Components.

## How to work

1. Read this file and the current folder layout before changing code.
2. Prefer small, focused edits over rewrites.
3. Do not add files the user did not ask for (README, extra docs, configs).
4. Do not commit or push unless the user explicitly asks.
5. After UI/layout/routing/state changes, verify in the browser (or the closest substitute) before calling the work done.

## Language

- User may write in Bangla, English, or mixed. Reply in the same mix they used, unless they ask otherwise.
- Code, file names, comments, and commit messages stay in English.

## Code style

- Match existing patterns in the repo once they exist.
- Keep diffs small. No drive-by refactors.
- No unused dependencies, commented-out blocks, or speculative features.
- Secrets stay out of git (`.env`, tokens, passwords). Warn if the user asks to commit them.

## Hostinger

If the task touches Hostinger (sites, DNS, WordPress, VPS, billing):

- Use Hostinger MCP tools, not curl/ssh/hand-rolled API calls.
- Confirm destructive or live-overwriting actions with the user first (delete, deploy overwrite, DNS A/MX/NS, spend money).
- Read/list/get/validate calls do not need confirmation.
- Node.js / Next.js deploys: use the Hostinger Node.js deployment tools and project `nodejs-deployments` rules when shipping.

## Git

- Commit only when asked.
- Never change git config, skip hooks, or force-push unless the user explicitly requests it.
- Never amend a commit that is already pushed.

## When the repo grows

Update this file when deploy target, live domain, database, or auth become real.
