---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, definitions]
---

# Workflows and agents differ by who controls the path

Anthropic groups everything under "agentic systems" and then draws one line inside that group. In a workflow, code decides the sequence of steps and the LLM fills in each step. In an agent, the LLM decides the sequence itself, choosing which tools to call and when to stop. The distinction is about who owns control flow, not about how many tools are involved or how capable the model is.

This matters for scoping because it is the first question to ask about any proposed "agent." If you can write down the steps in advance, you are describing a workflow, and workflows are cheaper, more predictable, and easier to test.

Applies when: someone proposes an AI system and calls it an agent. Ask whether the path is fixed.

Related: [[Agentic complexity is bought with latency and cost]], [[An agent is a tool loop grounded in environmental feedback]]

## Cards

START
Basic
A proposed system has an LLM call five tools in a fixed order, with code checking each result. Workflow or agent, and why?
Back: Workflow. Code owns the control flow; the LLM only fills in steps. It becomes an agent when the LLM decides which tool to call next and when to stop.
END
