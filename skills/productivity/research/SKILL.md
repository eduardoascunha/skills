---
name: research
description: Investigate a question against high-trust primary sources and capture the findings as a Markdown file in the repo.
disable-model-invocation: true
---

Spin up a **background agent** to do the research, so you keep working while it reads.

Its job:

1. Investigate the question against **primary sources** (official docs, source code, specs, first-party APIs), not a secondary write-up of them. Follow every claim back to the source that owns it.
2. Create one Markdown report in the root of the currently open workspace. Name it descriptively, using lowercase hyphenated words, for example `input-example.md`.
3. Structure the report with a title, the research question, a short summary, findings grouped by topic, and a sources section. Cite the primary source directly beside each claim and include its link in the sources section.
4. In the final response, briefly state that the research is complete and link to the created Markdown file.
