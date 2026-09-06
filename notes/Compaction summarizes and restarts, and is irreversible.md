---
type: claim
source: ["[[effective-context-engineering-anthropic]]", "[[managed-agents-engineering-anthropic]]", "[[context-engineering-cookbook-anthropic]]"]
created: 2026-09-05
tags: [agentic-sdlc, context-engineering, managed-agents]
---

# Compaction summarizes and restarts, and is irreversible

When a conversation nears the window limit, compaction has the model summarize it and starts a fresh window from the summary plus a few recent items. Claude Code keeps architectural decisions, open bugs, and implementation details, drops redundant tool output, and carries over the five most recently touched files. It is usually the first lever for long-horizon coherence.

Tuning order matters. Start by maximizing recall so the summary captures everything relevant from real complex traces, then tighten precision by cutting what isn't needed. Over-aggressive compaction loses details whose importance only shows up later. The safest first step is tool-result clearing: an old tool result deep in history rarely needs to be seen again in raw form.

Compaction, tool-result clearing, and the memory tool are now primitives on the Claude Developer Platform, with a cookbook covering how to replace the default compaction prompt and how to test clearing settings against your own tool-use pattern. Anthropic's Managed Agents post adds the caveat that all of these are irreversible: once tokens are summarized away, they're gone unless stored elsewhere, and you can't know which ones future turns will need. Their architecture keeps a durable session log outside the context window that the harness can re-read by position, which makes context decisions recoverable.

Applies when: an agent's task will outlast one context window. Reach for tool-result clearing first, compaction second, and make sure the raw history is stored somewhere before compaction throws it away.

Related: [[Structured notes give an agent memory outside the window]], [[Sub-agents isolate exploration and return a distilled summary]], [[Pick compaction, notes, or sub-agents by task shape]]

## Cards

START
Basic
You're tuning a compaction prompt for an agent. Which do you optimize first, recall or precision, and why?
Back: Recall first, on real complex traces, so nothing critical is dropped. Then precision to cut noise. Over-aggressive compaction loses details whose importance only shows up later.
<!--ID: 1788645191050-->
END

START
Basic
What is the lightest-touch form of compaction, and why is it safe?
Back: Clearing old tool results from the history. A raw tool result deep in the conversation almost never needs to be re-read in full; the agent already acted on it.
<!--ID: 1788645191052-->
END

START
Basic
What's the structural weakness shared by compaction, memory files, and tool-result clearing, and how does Anthropic's Managed Agents design address it?
Back: All three are irreversible; you can't know which tokens later turns will need. Managed Agents keeps a durable session log outside the context window that the harness can re-read by position, so the decision is recoverable.
<!--ID: 1788645191054-->
END
