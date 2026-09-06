---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, workflow-patterns]
---

# Parallelization means sectioning or voting

Parallelization runs LLM calls at the same time and combines the outputs in code. There are two shapes. Sectioning splits a task into independent pieces that run at once (one call answers the user's input while a separate call screens the input for policy violations). Voting runs the same task several times and aggregates (multiple LLMs or prompts review a code change for vulnerabilities or inappropriate materials, with a threshold to tune false positives against false negatives).

The underlying reason it works: models do better when each concern gets its own call and full attention, instead of one call juggling several considerations.

Applies when: subtasks are independent and speed matters, or when confidence needs more than one attempt.

![[Pasted image 20260905110321.png]]

Related: [[Orchestrator-workers is for tasks whose subtasks cannot be predicted]]

## Cards

START
Basic
Parallelization has two variants. Name them and give the distinguishing feature of each.
Back: Sectioning splits a task into independent parts run at once. Voting runs the same task multiple times and aggregates the answers.
<!--ID: 1788645191030-->
END
