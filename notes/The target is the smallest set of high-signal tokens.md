---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# The target is the smallest set of high-signal tokens

The whole discipline reduces to one goal: find the smallest set of tokens that makes the desired outcome most likely. Smallest does not mean short. The agent still needs enough up front to behave correctly; it means nothing in the window that isn't earning its place. This applies to every component: system prompt, tools, examples, history.

The working method is to start with a minimal prompt on the strongest available model, run it, and add instructions or examples only in response to failures you observed.

Applies when: reviewing any context component. For each block, ask what breaks if it's removed. If nothing, remove it.

Related: [[Attention is a budget that depletes as context grows]], [[Agentic complexity is bought with latency and cost]]

## Cards

START
Basic
What is the one-sentence goal of context engineering, and what does "minimal" not mean?
Back: The smallest set of high-signal tokens that maximizes the chance of the desired outcome. Minimal does not mean short; it means nothing present that isn't doing work.
<!--ID: 1788645191011-->
END

START
Basic
You're starting a new agent's system prompt. What's the recommended order of operations?
Back: Start minimal on the best model available, run it, then add instructions and examples only for the failure modes you actually observe. Don't pre-load rules for problems you haven't seen.
<!--ID: 1788645191012-->
END
