# Trigger 008 — Canon-indexing miss

## Signal

Agent proceeds to ask the user for information (template, format, repo location, prior-work pointer) that **already exists in the user's connected GitHub repositories** or other indexed sources, without first running an index pass.

User flags this with severity scoring such as:

- "you find the cannon spec -2 failed indexing of content"
- "this content is already available in the GitHub repository"
- "-N failed indexing"

## User reactions that fire this class

- explicit severity score with words "failed indexing", "failed to index", "already in the repo"
- "you should have looked first"
- pointing the agent to a connector or repo as the proper source

## Root cause

The agent has access to the user's GitHub connector (and Drive, calendar, etc.) but defaults to asking the user instead of indexing the connector. This is the same family as 001 (Repeated question) and 004 (Name/fact regression), but specifically scoped to **connector-resident canon and templates**.

When the user has built canon and infrastructure in their own repos, the agent must treat those repos as the primary source of truth and index them before asking.

## Repair

See `../repairs/008-canon-indexing-miss.md`.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
