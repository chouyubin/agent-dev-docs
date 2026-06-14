# Agent Dev Docs Skill

> 在软件实现开始前，生成适合 AI Agent 执行的开发文档体系。<br>
> Generate AI-ready development documentation before software implementation begins.

<p align="center">
  <a href="#中文">中文</a> |
  <a href="#english">English</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Codex-Skill-blue.svg" alt="Codex Skill">
  <img src="https://img.shields.io/badge/docs-AI--ready-success.svg" alt="AI-ready docs">
  <img src="https://img.shields.io/badge/language-中文%20%7C%20English-lightgrey.svg" alt="Language">
  <img src="https://img.shields.io/badge/license-MIT-green.svg" alt="License">
</p>

---

## 中文

[English](#english) | [协议](#license) | [免责声明](#disclaimer)

`agent-dev-docs` 是一个 Codex Skill，用于把产品想法、功能需求或现有仓库整理成适合 AI Agent 执行的开发文档体系。

它适合 AI 辅助开发流程：在正式写代码之前，先让未来的编程 Agent 明确目标、边界、架构、任务拆解、验收标准和项目操作规范。

### 功能特性

| 功能 | 说明 |
| --- | --- |
| AI 可执行规划 | 将模糊想法转为明确目标、约束、假设和验收标准。 |
| 文档体系生成 | 按需生成 Vision/Requirements、PRD、Agent-Ready PRD、Design、Spec、Workplan、测试和运维文档。 |
| Agent 操作手册 | 创建或更新 `AGENTS.md`、`CLAUDE.md` 和 `.ai/` 工作流文件，方便后续 Agent 协作。 |
| 适配仓库结构 | 根据现有仓库目录选择文件位置，而不是强行套用固定结构。 |
| 默认最小必要 | 优先生成当前阶段最有用、最小必要的文档集合。 |
| 假设追踪 | 对未确认决策标记为假设或待确认问题，避免把模糊点藏起来。 |

### 会生成哪些文档

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

### 快速开始

把本目录安装或放置到 Codex skills 目录后，直接按名称调用：

```text
用 $agent-dev-docs 先帮我把这个项目整理成 AI 可执行的开发文档。
```

针对单个功能的示例：

```text
用 $agent-dev-docs 为这个功能创建 PRD、Agent-Ready PRD、Spec 和 Workplan。
```
也可以下载项目成ZIP文件直接导入到CC Switch中
### Skill 结构

```text
agent-dev-docs/
  SKILL.md
  README.md
  LICENSE
  agents/
    openai.yaml
  references/
    doc-templates.md
```

### 常见问题

<details>
<summary><b>这个 skill 每次都会生成全部文档吗？</b></summary>

不会。它应该根据项目阶段选择最小必要文档集。新想法通常先生成规划文档；现有仓库可能只需要 Agent 操作说明、Spec、测试边界或运维说明。
</details>

<details>
<summary><b>它会覆盖已有文档吗？</b></summary>

它应该优先保留已有文档。当意图不明确时，应创建功能级文档，或在更新共享文档前清楚说明拟变更内容。
</details>

<details>
<summary><b>Agent-Ready PRD 和普通 PRD 有什么区别？</b></summary>

Agent-Ready PRD 会进一步消除 AI 编程 Agent 执行时的歧义，明确状态、业务规则、输入输出、错误状态、边界情况、验收标准和不做事项。
</details>

---

## English

[中文](#中文) | [License](#license) | [Disclaimer](#disclaimer)

`agent-dev-docs` is a Codex skill that helps turn an idea, feature request, or existing repository into a practical AI-agent-friendly development document set.

It is designed for AI-assisted software development workflows where future coding agents need clear goals, boundaries, architecture notes, task breakdowns, acceptance criteria, and project operating instructions before implementation starts.

### Highlights

| Capability | Description |
| --- | --- |
| AI-ready planning | Converts vague product ideas into explicit goals, constraints, assumptions, and acceptance criteria. |
| Document map | Produces Vision/Requirements, PRD, Agent-Ready PRD, Design, Spec, Workplan, tests, and ops docs when useful. |
| Agent instructions | Creates or updates `AGENTS.md`, `CLAUDE.md`, and `.ai/` workflow files for future coding agents. |
| Repo-aware output | Adapts file placement to the existing repository structure instead of forcing a fixed layout. |
| Minimal by default | Generates the smallest useful documentation set for the current stage. |
| Assumption tracking | Marks unresolved decisions as assumptions or open questions instead of hiding ambiguity. |

### Generated Documents

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
- `.ai/` workflow files, prompt templates, and checklists

### When To Use

Use this skill when you are:

- Starting a new AI-assisted software project.
- Turning a rough product idea into implementation-ready documentation.
- Preparing an existing repository so future AI agents can contribute safely.
- Creating an Agent-Ready PRD, implementation spec, or workplan.
- Standardizing project instructions through `AGENTS.md`, `CLAUDE.md`, or `.ai/`.

### Quick Start

Install or place this folder in your Codex skills directory, then invoke it by name:

```text
Use $agent-dev-docs to turn this idea into an AI-ready development document set.
```

Feature-scoped example:

```text
Use $agent-dev-docs to create a PRD, Agent-Ready PRD, spec, and workplan for this feature.
```

### Skill Structure

```text
agent-dev-docs/
  SKILL.md
  README.md
  LICENSE
  agents/
    openai.yaml
  references/
    doc-templates.md
```

### FAQ

<details>
<summary><b>Does this skill always generate every document?</b></summary>

No. It should choose the smallest useful set based on the project stage. A new idea usually needs planning docs first; an existing repo may only need agent instructions, specs, tests, or ops notes.
</details>

<details>
<summary><b>Will it overwrite existing documentation?</b></summary>

It should preserve existing documentation. When intent is unclear, it should create feature-scoped files or clearly summarize proposed changes before updating shared docs.
</details>

<details>
<summary><b>What makes an Agent-Ready PRD different from a normal PRD?</b></summary>

An Agent-Ready PRD removes ambiguity for coding agents by spelling out states, business rules, inputs, outputs, error states, edge cases, acceptance criteria, and explicit non-goals.
</details>

---

## License

MIT © 2026 chouyubin

See [LICENSE](LICENSE) for details.

---

## Disclaimer

本项目仅供个人学习、研究和 AI 辅助开发工作流探索使用。使用者应在真实项目中使用前，自行审查、验证并调整生成的文档。当项目信息不完整时，生成内容可能包含假设、遗漏或不准确之处。因使用本 skill 或其辅助生成的文档而产生的任何直接或间接后果，项目作者不承担责任。

This project is provided for personal learning, research, and AI-assisted development workflow exploration. Users are responsible for reviewing, validating, and adapting any generated documentation before using it in real projects. The generated documents may contain assumptions, omissions, or inaccuracies, especially when project context is incomplete. The author is not liable for any direct or indirect consequences arising from the use of this skill or the documents it helps produce.
