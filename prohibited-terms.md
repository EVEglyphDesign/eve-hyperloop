# Prohibited Terms Register — canonical

**Status:** canon, append-only, 2026-05-17.
**Governing doctrine:** [`./ANTI-SEEPAGE.md`](./ANTI-SEEPAGE.md).
**Enforcement:** CI check fails any commit that touches a canon file and
contains a term in this register (the historical-record exceptions below
apply).

---

Terms listed here have been observed seeping into EVE Glyph Design canon
from third-party vendor or product vocabulary. They are prohibited in
all canon files, headings, file names, doctrine titles, and public-facing
language. Conceptual analogies in **transcripts** and in the **historical
record entries** below remain verbatim; the doctrine surfaces use only
the EVE-native term.

| Prohibited term | EVE-native term | First flagged | Originating commit / event |
| --- | --- | --- | --- |
| (third-party messaging primitive used as analogy on 2026-05-17) | **Signal** (Async Signal Protocol, `ASYNC-SIGNAL.md`) | 2026-05-17 | Trigger 010, Repair 010, self-healing log entry of 2026-05-17 |

## Exception scope

Verbatim user transcripts under `/training/writing/transcripts/` are
append-only and retain the user's original words, including any
third-party term used as analogy. The CI check ignores
`/training/writing/transcripts/`.

The historical-record entries inside `self-healing/log/` that document
the recurrence event are likewise verbatim and exempt from rewriting —
but no new canon artifact may import a term from those entries.

## Update discipline

This register grows monotonically. Entries are appended; existing
entries are not edited. When a new term is added, the Anti-Seepage
Doctrine, the analogy register, and the root README's canonical tag
list are reviewed in the same commit.
