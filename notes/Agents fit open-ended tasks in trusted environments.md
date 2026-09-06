---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, scoping, agents]
---

# Agents fit open-ended tasks in trusted environments

Reach for a full agent for open-ended problems when the number of steps cannot be predicted and there is no fixed path to hardcode. That autonomy has two costs: higher spend, since the model may run many turns, and compounding error, since one wrong step feeds the next. So agents belong where you can trust the model's judgment and contain the blast radius. The post's recommendation is heavy sandboxed testing plus guardrails before letting one loose.

Anthropic's own examples are a coding agent that resolves SWE-bench issues and the computer-use reference implementation.

Applies when: scoping whether a problem warrants an agent. Two questions: is the step count unpredictable, and can mistakes be contained?

Related: [[Agentic complexity is bought with latency and cost]], [[Agents pay off where the task is specified, actionable, and verifiable]]

## Cards

START
Basic
You're deciding whether a problem needs a full agent rather than a workflow. What two questions decide it?
Back: 1) Is the step count unpredictable, with no fixed path you could hardcode? 2) Can mistakes be contained (trusted environment, sandboxed testing, guardrails)? Both need a yes.
<!--ID: 1788645191055-->
END

START
Basic
Why do agents need sandboxed testing and guardrails more than workflows do?
Back: Errors compound. The agent chooses its own next step, so one wrong step feeds the next and the model may run many turns before anything catches it.
<!--ID: 1788645191057-->
END
