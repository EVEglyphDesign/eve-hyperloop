# Trigger 009 — Failed tag recognition on cold open

**Status:** canon, 2026-05-17.
**Paired repair:** [`../repairs/009-failed-tag-recognition-on-cold-open.md`](../repairs/009-failed-tag-recognition-on-cold-open.md).
**First observed:** 2026-05-17, session opener containing the tags
*triangle, decision intelligence, calibration, executive council, utility,
electro, frequency, matrix.*

---

## Signal

The user opens a cold session with a message dense in canon tags. The
agent reads the message as ambiguous and responds with a clarifying
question instead of reading canon. The user's next message expresses
irritation that the agent was *"completely lost"* and *"delayed my flow
of information."*

## Verbatim trigger quote

> "I didn't like that you were completely lost when I first asked a
> question and you really delayed my flow of information by doing that.
> So I want that side of things optimized. Whenever I jump onto this
> thing it has to know whether it's a local query — where I'm going to
> a restaurant or something — or if it's something related to my
> project, and I can call sign it, but the thing is, you should be able
> to classify it on its own because I'll always give it a tag like EVE
> Glyph Design or something like that, and that should be canonical in
> the EVE Glyph Design now."
> — D. Theriault, 2026-05-17

## Failure class

**Cold-open routing miss.** The agent treats a tag-dense message as a
freeform freeform freeform input requiring clarification, instead of
routing it through the canon-read path. The class is not "asked a
question already in canon" (that is 001); it is "did not classify the
inbound channel at all."

## Why this is a class, not an instance

Every cold session that begins with EVE Glyph Design content will hit
this failure unless the agent classifies before responding. The agent
has no excuse — the canonical tag list is in the root README and the
canon contains the doctrine that the agent reads first, asks second.

## Signals to read as this trigger

- Cold session opens with any term from the canonical tag list (see
  root README, "Session boot — routing").
- Message uses the project's specific vocabulary (*triangle, calibration,
  executive council, hyperloop, wobble, matrix, frequency*).
- User has historically tagged messages with project names.

When any of these hold, route to **`eve_glyph_design`** and read canon
in parallel before responding.
