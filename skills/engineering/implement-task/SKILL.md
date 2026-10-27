---
name: implement-task
description: Implement one approved task from .spec-driven/tasks.md.
disable-model-invocation: true
---

Implement only the selected approved task.

1. Require a task ID: `/implement-task <id>`. If no task ID is provided, tell the user to provide one and stop.

2. Read `.spec-driven/tasks.md`. If it does not exist, tell the user to run `/to-task` first and stop. Confirm that the named task exists and its `Status` is `open` or `in progress`. Stop when it is `in review`, `done`, or `blocked`.

3. Before changing code, set only the selected task's `Status` to `in progress`. Do not change any other task.

4. Explore only the relevant code. Follow existing patterns unless the selected work requires a change.

5. Prefer the simplest design that satisfies the selected work and follows local patterns. Reuse existing code before adding an abstraction. Do not add unsupported modes, configuration, extension points, or validation.

6. Add comments only when they explain a non-obvious reason. Keep them concise, timeless, and useful.

7. Validate throughout with the narrowest relevant typecheck and tests. Run pre-commit when configured. Run the full test suite before completion when the project provides one. If work cannot continue because of a concrete dependency or missing decision, set the task's `Status` to `blocked`, record the reason in `Blocked by:`, and report it.

8. After validation passes, set only the selected task's `Status` to `in review` and append the checks that passed under `### Checks`.

9. Run `/code-review-task <id>`. If it finds issues, return the task to `in progress`, address the findings, validate again, and repeat the review. When the review reports `No issues found.`, set the task's `Status` to `done`. Leave the changes uncommitted.

10. End every final response with the task outcome. When the selected task is `done`, find the next task with `Status: open` in `.spec-driven/tasks.md`. If one exists, end with `Next step: /implement-task <id>`. If none exists, end with `All tasks done.` When the task is blocked, in progress, in review, missing, or cannot start, clearly state that status and the reason or required action; do not suggest another task.