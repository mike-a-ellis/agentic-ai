---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering, agent-patterns]
---

# Sub-agents isolate exploration and return a distilled summary

Rather than one agent carrying all state, a lead agent holds the plan and delegates focused work to sub-agents that each start with a clean window. A sub-agent may burn tens of thousands of tokens exploring, but returns only a condensed summary, often one to two thousand tokens. The messy search context stays inside the sub-agent; the lead sees only results and spends its attention on synthesis.

This is the context-engineering reason the orchestrator-workers pattern works for research: it is attention isolation, not just parallelism.

Applies when: a task requires broad exploration whose intermediate steps the lead agent doesn't need to see.

Related: [[Orchestrator-workers is for tasks whose subtasks cannot be predicted]], [[Compaction summarizes and restarts, and is irreversible]], [[Pick compaction, notes, or sub-agents by task shape]]

## Cards

START
Basic
Beyond running work in parallel, what does a sub-agent architecture do for context?
Back: It isolates the exploration context. Each sub-agent spends its own window searching and returns a short distilled summary, so the lead agent's window holds only results, not the search trail.
<!--ID: 1788645191021-->
END
