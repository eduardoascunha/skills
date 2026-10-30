---
name: to-task
description: Turn .spec-driven/spec.md into ordered implementation tasks in .spec-driven/tasks.md.
disable-model-invocation: true
---

Read `.spec-driven/spec.md`. If it does not exist, tell the user to run `/to-spec` first and stop.

Explore relevant code when available only to determine task boundaries and dependencies. Do not implement.

Draft the breakdown, then show the user a numbered list with each task's title, dependencies, and the behaviour it delivers. Ask whether the granularity and dependencies are right and whether any tasks should be merged or split. Iterate until the user approves, then write the file.

Write `.spec-driven/tasks.md` using this template:

```markdown
# Implementation Tasks

## Task <id>: <short title>

**Status:** open
**Depends on:** none | Task <id>
**Blocked by:** none

### What to implement

<the complete behaviour this task delivers>

### How to implement

<the components, data, interfaces, and ordered steps needed>

### Verify

- <test or check>

### Checks

- None yet.
```

Create tasks that are small enough to implement and review independently. Put tasks in dependency order. Each task must deliver a complete, verifiable behaviour, not a horizontal layer such as "add API" or "write tests".

Derive each task's `### Verify` from the spec's `Testing` section. When automated tests are required, put them in the task that changes the behaviour, naming the behaviours to test. When the spec says no automated tests are needed, list manual checks instead. Do not create tasks for anything under the spec's `Out of Scope`.

Keep the work simple. Reuse existing patterns and avoid tasks for speculative abstractions, configuration, or future features.

Use only these exact `Status` values:

- `open`: ready to start when dependencies are done.
- `in progress`: implementation is underway.
- `in review`: validation has passed and the task is awaiting or undergoing `/code-review-task <id>`.
- `done`: validation and code review passed.
- `blocked`: work cannot continue. Replace `Blocked by: none` with the specific reason.

`/implement-task` owns state transitions. It moves a task from `open` to `in progress`, then to `in review` after validation. It moves the task to `done` only after a clean review, returns it to `in progress` when review findings need fixes, and moves it to `blocked` only with a recorded reason.

After writing the file, list the task IDs and titles. End the final response with `Next step: /implement-task <id>`, replacing `<id>` with the first task whose dependencies are satisfied.