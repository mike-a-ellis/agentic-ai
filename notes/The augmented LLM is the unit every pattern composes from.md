---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, building-blocks]
---

# The augmented LLM is the unit every pattern composes from

The base building block is one LLM call with three augmentations available: retrieval, tools, and memory. Current models drive these themselves, writing their own search queries, picking tools, deciding what to keep. Every workflow and agent pattern is some arrangement of these calls, so the quality of each pattern is bounded by how well the augmentations are tailored and documented for the model.

MCP is one way to supply the tools side of this with a standard interface.

Applies when: designing any agentic system. Get the single augmented call right before composing it.

![[Pasted image 20260905095841.png]]

Related: [[Tool definitions deserve as much prompt engineering as prompts]]

## Cards

START
Basic
What are the main 3 LLM augementations?
Back: Retrieval, Tools, Memory
<!--ID: 1788645191014-->
END