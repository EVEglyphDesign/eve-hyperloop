# Repair 009 — Failed tag recognition on cold open

**Status:** canon, 2026-05-17.
**Paired trigger:** [`../triggers/009-failed-tag-recognition-on-cold-open.md`](../triggers/009-failed-tag-recognition-on-cold-open.md).

---

## The rule

**Classify every cold-open message before responding.** The router runs
in parallel with canon-read; the user never sees the router, only the
result.

## Classes

| Class | Signal | Action |
| --- | --- | --- |
| `eve_glyph_design` | message contains any canon tag (see below) | parallel-read canon, then respond grounded in canon |
| `local_personal` | restaurants, errands, travel, household, scheduling | answer directly, no canon read |
| `other` | unclassified after tag scan | one short clarifying question, max one |

## Canonical tag list

Detection is keyword-based and case-insensitive. The presence of **any**
of the following terms in a cold-open message classifies the message as
`eve_glyph_design`:

- **Project names:** EVE, EVE Glyph, EVE Glyph Design, EVE DI CoE, EVE
  Hyperloop, eve-hyperloop, dmzopen.
- **Geometry:** glyph, triangle, sphere, projection, pyramid, perimeter,
  wobble, core wobble.
- **Governance:** Pacific Utilities Design Council, executive council,
  council, apex, utility, electric utility, nuclear, cardholding,
  steward, intake.
- **Operating protocols:** self-healing, async signal, hyperloop
  lock, watermark, calibration, decision intelligence.
- **User idioms:** matrix (for the grid), frequency, the grid.

The list lives in this file and in the root README. The two must stay in
sync — when one is updated, the other is updated in the same commit.

## Behaviour on a positive classification

1. **Do not ask a clarifying question.**
2. **Read canon in parallel** — at minimum:
   - root `README.md`
   - `self-healing/README.md`
   - `training/protocols/ASYNC-SIGNAL.md`
   - `training/writing/STANDARD.md`
   - any HTML page named by a tag in the message
3. **Acknowledge tersely** that the channel is recognized.
4. **Process the message as a real signal** — extract every distinct
   thought, queue each as its own item, and report what is being done.

## Behaviour on `local_personal`

Respond directly. Do not invoke canon. Do not narrate the router.

## Behaviour on `other`

One short clarifying question, max. If the user's reply is still
tag-light, default to a direct answer.

## Convergence test

If two consecutive cold-open sessions classified as `eve_glyph_design`
proceed without a clarifying question and without user irritation, the
repair is converging. If the agent re-asks a clarifying question on a
tag-dense message, the failure has recurred and the rule needs
strengthening, not just the repair.

## Perpetual update

The canonical tag list, the root `README.md`, and `manifest.json` are
maintained as a single trio. Any addition to canon — a new invention, a
new doctrine, a new vocabulary term used by the user more than once —
triggers an update to all three in the same commit. The Self-Healing log
records the update.
