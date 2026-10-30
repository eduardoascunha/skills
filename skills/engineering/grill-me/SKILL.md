---
name: grill-me
description: Interview the user to settle what to build before writing a spec.
disable-model-invocation: true
---

Interview the user until you share an understanding of what they want built. Do not write the spec or implement anything.

Ask only about what only the user can decide: goals, behaviour, scope, constraints, trade-offs, and whether automated tests are needed.

Do not ask about technical choices such as libraries, file layout, function design, or implementation steps. Decide those yourself later, using what you know and what the codebase shows. Exception: when the user raises a technical choice or requirement themselves, discuss it and record it.

Find facts yourself, including by reading code if available.

Map the topic as a tree of decisions. The **frontier** is every decision whose prerequisites are already settled. Ask the whole frontier in one round, numbered, then wait for the answers. A question that depends on another open question in the same round belongs to a later round.

Give every question a recommended answer, worded so that "yes" accepts it. Format a round like this:

```
**Q1 - <question title>**: <question>

Recommendation: <recommended answer and reason>.
```

Add labelled options only when the choice is not binary.

Repeat any unanswered or skipped question in the next round. For "I don't know", "idk", or equivalent replies, rephrase the question with options or examples. If the user again gives an equivalent reply, record the decision as **no answer** with its consequence as an open decision, then continue.

The interview is done when the frontier is empty or the user asks to stop. Then write `.spec-driven/grill-me_result.md`, creating `.spec-driven/` if needed, using this template:

```markdown
# Grill-Me Result
## Questions and Answers

## Summary

## Open Decisions (omit when none)
```

The summary states what the user wants built, the agreed scope, and the agreed testing expectations. Include technical details only when the user specified them.