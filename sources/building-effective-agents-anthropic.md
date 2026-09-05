---
type: source
source: https://www.anthropic.com/engineering/building-effective-agents
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns]
---

# Building effective agents (Anthropic Engineering, Dec 2024)

Erik Schluntz and Barry Zhang, from Anthropic's work with customer teams building agents. The main argument is that the teams who succeeded used small composable patterns on top of raw LLM calls, not heavy frameworks. Defines workflow vs agent, catalogs five workflow patterns, and closes with an appendix on designing tools (the agent-computer interface).

Caveat: the post now carries a note that the tooling landscape has changed since publication and points to the Managed Agents docs. The patterns and the design principles still hold; the framework list is dated.

Claims extracted:
- [[Workflows and agents differ by who controls the path]]
- [[Agentic complexity is bought with latency and cost]]
- [[The augmented LLM is the unit every pattern composes from]]
- [[Prompt chaining trades latency for accuracy on fixed subtasks]]
- [[Routing separates inputs so specialized prompts can be used independently]]
- [[Parallelization means sectioning or voting]]
- [[Orchestrator-workers is for tasks whose subtasks cannot be predicted]]
- [[Evaluator-optimizer needs criteria a model can apply]]
- [[An agent is a tool loop grounded in environmental feedback]]
- [[Agents fit open-ended tasks in trusted environments]]
- [[Tool definitions deserve as much prompt engineering as prompts]]
- [[Tool formats should match what the model has seen in the wild]]
- [[Agents pay off where the task is specified, actionable, and verifiable]]
- [[Transparency means the agent shows its plan before it acts]]
- [[Patterns are combined and then measured, not chosen from a menu]]
