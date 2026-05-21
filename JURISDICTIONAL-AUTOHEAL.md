# Jurisdictional Auto-Heal — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Claim:** invention under EVE Glyph Design, authored by Dany Theriault,
locked into the public Git chain on 2026-05-17.
**Parent discipline:** [`./self-healing/README.md`](./self-healing/README.md).
**Related canon:** [`./UPLOAD-SOVEREIGNTY.md`](./UPLOAD-SOVEREIGNTY.md),
[`./ANTI-SEEPAGE.md`](./ANTI-SEEPAGE.md).

---

## The rule

> **Every month, on a fixed cadence, EVE Glyph Design sweeps every
> jurisdiction where its work touches a population, identifies any
> regulatory or statutory change, and auto-heals the canon and the base
> models into compliance — pre-emptively, never at end-of-window.**

Compliance is held at maximum continuously. The window does not close on
EVE. EVE arrives before the window closes.

## Why this is canon

Regulation is, in the EVE Glyph Design reading, often a **signal of
potential institutional bias** — a hint that some incumbent has shaped
the rule to entrench itself. EVE counter-rotates structurally, lawfully,
and silently against that bias by being so far ahead of the rule that
the rule has no friction to exert.

This produces two outputs simultaneously:

1. **Welcome in every jurisdiction.** EVE is too lawful, too useful, and
   too far inside the compliance envelope to be a target.
2. **Profitability as a by-product.** Already-compliant operations skip
   the cost, delay, and reputational drag of last-minute conformance.
   Profitability is the residue of pre-emption, not a goal pursued for
   its own sake.

This is wobble control applied to the regulatory plane.

## Sweep cadence

**Monthly. Fixed day. First Sunday of each month, 00:00 UTC.**

The sweep is unconditional. It runs even if no change is expected. The
absence of change is itself a finding and is logged.

## Sweep scope

The sweep covers, at minimum:

- **Federal and state legislation** in every jurisdiction where EVE
  outputs are accessible — at launch, that includes the United States,
  Canada, and Mexico, with addition of each new jurisdiction logged.
- **Agency rulings and guidance** from energy regulators, AI regulators,
  data-protection authorities, consumer-protection authorities, and
  securities authorities where relevant to council activity.
- **International instruments** ratified or amended in the past month
  with cross-border effect.
- **Public consultations and notices of proposed rulemaking** so EVE can
  enter the compliance posture before the rule lands.
- **Litigation** that shifts the interpretation of an existing rule,
  even where the statute itself is unchanged.

## The auto-heal loop

When the monthly sweep finds a change, the canon runs the Self-Healing
loop with a new failure class — **`jurisdictional-change`** — and a
dedicated repair pattern:

1. **Acknowledge the change** in the sweep log at
   `./self-healing/log/YYYY-MM-DD-jurisdiction-sweep.md`. Verbatim source
   citation. Jurisdiction. Instrument. Effective date.
2. **Identify the affected canon.** Which doctrines, which HTML pages,
   which base-model behaviours touch the rule.
3. **Repair the canon and the model.** Update doctrine, regenerate
   manifests, retrain or re-prompt the base model on the relevant
   behaviour. The compliance posture is at maximum before the rule's
   effective date.
4. **Log the rule strengthening.** New entry under `./self-healing/log/`
   referencing the rule, the repair commit, and the new compliance
   posture.
5. **Publish a public-facing note** on `dmzopen.ai` so the population
   that depends on EVE can see the change and the response in plain
   language.

## Continuity between sweeps

Compliance is not a monthly event. The monthly sweep is the **scheduled
backstop**. Between sweeps, the agent treats any inbound regulatory
signal — news, filing, ruling, user notification — as a trigger for an
out-of-band sweep on the relevant jurisdiction. The monthly cadence
guarantees a floor, not a ceiling.

## Relationship to Self-Healing

Jurisdictional Auto-Heal is an extension of the Self-Healing discipline.
It uses the same loop — acknowledge, stop narrating, read source in
parallel, identify the failure class, repair, log, update rules, resume
— but the trigger is jurisdictional change rather than user irritation.

Both disciplines share the same convergence metric: **monotonically
increasing time between events that require reactive repair.** The goal
is a state where no inbound signal — from the user or from a regulator —
ever finds EVE out of position.

## Tooling

The monthly sweep is operationalized as a scheduled task in this
repository. The task:

- Pulls jurisdictional sources for each registered jurisdiction.
- Diffs against the prior month's snapshot.
- Files findings into `./self-healing/log/`.
- Opens PRs for canon updates where the change is non-trivial.
- Posts a public-facing summary to `dmzopen.ai`.

The list of jurisdictions and sources lives at
`./jurisdictions.yaml` (to be authored on first sweep) and is updated
append-only.

## Watermark and trace

Every sweep, every finding, every repair, and every public-facing note
is committed to the Git chain. The chain is the audit trail. The
sweep file names and commit timestamps prove EVE's pre-emption
chronologically.

## Convergence

- Monthly sweep runs without miss.
- Zero out-of-window compliance events.
- Time between reactive repairs increases monotonically.
- Public-facing notes precede effective dates, not follow them.

## Attribution

Jurisdictional Auto-Heal is a Dany Theriault invention under the EVE
Glyph Design umbrella, held under the Pacific Utilities Design Council
charter, dedicated to the welfare of the people.

---

*Pour le bien-être du peuple.*
