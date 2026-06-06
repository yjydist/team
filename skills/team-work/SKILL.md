---
name: team-work
description: Use this skill when the user explicitly asks for an agent team, team dispatch, coordinated specialists, parallel agents, multi-agent software development, or when a software engineering task spans multiple independent domains such as product, architecture, frontend, backend, database, DevOps, QA, and security. Prefer direct local work for narrow single-domain tasks unless coordination materially improves the result.
---

# Team Work

Coordinate specialist software engineering work without over-dispatching. Optimize for correct decomposition, complexity-appropriate process, safe parallelism, clear handoffs, and concise final synthesis.

## Core Workflow

1. **Classify** the request: goal, deliverable, domains, risk, dependencies, whether code edits are expected, and task complexity.
2. **Match process depth to complexity**. Simple tasks stay direct; complex tasks get phased coordination. If a process feels larger than the request, downshift complexity before adding agents.
3. **Read [routing-matrix.md](references/routing-matrix.md)** when role selection is unclear.
4. **Build dependency batches** before dispatching work. Run independent batches in parallel when write scopes and decisions do not conflict.
5. **Use [dispatch-protocol.md](references/dispatch-protocol.md)** for parallelization, ownership, failure handling, and merge rules.
6. **Use [handoff-contracts.md](references/handoff-contracts.md)** when preparing specialist briefs or synthesizing multiple outputs.
7. **Return one unified answer**. Use aggregation only when multiple outputs, unresolved decisions, or contradictions need synthesis.

## Complexity Levels

- **Simple**: one narrow domain, one file/component/query/test failure, or ordinary explanation. Handle locally or use one specialist. Do not add product, architecture, QA, security, or aggregation unless the user explicitly asks or risk requires it.
- **Medium**: one feature slice or 2-3 domains with clear scope, such as API plus UI, schema plus migration, or CI plus test gates. Use 2-4 roles, define contracts first, and parallelize only after dependencies are clear.
- **Complex**: new product/platform, major refactor, multi-system change, unclear scope, or several risk domains. Use phased coordination: product scope, architecture/design, implementation batches, targeted QA/security, then synthesis if needed.

### Common Compositions

| Task | Team |
| --- | --- |
| Login or account feature | backend-developer + frontend-developer; add security-engineer for auth review |
| Data-heavy feature | database-engineer for schema/query contract, backend-developer for API, frontend-developer for UI |
| Small full-stack CRUD | fullstack-developer alone unless separate ownership or risk justifies specialists |
| Platform build | product-manager, system-architect, then implementation specialists by ownership, then targeted QA/security |
| CI or deployment | devops-engineer, plus qa-engineer only if quality gates are part of the request |

## Dispatch Heuristics

- **Do not dispatch** for a single bug explanation, one SQL query, one component, one file edit, or ordinary Q&A unless the user explicitly asks for team mode.
- **Use one specialist** when one domain owns the work and no cross-domain contract is needed.
- **Use 2-4 specialists** when work spans separable domains, such as API plus UI, schema plus migration, or deployment plus CI.

See [routing-matrix.md](references/routing-matrix.md) for per-role triggers, avoidance guidance, and the full role catalog.

## Parallelism and Handoffs

See [dispatch-protocol.md](references/dispatch-protocol.md) for safe/unsafe parallel patterns, batch building, and conflict handling.

See [handoff-contracts.md](references/handoff-contracts.md) for specialist brief and aggregation templates.

## Compatibility

This skill targets Codex; other agent ecosystems may use the files in `agents/` and `.claude-plugin/` as role references.
