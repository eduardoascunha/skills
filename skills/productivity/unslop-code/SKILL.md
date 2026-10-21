---
name: unslop-code
description: Simplify supplied code and implement requested changes without unnecessary complexity.
---

Remove code, comments, configuration, and abstractions that do not serve a concrete need. When the request requires a change, implement it in the simplest form that meets the stated need.

1. Preserve existing behaviour, public interfaces, and facts. Add features, configuration, abstractions, dependencies, validation, or metadata only when the request or the implementation genuinely requires them.

2. Remove unnecessary comments, wrappers, helpers, branches, configuration, duplication, validation, and metadata. Keep established project patterns and do not change behaviour without calling it out.

3. Keep comments only when they explain a non-obvious decision, constraint, or trade-off. Remove comments that restate the code, narrate simple steps, or add generic section headings. Do not add a comment by default.

4. Define inputs, types, query parameters, documentation, validation, defaults, and abstractions only when each is needed. For example, if one new input requires bounds and a default while another only needs to be an integer, model them differently; do not add query wrappers or descriptions to both by default.