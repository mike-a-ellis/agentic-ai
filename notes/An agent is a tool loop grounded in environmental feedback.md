---
type: claim
source: ["[[building-effective-agents-anthropic]]", "[[effective-context-engineering-anthropic]]"]
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, agents]
---

# An agent is a tool loop grounded in environmental feedback

Stripped down, an agent is an LLM calling tools in a loop and reading the results to decide the next step. Anthropic has since adopted that as the working definition: an LLM autonomously using tools in a loop, with autonomy scaling as models improve. What keeps it honest is ground truth from the environment on every iteration: a tool result, a test output, a command's exit code. Without that signal the model is planning against its own guesses.

Control comes from checkpoints where the agent pauses for human input, and from stopping conditions such as a maximum iteration count. Because the architecture is so simple, most of the engineering effort lands on the tools and their documentation, not on the loop.

Applies when: explaining what an agent actually is, or reviewing one that lacks feedback signals or a stopping rule.

Related: [[Workflows and agents differ by who controls the path]], [[Tool definitions deserve as much prompt engineering as prompts]]

## Cards

START
Basic
An agent design has no test runner, no tool results fed back, and no iteration cap. What is wrong with it?
Back: It has no ground truth from the environment to check progress against, and no stopping condition. Agents need both a feedback signal each step and a way to halt.
<!--ID: 1788645191066-->
END

START
Basic
What is the most basic definition of an agent?
Back: an LLM autonomously using tools in a loop, with autonomy scaling as models improve.
<!--ID: 1788645191068-->
END

