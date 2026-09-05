---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Context engineering curates the whole token set on every turn

Context is every token the model sees when it samples: system prompt, tool definitions, retrieved documents, message history, tool results. Prompt engineering is writing the instructions well. Context engineering is deciding, at each turn, which tokens from everything that could go in actually should. It is a loop, not a one-time write, because an agent generates new candidate context on every step.

Applies when: someone treats an agent problem as a prompt problem. Ask what else is in the window and who decided it should be there.

![[Pasted image 20260905151518.png]]

Related: [[Attention is a budget that depletes as context grows]], [[The target is the smallest set of high-signal tokens]]

## Cards

START
Basic
An agent degrades after twenty turns. The team's fix is to rewrite the system prompt. Why is that probably the wrong lever?
Back: The system prompt is a small fixed part of context. After twenty turns most of the window is message history and tool results. Context engineering means curating that whole set each turn, not just the instructions.
END
