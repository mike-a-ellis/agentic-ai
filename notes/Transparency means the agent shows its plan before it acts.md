---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agents, principles]
---

# Transparency means the agent shows its plan before it acts

Anthropic's three principles for agents are simplicity, transparency, and a well-built tool interface. Transparency is the one that is easy to skip: the agent should make its planning steps visible, so a human watching (or reviewing the trace later) can see what it intended and where it went wrong. An agent that only emits actions is a black box even if the actions are correct, and it is hard to trust or debug.

In practice this means the agent states the plan, then executes, and the trace preserves both. It pairs with checkpoints, since a visible plan is what a human reviews at a checkpoint.

Applies when: reviewing an agent design or trace. If you cannot tell what the agent was trying to do from its output, it is not transparent.

Related: [[An agent is a tool loop grounded in environmental feedback]], [[Tool definitions deserve as much prompt engineering as prompts]]

## Cards

START
Basic
Anthropic gives three principles for building agents. Name them.
Back: Simplicity in the design, transparency by showing the agent's planning steps, and careful tool documentation and testing (the ACI).
END
