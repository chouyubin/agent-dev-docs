# Agent Dev Docs Skill

`agent-dev-docs` is a Codex skill for preparing AI-ready development documentation before software implementation begins.

Use it when you want an AI coding agent to turn an idea, feature request, or existing project into a practical document set that future agents can execute against with less ambiguity.

## What It Generates

Depending on the project stage, the skill can create or update:

- `docs/vision-requirements.md`
- `docs/prd.md`
- `docs/agent-ready-prd.md`
- `docs/design.md`
- `docs/spec.md`
- `docs/workplan.md`
- `docs/development-standards.md`
- `docs/test-boundary-cases.md`
- `docs/ops-telemetry.md`
- `AGENTS.md`
- `CLAUDE.md`
- `.ai/` workflow files, prompts, and checklists

## When To Use

Use this skill when you are:

- Starting a new AI-assisted software project.
- Turning a rough product idea into implementation-ready docs.
- Preparing a repo so future AI agents can safely contribute.
- Creating an Agent-Ready PRD, implementation spec, or workplan.
- Standardizing project instructions through `AGENTS.md`, `CLAUDE.md`, or `.ai/`.

## Example Prompts

```text
Use $agent-dev-docs to turn this idea into an AI-ready development document set.
```

```text
用 $agent-dev-docs 先帮我把这个项目整理成 AI 可执行的开发文档。
```

```text
Use $agent-dev-docs to create a PRD, Agent-Ready PRD, spec, and workplan for this feature.
```

## Skill Structure

```text
agent-dev-docs/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    doc-templates.md
```

## Notes

The skill favors the smallest useful document set for the current stage. It should preserve existing documentation, make reasonable assumptions when possible, and mark unresolved decisions as assumptions or open questions.
