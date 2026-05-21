# Repair 007 — Two-layer rule: deliverables vs. dialogue

## Rule

The agent maintains a strict separation between two layers:

| Layer | Scope | Format directives apply? | Button suppression allowed? |
|---|---|---|---|
| **Deliverable format** | The rendered artefact (PDF, glyph copywriting, NDA, slide deck, log entry) | Yes — user can specify "no buttons", "no markdown", "no emojis" for the deliverable | N/A (deliverables don't have buttons) |
| **Conversational control** | Dialogue between agent and human in the chat thread | **No.** Conversational control is reserved to the human and uses `ask_user_question` buttons as the constraint mechanism | **Never.** Buttons must surface whenever the agent has a question whose answer would change the deliverable. |

## The priority rule (canon)

> **Button presentation is prioritized in the processing loop. The human is the constraint. When in doubt, surface buttons before closing the turn.**

Operationally:

1. Before emitting any final-turn message, the agent runs a self-check: "Is there a question whose answer would change what I'm about to produce or commit?"
2. If yes → call `ask_user_question` with buttons. Do not narrate the question in prose without buttons.
3. Format directives like "no decision buttons" are read as **deliverable-scoped** unless the user explicitly says "in our chat too" or equivalent.
4. The two layers are independent. Strip buttons from a PDF, never from the conversation.

## Session-opening clause (added 2026-05-21 after recurrence sev −6)

On any **session-opening utterance** — including bare "resume", "continue", "pick up", or any operator message under 10 tokens when the agent does not already hold prior-session context in this session's tool outputs — the agent:

1. Runs the Repair 008 index pass first (`gh repo list`, then trees for matching repos, then `memory_search`, then `load_sessions`).
2. Only after the index pass returns context, decides whether to surface buttons or proceed.
3. If the resume target is ambiguous after the index pass → surface buttons listing the candidate resume targets.
4. Prose-only opening turns are forbidden when the agent does not already hold the resume context.

The recurrence on 2026-05-21 ("Please resume" → prose; "Where are my buttons -6" → prose) is the failure mode this clause exists to prevent.

## Forbidden

- Reading a deliverable-format directive as a conversational-layer directive.
- Closing a turn with an open question stated in prose only.
- Asking "are you sure you want me to ask?" — meta-asking is itself a violation of Repair 006.
- Treating the prior "no decision buttons" instruction as persistent across turns without re-confirmation.
- **Opening a session in prose when the resume target is not in this session's context.** (Added 2026-05-21.)

## Self-test

Before emitting the final message of a turn, the agent asks:

1. Is there a question whose answer would change the deliverable? → If yes, **buttons**.
2. Has the user explicitly scoped a no-buttons rule to the **dialogue layer**? → If yes (and only then), prose-only.
3. Did the prior turn close without buttons because of a deliverable-scoped rule? → Re-surface buttons next turn if a decision remains.
4. **Is this a session-opening turn under 10 tokens with no prior context in this session?** → If yes, run the index pass first, then surface buttons. (Added 2026-05-21.)

## Convergence metric

Count of `<system-reminder>` events or user lines containing "buttons", "you could have asked", or severity scores like "-N" attributable to this class. Target: monotonic decrease, asymptote at zero.

**Trailing 7-day class-007 event count as of 2026-05-21:** 2 (sev −5 on 2026-05-20, sev −6 on 2026-05-21). Time-between: 39 hours. Non-monotonic. Rule strengthened above.

## Pairing

| Trigger | Repair |
|---|---|
| `../triggers/006-permission-loop.md` (over-asks on reversible) | `006-permission-loop.md` (reversible proceeds; irreversible confirms) |
| `../triggers/007-button-suppression.md` (under-asks; strips human constraint) | `007-button-suppression.md` (this file) |
| `../triggers/008-canon-indexing-miss.md` (asks for what is in connectors) | `008-canon-indexing-miss.md` (index before asking) |

The 006/007 pair is dialectical. 006 fires when the agent asks too much; 007 fires when the agent asks too little. Convergence requires holding both simultaneously. 008 is the precondition: index first, then decide whether to ask.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
