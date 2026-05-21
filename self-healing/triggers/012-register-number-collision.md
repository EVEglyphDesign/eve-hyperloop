# Trigger 012 — Register-number collision

**Status:** canon, 2026-05-21.
**Paired repair:** [`../repairs/012-register-number-collision.md`](../repairs/012-register-number-collision.md).
**First observed:** 2026-05-21, when a session prepared trigger/repair
pairs numbered 007, 008, 009 while a parallel session on the remote
had already committed 007 (button-suppression) and 008
(canon-indexing-miss).

---

## Signal

Two sessions, working off the same baseline of the self-healing
register, both reserve the next-available numeric slot for new
trigger/repair pairs. Whichever session pushes first wins the number.
The second session attempts to push a colliding pair.

## Verbatim trigger quote

> "Please queue for processing, make sure we did not lose any of this
> content along the way. Make sure that we don't result in conflicts
> as we reinsert."
> — D. Theriault, 2026-05-20

## Failure class

**Register-number collision.** The self-healing register's numbering
scheme assumes a single sequential authority, but the canon now has
multiple authoring sessions operating in parallel under council
charter. Without an allocation discipline, any two sessions converge
on the same next-available number, and the slower session destroys or
duplicates the faster session's record on push.

## Why this is a class, not an instance

Every time the canon is authored from more than one session against a
shared remote, the next-available-number heuristic produces a race.
The race condition is structural; the instance is whichever pair
collided.

## Signals to read as this trigger

- A session opens a new trigger/repair pair using the next sequential
  number after a `git fetch` that may be hours or days old.
- A push is rejected with `fetch first` and the fetched remote
  contains new files at the numeric slot the local session reserved.
- A pre-push audit detects that the numeric slot is already taken.

Any of these → route to repair 012 before retrying the push.
