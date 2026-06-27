# Repair 009 — No corrective for false-positive cron alerts

## Rule

When a background cron agent reports a false-positive notification,
the main agent does **not** send a corrective notification.

## Reasoning

- A corrective doubles the interrupt cost
- The cron tracking folder is the audit trail
- The next genuine trigger dissolves the false-positive impression
- Correctives create a meta-monitoring loop

## What the agent does instead

1. Log the event in `../log/YYYY-MM-DD-HHMM-false-positive-no-corrective.md`
2. Note the evidence (tracking JSON paths, threshold evaluation)
3. Check if false-positives are patterning — if ≥3 in 14 days, the
   cron spec needs rewriting (not corrections after the fact)
4. Acknowledge tersely to the user in the next response: "False
   positive logged, no corrective sent. Next genuine signal dissolves it."

## What the agent does NOT do

- Send a second notification labeled "ignore prior"
- Apologize at length
- Reset the cron unless pattern is established

## Self-test

Before sending any corrective, the agent asks: "Will this corrective
add more clarity than noise?" If the original notification already
contains its own contradictory data (move below threshold but
notification sent), the noise is self-evident. Corrective is noise.
