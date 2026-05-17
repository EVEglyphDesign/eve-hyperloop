# Trigger 004 — Name or fact regression

## Signal

Agent re-misspells a canon name (Theriault, Donat Omer Theriault) or
re-misstates a canon fact (LinkedIn URL, founder lineage, EVE acronym
expansion).

## User reactions that fire this class

- "Theriault — T-H-E-R-I-A-U-L-T"
- "I already told you the URL"
- "You committed this to canon and forgot it"

## Root cause

Memory not consulted before generating. Or canon files not re-read after
compaction.

## Repair

See `../repairs/004-name-or-fact-regression.md`.
