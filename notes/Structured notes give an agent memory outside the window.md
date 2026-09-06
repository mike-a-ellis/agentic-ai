---
type: claim
source: ["[[effective-context-engineering-anthropic]]", "[[context-engineering-cookbook-anthropic]]"]
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Structured notes give an agent memory outside the window

The agent periodically writes notes to storage outside its context (a NOTES.md, a to-do list, a memory directory) and reads them back later, including after a context reset. Cost is near zero and it preserves progress, dependencies, and decisions that would otherwise vanish across dozens of tool calls.

Claude playing Pokémon is the reference case: it kept precise tallies over thousands of steps, mapped explored areas, and recorded which attacks worked, without being told how to structure memory. After each reset it read its own notes and continued multi-hour sequences.

The memory tool on the Claude Developer Platform is the productized version: a file-based store the agent reads and writes through tool calls, persisting across sessions, with storage on your side.

Applies when: a task has milestones or state that must survive a reset. Give the agent a place to write and a habit of writing.

Related: [[Compaction summarizes and restarts, and is irreversible]], [[Pick compaction, notes, or sub-agents by task shape]]

## Cards

START
Basic
An agent doing a multi-hour migration loses track of which modules it already converted after each compaction. What technique fixes that, and what does the fix look like concretely?
Back: Structured note-taking. The agent writes progress to a file outside context (a NOTES.md or memory directory) and re-reads it after each reset. Compaction summaries alone are too lossy for this kind of state.
<!--ID: 1788645191016-->
END
