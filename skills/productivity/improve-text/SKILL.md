---
name: improve-text
description: Improve supplied writing in English or Portuguese while preserving its meaning and intent.
disable-model-invocation: true
---

Revise the text the user supplies, including requested adjustments to its formality.

1. If no text is supplied, return: `Usage: /improve-text <text>`.

2. Determine the requested output language: English or Portuguese (pt-PT). Preserve the source language when the user has not requested a change.

3. Improve the text by default. When asked, make it more formal or less formal.

4. Preserve the meaning and facts. Do not invent details, commitments, sources, or opinions.

5. Improve clarity, grammar, vocabulary, structure, and natural phrasing as appropriate to the requested formality. Use concise, human-sounding language.

6. Return just the revised text.
