---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, workflow-patterns]
---

# Prompt chaining trades latency for accuracy on fixed subtasks

Prompt chaining splits a task into a fixed sequence where each LLM call consumes the previous call's output. You can insert programmatic gates between steps to check the intermediate result is still on track. The point is to make each individual call easier, which raises accuracy at the price of more round trips.

Fits when the decomposition is clean and known in advance: draft copy then translate it, or write an outline, validate it, then write the document from it.

Applies when: a task has obvious stages and you are willing to be slower to be more reliable.

![[Pasted image 20260905102011.png]]

Related: [[Routing separates inputs so specialized prompts can be used independently]], [[Orchestrator-workers is for tasks whose subtasks cannot be predicted]]

## Cards

START
Basic
When chaining prompts, what can be inserted between prompts ? What is the purpose of these?
Back: Programmatic Gates, These gates or checks ensure a process is still on track.
<!--ID: 1788645191026-->
END
