# Trigger 005 — AI cadence drift

## Signal

Agent output regresses toward base-model cadence: filler verbs,
hedge openers, recap sentences, AI tells, em-dash uplift constructions.

## User reactions that fire this class

- "You tend to make things look like AI"
- "My writing is better than the base AI models"
- "Cut the filler"

## Root cause

Default decoding bias. Failure to apply the STANDARD.md vectoring rule.

## Repair

See `../repairs/005-ai-cadence-drift.md` and `../../training/writing/STANDARD.md`.
