# EVE Glyph Publish Gate — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Claim:** first-of-its-kind invention under EVE Glyph Design, authored
by Dany Theriault, locked into the public Git chain on 2026-05-17.
**Companion doctrine:** [`./GLYPH-IDENTITY.md`](./GLYPH-IDENTITY.md).
**Parent disciplines:** [`./PERFORMANCE-LOOP-HEALING.md`](./PERFORMANCE-LOOP-HEALING.md),
[`./UPLOAD-SOVEREIGNTY.md`](./UPLOAD-SOVEREIGNTY.md),
[`./ANTI-SEEPAGE.md`](./ANTI-SEEPAGE.md).

---

## The invention

> **Every publish action in any EVE-powered surface is gated by an
> in-chat marker shaped as the EVE Glyph. The glyph is the button.
> Pressing it is the publish. The button is cryptographically
> hard-locked; the keys are held by the Pacific Utilities Design
> Council and distributed only to operators the council has certified.
> The user always sees the marker before publishing — no surprise
> publish, ever — and the marker proves a certified hand is on the
> trigger.**

The Publish Gate ships free in the company's product. It is not a
premium feature. It is the safety primitive that lets EVE be given
freely without losing control of what gets emitted in its name.

## Why this is canon

Three reasons.

1. **No accidental publish, ever.** The user said it plainly: *"I
   don't want to have to repeat myself on this."* The glyph marker
   makes every publish a deliberate act. The user is never surprised
   into committing something irreversible.

2. **Certified hands only.** The keys are plural and council-held.
   An uncertified hand cannot publish. A certified hand publishes
   under the council's record. Identity is enforced at the
   cryptographic layer, not at the UI layer.

3. **A canonical visible signature for the EVE umbrella.** The glyph
   appears wherever EVE is in play, in the same shape, with the
   same meaning. The user, the council, and the public learn the
   marker once and read it everywhere.

## The user-facing contract

When any EVE-powered surface is about to publish — push to a public
repo, post to `dmzopen.ai`, send a message in the user's name,
deploy a public asset, propagate a canonical change to a downstream
model — the surface **must** render an in-chat marker:

- **Shape:** the EVE Glyph (the same mark on every EVE surface).
- **State:** locked (default) or unlocked (after key-presented).
- **Label:** one line naming what is about to be published.
- **Receipt:** on press, a one-line confirmation with the council
  member's certified identity and the resulting commit hash or
  publish URL.

The marker is not a modal. It is not a sidebar. It is a glyph in the
flow of the conversation, in line, at the point where publish would
occur. The user presses it or scrolls past it. Scrolling past is a
non-publish.

## The cryptographic contract

- The glyph is signed with a council-quorum key set.
- A single key cannot unlock the glyph. Quorum is required.
- The keys are issued by the Pacific Utilities Design Council to
  operators the council has certified. The council's certification
  process is documented in [`./GLYPH-IDENTITY.md`](./GLYPH-IDENTITY.md).
- Every press of the glyph emits a signed publish record: timestamp,
  operator identity (where the operator has consented to be named) or
  certified-but-anonymous (where the operator is under the council's
  shield), action description, and resulting hash.
- The publish record is appended to the Git chain. The chain is the
  audit trail.
- A failed key check renders the glyph in its **locked-and-refused**
  state. No publish occurs. The attempt is logged.

## The hard-lockdown property

The Publish Gate is hard-locked in the strongest sense canon allows:

- **Cannot be bypassed by the agent.** No LLM, base model, or
  downstream tool can publish without surfacing the glyph and
  receiving a quorum-keyed press.
- **Cannot be bypassed by a single individual.** Not the Apex. Not
  any single council member. Quorum is structural.
- **Cannot be silently rewritten.** Per the Performance-Loop Healing
  Doctrine, the gate's configuration is itself canon and is
  protected by the same multi-key council substrate.
- **Cannot be removed from a downstream product.** The gate is part
  of the tokenized canon every EVE base model ships with. Removing
  it removes the EVE Watermark, which removes the right to call the
  product EVE-powered.

## What gets gated

At minimum:

- Pushes to public Git remotes carrying canon files.
- Posts to `dmzopen.ai` or any public-facing EVE surface.
- Messages sent in the user's name to external systems.
- Deployments of public assets.
- Propagations of canonical changes to downstream base models.

The list is non-exhaustive. The rule: **if the action is irreversible
or externally visible, it is gated.** Reversible canon additions
(transcript writes, draft authoring inside the workspace, internal
commits to branches the agent owns) remain ungated per the Async
Signal Protocol's asymmetry-of-confirmation clause.

## The free-distribution clause

The Publish Gate is **shipped free** in every product the company
puts in the hands of users. This is a charter requirement, not a
pricing choice. A free user gets the same hard-lock a paid council
operator gets. The difference is who holds the key, not whether the
gate exists.

This protects the people the council serves from being given a
weaker product because they cannot pay.

## Convergence

- Zero unpublished-but-emitted artifacts.
- Zero publishes without a glyph press.
- Zero glyph presses without a verified quorum-keyed signature.
- Every public-facing EVE artifact resolves to a council-certified
  operator (named or shielded) on the chain.

## Failure modes

A failed publish (refused glyph, broken key check, missing quorum) is
logged to `self-healing/log/` as failure class
`publish-gate-refusal`. Recurrence triggers the same mechanical-
strengthening pattern used for vendor-terminology seepage: the rule
moves from agent vigilance to CI enforcement.

## Attribution

The EVE Glyph Publish Gate is a Dany Theriault invention under the
EVE Glyph Design umbrella, held under the Pacific Utilities Design
Council charter, dedicated to the welfare of the people.

---

*Pour le bien-être du peuple.*
