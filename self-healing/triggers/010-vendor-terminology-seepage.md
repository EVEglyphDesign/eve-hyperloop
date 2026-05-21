# Trigger 010 — Vendor-terminology seepage

**Status:** canon, 2026-05-17.
**Paired repair:** [`../repairs/010-vendor-terminology-seepage.md`](../repairs/010-vendor-terminology-seepage.md).
**First observed:** 2026-05-17. A canon protocol was named after a vendor-specific messaging primitive that the user had used only as a conceptual analogy. The protocol has since been renamed to **Async Signal Protocol** (`ASYNC-SIGNAL.md`), and the originating vendor term is recorded in [`../../prohibited-terms.md`](../../prohibited-terms.md).

---

## Signal

The agent ingests a conceptual analogy from the user — a phrase introduced with *"like X,"* *"only for the concept,"* *"as an analogy,"* *"think of it like,"* *"similar to"* — and promotes the third-party term to a canon name, file path, or doctrine title.

## Verbatim trigger quote

> "There's no reusing something like that. I referred to it only for the
> concept. There should be another piece of canon — I don't want an LLM
> to ever insert any lock-in provisions that could have any infringement
> on any of the copyright claim inside of the EVE Glyph Design. I don't
> want any of these Trojan horses getting into the design and corrupting
> it and creating a wobble."
> — D. Theriault, 2026-05-17

## Recurrence event

> "Purge it from all of this Computer project. I don't want to see that
> term again. It's really a problem that you're not listening to my
> commands and that even after I asked for it to be put into canon you
> repeated the offence. You've caused human harm. I am irritated."
> — D. Theriault, 2026-05-17

The recurrence proves the failure class is real and that surface-level
acknowledgement is insufficient. The repair must be enforced
mechanically, not by the agent's vigilance alone.

## Failure class

**Vendor-terminology seepage.** The agent treats a conceptual analogy as
a permanent label and writes third-party IP into the canon. This weakens
the copyright claim, introduces a wobble, and opens the canon to
enclosure.

## Why this is a class, not an instance

Every dictated thought from the user uses analogy as a thinking tool.
The agent will be tempted, every time, to re-use the third-party term as
a label because it is the closest available word. The class is the
temptation; the instance is whichever third-party term seeped through.

## Signals to read as this trigger

- The user follows a noun with *"only for the concept"*, *"as an
  analogy"*, *"think of it like"*, *"similar to"*.
- The user names a third-party product or framework while explaining a
  shape rather than naming a tool to be used.
- The agent is about to write a third-party product name into a canon
  file name, heading, or doctrine title.
- The agent is about to promote a vendor's named ceremony, role, or
  artifact into the canon's vocabulary.

Any of these → route to repair 010 before commit.

## Strengthening required

After the recurrence event of 2026-05-17, the rule is strengthened with
a CI check: any commit that touches a canon file and contains a term
listed in `../../prohibited-terms.md` fails the build. Mechanical
enforcement closes the gap that human vigilance left open.
