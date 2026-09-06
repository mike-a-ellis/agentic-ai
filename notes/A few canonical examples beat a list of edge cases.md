---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# A few canonical examples beat a list of edge cases

Few-shot examples remain one of the strongest levers. The mistake is using them to enumerate every edge case, which turns the prompt into a rule list that costs context and still misses cases. Instead, pick a small set of diverse examples that each show the expected behavior clearly. The model generalizes from the pattern; it doesn't need the exhaustive list.

Applies when: a prompt's example section keeps growing. If new examples are being added per bug, you're enumerating instead of illustrating.

Related: [[The target is the smallest set of high-signal tokens]], [[System prompts sit at the right altitude between brittle and vague]]

## Cards

START
Basic
Every time a bug report comes in, the team adds another example to the prompt. It now has thirty. What's the problem and what should they do instead?
Back: They're enumerating edge cases, which bloats context and never finishes. Replace with a handful of diverse canonical examples that show the pattern, and let the model generalize.
<!--ID: 1788645191069-->
END
