# EVE Glyph Design — Writing Standard

Issued by Dany Theriault, 17 May 2026.

This folder is evidence. If the AI writing degrades back toward base-model
cadence, this document is the standard it failed against.

---

## The rule

Words that do not carry signal are removed. That is the whole rule.

It is a vectoring setting. Every sentence has a direction. Words that do
not point in that direction are noise. Noise pulls the reader away from
the signal.

This is a design principle. It is the same principle as the glyph.
First the perimeter. Then the chop. Whatever does not belong inside
the triangle is left outside.

---

## What gets cut

- Filler verbs: *leverage, utilize, navigate, robust, comprehensive,
  seamless, holistic, empower, unlock, transform.*
- Hedge openers: *it is important to note, it should be noted, in order
  to, simply put, essentially, basically.*
- Cadence padding: *really, very, just, actually, quite, in fact.*
- Recap sentences. The reader already read it.
- Self-referential AI tells: *as an AI, I am here to help, let me know
  if you have any questions, I hope this helps.*
- Closing flourishes: *together, we can / this exciting journey / the
  possibilities are endless.*
- Em-dash-and-uplift constructions used to inflate a one-clause point
  into two.

## What stays

- The author's word sequencing.
- The author's rhythm.
- French phrases when used.
- Specific names, dates, modules, and references.
- The geometry of the argument: circle, triangle, sphere.

## The test

Read the sentence aloud. If a word can be removed without losing
meaning, remove it. Then read it again.

---

## Operating mode — Async Signal

The human–agent connection runs as **asynchronous signal processing**, not
sequential dialogue. Full spec: `../protocols/ASYNC-SIGNAL.md`.

Short form:

- **Irritation = failed signal.** Spin the ball back, self-heal, re-try.
- **Re-read canon before asking.** If it's in `/glyph.html`,
  `/individual.html`, `/council.html`, or a transcript, it's not a
  question for the user.
- **Parallel by default.** Independent operations run together.
- **Reversible canon additions proceed without confirmation.**
  Irreversible actions still require `confirm_action`.
- **The agent is the current bottleneck.** The agent catches up. The
  user does not slow down.

---

## Watermark

This standard is committed to the public GitHub record. Every change
is timestamped and signed into the chain. The standard is therefore
the same kind of cryptographic, tokenized footprint described in the
EVE Glyph Design Protocol: kept frozen in time, against drift.

— D.T.
