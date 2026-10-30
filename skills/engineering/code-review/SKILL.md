---
name: code-review
description: Review the current implementation against .spec-driven/spec.md for bugs, missing work, and needless complexity.
---

Review the implementation of the approved spec. Do not modify code or commit.

## Process

1. Read `.spec-driven/spec.md`. If it does not exist, warn the user and stop.

2. Review staged and unstaged changes against `HEAD`, including relevant untracked files. If there is no diff, say so and stop. Review the selected changes for:
   - bugs, error paths, boundary cases, regressions, and unsafe data changes;
   - missing, incorrect, or out-of-scope behaviour against the spec, including anything listed under its `Out of Scope`;
   - unnecessary abstraction, configuration, input modes, duplication, or comments that do not explain a non-obvious reason;
   - missing or inadequate tests, judged against the spec's `Testing` section.

   Follow repository conventions when they exist. Do not report formatting or lint issues that tooling already catches. Do not invent requirements.

3. Output only actionable issues for `/implement` to fix, ordered by severity:

   ```markdown
   - [P1] [path/to/file:line] Short title
     Impact and the smallest useful fix.
   ```

   Use `P0` for blocking data loss, security, or broken core behaviour; `P1` for likely bugs or missing required behaviour; `P2` for meaningful maintainability or test gaps. Do not add summaries, praise, or unrelated refactors. If there are no issues, say `No issues found.`