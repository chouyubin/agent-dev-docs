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

## Vision / Requirements

```markdown
# Vision / Requirements

## Background

## Problem

## Target Users

## Goals

## Non-Goals

## Business Boundaries

## Success Signals

## Assumptions

## Open Questions
```

## PRD

```markdown
# Product Requirements Document

## Summary

## Users and Use Cases

## Functional Requirements

## Non-Functional Requirements

## UX / Interaction Requirements

## Data Requirements

## Permissions and Security

## KPIs

## Risks

## Release Criteria
```

## Agent-Ready PRD

```markdown
# Agent-Ready PRD

## Implementation Objective

## Source of Truth

## Explicit States

## User Flows

## Business Rules

## Inputs and Outputs

## Error and Empty States

## Edge Cases

## Acceptance Criteria

## Do Not Do

## Assumptions to Preserve
```

## Design / HLD / LLD

```markdown
# Design

## Architecture Overview

## Modules

## Data Model

## APIs / Interfaces

## Integrations

## State Management

## Security Model

## Performance Considerations

## Migration / Compatibility

## Alternatives Considered
```

## Spec

```markdown
# Implementation Spec

## Scope

## Tasks

| ID | Task | Dependencies | Acceptance Criteria |
| --- | --- | --- | --- |
| T1 |  | None |  |

## Cross-Cutting Requirements

## Files Likely to Change

## Validation Commands

## Rollback Plan
```

## Workplan

```markdown
# Workplan

## Milestones

## Recommended Sequence

## Parallel Work

## Integration Points

## Checkpoints

## Human Review Needed

## Definition of Done
```

## AGENTS.md / CLAUDE.md

```markdown
# Agent Instructions

## Project Overview

## Repository Structure

## Setup Commands

## Development Commands

## Test Commands

## Coding Standards

## Documentation Rules

## Safety Rules

## Before Finishing
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

## Unit Tests

## Integration Tests

## E2E / User Flow Tests

## Boundary Cases

## Negative Cases

## Performance Cases

## Accessibility Cases

## Manual QA Checklist
```

## Ops / Telemetry

```markdown
# Ops and Telemetry

## Environments

## Deployment

## Configuration

## Metrics

## Logs

## Alerts

## Runbooks

## Backup and Recovery

## Maintenance Tasks
```
