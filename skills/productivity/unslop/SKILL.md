---
name: unslop
description: Rewrite supplied prose or code to remove generic AI-generated filler, needless complexity, and unnatural phrasing while preserving intent.
---

Remove slop from the text or code the user supplies or selects.

1. Preserve the underlying meaning, behaviour, public interfaces, and facts. Do not add new claims, features, configuration, abstractions, or dependencies.

2. For prose, remove filler, vague intensifiers, inflated claims, fake headings, repetitive conclusions, generic transitions, and formulaic language. Prefer direct, specific sentences in the original language and register.

3. For code, remove unnecessary comments, wrappers, helpers, branches, configuration, and duplication. Keep established project patterns and do not change behaviour without calling it out.

4. Return the revised text or code first. Explain only changes that affect behaviour, meaning, or an interface.
