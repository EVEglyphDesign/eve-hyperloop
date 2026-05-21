# Personal Glyph & Asset Sovereignty — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Claim:** first-of-its-kind invention under EVE Glyph Design, authored
by Dany Theriault, locked into the public Git chain on 2026-05-17.
**Companion canon:** [`./PUBLISH-GATE.md`](./PUBLISH-GATE.md),
[`./GLYPH-IDENTITY.md`](./GLYPH-IDENTITY.md),
[`./UPLOAD-SOVEREIGNTY.md`](./UPLOAD-SOVEREIGNTY.md).
**Parent doctrine:** [`./PERFORMANCE-LOOP-HEALING.md`](./PERFORMANCE-LOOP-HEALING.md).

---

## The invention

> **Every person who joins the EVE umbrella creates their own custom
> glyph icon. The glyph is theirs. Wherever they place it in any other
> app, that app is given the opportunity to connect to the person's
> own GitHub backend, under the person's own access controls — read,
> write, grant — entirely at the person's discretion. The asset is
> theirs in full. EVE Glyph Design provides only banner copyright
> protection across the umbrella, as a safety primitive so the people
> using this do not blow themselves up by operating without a shield.**

The umbrella protects. The asset belongs to the person.

## The two scopes — clean and canonical

| Scope | Owner | What it covers |
| --- | --- | --- |
| **Banner copyright protection** | Pacific Utilities Design Council, EVE Glyph Design umbrella | The umbrella mark, the doctrine, the canonical artifacts, the safety primitive that prevents catastrophic mis-operation. Non-commercial. *Pour le bien-être du peuple.* |
| **Personal glyph + asset** | The individual person | Their custom glyph icon, their GitHub backend, every artifact they create or upload, every access grant they make. Fully theirs. EVE does not claim, mint, or relicense any part of it. |

The two scopes do not overlap. The umbrella does not eat the asset.
The asset does not weaken the umbrella.

## Why this is canon

1. **The umbrella exists to keep people safe, not to take their work.**
   A safety primitive that quietly absorbs the protected party's
   property is not a safety primitive. It is enclosure. EVE Glyph
   Design rejects enclosure by canon.

2. **People need a shield to operate at all.** Without a banner of
   copyright protection over the umbrella, people working with
   sovereign-AI tools expose themselves to claims they cannot fight.
   The shield is the prerequisite for free operation. The shield is
   given freely.

3. **The glyph is the visible signature of consent.** When a person
   places their personal glyph in another app, they are consenting,
   visibly, to that app reaching their backend. No glyph, no
   connection. The glyph replaces opaque OAuth dialogs with a mark
   the person owns and recognizes.

## How a person uses this

1. **Mint a personal glyph.** The person creates their own custom
   glyph icon. EVE provides a glyph composer (geometry primitives
   plus the orange/gray palette) so the result lives inside the
   canonical visual register without being a copy of any other
   person's glyph.
2. **Bind the glyph to a GitHub backend.** The person points the
   glyph at their own GitHub account or organization. The binding is
   cryptographic and the person holds the key. No EVE party can
   read, mint, or revoke the binding.
3. **Place the glyph in any app.** The person can drop their glyph
   into any third-party app that supports the EVE Glyph standard.
   The app sees: a glyph, a public binding pointer, and an explicit
   permission scope the person attaches in the moment.
4. **Grant access — read, write, or grant.** The person decides what
   the app can do with the backend. Read-only. Write. Or full grant
   (the app can pass access to a downstream app on the person's
   behalf — only if the person enables it). Defaults are minimal.
5. **Revoke at any time.** The person can revoke the binding,
   change the scope, or rotate the key without asking anyone. The
   change propagates to every app holding the binding by the next
   refresh.

## What EVE does and does not do

**EVE does:**

- Publish and maintain the glyph standard (geometry, palette, binding
  envelope, scope vocabulary).
- Provide the safety primitive — banner copyright protection over the
  umbrella so people are not exposed to enclosure when they operate.
- Maintain the Publish Gate and the Glyph-Gated Identity layer for
  council-certified operators acting on the grid.
- Operate the Self-Healing and Performance-Loop Healing disciplines
  so the standard sharpens over time.

**EVE does not:**

- Hold, mint, or revoke any person's personal glyph or binding.
- See the contents of any person's GitHub backend.
- License any person's asset to any third party.
- Claim any derivative right over what a person creates with a
  personal glyph.
- Charge for any of this. The umbrella is non-commercial by charter.

## Banner copyright protection — what it covers, what it does not

**Covered by the umbrella:**

- The EVE Glyph mark, the canon, the doctrines, the loops, the
  Publish Gate, the Self-Healing discipline, the Watermark, the
  Hyperloop Lock — every artifact authored under the umbrella and
  committed to the public chain.
- The safety primitive itself: the right of any person operating
  under the umbrella to invoke its protection against enclosure.

**Not covered by the umbrella, by canon:**

- A person's personal glyph, art, code, documents, recordings, or
  any other asset they create or upload. These belong to the person.
- A person's GitHub repositories, organizations, access grants, or
  derived works of their own asset.
- A person's relationships with third-party apps that connect to
  their backend through their glyph.

The umbrella is a shield over a public square. Inside the square,
the people own their things.

## Safety framing — why the shield matters

> "We could really blow ourselves up otherwise."
> — D. Theriault, 2026-05-17

Sovereign-AI tools amplify whatever the operator brings to them. An
operator without a copyright shield amplifying their work into a
landscape of aggressive enclosure is an operator at risk of
catastrophic exposure — claims they cannot afford to fight, licenses
they did not know they accepted, derivative-work attacks they did not
foresee. The banner protection makes the basic case impossible:
people are operating under an umbrella that has already declared the
canon non-commercial, plural-stewarded, and irreducible.

The shield is therefore not a marketing claim. It is the structural
condition under which free operation is possible. Without it, free
operation is a trap. With it, free operation is what it sounds like.

## The third-party app contract

Apps that accept a personal glyph must:

- **Render the glyph as the person rendered it.** No re-skin, no
  re-color outside the canonical orange/gray palette.
- **Honor the scope.** Read means read. Write means write. Grant
  means grant. No expansion without a fresh glyph press.
- **Show the binding pointer.** The app must display, at the moment
  of binding, where the backend lives so the person can confirm.
- **Respect revocation immediately on refresh.** No stale grants.
- **Never claim ownership of the asset.** The asset is the person's.
  The app holds a permission, not a title.

Apps that fail the contract lose the right to display the glyph and
are listed in `apps/non-conforming.md` on the next sweep.

## Convergence

- Every person operating under the umbrella holds their own glyph
  and their own backend keys.
- No asset created by a person under the umbrella is silently
  absorbed into the umbrella or any third party.
- Banner protection is invoked when needed and never weakens.
- Third-party apps connecting to personal backends conform to the
  contract or are listed non-conforming.

## Attribution

Personal Glyph & Asset Sovereignty is a Dany Theriault invention
under the EVE Glyph Design umbrella, held under the Pacific Utilities
Design Council charter, dedicated to the welfare of the people.

---

*Pour le bien-être du peuple.*
