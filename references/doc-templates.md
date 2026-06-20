# AI Agent Development Documentation Templates

Use these templates selectively. Generate only the documents that fit the user's stage and repo.

## Document Map

| Document | Purpose | Typical file |
| --- | --- | --- |
| Vision / Idea / Requirements | Define why to build, business boundary, users, and success direction | `docs/vision-requirements.md` |
| PRD | Define what to build, non-functional needs, KPIs, risks | `docs/prd.md` |
| Agent-Ready PRD | Remove ambiguity for AI agents: states, rules, edge cases, acceptance criteria | `docs/agent-ready-prd.md` |
| Design / HLD / LLD | Define how to build: architecture, modules, APIs, data, integration | `docs/design.md` |
| Spec | Define executable task list, dependencies, and acceptance criteria | `docs/spec.md` |
| Workplan | Define step-by-step implementation plan and parallelization guidance | `docs/workplan.md` |
| AGENTS.md / CLAUDE.md | Define agent operating manual for the repo | `AGENTS.md`, `CLAUDE.md` |
| `.ai/` | Store AI workflow config, prompts, checklists, and reusable instructions | `.ai/` |
| Development Standards | Define team engineering rules | `docs/development-standards.md` |
| Test / Boundary Cases | Define quality gates and edge-case coverage | `docs/test-boundary-cases.md` |
| Ops / Telemetry | Define production monitoring, runbooks, alerts, and maintenance | `docs/ops-telemetry.md` |

## Authoring Guidance

- Prefer concrete, testable statements over broad intent.
- Mark uncertainty explicitly with `Assumption:` or `Open question:`.
- Include non-goals so future agents do not expand the scope silently.
- Acceptance criteria should describe observable behavior, including success, failure, empty, permission, and boundary states when relevant.
- Specs and workplans should name dependencies and sequencing so future agents can parallelize safely.
- Keep generated docs proportional to the project stage; do not create every document by default.

## Vision / Requirements

```markdown
# Vision / Requirements

## Background

Explain the product or project context in plain language.

## Problem

Describe the user or business problem being solved.

## Target Users

List primary and secondary users, including their needs or constraints.

## Goals

- Goal 1 with a measurable or observable outcome.

## Non-Goals

- Explicitly out-of-scope item.

## Business Boundaries

Define constraints such as market, deployment context, supported platforms, compliance assumptions, or operational limits.

## Success Signals

- User, business, or technical signal that indicates the project is working.

## Assumptions

- Assumption: Something treated as true until confirmed.

## Open Questions

- Open question: Decision or missing context that needs human input.
```

## PRD

```markdown
# Product Requirements Document

## Summary

State what will be built and why now.

## Users and Use Cases

- User type: use case, trigger, expected result.

## Functional Requirements

- FR-1: The system must...

## Non-Functional Requirements

- Performance, availability, privacy, security, accessibility, localization, or maintainability needs.

## UX / Interaction Requirements

- Required screens, flows, empty states, loading states, and error states.

## Data Requirements

- Entities, fields, retention, import/export, privacy, and migration needs.

## Permissions and Security

- Roles, access rules, sensitive operations, and audit needs.

## KPIs

- Metric, target, and measurement method.

## Risks

- Risk, impact, likelihood, mitigation.

## Release Criteria

- Observable conditions that must be true before release.
```

## Agent-Ready PRD

```markdown
# Agent-Ready PRD

## Implementation Objective

One or two sentences describing the exact implementation outcome.

## Source of Truth

- Product source: link or summary of the user request.
- Technical source: existing files, APIs, schemas, or docs that must be followed.

## Explicit States

| State | Trigger | User-visible behavior | Data/system behavior |
| --- | --- | --- | --- |
| Empty |  |  |  |
| Loading |  |  |  |
| Error |  |  |  |
| Success |  |  |  |

## User Flows

1. User action.
2. System response.
3. Expected completion state.

## Business Rules

- Rule with inputs, conditions, and expected result.

## Inputs and Outputs

| Input/Output | Type | Required | Validation / format | Notes |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Error and Empty States

- Error or empty condition, user message, recovery action, and logging expectation.

## Edge Cases

- Boundary case and expected behavior.

## Acceptance Criteria

- Given a specific context, when an action happens, then the observable result is true.
- Include success, failure, empty, permission, and boundary states when they apply.

## Do Not Do

- Explicit implementation or product behavior that is out of scope.

## Assumptions to Preserve

- Assumption: Context the implementation should not silently reinterpret.
```

## Design / HLD / LLD

```markdown
# Design

## Architecture Overview

Describe the major components and how data/control flows through them.

## Modules

| Module | Responsibility | Key files | Depends on |
| --- | --- | --- | --- |
|  |  |  |  |

## Data Model

Define entities, fields, relationships, indexes, migrations, and retention rules.

## APIs / Interfaces

| Interface | Method / type | Input | Output | Errors |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Integrations

External services, SDKs, queues, storage, or platform dependencies.

## State Management

Client, server, cache, background job, and persistence state rules.

## Security Model

Authentication, authorization, secrets, validation, and abuse prevention.

## Performance Considerations

Expected load, bottlenecks, caching, pagination, and background work.

## Migration / Compatibility

Backward compatibility, data migration, rollout, and rollback notes.

## Alternatives Considered

Rejected option, reason rejected, and tradeoff.
```

## Spec

````markdown
# Implementation Spec

## Scope

Define what this implementation includes and excludes.

## Tasks

| ID | Task | Dependencies | Acceptance Criteria |
| --- | --- | --- | --- |
| T1 |  | None |  |

## Cross-Cutting Requirements

- Logging, validation, accessibility, performance, documentation, or security requirements that apply across tasks.

## Files Likely to Change

- `path/to/file`: expected change.

## Validation Commands

```bash
# Replace with repo-specific commands.
npm test
````

## Rollback Plan

Describe how to revert or disable the change safely.
```

## Workplan

```markdown
# Workplan

## Milestones

- Milestone 1: outcome and completion signal.

## Recommended Sequence

1. First step and why it must happen first.

## Parallel Work

- Workstream that can happen independently, plus integration dependency.

## Integration Points

- Where separate tasks must be merged, reviewed, or tested together.

## Checkpoints

- Human or automated checkpoint before proceeding.

## Human Review Needed

- Decision, risk, or product judgment requiring confirmation.

## Definition of Done

- Required docs, tests, behavior, review, and deployment readiness.
```

## AGENTS.md / CLAUDE.md

````markdown
# Agent Instructions

## Project Overview

Short description of the project and current implementation stage.

## Repository Structure

- `path/`: purpose.

## Setup Commands

```bash
# install dependencies
````

## Development Commands

```bash
# run the app locally
```

## Test Commands

```bash
# run relevant checks
```

## Coding Standards

- Repo-specific conventions future agents must follow.

## Documentation Rules

- When to update docs and where to place new planning artifacts.

## Safety Rules

- Files, commands, environments, or data that require extra care.

## Before Finishing

- Checks, summaries, and handoff notes required before an agent stops.
```

## `.ai/` Directory

Recommended files when useful:

- `.ai/workflow.md`: standard agent workflow for this repo.
- `.ai/prompts/feature-planning.md`: reusable planning prompt.
- `.ai/prompts/code-review.md`: reusable review prompt.
- `.ai/checklists/implementation.md`: pre-merge checklist.

## Development Standards

```markdown
# Development Standards

## Language and Framework Rules

## Architecture Rules

## API Rules

## UI Rules

## Error Handling

## Logging

## Security

## Testing

## Documentation
```

## Test / Boundary Cases

```markdown
# Test and Boundary Cases

## Test Strategy

Unit, integration, end-to-end, manual QA, and regression approach.

## Unit Tests

- Function, component, or module behavior to verify.

## Integration Tests

- Cross-module or API behavior to verify.

## E2E / User Flow Tests

- Critical user flow and expected result.

## Boundary Cases

- Minimum, maximum, empty, duplicate, malformed, slow, and large input cases.

## Negative Cases

- Invalid input, permission denied, failed dependency, timeout, and conflict cases.

## Performance Cases

- Load, latency, memory, pagination, and background work expectations.

## Accessibility Cases

- Keyboard, focus, labels, contrast, screen reader, and reduced-motion expectations.

## Manual QA Checklist

- Step-by-step checks a human can perform before release.
```

## Ops / Telemetry

```markdown
# Ops and Telemetry

## Environments

Development, staging, production, and any required external services.

## Deployment

Build, release, migration, rollback, and verification steps.

## Configuration

Environment variables, secrets, feature flags, and safe defaults.

## Metrics

Business, product, system, and error metrics.

## Logs

Required log events, fields, redaction rules, and retention.

## Alerts

Alert condition, threshold, owner, and response expectation.

## Runbooks

Common incident, diagnosis steps, mitigation, and escalation.

## Backup and Recovery

Backup schedule, restore procedure, and recovery objectives.

## Maintenance Tasks

Recurring checks, dependency updates, cleanup, and documentation upkeep.
```
