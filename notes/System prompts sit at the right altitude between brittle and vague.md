---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# System prompts sit at the right altitude between brittle and vague

Two failure modes bracket a good system prompt. Too low: hardcoded if-then logic that tries to script exact behavior, which is fragile and expensive to maintain. Too high: vague guidance that gives no concrete signal, or that assumes shared context the model doesn't have. The right altitude is specific enough to steer and loose enough to leave the model heuristics rather than rules.

Structure helps. Split the prompt into labeled sections (background, instructions, tool guidance, output format) using XML tags or markdown headers. Exact formatting matters less as models improve, but the sections still make the prompt easier to maintain and audit.

Applies when: reading a system prompt in review. If it reads like a decision tree, it's too low. If a new hire couldn't act on it, it's too high.

Related: [[The target is the smallest set of high-signal tokens]], [[Harness assumptions go stale as models improve]]

## Cards

START
Basic
A system prompt reads "if the user mentions refunds, first check X, then if Y, do Z, unless W." What's wrong with it and what's the fix?
Back: It's at the brittle end: hardcoded branching that breaks on unanticipated cases and is costly to maintain. Raise the altitude: state the goal and the heuristics, give a canonical example, let the model handle the branching.
<!--ID: 1788645191017-->
END

START
Basic
What does it mean to give a system prompt "heuristics rather than rules," and why does it matter?
Back: State the goal and the rules of thumb for reaching it, not an if-then list. Rules only cover the cases you wrote down; heuristics carry the intent, so the model can decide cases you didn't anticipate.
<!--ID: 1788645191019-->
END