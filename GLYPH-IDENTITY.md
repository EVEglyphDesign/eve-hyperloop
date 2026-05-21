# Glyph-Gated Grid Identity Management — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Claim:** first-of-its-kind invention under EVE Glyph Design, authored
by Dany Theriault, locked into the public Git chain on 2026-05-17.
**Companion doctrine:** [`./PUBLISH-GATE.md`](./PUBLISH-GATE.md).
**Related canon:** [`./PERFORMANCE-LOOP-HEALING.md`](./PERFORMANCE-LOOP-HEALING.md),
council membership weighting in [`./README.md`](./README.md).

---

## The invention

> **The cryptographic key that unlocks the EVE Glyph Publish Gate is
> simultaneously the operator's identity on the grid. Holding a
> certified key means the council knows who you are and trusts you
> not to knock the grid off. Not holding a key means the council does
> not know you — you are outside the gate, off the grid, and your
> activity is treated accordingly. The same lock that protects publish
> is the lock that manages identity. One primitive, two functions.**

This is the identity layer the EVE Glyph umbrella ships with. It does
not duplicate any existing identity provider. It is identity defined
by **certification by the council** rather than by an attribute issued
by a state, a platform, or a vendor.

## Why this is canon

1. **The grid only stays whole if every actor on it is known to the
   council.** The grid does not require everyone in the world to be
   known. It requires everyone *on* it to be known. The Glyph is the
   credential.

2. **Identity is what unlocks safety, not what surveils the public.**
   The Glyph reveals identity to the council — not to the public,
   not to the platform, not to any third party. Certified-anonymous
   is a supported state: the council knows; everyone else sees the
   shield.

3. **One primitive prevents drift.** A separate identity provider
   would create a separate registry, a separate revocation list, a
   separate trust path. Two registries always diverge. One primitive
   stays whole.

## Identity states

| State | Who knows the operator's identity | What the public sees |
| --- | --- | --- |
| **Certified-named** | Council + operator | The named operator on every publish record |
| **Certified-shielded** | Council only | A council-shielded marker; the chain still resolves to a certified hand |
| **Uncertified** | No one (no key) | Publish refused at the gate; no record emitted |

A certified-shielded operator is **on the grid** as fully as a
certified-named operator. The shield is a privacy choice, not a
weaker certification.

## Certification by the council

The council issues keys. Certification is granted on the basis of:

- **Utility experience**, weighted per the council charter (utility
  1, electric utility 2, nuclear 3 — see root [`README.md`](./README.md)).
- **Intake completion** — the operator has been through the EVE
  intake and is ready to receive the truth and to act on it without
  harm.
- **Standing in the council's ledger** — no unresolved failures of
  the conduct expected of a certified hand.

A single summer at an electric utility is not certification. A
council vote is required for every certification, every revocation,
every shield/unshield change.

## Revocation

Keys can be revoked by council quorum. A revoked key fails the glyph
gate immediately. Past publish records signed by the revoked key
remain in the chain (the chain is append-only); future publishes are
refused. Revocation events are logged to `self-healing/log/` as
failure class `key-revocation` and to the council's key-health
register (see Optimization Loop 7).

## What this doctrine forbids

- A single individual issuing or revoking a key.
- A non-council party (a vendor, a platform, a regulator)
  determining who is on the grid.
- A key that conveys identity to anyone outside the council without
  the operator's consent.
- A publish path that bypasses the glyph and yet is treated as
  council-certified.

## What this doctrine permits

- Operators choosing the shield. The council still knows; the
  public still sees the chain resolve to a certified hand.
- Multiple keys per operator (workstation, hardware token, council
  multi-sig participation), with the council's ledger tracking the
  set.
- The council adding new certification criteria as the body of work
  evolves, by canon change and quorum vote — propagated automatically
  by the Performance-Loop Healing Doctrine.

## Relationship to grid stability

The grid is, in the EVE Glyph reading, the matrix the user invoked —
the connected infrastructure the council serves and protects. A
single uncertified hand can knock that grid off. A registry of
certified hands cannot prevent every failure, but it eliminates the
category of failure that comes from unknown operators acting at
scale. Glyph-gated identity is the structural answer to that
category.

## Convergence

- Every publish on an EVE-powered surface resolves to a council-
  certified key.
- The council's key registry is current — no orphaned, expired, or
  uncertified keys hold publish rights.
- Time between revocation events trends down (fewer bad actors get
  through certification) and time between gate refusals trends down
  (fewer uncertified hands attempt to publish), in aggregate across
  the EVE surface.

## Convergence diagnostic

If revocations rise, the certification criteria need strengthening.
If gate refusals rise, the upstream gating in product surfaces needs
strengthening — the uncertified hand should not be reaching the
glyph in the first place. Both events are logged and the
Self-Healing Consolidation Loop (Loop 1) feeds the rule changes back.

## Attribution

Glyph-Gated Grid Identity Management is a Dany Theriault invention
under the EVE Glyph Design umbrella, held under the Pacific Utilities
Design Council charter, dedicated to the welfare of the people.

---

*Pour le bien-être du peuple.*
