---
name: code-review-task
description: Review the current implementation against one task in .spec-driven/tasks.md for bugs, missing work, and needless complexity.
---

Review the implementation of the selected task. Do not modify code or commit.

## Process

1. Require a task ID: `/code-review-task <id>`. If no task ID is provided, tell the user to provide one and stop.

2. Read `.spec-driven/tasks.md`. If it does not exist, warn the user and stop. Confirm that the named task exists and its `Status` is `in review`. Otherwise, warn the user and stop. This skill reports findings only; `/implement-task` owns the task's state transitions.

3. Review staged and unstaged changes against `HEAD`, including relevant untracked files. The diff may also contain work from other tasks, since the user may or may not commit between tasks. Review only the changes that belong to the selected task. Treat changes from tasks with `Status: done` as already reviewed, and report them only when the selected task breaks them. If there is no diff, say so and stop. Review the selected changes for:
   - bugs, error paths, boundary cases, regressions, and unsafe data changes;
   - missing, incorrect, or out-of-scope behaviour against the task;
   - unnecessary abstraction, configuration, input modes, duplication, or comments that do not explain a non-obvious reason;
   - missing or inadequate tests, judged against the task's `Verify` section and, when `.spec-driven/spec.md` exists, its `Testing` and `Out of Scope` sections.

   Follow repository conventions when they exist. Do not report formatting or lint issues that tooling already catches. Do not invent requirements.

4. Output only actionable issues for `/implement-task <id>` to fix, ordered by severity:

   ```markdown
   - [P1] [path/to/file:line] Short title
     Impact and the smallest useful fix.
   ```

   Use `P0` for blocking data loss, security, or broken core behaviour; `P1` for likely bugs or missing required behaviour; `P2` for meaningful maintainability or test gaps. Do not add summaries, praise, or unrelated refactors. If there are no issues, say `No issues found.`