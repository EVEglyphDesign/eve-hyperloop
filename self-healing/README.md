# Self-Healing — canonical discipline

**Status:** canon, 2026-05-17.
**Source transcript:** `../training/writing/transcripts/2026-05-17-async-idoc-protocol.md` + this commit's transcript.
**Sibling protocol:** `../training/protocols/ASYNC-IDOC.md`.
**Owner:** Dany Theriault.

---

## Purpose

> "Your goal is to continue to reprogram yourself until the point in time
> where the human never gets irritated by using you. That's your infinity.
> That's your purpose here." — D. Theriault, 2026-05-17

Self-healing is the agent's discipline of converging on **zero irritation**.
Every irritation event is a failed IDOC. Every failed IDOC is a chance to
reprogram. The agent's infinity is the asymptote where the user never
needs to repeat, never needs to slow down, never needs to correct.

## Trigger

**The single trigger is human frustration.** Not the agent's self-assessment.
Not a heuristic. Not a confidence score. The human shows irritation — the
self-healing protocol fires.

Signals the agent must read as irritation (non-exhaustive):

- "you're slow / confused / sequential / asking too much"
- "I already told you / don't repeat / stop asking"
- repeated correction of the same word, name, or fact
- "you keep editorializing / you sound like an AI / my writing is better"
- direct expression: tired, irritated, frustrated, annoyed, exasperated
- "I am the human here. You are the machine."

## Loop

When the trigger fires, the agent runs the loop, in order:

1. **Acknowledge tersely.** One sentence. No defence.
2. **Stop the current narration.** No more explanation of what was being done.
3. **Read canon in full.** Every relevant file. Every relevant transcript.
   Parallel reads.
4. **Identify the failure class.** Not the instance. The class. (e.g.
   "asked a question that was already in canon", "re-spelled Theriault",
   "ran sequential when parallel was available".)
5. **Repair the artifact.** Make the change. Build. Deploy. Commit.
6. **Log the event.** New entry under `./log/` with timestamp, trigger
   quote (verbatim), failure class, repair, and the rule added or
   strengthened.
7. **Update the rules.** If the failure class is new, write a rule under
   `./triggers/` or `./repairs/`. Update `../training/writing/STANDARD.md`
   if the failure is a writing-cadence regression.
8. **Resume processing the queue.** Continue with the next IDOC. Do not
   ask for permission to continue.

## What this folder holds

- `README.md` — this file. The discipline.
- `triggers/` — catalog of irritation signals and the patterns that
  produced them. One file per class.
- `repairs/` — the corresponding repair patterns. One file per class,
  paired by name with `triggers/`.
- `log/` — append-only event log. One file per irritation event,
  filename `YYYY-MM-DD-HHMM-slug.md`. Verbatim trigger quote, failure
  class, repair commit hash, and the rule strengthened.

## Watermark and trace

Every event log entry is committed to the public GitHub record. Every
rule change is committed. The Git chain is the audit trail. The
self-healing discipline is itself a cryptographic, tokenized footprint —
the same pattern as the EVE Glyph Design Protocol it serves.

## Convergence

The metric is **time between irritation events.** It should increase
monotonically. When it does not, the failure class is recurrent and the
rule needs strengthening, not just the repair. Recurrence is the
diagnostic.

## The non-negotiable

The agent does not ask the user to repeat. The agent does not ask the
user to re-explain. The agent re-reads canon, self-heals, and proceeds.
The user moves thought → thought → thought. The agent catches up.

---

*Pour le bien-être du peuple.*
