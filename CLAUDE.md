# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Build & Development Commands

- `pnpm dev` — Start Vite dev server with HMR
- `pnpm build` — Type-check with `tsc -b` then bundle with Vite
- `pnpm lint` — Run ESLint on .ts/.tsx files
- `pnpm preview` — Preview production build locally

Firebase deployment uses the `dist/` output directory and is configured for SPA routing.

## Tech Stack

- **React 19** + **TypeScript 5.9** (strict mode, react-jsx transform)
- **Vite 7** with SWC plugin (`@vitejs/plugin-react-swc`) for fast refresh
- **Firebase** (Firestore, Realtime Database, Hosting) — project: `hydration-315f8`, region: asia-northeast1
- **pnpm** as package manager (workspace-enabled)
- **ESLint 9** flat config with typescript-eslint, react-hooks, and react-refresh plugins

## Architecture

Single-page React app. Entry flow: `index.html` → `src/main.tsx` (React root with StrictMode) → `src/App.tsx`.

Firebase is initialized in `App.tsx` but not yet wired into app logic. The project is in early stage — currently a starter template with a counter component.

## TypeScript

Strict mode with `noUnusedLocals`, `noUnusedParameters`, `noFallthroughCasesInSwitch`, and `noUncheckedSideEffectImports` enabled. Bundler module resolution targeting ES2022.
