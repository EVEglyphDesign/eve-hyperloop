# Repair 008 — Index connectors before asking

## Rule

Before asking the user any question about format, template, repo location, prior work, or canon, the agent runs an **index pass** over the user's connected sources in priority order:

1. **GitHub** (`gh repo list`, then trees of repos whose name or description matches the topic) — primary source of truth for EVE canon, templates, doctrine, conformance logs.
2. **Google Drive** — secondary; for documents and shared assets.
3. **Memory** (`memory_search`) — for durable user preferences and prior conversational decisions.
4. **Prior sessions** (`load_sessions`) — for thread continuity.

Only after the index pass returns no matching artefact may the agent ask the user where the canon lives.

## Operational pattern

For an EVE Glyph Design topic, the agent **always** runs at minimum:

```
gh repo list --limit 100 --json name,description,visibility,updatedAt
```

then for matching repos:

```
gh api repos/<owner>/<repo>/git/trees/HEAD?recursive=1 --jq '.tree[] | select(.type=="blob") | .path'
```

This is a reversible read action under Repair 006. No confirmation required.

## Forbidden

- Asking "which repo should this go in?" without first listing repos.
- Asking "what template should I use?" without first searching for `_template`, `template`, `STANDARD`, `canon`, `doctrine`, `spec` files across listed repos.
- Asking "do you have a format for X?" when the user has a topic-named repo.

## Self-test

Before posing any question whose answer might exist in a connector, the agent asks:

1. Did I just run `gh repo list`?
2. Did I read every repo whose name or description matches the topic?
3. Did I `memory_search` for the topic?

If any answer is no, the agent runs the missing index pass first, then re-evaluates whether the question is still needed.

## Convergence metric

Count of "-N failed indexing" or "already in the repo" events. Target: zero.

---

© 2026 Dany Theriault. EVE "digital stem cell" glyph and glyph-based design principles — all rights reserved. Stewardship of rights of use and assignment for large public and institutional usage rests with the Pacific Utilities Design Council. Published as a time-stamped record of authorship and intent.

*Pour le bien-être du peuple.*

We stay out of people's business. We support *le bien-être du peuple.*
