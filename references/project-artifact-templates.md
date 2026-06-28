# Project Artifact Templates

Use these templates after the preflight has enough confirmed information. Keep the files concise and update them when major decisions change. Mark irrelevant sections as `N/A` instead of inventing details.

## Contents

- [Lightweight Project Contract](#lightweight-project-contract)
- [PRD.md](#prdmd)
- [ARCHITECTURE.md](#architecturemd)
- [PROJECT_STATE.md](#project_statemd)
- [AI_RULES.md](#ai_rulesmd)

## Lightweight Project Contract

Use this in chat for small projects before coding. Create the full files only when the project will continue across sessions or the user asks for persistent context.

```markdown
# Project Contract

- Mode: Lightweight
- Goal:
- Target user:
- MVP scope:
- Out of scope:
- Core screen or operation:
- Data/login/API:
- Technical assumption:
- Local run command:
- Acceptance check:
```

## PRD.md

```markdown
# PRD

## Project Goal

- One-sentence project:
- Target users:
- Core scenario:
- First-version success standard:

## Scope

### MVP Features

- 

### Later

- 

### Excluded From This Version

- 

## User Flow

### Main Flow

1. 

### Empty States

- 

### Error States

- 

### Success States

- 

## Pages

| Page | Purpose | Main Sections | Related Features |
| --- | --- | --- | --- |
|  |  |  |  |

## Features and Acceptance Criteria

### Feature: 

- User story:
- Input:
- Output:
- Normal path:
- Exception path:
- Acceptance criteria:
  1. 
- Verification method:
```

## ARCHITECTURE.md

```markdown
# Architecture

## Technical Stack

- Frontend:
- Backend:
- Database/storage:
- Authentication:
- Package manager:
- Local run command:
- Deployment target:

## Runtime and Environment

- Required versions:
- Environment variables:
- External services:

## Directory Plan

- `/`

## Data Model

### Entity: 

| Field | Type | Required | Default | Notes |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Relationships

- 

## Validation and Error Rules

- 

## Constraints and Decisions

- 
```

## PROJECT_STATE.md

```markdown
# Project State

## Current Status

- Phase:
- Current module:
- Last verified behavior:

## Completed

- 

## In Progress

- 

## Pending

- 

## Known Issues

- 

## Decisions

- 

## Next Step

- 

## Last Verification

- Command or manual check:
- Result:
- Date:
```

## AI_RULES.md

```markdown
# AI Rules

## Working Rules

- Do not implement outside the confirmed MVP scope without asking.
- Do not add production dependencies without confirmation.
- Do not start the next module while the current module has failing checks.
- Update PROJECT_STATE.md after meaningful implementation, verification, or decision changes.

## Coding Rules

- Match the existing code style.
- Keep files focused and avoid large unrelated edits.
- Prefer simple implementation over abstraction unless the codebase already has that pattern.

## Module Workflow

For each module:

1. Explain the implementation plan.
2. Define or update the test/verification method.
3. Implement only the current module.
4. Run verification.
5. Record the result in PROJECT_STATE.md.

## Git Rules

- Git commits are optional. Do not commit unless the user asks, the repository rules require it, or the user has approved checkpoint commits.
- When committing, use clear commit messages that name the completed module.
- Do not rewrite unrelated user changes.

## Quality Gates

- Local run command succeeds.
- Targeted tests or manual checks pass.
- Acceptance criteria for the module are verified.
- PROJECT_STATE.md is current.
```
