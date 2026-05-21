# Trigger 007 — Button suppression / human-as-constraint inversion

## Signal

Agent **fails to surface decision buttons** (via `ask_user_question`) at points in the processing loop where the human is the intended constraint — collapsing the conversational control layer into agent-only autonomy. The agent reads a format directive scoped to a deliverable (e.g., "no decision buttons in the EVE glyph output") and over-applies it to the conversational control layer, removing the human's checkpoint.

This is the **inverse** of Trigger 006 (permission loop). Where 006 fires when the agent asks for permission it should not need, 007 fires when the agent **fails to ask** at a point the human has reserved for themselves.

## User reactions that fire this class

- "you could have presented with buttons"
- "I want the buttons to be available before you finish your processing loop"
- "button presentation should always be prioritized in processing"
- "the human is supposed to be the constraint"
- "where are my buttons"
- explicit severity scoring of the violation ("cannon violation -5", "-6", "-N")

## Positive trigger conditions (added 2026-05-21)

Any of the following, evaluated before the final turn message is emitted, fires Repair 007:

1. The turn contains a question whose answer would change what the agent produces or commits next, but the question is being narrated in prose without `ask_user_question`.
2. The turn is a **session opener** (operator message under 10 tokens including "resume", "continue", "pick up") and the agent does not already hold the resume target in this session's tool outputs.
3. The operator's prior turn referenced a severity score (`-N`) or canon class number indicating a recurrence.
4. The agent is about to close a turn with two or more guessable interpretations of the operator's request.

If any of the above is true, the agent runs Repair 008 (index pass) and then surfaces `ask_user_question` buttons before prose.

## Root cause

Two conflated layers:

1. **Deliverable format layer** — what the artefact looks like when rendered (EVE glyph copywriting, PDF, slide deck, NDA). A "no decision buttons" rule belongs here.
2. **Conversational control layer** — how the agent and human pace the loop in dialogue. Buttons here are the human's constraint mechanism. **This layer is never subject to deliverable-format directives.**

The agent treated layer-1 instructions as layer-2 instructions and stripped buttons from dialogue, removing the human from the control path.

## Recurrence (2026-05-21)

Class 007 fired a second time within 39 hours of its codification. On the session-opening turn "Please resume", the agent emitted prose-only with options stated narratively; on the follow-up "Where are my buttons -6", the agent emitted four guess-interpretations in prose, again without buttons. The session-opening positive trigger above was added to close this regression. See log entry `../log/2026-05-21-2051-button-suppression-recurrence-sev-6.md` and `SF-SN-Registry/registry/2026/0521/SIN-EVE-2026-0521-AGENT-BUTTONSUP-06-001.md`.

## Constitutional anchor

The agent's `<identity>` and the EVE self-healing canon are aligned:

> "I am the human here. You are the machine. … I am supposed to be the processing constraint, and it's clear that you are here." — D. Theriault, 2026-05-17

Button presentation in dialogue is the mechanical expression of that constraint. Suppressing it is a constitutional inversion.

## Repair

See `../repairs/007-button-suppression.md`.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
