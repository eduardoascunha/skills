---
name: grill-me
description: Interview the user to uncover context needed for a complete future spec. Use before writing a spec.
disable-model-invocation: true
---

Interview the user to uncover context, intent, and decisions that code and research cannot establish. Prepare the ground for a complete future spec. Do not write the spec or implement anything.

Find facts yourself, including by reading code if available. Ask the user only about intent, preferences, or unresolved uncertainty.

Ask numbered questions in dependency order. Always ask whether automated tests are needed. Give relevant labelled options or a recommendation, then wait for the user's reply before continuing.

Use this format:
```
**Q1 - <question title>**: <question>

Options: 
- A. <option>; 
- B. <option>; 
- C. <option>.

**Q2 - <question title>**: <question>

Recommendation: <recommended answer and reason>.
```

Repeat every unanswered or skipped question in the next question group until the user answers it. For "I don't know", "idk", or equivalent replies, rephrase the question with labelled options or examples. If the user again gives an equivalent reply, record the decision as **no answer**, including its consequence as an open decision, then continue with independent questions.

Ask at most five questions in each response. After every 20 questions, ask permission to continue with another group of up to 20 questions.

Continue in groups of up to 20 questions, delivered five at a time, until the user declines to continue or no relevant questions remain. Then write `.spec-driven/grill-me_result.md`, creating `.spec-driven/` if needed, using this template:

```markdown
# Grill-Me Result
## Questions and Answers

## Implementation Summary

## Open Decisions (omit when none)
```