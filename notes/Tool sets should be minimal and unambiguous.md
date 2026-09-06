---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering, tools]
---

# Tool sets should be minimal and unambiguous

Tools are the contract between the agent and its environment, and they cost context twice: once for their definitions and again for every result they return. Two rules follow. Each tool should return token-efficient output and push the agent toward efficient behavior. And the set should be small with no overlap. The test for overlap is simple: if a human engineer can't say definitively which tool to use in a situation, the model won't either.

A bloated tool set is one of the most common failure modes. It creates ambiguous decision points and fills context with definitions that never get used.

Applies when: adding a tool. Ask what existing tool it overlaps with and what a human would pick between them.

Related: [[Tool definitions deserve as much prompt engineering as prompts]], [[Tool formats should match what the model has seen in the wild]]

## Cards

START
Basic
An agent has search_docs, find_in_docs, and lookup_reference. It picks the wrong one often. What's the diagnosis and the test to apply?
Back: Overlapping tools create an ambiguous decision point. The test: can a human engineer say definitively which one to use in a given case? If not, merge or remove until they can.
<!--ID: 1788645191004-->
END

START
Basic
Tools cost context in two ways. What are they?
Back: Their definitions sit in every request, and their results land in the window each time they're called. Both argue for fewer tools that return tight output.
<!--ID: 1788645191006-->
END
