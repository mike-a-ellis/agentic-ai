---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Just-in-time retrieval keeps identifiers in context and loads data on demand

Instead of pre-loading everything relevant, the agent holds lightweight references (file paths, saved queries, URLs) and uses tools to pull the actual content when it needs it. Claude Code works this way: it can query a large database, store the result, and use head and tail to inspect pieces without the full object ever entering context.

The references carry signal on their own. A file named test_utils.py under tests/ means something different from the same name under src/core_logic/. Paths, naming conventions, sizes, and timestamps let the agent decide what to open next. This is progressive disclosure: understanding built up layer by layer, keeping only what's needed in the window.

The cost is speed and the need for good navigation tools and heuristics. Without them the agent wastes context on dead ends. The usual answer is a hybrid: drop a small amount of stable context in up front (Claude Code loads CLAUDE.md this way) and let the agent fetch the rest with glob, grep, and reads. Stable domains like legal or finance lean further toward pre-loading.

Applies when: designing how an agent gets information. Default to references plus tools; pre-load only what is small, stable, and always needed.

Related: [[Attention is a budget that depletes as context grows]], [[An agent is a tool loop grounded in environmental feedback]]

## Cards

START
Basic
A team wants to embed and pre-retrieve every document an agent might need, then stuff the top results into context. What's the just-in-time alternative and when does it win?
Back: Keep only identifiers (paths, queries, links) in context and load content on demand with tools. Wins when data is large or changes often, or when metadata like paths and timestamps helps the agent decide what to read. Costs speed and needs good navigation tools.
<!--ID: 1788645191032-->
END

START
Basic
Claude Code loads CLAUDE.md up front but finds source files with glob and grep. Why the split?
Back: CLAUDE.md is small, stable, and always relevant, so pre-loading is cheap. Source files are large and task-dependent, so fetching just-in-time avoids stale indexes and keeps context tight. That's the hybrid strategy.
<!--ID: 1788645191033-->
END
