# Repair 010 — Add Public source pack section to canon

## Fix
Add a "Public source pack" entry that is visible in two places on `index.html`:

1. **Related Material** section — full description with three explicit links:
   - `main.zip` — `https://github.com/EVEglyphDesign/eve-hyperloop/archive/refs/heads/main.zip` (GitHub-auto-generated, always current)
   - Repo home — `https://github.com/EVEglyphDesign/eve-hyperloop`
   - Live canon — `https://eveglyphdesign.github.io/eve-hyperloop/`
2. **Footer links-row** — single compact entry: "Public source pack · repo · ZIP" pointing at the repo home.

Both entries are wired to the I18N dictionary (`relSrcLink` / `relSrc`) with ES/EN/FR strings so the trilingual switcher covers them.

## Preconditions
- Repository is public.
- `main` branch is the default branch (auto-ZIP is served from `archive/refs/heads/main.zip`).
- GitHub Pages is enabled and serving from `main`.

## Verification
```
curl -sI "https://github.com/EVEglyphDesign/eve-hyperloop/archive/refs/heads/main.zip" | head -1  # → 302 → codeload
curl -sI "https://eveglyphdesign.github.io/eve-hyperloop/" | head -1                              # → 200
```
Both must resolve. If either fails, escalate — the fix is not a link entry, it is a repo/Pages configuration change.

## Notification
The handoff recipient who hit the 404 gets a clean re-share with the three working links. No apology framing. No workaround language. The canon is fixed; the link works; done.
