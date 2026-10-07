# ADR-0001: Start with a modular Next.js application, not microservices

- **Status:** Accepted
- **Date:** 2026-10-08

## Context

ExamOps is a new product with a small team and requirements that are still forming. We need to deliver and change features quickly while keeping the codebase understandable.

## Decision

Build ExamOps as a single Next.js (App Router, TypeScript) application, organized internally into modules by domain area. We will not start with microservices.

## Rationale

- **Speed.** One codebase, one build, one deployment. No service contracts, network calls, or distributed debugging between features.
- **Unclear boundaries.** Service boundaries are expensive to get wrong and hard to move. Modules inside one app can be reshaped cheaply while the domain is still being learned.
- **Operational cost.** Microservices need service discovery, inter-service auth, distributed tracing, and more infrastructure. That cost isn't justified at this scale.
- **Consistency.** A single app makes transactions and data consistency straightforward.
- **Fit.** Next.js covers both UI and server-side logic (Server Components, Route Handlers, Server Actions), so no separate backend is needed yet.

## Consequences

- Module boundaries must be kept deliberately: each module exposes a small public API, and other modules do not reach into its internals.
- The whole app scales and deploys as one unit. That's acceptable for now.
- If a module later has clearly different scaling, reliability, or ownership needs, it can be extracted into a separate service. That will require a new ADR.
