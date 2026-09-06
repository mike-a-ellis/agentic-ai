---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, workflow-patterns]
---

# Orchestrator-workers is for tasks whose subtasks cannot be predicted

An orchestrator LLM reads the task, decides what subtasks it needs, hands them to worker LLMs, and merges the results. It looks like parallelization on a diagram, but the difference is that the subtasks are not fixed ahead of time. The orchestrator invents them per input.

The canonical example is a coding change that touches several files: which files, and what changes each needs, depend on the specific request, so no fixed pipeline can express it. Multi-source research tasks have the same shape.  Another example is search tasks that involve gathering and analyzing information from multiple sources for possible relevant information.

Applies when: you know the general shape of the work but not how many pieces it will have until you see the input.

![[Pasted image 20260905110452.png]]

Related: [[Parallelization means sectioning or voting]], [[An agent is a tool loop grounded in environmental feedback]]

## Cards

START
Basic
Orchestrator-workers and parallelization look the same on a diagram. What separates them?
Back: In parallelization the subtasks are defined in advance. In orchestrator-workers the orchestrator LLM decides the subtasks at runtime based on the input.
<!--ID: 1788645191038-->
END
