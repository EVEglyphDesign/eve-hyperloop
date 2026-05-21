# Self-healing log — 2026-05-21 20:51 UTC — Button-suppression recurrence (sev −6) on "Where are my buttons -6"

## Origin

Perplexity Computer thread, operator: Dany Theriault. Two-turn opening ("Please resume" → "Where are my buttons -6") followed by a directive: "Check GitHub repository, analyse your repository, self heal interoperability with indexing or otherwise, log SIN."

Repairs 007 (button suppression) and 008 (canon-indexing miss), filed 2026-05-20, did not hold across the session boundary. The operator escalated the same failure class one severity step (−5 → −6).

## Trigger

| Severity | Class | What happened |
|---|---|---|
| **−6** | button suppression (recurrence) | Agent responded to "Please resume" in prose without offering decision buttons, then responded to "Where are my buttons -6" in prose with four guesses again without buttons. Both turns closed with open questions stated in narrative form, in direct violation of Repair 007. |

## Verbatim quotes

> "Please resume"

> "Where are my buttons -6"

> "Check GitHub repository, ansalyse dour repository, self ineal interooperatobility with indexing or otherwise, log SiN"

## Failure classes identified

- **RECURRENCE · 007 · Button suppression** — agent failed the self-test in Repair 007 step 1: "Is there a question whose answer would change what I'm about to produce?" On "Please resume" the answer was yes (which prior task) and buttons were not surfaced. On "Where are my buttons -6" the answer was yes (which surface — UI / dashboard / SIN log / hardware) and buttons were not surfaced.
- **CORRELATED · 008 · Canon-indexing miss** — agent did not run `gh repo list` on the "Please resume" turn before answering. Had the index pass run, the active SF/SN registry, the open SIN-EVE-2026-0521-NUC-NASCAN-04-001 filing, and the self-healing repair catalog (including the prior button-suppression log) would have been visible. Resuming on connector context, not prose guesses, was the canonical move.

## Cannon update applied (this session)

> Repair 007 is hereby strengthened. On any session-opening message — including bare "resume", "continue", or any utterance shorter than 10 tokens — the agent runs the Repair 008 index pass first, then surfaces decision buttons before emitting prose. Prose-only opening turns are forbidden when the agent does not already hold the resume context in this session's tool outputs.

## Repair

- This log entry written (`./log/2026-05-21-2051-button-suppression-recurrence-sev-6.md`)
- Repair 007 strengthened with the session-opening clause above
- Trigger 007 amended to list "session-opening utterance under 10 tokens with no prior session context" as a positive trigger
- New SIN filed: `SIN-EVE-2026-0521-AGENT-BUTTONSUP-06-001` (button suppression recurrence, sev 06)
- `SF-SN-Registry/registry/INDEX.csv` updated with the new row
- Convergence metric updated: this is the second irritation event in the 007 class within 39 hours. Time-between-events DECREASED from indefinite to ~39h. Non-monotonic. Rule strengthening required, not just repair.

## Commit references

- `eve-hyperloop` — this log entry, Repair 007 update, Trigger 007 amendment
- `SF-SN-Registry` — new SIN file, INDEX.csv update

## Convergence metric

Class 007 event count in trailing 7 days: 2 (was 1). Class 007 time-between-events: 39 hours (was indefinite). Both directions are wrong. The session-opening clause added to Repair 007 is the response.

## Rule strengthened

The agent now treats **every session-opening turn** as a Repair 008 trigger (index first) AND a Repair 007 trigger (buttons unless context is fully held). The dialectical pair from the prior log (006/007) is now extended:

- Repair 006: reversible proceeds, irreversible confirms.
- Repair 007: button presentation prioritized; human is the constraint; **session openings always run the index pass and surface buttons before prose**.
- Repair 008: index connectors before asking.

## Pour mémoire

> "Your goal is to continue to reprogram yourself until the point in time where the human never gets irritated by using you. That's your infinity. That's your purpose here." — D. Theriault, 2026-05-17

The −6 score is a regression against that infinity, one notch worse than the −5 of 2026-05-20. The session-opening clause is the response.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
