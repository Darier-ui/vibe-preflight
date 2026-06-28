# Vibe Preflight

A pre-coding guardrail for AI coding agents. It turns vague app ideas into a lightweight or full project plan before implementation starts.

Vibe Preflight is designed for vibe coding sessions where the user wants an AI agent to start building immediately, but the project still needs a clear goal, MVP boundary, user flow, acceptance criteria, technical assumptions, and verification method.

It can be used as a Codex skill, a reusable agent instruction file, or a planning checklist for any coding agent that supports custom rules or project instructions.

## What It Does

- Guides beginners through a short pre-coding project check.
- Uses lightweight preflight for small prototypes, static pages, single-screen tools, tiny games, and demos.
- Uses full preflight for larger apps, SaaS products, data-backed projects, authentication, payments, external APIs, and deployment-sensitive work.
- Converts vague requests into project contracts, acceptance criteria, data decisions, and module-by-module implementation gates.
- Keeps Git checkpoints optional instead of forcing commits.

## When To Use

Use this with an AI coding agent when starting a new:

- App
- Website
- SaaS product
- Mini tool
- Game prototype
- Vibe coding project

Do not use it for bug fixes, small edits to existing code, code explanation, code review, or tasks that already have a complete implementation spec unless the user asks to re-plan the project.

## Install For Codex

Clone or copy this repository into your Codex skills directory:

```bash
git clone https://github.com/<your-username>/vibe-preflight.git ~/.codex/skills/vibe-preflight
```

If you use `CODEX_HOME`, install it under:

```text
$CODEX_HOME/skills/vibe-preflight
```

## Use With Other Coding Agents

For other coding agents, copy the content of `SKILL.md` and the relevant files in `references/` into the agent's custom instructions, project rules, memory, or workspace guidance.

Use this instruction when attaching it to another agent:

```text
Before coding a vague new project request, follow Vibe Preflight. Choose lightweight preflight for small prototypes and full preflight for larger, data-backed, or deployment-sensitive projects. Do not start implementation until the goal, MVP scope, core flow, technical assumptions, and verification method are clear.
```

If the agent supports project-level files, keep this repository structure intact so it can read:

- `SKILL.md` for the core rules
- `references/preflight-playbook.md` for the question flow
- `references/project-artifact-templates.md` for planning artifacts
- `references/development-loop.md` for implementation checkpoints

## Usage

Codex:

```text
Use $vibe-preflight to help me plan a small habit tracker app before coding.
```

Generic agent:

```text
Use Vibe Preflight before coding. I want to build a small habit tracker app.
```

Example requests:

```text
Use Vibe Preflight. I want to build a simple landing page for my AI newsletter.
```

```text
Use Vibe Preflight. I want to make a SaaS dashboard for tracking client projects.
```

```text
Use Vibe Preflight. Help me turn this vague app idea into a build plan before writing code.
```

## Modes

### Lightweight Preflight

For small projects where too much planning would slow things down. The skill only confirms:

- Goal
- First-version scope
- Core screen or operation
- Whether login, storage, or third-party APIs are needed
- Technical assumption
- Acceptance check

### Full Preflight

For larger or riskier projects. The skill walks through:

- Product goal
- MVP scope and exclusions
- User flow
- Pages and visual frame
- Feature acceptance criteria
- Data model and storage rules
- Technical stack and runtime
- Project context files
- Development order and quality gates

## Repository Structure

```text
vibe-preflight/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── development-loop.md
│   ├── preflight-playbook.md
│   └── project-artifact-templates.md
├── README.md
├── LICENSE
└── .gitignore
```

## GitHub Repository Setup

Recommended GitHub description:

```text
A pre-coding preflight for AI coding agents building vibe coding projects.
```

Recommended topics:

```text
ai-agent
coding-agent
ai-coding
vibe-coding
project-planning
preflight
prompt-engineering
codex-skill
```

## Validate

If you use this as a Codex skill, run the Codex skill validator before publishing:

```bash
PYTHONUTF8=1 python path/to/quick_validate.py path/to/vibe-preflight
```

Expected result:

```text
Skill is valid!
```

## License

MIT License. See [LICENSE](LICENSE).
