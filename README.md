# Agent Dev Docs Skill

## English

`agent-dev-docs` is a Codex skill for preparing AI-ready development documentation before software implementation begins.

Use it when you want an AI coding agent to turn an idea, feature request, or existing project into a practical document set that future agents can execute against with less ambiguity.

### What It Generates

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

### When To Use

Use this skill when you are:

- Starting a new AI-assisted software project.
- Turning a rough product idea into implementation-ready docs.
- Preparing a repo so future AI agents can safely contribute.
- Creating an Agent-Ready PRD, implementation spec, or workplan.
- Standardizing project instructions through `AGENTS.md`, `CLAUDE.md`, or `.ai/`.

### Example Prompts

```text
Use $agent-dev-docs to turn this idea into an AI-ready development document set.
```

```text
Use $agent-dev-docs to create a PRD, Agent-Ready PRD, spec, and workplan for this feature.
```

### Skill Structure

```text
agent-dev-docs/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    doc-templates.md
```

### Notes

The skill favors the smallest useful document set for the current stage. It should preserve existing documentation, make reasonable assumptions when possible, and mark unresolved decisions as assumptions or open questions.

## 中文

`agent-dev-docs` 是一个 Codex Skill，用于在软件实现开始之前，先生成适合 AI Agent 执行的开发文档体系。

当你希望 AI 编程 Agent 把一个想法、功能需求或现有项目整理成清晰、可执行、低歧义的开发文档时，可以使用这个 skill。

### 它会生成什么

根据项目阶段不同，这个 skill 可以创建或更新：

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
- `.ai/` 工作流文件、提示词模板和检查清单

### 什么时候使用

适合在这些场景中使用：

- 启动一个新的 AI 辅助开发项目。
- 把粗略产品想法整理成可实施的开发文档。
- 为现有仓库补齐 AI Agent 可遵循的项目说明。
- 创建 Agent-Ready PRD、实现规格说明或工作计划。
- 通过 `AGENTS.md`、`CLAUDE.md` 或 `.ai/` 统一项目级 AI 协作规范。

### 调用示例

```text
Use $agent-dev-docs to turn this idea into an AI-ready development document set.
```

```text
用 $agent-dev-docs 先帮我把这个项目整理成 AI 可执行的开发文档。
```

```text
用 $agent-dev-docs 为这个功能创建 PRD、Agent-Ready PRD、Spec 和 Workplan。
```

### Skill 结构

```text
agent-dev-docs/
  SKILL.md
  README.md
  agents/
    openai.yaml
  references/
    doc-templates.md
```

### 说明

这个 skill 会优先生成当前阶段最有用、最小必要的文档集合。它应该保留已有文档，在信息不足时做出合理假设，并把未确认的决策明确标记为假设或待确认问题。
