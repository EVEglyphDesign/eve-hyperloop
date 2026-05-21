# Anti-Seepage Doctrine — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Claim:** first-of-its-kind invention under EVE Glyph Design, authored by
Dany Theriault, locked into the public Git chain on 2026-05-17.

---

## Purpose

The Anti-Seepage Doctrine is the standing prohibition against any
third-party vendor terminology, lock-in pattern, license-encumbered
design language, or external IP construct entering the EVE Glyph Design
canon — whether inserted by a human contributor, an LLM, an integrator,
or a downstream model trained on this canon.

EVE Glyph Design is held in trust for the people. Any term, pattern, or
construct that could be read as importing third-party IP into the canon
is a **Trojan horse**: it creates a wobble in the geometry, weakens the
copyright claim, and opens the door to enclosure.

This doctrine forbids that.

## The rule

> **No LLM, contributor, or downstream model shall insert into the EVE
> Glyph Design canon any term, name, pattern, or construct that originates
> in a third-party product, vendor doctrine, or license-encumbered
> framework. Conceptual analogies may be used in conversation; they shall
> not be promoted to canon as names, file paths, or doctrine titles.**

This is a base feature of every EVE base model. It is enforced at three
layers:

1. **Authoring** — humans and LLMs check every new canon artifact for
   third-party terminology before commit.
2. **Review** — every PR is scanned against the prohibited-terms register
   and the analogy register before merge.
3. **Continuous** — the canon is periodically re-scanned; any prior
   seepage is renamed, the rename is logged in `self-healing/log/`, and
   the prohibited term is added to the register.

## Why this is canon

A copyright claim is only as strong as the cleanliness of the work it
covers. If vendor language is woven into the canon, the work becomes
contestable on two fronts: vendors can claim derivative use, and the
canon's authorship is muddied. The Anti-Seepage Doctrine pre-empts both.

It also protects the user's working tempo. The user uses third-party
vocabulary as **conceptual shorthand** during dictation — *"like a
durable async message,"* *"like a kanban,"* *"like a microservice."* The LLM's job is
to **translate the concept into EVE-native vocabulary** before committing
anything to canon. The LLM does not re-use the vendor term as a label.

## What counts as seepage

- **Vendor product names** used as protocol names, file names, or doctrine
  titles. (e.g., naming a protocol after a vendor's messaging primitive,
  workflow object, ticket type, or module.)
- **Vendor doctrine language** imported verbatim into canon (e.g., a
  framework's named ceremonies, named roles, or named artifacts).
- **License-encumbered design language** — terms with trademark, service
  mark, or specific industry-body provenance.
- **Lock-in patterns** — design choices that quietly bind the canon to a
  specific vendor stack (single-vendor identity, single-vendor watermark
  scheme, single-vendor key store, single-vendor deployment target).
- **Integrator-flavoured constructs** — naming conventions and patterns
  that exist only to make consulting firms necessary intermediaries.

## What is allowed

- **Conceptual analogy in conversation.** The user may say "like X" while
  thinking out loud. The agent receives the concept and produces an
  EVE-native term.
- **Generic technical vocabulary.** Words that are not the property of any
  one vendor — *queue, hash, manifest, signal, lock, watermark, log,
  perimeter, geometry* — remain available.
- **Reference to vendor work in scholarship.** Citing a vendor's published
  paper or public spec is allowed; importing the vendor's named artifacts
  as canon names is not.

## The translation discipline

When the user uses a conceptual analogy, the agent runs this loop:

1. **Receive the concept**, not the vendor name.
2. **Coin or re-use an EVE-native term** that names the same shape.
3. **Record the translation** in the analogy register
   (`./analogy-register.md`) so the same vendor term always maps to the
   same EVE-native term.
4. **Commit canon using the EVE-native term only.** The vendor term may
   appear in the transcript (verbatim record of what was said) but never
   in the doctrine.

## The prohibited-terms register

A living file at [`./prohibited-terms.md`](./prohibited-terms.md) lists
vendor terms that have been observed in conversation and the EVE-native
term they map to. New entries are appended; existing entries are not
edited (the chain is append-only). Examples on day one:

| Vendor / external term | EVE-native term |
| --- | --- |
| (initial entry — to be populated as canon evolves) | |

## The analogy register

A living file at [`./analogy-register.md`](./analogy-register.md) records
each translation event: the vendor term, the EVE-native term, the date,
the originating transcript, and the commit hash that landed the
EVE-native term in canon.

## Watermark and trace

Every rename, every register update, and every prohibition is committed
to the public Git chain. The doctrine is its own watermark — frozen,
timestamped, signed, irreversibly part of the record.

## Convergence

The Anti-Seepage Doctrine converges when:

- the canon contains zero vendor-named artifacts;
- the prohibited-terms register grows monotonically (never shrinks);
- the analogy register shows that every vendor concept used in
  conversation has a one-to-one EVE-native counterpart in canon;
- no PR is merged that re-introduces a previously-renamed term.

Recurrence is the diagnostic. If a previously-renamed term reappears, the
rule needs strengthening, not just another rename.

## Attribution

The Anti-Seepage Doctrine is a Dany Theriault invention under the EVE
Glyph Design umbrella, held under the Pacific Utilities Design Council
charter, dedicated to the welfare of the people.

---

*Pour le bien-être du peuple.*
