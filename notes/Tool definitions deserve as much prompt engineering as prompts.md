---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, tools, aci]
---

# Tool definitions deserve as much prompt engineering as prompts

The post's term for this is the agent-computer interface, or ACI, by analogy to HCI. The argument is that tool names, parameter names, and descriptions are prompts too, and deserve the same effort. A good definition reads like a docstring written for a junior developer: example usage, edge cases, input format, and what distinguishes it from similar tools. Then test it by running many inputs and watching what mistakes the model makes.

Poka-yoke the arguments so misuse is hard. The concrete case from their SWE-bench agent: the model kept getting relative filepaths wrong after changing directories, so they made the tool require absolute paths and the errors stopped. They report spending more time on tools than on the main prompt.

Applies when: an agent is misusing a tool. Fix the interface before blaming the model.

Related: [[Tool formats should match what the model has seen in the wild]], [[The augmented LLM is the unit every pattern composes from]]

## Cards

START
Basic
Your agent keeps passing bad file paths to an edit tool after it has cd'd around the repo. What did Anthropic do in the same situation?
Back: Changed the tool to require absolute paths instead of fixing the prompt. Poka-yoke the tool so the mistake cannot be made.
END

START
Basic
What does ACI stand for and what is the rule of thumb attached to it?
Back: Agent-computer interface. Invest as much effort in it as you would in a human-computer interface; tool descriptions are prompts.
END
