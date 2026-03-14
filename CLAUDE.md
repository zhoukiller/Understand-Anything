# Understand Anything

## Project Overview
An open-source tool combining LLM intelligence + static analysis to produce interactive dashboards for understanding codebases.

## Architecture
- **Monorepo** with pnpm workspaces
- **packages/core** — Shared analysis engine (types, persistence, tree-sitter plugin, LLM prompt templates)
- **packages/dashboard** — React + TypeScript web dashboard (React Flow, Monaco Editor, Zustand, TailwindCSS)
- **packages/skill** — Claude Code skills (`/understand-chat`, `/understand-diff`, `/understand-explain`, `/understand-onboard`)

## Key Commands
- `pnpm install` — Install all dependencies
- `pnpm --filter @understand-anything/core build` — Build the core package
- `pnpm --filter @understand-anything/core test` — Run core tests
- `pnpm dev:dashboard` — Start dashboard dev server

## Key Commands (updated)
- `pnpm --filter @understand-anything/skill build` — Build skill package
- `pnpm --filter @understand-anything/skill test` — Run skill tests

## Phase 2 Features
- Fuzzy search via Fuse.js (SearchEngine in core)
- Zod schema validation on graph loading
- Staleness detection + incremental graph merging
- Layer auto-detection (heuristic + LLM prompt)
- `/understand-chat` skill command
- Dashboard chat panel (Claude API integration)
- Dagre auto-layout for graph visualization
- Layer visualization with grouping and legend

## Conventions
- TypeScript strict mode everywhere
- Vitest for testing
- ESM modules (`"type": "module"`)
- Knowledge graph JSON lives in `.understand-anything/` directory of analyzed projects
