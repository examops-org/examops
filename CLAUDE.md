# ExamOps project rules

@AGENTS.md

## What ExamOps is

ExamOps is a certification preparation platform. The initial product focuses on:

- Questions
- Practice
- Mock exams
- Explanations
- Notes
- Progress
- Readiness

We are building ExamOps to be AI-native, but AI must never automatically publish certification content. All AI-generated content requires human review before it is published.

## Rules

- Keep the architecture simple. Prefer a plain module over a new layer or abstraction.
- Do not implement features that were not requested.
- Ask for clarification before making a major architectural decision. Record decisions as ADRs in `docs/decisions/`.
- Never commit secrets. Only `.env.example`, with placeholder values, is committed.
- Use TypeScript for all application code, with `strict` mode on.
- Do not add dependencies without a reason.
- Write tests for important business logic. See `docs/architecture/testing-strategy.md`.

## Before completing work

Run all of these, and make sure they pass:

```bash
pnpm lint
pnpm typecheck
pnpm test
pnpm build
```

## Layout

- `src/app/`: Next.js App Router routes
- `src/components/`: UI components (shadcn/ui components live in `src/components/ui/`)
- `src/lib/`: shared utilities
- `src/modules/`: domain and business logic, one folder per domain area
- `docs/`: product, architecture, content, and decision records
