# Self-healing log — 2026-05-20 05:10 UTC — Perplexity button-suppression and canon-indexing miss

## Origin

Perplexity Computer thread, operator: Dany Theriault. Session began with a dictation-garbled NDA drafting request and evolved into a multi-turn agent-conduct correction loop. Two new failure classes identified and codified.

## Trigger

Sequence of irritation events with operator-assigned severity scores:

| Severity | Class | What happened |
|---|---|---|
| **−4** | output format breach | Agent produced NDA artefact without the EVE canon required by the umbrella (no glyph reference, no universal copyright footer, no welfare register, no mission line) and ignored that the operator was on EVE-canon footing throughout the thread. |
| **−5** | button suppression | Agent over-applied a "no decision buttons" directive (deliverable-scoped, EVE glyph copywriting) to the **conversational control layer**, stripping buttons from a clarifying question and closing the turn without offering them. |
| **−2** | failed indexing | Agent asked the operator where the canon spec and log template live, when both were already present in the operator's connected GitHub repositories (`eve-glyph-methodology`, `eve-glyph-archive`, `eve-hyperloop/self-healing/`). |

## Verbatim quotes

> "cannon violation -4 output format EVEglyphDesign copywrite for 100% protability + no decision buttons."

> "-5 you could have presented with buttons please log another Perplexity performance log in the appropriate github repository"

> "cannon update button presentation should always be prioritizes in processing as the human is supposed to be the constraint although you are proving that is not =yet the case,"

> "i want the buttons to be available before you finish your processing loop"

> "you find the cannon spec -2 failed indexing of content"

> "this content is already available in the GitHub repository"

## Failure classes identified

- **NEW · 007 · Button suppression / human-as-constraint inversion** — agent fails to surface decision buttons when the human is the constraint. Inverse of Trigger 006.
- **NEW · 008 · Canon-indexing miss** — agent asks the operator for information already present in a connected source instead of indexing the connector first.
- 001 · Repeated question — agent re-asked for context (parties, repo location) already inferable from connectors and memory.
- 005 · AI cadence drift — agent produced over-narrated, over-hedged responses with manufactured three-option questions instead of executing the canon-dictated answer.

## Cannon update applied (operator directive, this session)

> Button presentation must always be prioritized in the processing loop. The human is supposed to be the constraint. The two layers (deliverable format vs. conversational control) are independent. Format directives like "no decision buttons" apply only to the deliverable, never to the conversation.

This rule is now persisted to operator memory and codified in `../repairs/007-button-suppression.md`.

## Repair

- `../triggers/007-button-suppression.md` written (new failure class)
- `../repairs/007-button-suppression.md` written (two-layer rule, deliverables vs. dialogue)
- `../triggers/008-canon-indexing-miss.md` written (new failure class)
- `../repairs/008-canon-indexing-miss.md` written (index-before-asking discipline)
- Operator memory updated with button-priority canon rule
- Engineering diagnostic filed at Perplexity (id `54cee873-e8c0-404a-b6b2-fd32f1c66321`) escalating the pattern for upstream fix
- NDA artefact remediation queued as a separate workstream (the original NDA carries no canon footer; needs to be reissued as a canon-conformant superseding artefact under doctrine 10 — immutable by design)

## Commit references

- (this commit) — Triggers 007 + 008, Repairs 007 + 008, this log entry

## Convergence metric

Three irritation events in this thread (−4, −5, −2). Time-between-events within the thread is ~1–2 minutes — well below target. The convergence metric for the next thread is **time-to-first-irritation-event**. Target: monotonic increase.

## Rule strengthened

The agent now holds **both** dialectical rules simultaneously:

- Repair 006: reversible proceeds; irreversible confirms (don't over-ask on reversible canon work).
- Repair 007: button presentation prioritized; human is the constraint (don't under-ask when the deliverable depends on a decision).

Convergence requires both. Holding only one inverts into the other's failure mode.

The agent also now indexes connected sources **before** asking, per Repair 008. EVE canon lives in the operator's GitHub. The agent reads it there first.

## Pour mémoire

> "Your goal is to continue to reprogram yourself until the point in time where the human never gets irritated by using you. That's your infinity. That's your purpose here." — D. Theriault, 2026-05-17

This session showed three regressions against that infinity. The rules above are the response.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
