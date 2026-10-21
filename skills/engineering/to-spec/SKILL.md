---
name: to-spec
description: Turn a grill-me result into a complete specification. Invoke explicitly after the interview.
disable-model-invocation: true
---

Read `.spec-driven/grill-me_result.md` before doing any other work. If it does not exist, stop and tell the user to run `/grill-me` first.

The grill-me result is the source of truth for intent and scope. Do not interview the user. Combine the recorded result with codebase evidence.

When the result contains **Open Decisions**, choose the best option using the available evidence. Mark each choice in the spec as: `AI decision`. Include the reason for the choice.

## Process

1. Explore the relevant code when available. Use the project's domain vocabulary and respect relevant ADRs. Record only evidence that changes the design or implementation.

2. Write `.spec-driven/spec.md` using the template below. Make it detailed enough to implement without another design discussion. State what to build and how to build it. Use codebase evidence to name relevant components, flows, data, and contracts. Include file paths and small code snippets only when they remove meaningful ambiguity.

3. Do not implement the spec. Tell the user they can either run `/implement` for the direct workflow or `/to-task` to create implementation tasks.

Use this template:
```markdown
# Spec

## What to Build

Describe exactly what must be implemented.

## How to Build It

Describe the implementation in detail. Include relevant components, such as data changes, interfaces, control flow, error handling, and compatibility rules.

Mark every decision made to resolve an Open Decision as: `<decision> (AI decision: <reason>)`.

Use numbered steps when order matters.
```

