---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Pick compaction, notes, or sub-agents by task shape

The three long-horizon techniques answer different task shapes. [[Compaction summarizes and restarts, and is irreversible|Compaction]] preserves conversational flow, so it fits tasks with a lot of back-and-forth. [[Structured notes give an agent memory outside the window|Structured notes]] fit iterative work with clear milestones, where progress state matters more than dialog. [[Sub-agents isolate exploration and return a distilled summary|Sub-agents]] fit research and analysis where parallel exploration pays and the lead only needs results. They combine; a research lead can use notes for its own plan and sub-agents for the search.

Applies when: a task will exceed one context window. Name its shape first, then pick.

Related: [[Patterns are combined and then measured, not chosen from a menu]]

## Cards

START
Basic
Three tasks: (a) a long design conversation with a user, (b) a codebase migration with checkpoints, (c) a literature review across many sources. Which long-horizon technique fits each?
Back: (a) Compaction, to preserve conversational flow. (b) Structured notes, to track milestones across resets. (c) Sub-agents, so exploration stays isolated and the lead gets summaries.
END
