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

### 安装

下载或克隆本仓库后，把整个 `agent-dev-docs` 目录放入 Codex skills 目录。

常见位置：

```text
Windows: %USERPROFILE%\.codex\skills\agent-dev-docs
macOS/Linux: ~/.codex/skills/agent-dev-docs
```

安装后重启或刷新 Codex，然后输入包含 `$agent-dev-docs` 的提示词即可调用。

如果你使用 CC Switch，也可以下载本项目 ZIP 文件并通过 CC Switch 导入。请以 CC Switch 当前版本的导入流程为准。

### 快速开始

为一个新项目生成开发文档：

```text
用 $agent-dev-docs 先帮我把这个项目整理成 AI 可执行的开发文档。
```

为单个功能生成文档：

```text
用 $agent-dev-docs 为登录功能创建 PRD、Agent-Ready PRD、Spec 和 Workplan。
```

只想先看草稿、不写入文件：

```text
用 $agent-dev-docs 先输出文档草稿，不要修改仓库文件。
```

### 典型场景

| 场景 | 示例提示词 | 通常生成 |
| --- | --- | --- |
| 新项目想法 | `用 $agent-dev-docs 规划一个个人记账 Web App` | Vision/Requirements、PRD、Agent-Ready PRD、Spec、Workplan |
| 现有仓库补文档 | `用 $agent-dev-docs 为这个仓库补齐 Agent 可执行文档` | Design、AGENTS.md、Development Standards、Test/Boundary Cases |
| 单个功能 | `用 $agent-dev-docs 为导入 CSV 功能生成实现文档` | `docs/features/<feature-slug>/` 下的 PRD、Spec、Workplan、测试边界 |
| Agent 协作规范 | `用 $agent-dev-docs 创建 AGENTS.md 和 .ai 工作流` | AGENTS.md、`.ai/workflow.md`、`.ai/checklists/implementation.md` |

### 示例输出

输入：

```text
用 $agent-dev-docs 规划一个个人记账 Web App，支持记账、分类、月度统计。
```

可能生成：

```text
docs/vision-requirements.md
docs/prd.md
docs/agent-ready-prd.md
docs/spec.md
docs/workplan.md
AGENTS.md
```

生成内容会包含类似信息：

```markdown
## Acceptance Criteria

- 用户可以创建一条包含金额、分类、日期和备注的支出记录。
- 当金额为空、为负数或不是数字时，界面必须显示可理解的错误信息。
- 月度统计必须按自然月汇总，并在没有记录时显示空状态。

## Assumptions

- Assumption: 初始版本只支持单用户本地账户，不包含多人协作。
```

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

### 使用前你需要知道

- 它会优先读取当前仓库结构，再决定文档放在哪里。
- 它默认生成最小必要文档集，不会每次都创建全部文件。
- 它应保留已有文档；不确定是否覆盖时，应创建功能级文档或先说明拟修改内容。
- 信息不足时，它会使用 `Assumption:` 或 `Open question:` 标出假设和待确认问题。
- 你可以明确要求“只输出草稿，不写入文件”。

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

### Installation

Download or clone this repository, then place the whole `agent-dev-docs` folder in your Codex skills directory.

Common locations:

```text
Windows: %USERPROFILE%\.codex\skills\agent-dev-docs
macOS/Linux: ~/.codex/skills/agent-dev-docs
```

Restart or refresh Codex after installation, then invoke the skill with a prompt that includes `$agent-dev-docs`.

If you use CC Switch, you can also download this project as a ZIP file and import it through CC Switch. Follow the import flow for your current CC Switch version.

### Quick Start

Generate docs for a new project:

```text
Use $agent-dev-docs to turn this idea into an AI-ready development document set.
```

Generate docs for a single feature:

```text
Use $agent-dev-docs to create a PRD, Agent-Ready PRD, spec, and workplan for the login feature.
```

Preview a draft without writing files:

```text
Use $agent-dev-docs to draft the documents first without modifying repository files.
```

### Common Scenarios

| Scenario | Example prompt | Typical output |
| --- | --- | --- |
| New product idea | `Use $agent-dev-docs to plan a personal budgeting web app` | Vision/Requirements, PRD, Agent-Ready PRD, Spec, Workplan |
| Existing repo docs | `Use $agent-dev-docs to prepare this repo for future coding agents` | Design, AGENTS.md, Development Standards, Test/Boundary Cases |
| Single feature | `Use $agent-dev-docs to document CSV import implementation` | Feature-scoped PRD, Spec, Workplan, Test/Boundary Cases under `docs/features/<feature-slug>/` |
| Agent workflow | `Use $agent-dev-docs to create AGENTS.md and .ai workflow files` | AGENTS.md, `.ai/workflow.md`, `.ai/checklists/implementation.md` |

### Example Output

Input:

```text
Use $agent-dev-docs to plan a personal budgeting web app with expenses, categories, and monthly summaries.
```

Possible generated files:

```text
docs/vision-requirements.md
docs/prd.md
docs/agent-ready-prd.md
docs/spec.md
docs/workplan.md
AGENTS.md
```

The generated content should include concrete, testable details:

```markdown
## Acceptance Criteria

- A user can create an expense with amount, category, date, and optional note.
- Empty, negative, or non-numeric amounts show a clear validation error.
- Monthly summaries aggregate by calendar month and show an empty state when no records exist.

## Assumptions

- Assumption: The first release is single-user only and does not include collaboration.
```

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

### Before You Use It

- It should inspect the current repository structure before choosing file paths.
- It defaults to the smallest useful document set, not every possible file.
- It should preserve existing docs; when overwrite intent is unclear, it should create feature-scoped files or explain proposed updates first.
- Missing context should be marked as `Assumption:` or `Open question:`.
- You can explicitly ask for draft-only output if you do not want files written yet.

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
