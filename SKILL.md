---
name: agent-dev-docs
description: Generate AI-ready development documentation before or during software work. Use when the user wants to build with AI agents, turn an idea into development docs, create Vision/Requirements, PRD, Agent-Ready PRD, Design/HLD/LLD, Spec, Workplan, AGENTS.md, CLAUDE.md, .ai workflow files, development standards, test/boundary cases, or ops/telemetry docs; also use when the user asks to prepare a project so future AI coding agents can implement it accurately.
---

# Agent Dev Docs

## Purpose

Create a practical documentation set that lets AI coding agents move from idea to implementation with less ambiguity. Prefer useful, project-specific files over ceremony.

## Workflow

1. Gather context from the conversation and, when a repo exists, inspect the current structure before choosing file paths.
2. Ask at most one concise clarification question only if a blocking product decision is missing. Otherwise make reasonable assumptions and mark them in the docs.
3. Choose the smallest useful document set for the user's stage:
   - New idea: create Vision/Requirements, PRD, Agent-Ready PRD, Spec, and Workplan first.
   - Existing repo: add or update Design, AGENTS.md/CLAUDE.md, .ai workflow files, standards, tests, and ops docs as needed.
   - Feature request: create a feature-scoped PRD, Agent-Ready PRD, Spec, Workplan, and Test/Boundary Cases.
4. Read `references/doc-templates.md` when generating the actual files.
5. Preserve existing documentation. Update in place only when the user's intent is clear; otherwise create feature-scoped files under an existing docs/specs directory.
6. End with a short summary of created or updated files and the assumptions that need human confirmation.

## File Placement

Adapt to the repo's conventions. If no convention exists, use:

- `docs/vision-requirements.md`
- `docs/prd.md`
- `docs/agent-ready-prd.md`
- `docs/design.md`
- `docs/spec.md`
- `docs/workplan.md`
- `docs/development-standards.md`
- `docs/test-boundary-cases.md`
- `docs/ops-telemetry.md`
- `AGENTS.md` at repo root for Codex/OpenAI-agent operating instructions
- `CLAUDE.md` at repo root only if the user uses Claude or asks for it
- `.ai/` for prompt templates, workflow checklists, or agent configuration

For multiple features, prefer `docs/features/<feature-slug>/` with the same document names.

## Authoring Rules

- Write docs as executable guidance for future agents: explicit goals, states, inputs, outputs, constraints, acceptance criteria, and non-goals.
- Convert vague wishes into testable requirements. Keep unknowns visible as `Assumption:` or `Open question:`.
- Include acceptance criteria with observable behavior and failure states.
- Include dependencies and sequencing so agents can parallelize safely.
- Keep AGENTS.md/CLAUDE.md operational: commands, repo structure, coding rules, test commands, safety constraints, and how to update docs.
- Do not invent external facts, APIs, pricing, laws, or current product details without verifying them when accuracy matters.
- Do not overwrite user-authored docs casually. Diff mentally first and preserve useful existing content.

## Quality Bar

A generated doc set is ready when a fresh AI coding agent can answer:

- Why are we building this?
- What exactly must be built, and what is out of scope?
- How should the system be shaped?
- What tasks should be done first, in what order, and by whom?
- How will we know it works?
- What repo rules and commands must the agent follow?
- What needs monitoring after deployment?
