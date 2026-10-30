---
name: implement
description: Implement the approved spec in .spec-driven/spec.md.
disable-model-invocation: true
---

Implement only the approved spec.

1. Read `.spec-driven/spec.md`. If it does not exist, tell the user to run `/to-spec` first and stop.

2. Explore only the relevant code. Follow existing patterns unless the selected work requires a change.

3. Prefer the simplest design that satisfies the selected work and follows local patterns. Reuse existing code before adding an abstraction. Do not add unsupported modes, configuration, extension points, or validation.

4. Add comments only when they explain a non-obvious reason. Keep them concise, timeless, and useful.

5. Validate throughout with the narrowest relevant typecheck and tests. Run pre-commit when configured. Run the full test suite before completion when the project provides one.

6. Run `/code-review` after implementing the spec. If it finds issues, address them, validate again, and repeat the review until it reports `No issues found.`

7. Never commit; the user commits when ready. Report the result.