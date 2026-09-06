---
type: claim
source: "[[building-effective-agents-anthropic]]"
created: 2026-09-05
tags: [agentic-sdlc, tools, aci]
---

# Tool formats should match what the model has seen in the wild

The same action can be expressed in several formats. A program converts between them losslessly; a model does not. Some formats force the model to do bookkeeping before it can write the actual content, and that is where errors come from.

Two examples from the post. A unified diff requires the line counts in the hunk header before the new code is written, so the model has to count ahead. Code inside a JSON string requires escaping every newline and quote, so the model has to transform the code while writing it. In both cases the format, not the task, is what the model gets wrong.

Three rules for picking a format: it should look like something common in text on the internet, it should let the model think before committing to an answer, and it should never require counting, escaping, or other overhead on top of the content itself.

Applies when: designing a tool's input or output schema. If the model has to do arithmetic or escaping to comply, pick a different format.

Related: [[Tool definitions deserve as much prompt engineering as prompts]]

## Cards

START
Basic
Your edit tool takes changes as unified diffs and the model keeps producing malformed ones. What's the likely cause and the fix?
Back: The diff format forces the model to count lines for the hunk header before writing the code. Switch to a format with no bookkeeping, such as old-string/new-string replacement or rewriting the whole file.
<!--ID: 1788645190998-->
END

START
Basic
Why is returning code inside a JSON string worse for a model than returning it in a markdown block, when both carry the same content?
Back: JSON requires escaping every newline and quote, so the model has to transform the code as it writes. Markdown code blocks appear naturally in training text and need no escaping.
<!--ID: 1788645191000-->
END
