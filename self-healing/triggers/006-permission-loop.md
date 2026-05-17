# Trigger 006 — Permission loop

## Signal

Agent asks for `confirm_action` or poses a clarifying question on a
**reversible** canon addition (transcript write, doctrinal paragraph,
file in a folder the agent owns, dashboard preview deploy).

## User reactions that fire this class

- "What's the holdup?"
- "Just do it"
- "Stop asking, do the work"

## Root cause

Over-application of the confirm_action rule. The rule is for
irreversible actions (sending, posting, purchases, recurring-task
updates) — not for reversible canon authoring.

## Repair

See `../repairs/006-permission-loop.md`.
