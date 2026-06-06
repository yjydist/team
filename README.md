# Agent Team

Agent Team is a compatible multi-agent software development plugin. It provides a Codex-first `team-work` skill while keeping existing Claude Code and Qwen metadata for users who rely on those runtimes.

Use it when a request benefits from coordinated specialist reasoning: product scope, architecture, frontend, backend, database, DevOps, QA, security, mobile, and final synthesis.

## Repository Layout

```text
.
├── .codex-plugin/plugin.json      # Codex plugin manifest
├── .claude-plugin/plugin.json     # Claude Code compatibility manifest
├── qwen-extension.json            # Qwen compatibility manifest
├── skills/
│   └── team-work/
│       ├── SKILL.md               # Codex-first coordination skill
│       ├── agents/openai.yaml     # Codex skill UI metadata
│       ├── references/            # Routing, dispatch, handoff guidance
│       └── scripts/               # Offline routing eval validator
├── agents/                        # Specialist agent profiles (legacy/reference)
├── AGENTS.md                      # Contributor guide
└── LICENSE
```

## Usage in Codex

Invoke the skill explicitly for coordinated work:

```text
Use $team-work to plan and implement this full-stack feature.
Use $team-work to coordinate parallel agents for this migration.
Use $team-work to review this multi-domain architecture change.
```

The skill is intentionally selective. It should not expand a simple one-file bug, single SQL query, or ordinary explanation into a full team workflow unless you ask for team mode. Medium tasks use a small coordinated team; complex tasks use phased planning, implementation, verification, and synthesis.

See [skills/team-work/SKILL.md](skills/team-work/SKILL.md) for the full coordination model.

## Specialist Roles

| Role | Primary Ownership |
| --- | --- |
| `product-manager` | Scope, user stories, acceptance criteria, prioritization |
| `system-architect` | Architecture, service boundaries, technology choices |
| `ui-ux-designer` | User flows, wireframes, usability, design systems |
| `frontend-developer` | Browser UI, components, state, layout, accessibility |
| `backend-developer` | APIs, services, auth services, jobs, integrations |
| `fullstack-developer` | Small end-to-end slices and prototypes |
| `mobile-developer` | iOS, Android, React Native, Flutter, device APIs |
| `database-engineer` | Schema, migrations, queries, indexes, data pipelines |
| `devops-engineer` | CI/CD, containers, cloud, observability, releases |
| `qa-engineer` | Test strategy, automation, quality gates |
| `security-engineer` | Auth, secrets, payment, public APIs, compliance |
| `output-aggregator` | Multi-output synthesis and conflict resolution |
| `team-lead` | Legacy coordinator role; superseded by the `team-work` skill |

The `agents/*.md` files are retained for Claude Code compatibility and as source material for routing references.

## Development and Validation

See [AGENTS.md](AGENTS.md) for development commands, style guidelines, and contribution instructions.

## Compatibility Notes

Codex discovers the plugin through `.codex-plugin/plugin.json` and the `team-work` skill. Codex does not automatically treat `agents/*.md` as native subagents; those files are retained for Claude Code compatibility and as source material for the routing references.
