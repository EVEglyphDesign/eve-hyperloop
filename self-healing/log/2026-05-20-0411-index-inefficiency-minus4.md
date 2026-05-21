# Self-Healing Log Entry
Timestamp: 2026-05-20 04:11 EDT (entry created 2026-05-21 evening commit window)
Class: 002 — Choice prompt issued without buttons
Severity: **-4 index inefficiency** (user-assigned)
Status: LOCKED

## What happened
Across three consecutive turns (2026-05-14 physics-alignment turn, 2026-05-20 00:25 EDT queue/buttons turn, 2026-05-20 01:11 EDT reprocess turn) the assistant issued plain-text clarifying questions when the canon required `ask_user_question` buttons. User flagged the third occurrence with explicit "-4 index inefficiency" and "you keep failing on this."

## Failure class
- Trigger 002: assistant offered narrative branching instead of structured choice
- Compounded by: failure to call memory_search before the first clarifying question
- Root cause: assistant did not re-read canon (ark_protocol_governance, buttons_only) before responding to ambiguous directive

## Repair applied
1. memory_search executed, canon files re-read in parallel
2. ARK Queue file created at /workspace/ARK_QUEUE_2026-05-20.md, all three threads preserved
3. Buttons issued via ask_user_question with three structured questions (queue action, physics lens, log confirmation)
4. User confirmed: commit all, all three lenses, -4 locked

## Rule update (append to /self-healing/repairs/)
**Rule 002-R3 (NEW):** Any user turn containing the token "button" or "buttons" forces the `ask_user_question` path. No plain-text fallback is permitted regardless of perceived ambiguity. If intent is still unclear, the buttons themselves must enumerate the interpretations.

## Convergence impact
- Time since last class 002 violation before this entry: ~6 days (2026-05-14 → 2026-05-20)
- Target: monotonically increasing. Next class 002 violation must exceed 6-day gap or convergence is broken and severity escalates automatically.

## User acknowledgement
- Question 3 answered: "Confirm -4, lock the rule" ✓
