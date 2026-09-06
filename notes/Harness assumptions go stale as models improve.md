---
type: claim
source: ["[[effective-context-engineering-anthropic]]", "[[managed-agents-engineering-anthropic]]"]
created: 2026-09-05
tags: [agentic-sdlc, context-engineering, managed-agents]
---

# Harness assumptions go stale as models improve

Every piece of scaffolding around a model encodes a belief about what that model can't do alone. Smarter models need less prescriptive engineering, so those beliefs expire. Anthropic's own example: Sonnet 4.5 would wrap up work early as it sensed the context limit approaching, so the harness added context resets. On Opus 4.5 the behavior was gone and the resets were dead weight.

Two consequences. Build the harness so its parts can be swapped or removed without touching the rest. And re-test the harness on each new model, removing scaffolding that no longer pays for itself, rather than accumulating it. "Do the simplest thing that works" stays the advice because the simplest thing keeps changing.

Applies when: upgrading models. Treat every workaround in the harness as a hypothesis to re-test, not a fixture.

Related: [[System prompts sit at the right altitude between brittle and vague]], [[Agentic complexity is bought with latency and cost]]

## Cards

START
Basic
You upgrade an agent to a newer model and everything still works. What should you do with the harness anyway, and why?
Back: Re-test each workaround and remove the ones the new model no longer needs. Scaffolding encodes assumptions about model weaknesses; those go stale and become dead weight (Anthropic's context resets for Sonnet 4.5 were unnecessary on Opus 4.5).
<!--ID: 1788645191040-->
END
