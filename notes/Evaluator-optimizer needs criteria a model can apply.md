---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, workflow-patterns]
---

# Evaluator-optimizer needs criteria a model can apply

One LLM call produces a draft, a second call critiques it against explicit criteria, and the loop repeats until the evaluator is satisfied. Two conditions have to hold for this to be worth the extra calls: a human giving feedback would measurably improve the output, and an LLM is capable of giving that same feedback. If either fails, the loop just burns tokens.

Examples in the post are literary translation (an evaluator catches nuance the first pass missed) and iterative search where the evaluator decides whether another round is needed.

Applies when: quality has a clear rubric and revision is known to help. Does not apply when "better" cannot be stated concretely.

![[Pasted image 20260905110538.png]]

Related: [[Prompt chaining trades latency for accuracy on fixed subtasks]]

## Cards

START
Basic
In the evaluator-optimizer pattern, what three conditions should be true for it to be useful and effective?
Back: a human giving feedback would measurably improve the output, an LLM is capable of giving that same feedback, and quality has a clear rubric ("better" can be stated concretely) 
<!--ID: 1788645191042-->
END