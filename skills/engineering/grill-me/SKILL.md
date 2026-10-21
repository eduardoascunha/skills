---
name: grill-me
description: Interview the user to uncover context needed for a complete future spec. Use before writing a spec.
disable-model-invocation: true
---

Interview the user to uncover context, intent, and decisions that code and research cannot establish. Prepare the ground for a complete future spec. Do not write the spec or implement anything.

Find facts yourself, including by reading code if available. Ask the user only about intent, preferences, or unresolved uncertainty.

Ask numbered questions in dependency order. Give relevant options or a recommendation, then wait for the user's reply before continuing.

Use this format:
```
**Q1 - <question title>**: <question>

Options: <option>; <option>; <option>.

**Q2 - <question title>**: <question>

Recommendation: <recommended answer and reason>.
```

For "I don't know", "idk", or equivalent replies, mark the decision **no answer**. Rephrase it with options or examples. If it remains unclear, record the open decision and its consequence, then continue with independent questions.

Ask at most 20 questions. Then ask permission to continue in another group of up to 20.

Continue in groups of up to 20 questions until the user declines to continue or no relevant questions remain. Then write `.spec-driven/grill-me_result.md`, creating `.spec-driven/` if needed, using this template:

```markdown
# Grill-Me Result
## Questions and Answers

## Implementation Summary

## Open Decisions (omit when none)
```