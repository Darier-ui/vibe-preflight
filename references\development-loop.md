# Development Loop

Use this loop only after the preflight is complete and the first module is selected.

## Module Contract

Before coding a module, write:

```text
模块名称：
模块目标：
前置条件：
涉及文件：
实现思路：
验收标准：
验证方法：
回滚点：
```

If any field is missing, ask the user or derive the smallest reasonable assumption and ask for confirmation.

For lightweight projects, keep the module contract compact:

```text
本轮目标：
涉及文件：
验收方式：
```

Do not expand a small project into a heavy process when the goal, file scope, and verification method are already clear.

## Explain

Explain the implementation approach in plain language before editing files.

Include:

- What will change.
- Why these files are involved.
- What will not be touched.
- How the module will be verified.

## Test

Create or identify the narrowest useful verification before implementation.

Prefer, in order:

1. Existing targeted test for the touched behavior.
2. New focused test if the codebase has a reasonable test pattern.
3. Reproducible manual verification steps if tests are not practical.

Do not create broad or fragile tests just to satisfy the loop.

## Build

Implement only the current module. Keep edits surgical:

- Match existing project style.
- Avoid unrelated refactors.
- Avoid future features.
- Avoid new dependencies unless confirmed.
- Keep module boundaries clear.

## Verify

Run the agreed verification.

If verification fails:

1. Report the failure briefly.
2. Fix the smallest related issue.
3. Re-run the verification.
4. Do not proceed to the next module until the current module is verified or a real blocker is reported.

## Record

After verification, update `PROJECT_STATE.md` with:

```text
Completed:
Current status:
Verification run:
Known issues:
Next step:
```

Git checkpoints are optional. Suggest or create a checkpoint commit only when the user has asked for Git commits or the working agreement already permits it. Never discard unrelated user changes.

## Module Completion Checklist

```text
[ ] Module goal matched the confirmed MVP
[ ] Acceptance criteria covered
[ ] Verification run and result recorded
[ ] PROJECT_STATE.md updated
[ ] No unrelated files changed
[ ] Ready for next module
```
