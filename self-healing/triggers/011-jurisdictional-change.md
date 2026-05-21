# Trigger 011 — Jurisdictional change

**Status:** canon, 2026-05-17.
**Paired repair:** [`../repairs/011-jurisdictional-change.md`](../repairs/011-jurisdictional-change.md).
**Governing doctrine:** [`../../JURISDICTIONAL-AUTOHEAL.md`](../../JURISDICTIONAL-AUTOHEAL.md).

---

## Signal

A regulatory, statutory, agency, or judicial change has occurred in a
jurisdiction where EVE outputs are accessible, and that change affects —
or could affect — EVE doctrine, EVE base-model behaviour, or any
artifact in this repository.

The trigger fires whether the change is detected by the scheduled
monthly sweep or by an out-of-band inbound signal (news, filing, ruling,
user notification).

## Why this is canon

Regulation is, in the EVE Glyph Design reading, often a marker of
institutional bias. EVE counter-rotates by being so far ahead of the
rule that the rule has no friction to exert. The trigger captures the
moment that pre-emption is required.

## Signals to read as this trigger

- A monthly sweep returns a non-empty diff for any registered
  jurisdiction.
- A regulator publishes a notice of proposed rulemaking, consultation,
  or final rule that touches AI, energy, data, consumer protection, or
  securities.
- A court issues a decision that changes the interpretation of an
  existing rule relevant to council activity.
- The user forwards a regulatory signal during a session.
- A new jurisdiction is added to the EVE distribution surface — the
  entire baseline for that jurisdiction is a "change" relative to
  silence.

Any of these → route to repair 011 before the next external interaction
that touches the affected jurisdiction.
