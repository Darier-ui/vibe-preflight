---
name: vibe-preflight
description: "Guide AI coding agents through a pre-coding product and engineering preflight for new vibe coding projects. Use when a user wants to start a new app, website, SaaS, tool, mini-program, or vibe coding project from a vague idea, especially beginners who ask an AI agent to code immediately. Choose a lightweight preflight for small prototypes and a full preflight for larger or data-backed projects. Guide goals, scope, user flows, pages, acceptance criteria, data models, technical stack, project context files, development order, and quality gates before implementation. Do not use for bug fixes, small edits to existing code, code explanation, code review, or tasks with a complete implementation spec unless the user asks to re-plan the project."
---

# Vibe Preflight

## Core Rule

Do not let the agent start coding immediately for a vague new project request. First guide the user through the smallest useful project preflight so the idea becomes a stable project contract.

Use a coach-like tone: warm, concrete, and structured. Match the user's language. Explain that the pause protects the project from becoming a large bug pile later. Ask only the questions needed for the current step, then summarize the user's answers into a clean artifact before moving on.

## Mode Selection

Choose the lightest mode that protects the project:

- **Lightweight preflight**: use for small prototypes, static pages, single-screen tools, tiny games, demos, or beginner projects where too many technical questions would slow the user down.
- **Full preflight**: use for SaaS apps, multi-page products, data-backed apps, authentication, payments, external APIs, team workflows, deployment-sensitive work, or anything with unclear business rules.
- **Existing project adjustment**: if the user is changing an existing project, do not run the new-project guide. First inspect the project context, then ask only for missing product or verification details.

If the user explicitly asks to skip planning for a low-risk prototype, write a short assumptions contract and continue. For risky or ambiguous projects, pause only on the missing decisions that would cause rework.

## Operating Flow

Run the new project guide in this order:

0. Pause coding, explain the preflight, and choose lightweight or full mode.
1. Define the one-sentence project goal.
2. Lock project scope.
3. Map the user flow.
4. Define pages and visual frame.
5. Break down features with acceptance criteria.
6. Define data model and storage rules.
7. Lock technical stack and runtime.
8. Prepare project context files.
9. Create the development order and quality gates.

For the detailed question set, outputs, entry criteria, and prohibited shortcuts for each step, read `references/preflight-playbook.md` when running the guide.

## Conversation Rules

- Ask 2 to 4 focused questions at a time for beginners or small projects. Ask 3 to 5 only when the project is complex enough to need it.
- Avoid jargon in early questions. Prefer plain-language choices such as "browser only", "needs login", or "saves data" before asking about frameworks, databases, or auth providers.
- Prefer practical defaults when the user is unsure, but label them as assumptions.
- Summarize each step in a structured block and ask for confirmation before advancing.
- Keep scope small for MVP decisions. Move nice-to-have ideas into "later" unless the user explicitly confirms they are required.
- If the user asks to code before the preflight is complete, gently pause and return to the next missing preflight step.
- Do not invent business rules, data fields, or pages silently. State assumptions when they affect implementation.
- Mark irrelevant sections as `N/A` instead of forcing decisions. For example, a static landing page can have `Data model: N/A`.

Use this default opener when the user begins with a vague build request:

```text
我先不直接写代码。为了避免后面边做边返工，我们先用很短的预检判断这个项目适合轻量模式还是完整模式。小项目不会问很多技术问题，复杂项目再把范围、页面、数据、技术栈和验收标准定细。

先回答这几个问题就够：
1. 这个项目一句话是什么？
2. 第一版必须有哪 1 到 3 个功能？
3. 是否需要登录、保存数据或接第三方 API？
4. 这是一次性小原型，还是准备持续迭代的项目？
```

## Project Artifacts

Before substantial coding in full mode, produce or update these four project context files in the target project:

- `PRD.md`: product goal, users, scope, flows, pages, features, and acceptance criteria.
- `ARCHITECTURE.md`: technical stack, runtime, directory plan, data model, storage, integrations, and important constraints.
- `PROJECT_STATE.md`: current status, completed items, pending items, known issues, decisions, and next module.
- `AI_RULES.md`: coding rules, file boundaries, testing expectations, Git checkpoints, and update rules.

For lightweight mode, a compact project contract in chat is enough unless the project will continue across sessions or the user asks for persistent files.

Read `references/project-artifact-templates.md` before creating these files.

## Development Loop

After the preflight is complete, implement modules one at a time. For each module, use:

```text
Explain -> Test -> Build -> Verify -> Record
```

Read `references/development-loop.md` before writing code. Do not move to the next module while the current module has failing checks or missing verification.

## Hard Stops

Stop and return to preflight when any of these are missing:

- No MVP scope or explicit exclusions.
- No page list or core view for a frontend project.
- No data model for a data-backed project. Use `N/A` only when no data is stored.
- No acceptance criteria for the next feature.
- No technical stack or local run command.
- No verification method for the next module.

For lightweight mode, only stop on missing goal, MVP boundary, core view or input/output, local run method, and verification method.

Avoid these failure patterns:

- Generate the whole project in one large pass.
- Build UI before page structure is confirmed.
- Build storage or APIs before data fields are confirmed.
- Add future features into the first version without user confirmation.
- Continue after failed tests or unverified behavior.
- Make large changes without updating `PROJECT_STATE.md`.
