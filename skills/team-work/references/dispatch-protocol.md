# Dispatch Protocol

Use this protocol when coordinating multiple specialists or parallel agents. Scale the protocol to the task: simple tasks should not inherit complex ceremony.

## Complexity Fit

- **Simple**: answer directly or route to one specialist. Skip batching, aggregation, and multi-agent handoffs.
- **Medium**: define the minimum contract needed for 2-4 roles, then run independent work in one or two batches.
- **Complex**: use explicit phases: scope, architecture/design, implementation, verification, synthesis.

## Build Batches

1. Identify decisions that must happen before implementation: product scope, architecture, API contract, schema, UI flow.
2. Group independent work into batches. A later batch may depend on outputs from an earlier batch.
3. Assign each agent an explicit ownership area: files, modules, contracts, or deliverables.
4. State what each agent must not touch when parallel edits could conflict.

## Safe Parallel Patterns

- Product requirements and UX exploration can run together when both receive the same original request and no final design decision is required yet.
- Architecture and UX can run together after product scope is stable.
- Frontend and backend can run together after API contracts, data shapes, and auth assumptions are explicit.
- QA and security can run together after there is an implementation, design, or diff to inspect.
- Independent verification can run while non-overlapping implementation continues.

## Unsafe Parallel Patterns

- Two agents editing the same files or migration chain.
- Frontend starting before endpoint names, payloads, or auth behavior are known.
- Backend and database making incompatible schema or transaction decisions.
- DevOps changing deployment assumptions while architecture is undecided.
- Mobile and backend making incompatible sync, conflict, or offline decisions.
- Security or QA reviewing before any implementation, design, or diff artifact exists.
- Product and architecture running in parallel before scope is stable.
- Multiple specialists editing overlapping API contracts, schemas, or auth policies.
- Adding output-aggregator when only one specialist produced output.
- Aggregation before all required outputs are available.

## Failure and Conflict Handling

- If an agent cannot proceed, capture the blocker and continue independent work.
- If outputs conflict, identify the source of truth: user requirement, existing code, tests, architecture decision, or risk constraint.
- Resolve low-impact conflicts directly. Escalate only when the user must choose a product or risk trade-off.
- When integration risk is high, add a verification batch rather than expanding the implementation batch.

## Efficiency Rules

- Do not add roles for ceremony. Every role must reduce risk, unblock work, or improve quality.
- Prefer one strong owner over multiple overlapping owners.
- Parallelism is valuable only when it shortens the critical path without making integration harder.
- If a process feels larger than the user request, downshift the complexity before adding agents.
