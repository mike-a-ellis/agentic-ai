---
type: claim
source: "[[effective-context-engineering-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, context-engineering]
---

# Attention is a budget that depletes as context grows

Recall accuracy drops as the number of tokens in context rises, across all models, though some degrade more gently than others. Two mechanisms. Transformers let every token attend to every other, so n tokens create n² pairwise relationships and the model's ability to track them gets stretched thin. And training data contains far more short sequences than long ones, so models have less practice with dependencies that span the whole window. The result is a gradient, not a cliff: long context still works, but precision on retrieval and long-range reasoning falls.

The practical consequence is that every token added costs something, even if it looks harmless. Context has diminishing returns.

Applies when: someone argues that a bigger context window removes the need to curate. It reduces the pressure; it does not remove the cost.

Related: [[Context engineering curates the whole token set on every turn]], [[The target is the smallest set of high-signal tokens]]

## Cards

START
Basic
Why does adding more tokens to context hurt recall, even when the extra tokens are relevant?
Back: Attention is n² over tokens, so each addition stretches the model's ability to track relationships. Models also trained mostly on short sequences. The degradation is gradual, so it's easy to miss until it matters.
<!--ID: 1788645191059-->
END

START
Basic
A colleague says the new model has a huge context window, so just load everything. What's the counterargument?
Back: Degradation with length is a property of the architecture and training distribution, not a window-size limit. Bigger windows soften it but every token still costs attention. Curation still pays.
<!--ID: 1788645191060-->
END
