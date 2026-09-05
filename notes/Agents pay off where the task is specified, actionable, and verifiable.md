---
type: claim
source: ["[[building-effective-agents-anthropic]]", "[[managed-agents-in-production-buildmvpfast]]"]
created: 2026-09-05
tags: [agentic-sdlc, scoping, use-cases]
---

# Agents pay off where the task is specified, actionable, and verifiable

A task is a good agent candidate when four things hold. The task can be fully specified in writing before the run, including the constraints and conventions that would otherwise live in someone's head. The agent can act on it with tools, not just produce text. Success can be checked automatically, by tests, a grader, or a rubric. And there is a defined point where a human reviews the result or intervenes.

Coding and customer support are the reference domains. Coding has tests as the feedback signal, the agent iterates on failures, and a human reviews the change for fit with the wider system. Support has tools for customer data and refunds, and resolution is measurable. Scheduled headless agents do well on the same shape at smaller scale: dependency bumps, codemods, test generation, bug-to-PR pipelines. They do badly on greenfield architecture, ambiguous requirements, unwritten team conventions, and security changes that need a risk judgment. Every failure on that list is a missing property, usually the first one.

Applies when: deciding whether a business problem should be handed to an agent. If the spec cannot be written down, that is the blocker and no model choice fixes it.

Related: [[Agents fit open-ended tasks in trusted environments]], [[An agent is a tool loop grounded in environmental feedback]], [[Evaluator-optimizer needs criteria a model can apply]]

## Cards

START
Basic
A team wants to hand a task to a scheduled, headless agent. What four things do you check first?
Back: Can the task be fully specified before the run, can the agent act on it with tools, can success be checked automatically, and is there a defined point where a human reviews. If the spec can't be written down, stop there.
END

START
Basic
Headless agents handle dependency bumps and codemods well but fail on ambiguous requirements and unwritten team conventions. What property do the failures have in common?
Back: The task can't be fully specified in writing before the run. The agent has no way to resolve the ambiguity mid-task.
END

START
Basic
Coding is a reference agent domain. What supplies the feedback loop, and what still needs a human?
Back: Automated tests supply the feedback signal; the agent iterates on failures. A human still reviews whether the change fits the broader system, which tests don't check.
END
