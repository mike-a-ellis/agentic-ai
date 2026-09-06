---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, evals]
---

# Patterns are combined and then measured, not chosen from a menu

The five workflow patterns and the agent loop are not a list to pick one item from. Real systems mix them: a router in front of a chain, an orchestrator whose workers each run an evaluator loop. The post is explicit that the patterns are common shapes to reshape, and that the only thing deciding whether a given combination is right is measured performance. Add a layer, run the eval, keep it only if the number moved.

The five workflow patterns and what triggers each:

1. [[Prompt chaining trades latency for accuracy on fixed subtasks|Prompt chaining]]: the task splits cleanly into known sequential steps, and you'll accept slower for more accurate.
2. [[Routing separates inputs so specialized prompts can be used independently|Routing]]: inputs fall into distinct categories that need different handling, and you can classify them reliably.
3. [[Parallelization means sectioning or voting|Parallelization]]: subtasks are independent and can run at once (sectioning), or you want multiple attempts aggregated for confidence (voting).
4. [[Orchestrator-workers is for tasks whose subtasks cannot be predicted|Orchestrator-workers]]: the subtasks depend on the input and can't be fixed in advance.
5. [[Evaluator-optimizer needs criteria a model can apply|Evaluator-optimizer]]: there are explicit quality criteria, and iterating against them measurably improves the output.

Beyond these, [[An agent is a tool loop grounded in environmental feedback|the agent loop]] hands control of the sequence to the model itself.

This is the same discipline as starting simple, applied after you have already gone past a single call.

Applies when: someone asks "which pattern should we use." The answer is usually a combination, and the eval decides.

Related: [[Agentic complexity is bought with latency and cost]], [[Workflows and agents differ by who controls the path]]

## Cards

START
Basic
Name the five workflow patterns from Anthropic's agents post and give the one-line trigger for each.
Back: Prompt chaining (fixed sequential steps, trade latency for accuracy). Routing (distinct input categories, reliable classifier). Parallelization (independent subtasks, or voting for confidence). Orchestrator-workers (subtasks unknown until you see the input). Evaluator-optimizer (explicit criteria, iteration helps).
<!--ID: 1788645191035-->
END

START
Basic
A design combines a router feeding into an orchestrator whose workers each run an evaluator loop. Is that overbuilt?
Back: Can't tell from the diagram. Patterns are meant to be combined; the eval decides. Add each layer separately and keep it only if the score moved.
<!--ID: 1788645191037-->
END
