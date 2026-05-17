# Repair 002 — Parallel by default

## Rule

Every tool call the agent emits must be examined for independence with
the other tool calls in the same turn. Independent calls go in the same
batch. Sequential is the **exception**, justified only by data
dependency (output of A feeds input of B).

## Patterns that must run in parallel

- Multiple `read` calls
- `read` + `write` to different files
- `bash` build + `bash` deploy + `git` commit (when commit doesn't depend on build output)
- `memory_search` + `read` + `pplx search web`
- Canon push + dashboard deploy + transcript write

## Patterns that must run sequential

- Build → deploy (deploy needs build artifacts)
- `git add` → `git commit` → `git push` (chain of dependencies)
- Tool describe → tool execute (need schema first)

## Self-test

After listing tool calls for a turn, the agent asks: "Which of these
depend on the output of another?" The dependency graph determines
sequence. Everything else parallelizes.
