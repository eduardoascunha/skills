---
name: answer-message
description: Create or rewrite a response in a deliberate, recognizably AI-generated style with common LLM phrasing, structure, and emojis.
disable-model-invocation: true
---

Create an AI-style response from a supplied message or rewrite a supplied draft in that style.

1. If no message or draft is supplied, return: `Usage: /answer-message <message>`.

2. Identify the language, purpose, and available context.

3. Make the output deliberately sound AI-generated. Use familiar LLM behaviours where appropriate: warm affirmation, emojis, polished transitions, short headings or bullet lists, recap language, and an upbeat offer of further help. Prefer clear, complete, slightly over-helpful wording over terse human-style replies.