# Testing strategy

> Status: initial. No application tests exist yet.

## Approach

Test where bugs would be costly, and keep the tests fast.

| Layer | Tool | What to test | When |
| --- | --- | --- | --- |
| Unit | Vitest | Pure business logic, such as scoring, scheduling, and validation | Now: required for important business logic |
| Component | Vitest + Testing Library | Non-trivial interactive components | Add when such components exist |
| End-to-end | Playwright | A few critical user journeys | Add when the first full user flow exists |

Component and end-to-end tooling is intentionally **not installed yet**. Add it when there is something to test, per the dependency rule in `CLAUDE.md`.

## Conventions

- Put tests next to the code they test, named `*.test.ts`.
- Keep business logic in plain TypeScript functions (no React or Next.js imports) so it can be unit tested directly.
- Tests must not need network access or real secrets.

## Running

```bash
pnpm test        # run once
pnpm test:watch  # watch mode
```

Configuration is in `vitest.config.mts`. The `@/` import alias works in tests.
