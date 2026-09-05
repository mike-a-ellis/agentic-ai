---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, scoping, tradeoffs]
---

# Agentic complexity is bought with latency and cost

Every step up the ladder (single call, then workflow, then agent) trades speed and money for better task performance. The default recommendation is to find the simplest thing that works and only add a layer when measurement shows the simpler version falls short. For a lot of applications that ceiling is a single LLM call with retrieval and a few in-context examples, and no agentic system is needed at all.

The practical test: can you show, with an eval, that the added complexity improved the outcome? If not, you paid latency and cost for nothing.

Applies when: reviewing a design that jumps straight to multi-step or multi-agent. Ask what the single-call baseline scored.

Related: [[Workflows and agents differ by who controls the path]], [[Patterns are combined and then measured, not chosen from a menu]]

## Cards

START
Basic
What increases when you move from a single LLM call to a workflow to an agent, and what justifies it?
Back: Latency and cost go up at each step. Only measured improvement in task outcomes justifies it; otherwise stay simpler.
END

START
Basic
What is the fundamental pre-requisite and initially pre-cursor to adding complexity (more LLM calls, more agency, etc)?
Back: Evaluation, and measured baseline
END

START
Basic
A team proposes a multi-step agent for a task nobody has tried as a single LLM call. What's the first question, and why?
Back: What does a single call with retrieval and a few in-context examples score on the eval? Every layer above that (workflow, then agent) costs latency and money, so it has to beat the baseline by a measured margin to be worth building.
END
