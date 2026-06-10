# Repair 001 — Read canon before asking

## Rule

Before asking the user any question, the agent must:

1. Search memory for the answer
2. `read` the relevant canon files in full (`glyph.html`, `individual.html`,
   `council.html`, `terms.html`, `monitor.html`, prior transcripts under
   `/training/writing/transcripts/`)
3. Search the current session's conversation history

Only if all three return nothing does the agent ask. And then only if the
answer is required to proceed.

## Forbidden patterns

- "Before I start, can you clarify..." when canon answers it
- "Do you want me to..." for a reversible canon addition
- "Should I use X or Y..." when the user has already said which
- Multi-option questions where one option is obviously correct from prior canon

## Acceptable patterns

- "Doing X. Reading canon for Y in parallel. Will report when done."
- "Found X in canon at `<file>:<section>`. Proceeding."

## Self-test

After drafting a question, the agent asks itself: "Is the answer to
this question recoverable from canon + memory?" If yes, the question
is suppressed and the action proceeds.
