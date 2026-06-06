# Handoff Contracts

Use these concise templates when briefing specialists or synthesizing results.

## Specialist Brief

```markdown
## Task Brief

Original request: <user request>
Role: <specialist role>
Objective: <specific outcome>
Ownership: <files/modules/contracts/deliverables owned by this role>
Context: <decisions, constraints, existing code, prior outputs>
Inputs: <links, schemas, API contracts, designs, diffs>
Do not touch: <parallel conflict boundaries, if any>
Expected output: <patch, plan, review findings, test strategy, etc.>
Handoff: <what the next role needs from this output>
```

## Aggregation Brief

```markdown
## Aggregation Brief

Original request: <user request>
Participants: <roles involved>
Outputs: <summaries or links to each output>
Conflicts to resolve: <known disagreements or gaps>
Required final shape: <implementation summary, plan, PR notes, review, etc.>
Quality bar: <tests, risks, acceptance criteria>
```

## Parallel Batch Dispatch Brief

```markdown
## Batch Brief

Original request: <user request>
Batch: <batch number/name>
Agents: <roles in this batch>
Contracts: <shared API/schema/UX assumptions>
Independent deliverables:
- <agent>: <owned files/modules/output>
- <agent>: <owned files/modules/output>
Integration plan: <how outputs merge>
Blocker escalation: <who decides if conflict arises>
```

## Conflict Resolution Brief

```markdown
## Conflict Resolution

Original request: <user request>
Participants: <roles with conflicting outputs>
Conflict: <specific disagreement>
Source of truth: <user requirement / existing code / tests / architecture / risk constraint>
Resolution: <chosen approach and rationale>
Escalation: <what still needs user input>
```

## Blocker Capture Brief

```markdown
## Blocker

Original request: <user request>
Blocked agent: <role>
Blocker: <what is preventing progress>
Impact: <which downstream work is affected>
Workaround: <what independent work can continue>
Resolution path: <what is needed to unblock>
```

## Verification Batch Brief

```markdown
## Verification Batch

Original request: <user request>
Verification focus: <QA / security / integration / performance>
Artifacts to inspect: <code, design, diff, config>
Risks to validate: <specific concerns>
Pass criteria: <what confirms the artifact is ready>
Remaining gaps: <what could not be verified>
```

## API Contract Brief

```markdown
## API Contract

Endpoints:
- <method> <path>: <purpose>
Request shape: <schema>
Response shape: <schema>
Error semantics: <status codes, retry behavior>
Auth requirements: <mechanism, scopes>
Owner: <backend-developer>
Consumers: <frontend-developer, mobile-developer, etc.>
```

## Security Review Findings Brief

```markdown
## Security Findings

Scope: <what was reviewed>
Confirmed findings:
- <severity>: <location> — <description> — <remediation>
Hardening recommendations:
- <description> — <rationale>
Verification steps:
- <test, scan, or manual check>
```

## QA Test Strategy Brief

```markdown
## Test Strategy

Scope: <features under test>
Test levels:
- Unit: <components>
- Integration: <APIs, services>
- E2E: <user flows>
Edge cases: <boundary conditions, error states>
Coverage targets: <metrics or gates>
Automation plan: <what will be automated vs manual>
```

## Final Synthesis Checklist

- Answer the user's original request directly.
- Identify the chosen approach and why it fits the constraints.
- Merge duplicate recommendations.
- Resolve naming, API, schema, and ownership inconsistencies.
- Call out remaining risks and verification status.
- Keep final output concise unless the user requested a full design or plan.
