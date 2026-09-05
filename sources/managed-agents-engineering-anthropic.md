---
type: source
source: https://www.anthropic.com/engineering/managed-agents
created: 2026-09-05
tags: [agentic-sdlc, managed-agents, context-engineering]
---

# Scaling Managed Agents: decoupling the brain from the hands (Anthropic Engineering, Apr 2026)

Architecture post on the hosted Managed Agents service. Three parts matter for this vault: the session log lives outside the context window and can be re-read by position, so context choices are recoverable; compaction, memory, and trimming are described as irreversible decisions that can fail; and an example of a harness assumption going stale (context resets added for Sonnet 4.5 were dead weight on Opus 4.5).

Claims extracted:
- [[Compaction summarizes and restarts, and is irreversible]] (second source)
- [[Harness assumptions go stale as models improve]] (second source)
