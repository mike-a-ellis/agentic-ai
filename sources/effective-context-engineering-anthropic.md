---
type: source
source: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Effective context engineering for AI agents (Anthropic Engineering, Sep 2025)

Anthropic Applied AI team. Argues that as agents run over many turns, the job shifts from writing a prompt to curating the whole token set the model sees at each step. Covers why long context degrades, what a good system prompt, tool set, and example set look like, just-in-time retrieval, and three techniques for tasks that outgrow the window: compaction, note-taking, sub-agents.

Later Anthropic material updates the long-horizon section: see [[managed-agents-engineering-anthropic]] and [[context-engineering-cookbook-anthropic]].

Claims extracted:
- [[Context engineering curates the whole token set on every turn]]
- [[Attention is a budget that depletes as context grows]]
- [[The target is the smallest set of high-signal tokens]]
- [[System prompts sit at the right altitude between brittle and vague]]
- [[Tool sets should be minimal and unambiguous]]
- [[A few canonical examples beat a list of edge cases]]
- [[Just-in-time retrieval keeps identifiers in context and loads data on demand]]
- [[Compaction summarizes and restarts, and is irreversible]]
- [[Structured notes give an agent memory outside the window]]
- [[Sub-agents isolate exploration and return a distilled summary]]
- [[Pick compaction, notes, or sub-agents by task shape]]
- [[Harness assumptions go stale as models improve]]
- [[An agent is a tool loop grounded in environmental feedback]] (second source)
