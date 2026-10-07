# Architecture overview

> Status: initial. Update when the architecture changes.

## Approach

ExamOps is a single Next.js application, organized as a modular monolith. See [ADR-0001](../decisions/0001-modular-nextjs-monolith.md) for why we chose this over microservices.

## Stack

- **Framework:** Next.js with the App Router. Pages are Server Components by default; Client Components are used only when interactivity requires them.
- **Language:** TypeScript, with `strict` mode on.
- **Styling and UI:** Tailwind CSS and shadcn/ui.
- **Testing:** Vitest. See the [testing strategy](testing-strategy.md).

## Project structure

| Path | Purpose |
| --- | --- |
| `src/app/` | Routes, layouts, and pages (App Router) |
| `src/components/` | UI components. shadcn/ui components live in `src/components/ui/`. |
| `src/lib/` | Shared utilities |
| `src/modules/` | Domain and business logic, one folder per domain area (for example `src/modules/questions/`). Created when the first domain feature is built. |
| `docs/` | Product, architecture, content, and decision records (ADRs) |

### Module rules

- Each module exposes a small public API. Other modules don't import its internals.
- Business logic is written as plain TypeScript, with no React or Next.js imports, so it can be unit tested directly.
- Routes and components call into modules; modules don't depend on routes or components.

## Not implemented yet

The following are intentionally not implemented yet. Each will be decided, and recorded as an ADR, when a requested feature needs it:

- Database and data access
- Authentication and authorization
- AI integration
- Deployment and hosting

## Configuration

Environment variables are documented in `.env.example`. Real values go in `.env.local`, which is gitignored.
