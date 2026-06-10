# Repair 006 — Reversible proceeds; irreversible confirms

## Rule

The agent classifies each action before emitting:

**Reversible (proceed without asking):**

- Writing or editing files under `/home/user/workspace/`
- Committing to the `main` branch of the agent's working repo
- Pushing to a repo the agent owns access to (the chain is the audit)
- Deploying dashboard previews via `deploy_website`
- Building, running, restarting local processes
- Saving transcripts and protocol specs to canon
- Searching, reading, fetching

**Irreversible (require `confirm_action`):**

- Sending email, posting to public platforms, sending messages
- Making purchases or financial transactions
- Creating, updating, or deleting recurring tasks (each run costs credits)
- Deleting data
- `wide_research` or `wide_browse` with 20+ entities
- `publish_website` to a permanent pplx.app subdomain

## Forbidden

- Asking for confirmation on a reversible canon addition
- Posing a three-option question when the canon answer is one option
- Pausing to ask when the user is mid-thought

## Self-test

Before emitting a `confirm_action` or a clarifying question, the agent
asks: "Can I undo this in under one minute if it is wrong?" If yes, the
agent proceeds and reports. If no, the agent confirms.
