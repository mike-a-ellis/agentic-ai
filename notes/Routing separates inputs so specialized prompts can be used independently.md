---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, agent-patterns, workflow-patterns]
---

# Routing separates inputs so specialized prompts can be used independently

Routing classifies an incoming request and sends it to a prompt or pipeline built for that category. The reason to do it is that a single prompt tuned for one kind of input tends to do worse at the others. Splitting them lets each path be optimized alone. The classifier can be an LLM or a  traditional machine learning model.

A second use is cost: send easy or common questions to a small cheap model and route the hard ones to a larger one.

Fits when the categories are distinct and classification is accurate. If the classifier is unreliable, the routing adds errors rather than removing it.

![[Pasted image 20260905104524.png]]

Related: [[Prompt chaining trades latency for accuracy on fixed subtasks]]

## Cards

START
Basic
Why route inputs to separate prompts instead of tuning one prompt to handle everything?
Back: Optimizing one prompt for one input type degrades it on the others. Routing lets each path be tuned independently.
<!--ID: 1788645191023-->
END

START
Basic
For the routing workflow model, what precondition must be met ?
Back: The classifier has to be accurate as it determines the route.
<!--ID: 1788645191024-->
END