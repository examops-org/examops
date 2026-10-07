# ExamOps

ExamOps is a web application for managing exams. This repository is at the foundation stage: there are no product features yet.

## Stack

- [Next.js](https://nextjs.org) (App Router) with TypeScript
- [Tailwind CSS](https://tailwindcss.com) and [shadcn/ui](https://ui.shadcn.com)
- [Vitest](https://vitest.dev) for unit tests
- [pnpm](https://pnpm.io) for package management

## Getting started

Requires Node.js 20+ and pnpm.

```bash
pnpm install
cp .env.example .env.local
pnpm dev
```

Then open http://localhost:3000.

## Scripts

| Command          | What it does                       |
| ---------------- | ---------------------------------- |
| `pnpm dev`       | Start the dev server               |
| `pnpm build`     | Production build                   |
| `pnpm start`     | Serve the production build         |
| `pnpm lint`      | Run ESLint                         |
| `pnpm typecheck` | Generate route types and run `tsc` |
| `pnpm test`      | Run unit tests once                |

## Documentation

- [Product vision](docs/product/vision.md)
- [Architecture overview](docs/architecture/overview.md)
- [Testing strategy](docs/architecture/testing-strategy.md)
- [Architecture decision records](docs/decisions/)

Project rules for contributors and AI agents are in [CLAUDE.md](CLAUDE.md).
