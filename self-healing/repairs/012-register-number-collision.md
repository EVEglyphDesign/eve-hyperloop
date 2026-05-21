# Repair 012 — Register-number collision

**Status:** canon, 2026-05-21.
**Paired trigger:** [`../triggers/012-register-number-collision.md`](../triggers/012-register-number-collision.md).
**Governing doctrines:** [`../../PERFORMANCE-LOOP-HEALING.md`](../../PERFORMANCE-LOOP-HEALING.md),
[`../../ANTI-SEEPAGE.md`](../../ANTI-SEEPAGE.md).

---

## The rule

> **Before reserving a number for a new trigger/repair pair, fetch the
> remote, list the highest occupied slot across triggers and repairs,
> and reserve the next slot above that. Numbers are append-only on the
> chain; once committed they are never re-used.**

## Behaviour on detection

When a session is about to author a new trigger/repair pair:

1. **Fetch remote.** `git fetch origin main`.
2. **Read the live register.** Enumerate
   `self-healing/triggers/NNN-*.md` and
   `self-healing/repairs/NNN-*.md` on `origin/main`.
3. **Compute the next slot.** `next = max(NNN) + 1` across both
   directories combined.
4. **Reserve only after fetch is current.** If the fetch is older
   than 5 minutes when the pair is about to commit, re-fetch and
   recompute.
5. **Push immediately after commit.** Hold time between commit and
   push is the collision window; close it.
6. **On rejected push:** treat the rejection as trigger 012 firing.
   Fetch, re-renumber the local pair to the new next slot, rewrite
   internal cross-references, audit, and retry.

## Behaviour on a detected collision at push time

1. **Do not force.** A force-push destroys canonical record. The
   remote pair is canon — it was committed in good faith by another
   council-authorized session.
2. **Renumber local.** Shift the local pair to the new
   next-available slot.
3. **Rewrite internal cross-links.** Every reference to the old
   number in the local bundle (paths, headings, body prose) is
   rewritten in the same commit.
4. **Re-run the pre-push audit.** Anti-seepage scan, link audit,
   number-uniqueness check.
5. **Retry the push.** Single atomic commit per the edit discipline.

## Mechanical enforcement

After this repair lands, the Optimization Loop set is extended:

- **Loop 3 (Anti-Seepage Sweep)** gains a sibling check —
  **register-number uniqueness** — that verifies no two files share a
  numeric prefix in the trigger/repair register. A duplicate fails
  the CI gate.
- **Loop 1 (Self-Healing Consolidation)** treats every trigger 012
  event as a high-priority entry, surfacing the recurrence rate
  directly in the weekly digest.

## Why mechanical enforcement is required

Trigger 008's recurrence today taught the canon that vigilance is
insufficient. The same lesson applies here. The CI check that
verifies number uniqueness moves the rule out of "the agent
remembered to fetch" and into the build pipeline.

## Convergence test

- Zero rejected pushes from numeric collision.
- Zero pairs sharing a numeric prefix at any time.
- The register's numeric sequence is strictly monotonic on the chain
  with no reuse of retired numbers.

## Perpetual update

The collision-prevention rule lives alongside the other registers
(`prohibited-terms.md`, `analogy-register.md`) as part of the
canonical update set. Any change to the numbering discipline
triggers a review of all three in the same commit.
