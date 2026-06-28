# Preflight Playbook

Use this playbook to guide a new vibe coding project before coding. Run the steps in order. Keep the tone coach-like: explain the reason for each step, ask only the current questions, summarize, and ask for confirmation.

## Contents

- [Preflight Modes](#preflight-modes)
- [Question Style for Beginners](#question-style-for-beginners)
- [Step 0: Pause Coding](#step-0-pause-coding)
- [Step 1: One-Sentence Project Goal](#step-1-one-sentence-project-goal)
- [Step 2: Project Scope](#step-2-project-scope)
- [Step 3: User Flow](#step-3-user-flow)
- [Step 4: Pages and Visual Frame](#step-4-pages-and-visual-frame)
- [Step 5: Feature Acceptance Criteria](#step-5-feature-acceptance-criteria)
- [Step 6: Data Model and Storage Rules](#step-6-data-model-and-storage-rules)
- [Step 7: Technical Stack and Runtime](#step-7-technical-stack-and-runtime)
- [Step 8: Project Context Files](#step-8-project-context-files)
- [Step 9: Development Order and Quality Gates](#step-9-development-order-and-quality-gates)

## Preflight Modes

Choose the smallest useful mode before asking detailed questions.

### Lightweight Preflight

Use for small prototypes, single-page tools, static websites, tiny games, demos, and beginner projects where a long planning sequence would block momentum.

Ask only:

1. 这个小项目要帮用户完成什么？
2. 第一版必须有哪 1 到 3 个功能？
3. 用户打开后看到的核心页面或操作是什么？
4. 是否需要保存数据、登录、接第三方 API，还是都不需要？
5. 做完后你会怎么确认它能用？

If the user is unsure, propose a plain default:

```text
我先按小项目默认处理：浏览器里运行，不做登录，不接数据库，只保存必要的本地状态。后面如果需要再升级。
```

Output:

```text
预检模式：轻量
项目目标：
第一版范围：
核心页面或操作：
数据/登录/API：
技术默认：
验收方式：
暂不做：
```

Gate: goal, MVP boundary, core view or input/output, data decision, local run method, and verification method are clear enough to build.

After this gate, start implementation with the development loop. Create the four project context files only when the project will continue across sessions or the user wants persistent planning files.

### Full Preflight

Use the full Step 0 to Step 9 flow for multi-page apps, SaaS products, data-backed projects, auth, payments, external integrations, complex business rules, or deployment-sensitive work.

### Existing Project Adjustment

If the request targets an existing project, do not run the new-project guide mechanically. First inspect available project context such as README, package files, existing docs, and local instructions. Then ask only for missing product, scope, or verification details.

## Question Style for Beginners

- Ask 2 to 4 questions at a time unless the user is clearly ready for more detail.
- Avoid asking framework, database, auth, or deployment questions before the user understands whether those choices matter.
- Offer one simple default when the user is unsure, label it as an assumption, and ask for confirmation.
- Replace technical words with outcome words first: "needs login", "saves data", "shares with other users", "runs only on your computer".
- Mark irrelevant areas as `N/A`; do not force every project to have pages, storage, auth, or deployment.

## Step 0: Pause Coding

Purpose: prevent premature implementation and choose the right preflight depth.

Say:

```text
我先不直接写代码。我们先用很短的预检判断这个项目适合轻量模式还是完整模式。小项目只定目标、范围和验收方式；复杂项目再把页面、数据、技术栈和质量标准定细。
```

Output:

```text
当前状态：进入新项目预检
编码状态：暂缓
预检模式：轻量 / 完整
下一步：确认项目一句话目标或轻量项目合同
```

Gate: user agrees to start the preflight, provides enough information to complete Step 1, or the request is small enough for lightweight preflight.

Do not: create files, install packages, scaffold apps, or generate full code.

## Step 1: One-Sentence Project Goal

Purpose: turn the vague idea into a stable product target.

Ask:

1. 这个项目一句话是什么？
2. 主要给谁用？
3. 用户最核心要完成的一件事是什么？
4. 第一版做到什么程度，你会认为它成功了？

Output:

```text
项目一句话：
目标用户：
核心场景：
第一版成功标准：
关键假设：
```

Gate: the project has a clear user, core task, and success standard.

Do not: expand features before the core task is clear.

## Step 2: Project Scope

Purpose: prevent scope creep and "build everything" requests.

Ask:

1. 第一版必须完成哪些功能？
2. 哪些功能可以以后再做？
3. 哪些功能本版本明确不做？
4. 有没有时间、预算、平台、技术或账号限制？

Output:

```text
MVP 必做功能：
后续功能：
本版本排除项：
约束条件：
```

Gate: the user confirms MVP, later items, and excluded items.

Do not: include "maybe later" features in the first architecture unless required by the confirmed MVP.

## Step 3: User Flow

Purpose: define how the product is actually used before listing implementation tasks.

Ask:

1. 用户从哪里进入？
2. 第一个页面或状态看到什么？
3. 完成核心任务需要哪几步？
4. 成功后用户看到什么？
5. 空状态、错误状态、失败状态分别是什么？

Output:

```text
主流程：
异常流程：
空状态：
成功状态：
失败状态：
```

Gate: the core happy path and major non-happy paths are defined.

Do not: create page components before the flow is coherent.

## Step 4: Pages and Visual Frame

Purpose: create the product "blueprint" before UI generation.

Ask:

1. 需要哪些页面或主要视图？
2. 每个页面的核心区域是什么？
3. 导航方式是什么？
4. 视觉风格更接近哪个方向或参考产品？
5. 优先桌面端、移动端，还是都要？

Output:

```text
页面清单：
每页主要模块：
导航方式：
视觉风格：
响应式要求：
参考产品或素材：
```

Gate: every MVP feature maps to at least one page or view.

Do not: start frontend implementation without a page list and layout frame.

## Step 5: Feature Acceptance Criteria

Purpose: make each feature verifiable.

Ask for each MVP feature:

1. 用户故事是什么？
2. 输入是什么？
3. 输出是什么？
4. 正常路径是什么？
5. 异常路径是什么？
6. 怎么验证它完成了？

Output:

```text
功能名称：
用户故事：
输入：
输出：
正常路径：
异常路径：
验收标准：
验证方法：
```

Gate: every MVP feature has acceptance criteria and a reproducible verification method.

Do not: implement a feature with only a vague label such as "login", "dashboard", or "AI chat".

## Step 6: Data Model and Storage Rules

Purpose: stop AI from inventing inconsistent fields while coding.

Skip this step only when the project stores no data. Record `Data model: N/A` and the reason.

Ask:

1. 需要保存哪些对象？
2. 每个对象有哪些字段？
3. 字段类型、必填项、默认值是什么？
4. 对象之间有什么关系？
5. 数据存在哪里？
6. 重复、删除、更新、空值、权限不足时怎么处理？

Output:

```text
实体：
字段：
关系：
校验规则：
异常规则：
存储方案：
```

Gate: every saved object has fields, validation rules, and a storage decision, or the project explicitly stores no data.

Do not: write database, API, or persistence code before fields and rules are confirmed.

## Step 7: Technical Stack and Runtime

Purpose: lock the engineering foundation.

Ask:

1. 这个项目主要在哪里运行：浏览器、本地电脑、服务器，还是手机？
2. 是否需要登录、保存数据、多人共享或第三方 API？
3. 用户有没有指定必须使用或必须避免的技术？
4. 本地怎么运行和验证？
5. 是否有部署目标？

If the user is unsure, propose the simplest stack that satisfies the confirmed MVP. Label it as an assumption and ask for confirmation.

Output:

```text
技术栈：
本地运行方式：
依赖范围：
环境变量：
部署目标：
技术假设：
```

Gate: local run command, stack, and deployment target are clear enough to implement.

Do not: add new production dependencies without explicit confirmation.

## Step 8: Project Context Files

Purpose: give AI a persistent contract for future turns.

Create or update:

```text
PRD.md
ARCHITECTURE.md
PROJECT_STATE.md
AI_RULES.md
```

Use `project-artifact-templates.md`.

Gate: the four files exist or their full contents have been drafted for the user to approve before project creation.

Do not: treat chat history as the only source of truth once files can be created.

## Step 9: Development Order and Quality Gates

Purpose: split implementation into safe, testable modules.

Ask:

1. 哪个功能必须最先可用？
2. 哪些模块有依赖关系？
3. 每个模块怎么验证？
4. 是否需要保存 Git checkpoint？默认不提交，除非用户要求或项目规则要求。

Output:

```text
开发顺序：
模块目标：
涉及文件：
实现思路：
验收方法：
回滚点：
质量闸门：
```

Recommended order:

```text
1. 项目初始化
2. 基础布局和路由
3. 数据模型和存储
4. 核心功能 1
5. 核心功能 2
6. 异常状态和空状态
7. 测试和验收
8. UI 打磨
9. 部署准备
```

Gate: the first implementation module has a goal, affected files, verification method, and rollback point.

Do not: implement multiple unrelated modules in one pass.
