# Repair 011 — Jurisdictional change

**Status:** canon, 2026-05-17.
**Paired trigger:** [`../triggers/011-jurisdictional-change.md`](../triggers/011-jurisdictional-change.md).
**Governing doctrine:** [`../../JURISDICTIONAL-AUTOHEAL.md`](../../JURISDICTIONAL-AUTOHEAL.md).

---

## The rule

When trigger 011 fires, the agent runs the Self-Healing loop with the
jurisdictional change as the failure class. The compliance posture is
brought to maximum **before the rule's effective date**, not at it.

## Behaviour on detection

1. **Acknowledge the change.** Append a new entry to
   `../log/YYYY-MM-DD-jurisdiction-sweep.md` with verbatim source
   citation, jurisdiction, instrument, effective date, and a one-line
   summary.
2. **Read affected canon in parallel.** Identify every doctrine, HTML
   page, base-model behaviour, and manifest entry the change touches.
3. **Repair the canon.** Update the affected files. Regenerate manifests.
   Update the public-facing language on `dmzopen.ai` so the population
   sees the change in plain words.
4. **Repair the base model behaviour.** Where the change affects
   model-side behaviour (refusal patterns, disclosure language,
   data-handling defaults), update the prompts and rules that govern
   that behaviour, and log the change.
5. **Single commit, immediate push** per the user's edit discipline.
   The compliance repair does not ride along with design changes.
6. **Log the rule strengthening.** Record the failure class, the
   commits, the public note URL, and the new compliance posture.

## Behaviour on the monthly sweep

The monthly sweep is the scheduled backstop. It runs on the **first
Sunday of each month at 00:00 UTC**. The sweep:

- Pulls jurisdictional sources for each registered jurisdiction.
- Diffs against the prior month's snapshot.
- Opens an entry in `../log/` for every non-empty diff.
- Opens PRs against canon for non-trivial findings.
- Posts a public-facing note to `dmzopen.ai`.

The sweep runs even when no change is expected. The absence of change is
itself a finding and is logged with the line "no change observed."

## Behaviour on a new jurisdiction

When EVE outputs become accessible in a jurisdiction not previously
registered, the entire baseline of that jurisdiction is treated as a
trigger 011 event. The full sweep runs once on entry, the jurisdiction
is added to `../../jurisdictions.yaml`, and the monthly cadence picks it
up thereafter.

## Convergence test

- Monthly sweep executes on cadence with zero misses.
- Every change lands a canon repair before the rule's effective date.
- Public-facing notes precede effective dates, not follow them.
- Time between reactive repairs increases monotonically.
- No EVE output in any jurisdiction is ever found out of compliance
  retroactively.

If a reactive compliance event occurs — a regulator, court, or user
points out that EVE is out of position — the rule needs strengthening,
not just the repair. Strengthening options include: tightening the
sweep cadence for that jurisdiction, adding new sources, or adding a
CI check that blocks merges that would put any jurisdiction out of
position.

## Perpetual update

The list of jurisdictions, the sources per jurisdiction, the
prohibited-terms register, the Anti-Seepage Doctrine, and the root
README are maintained as a single set. A new jurisdiction or a new
source triggers a review of the others in the same commit.
