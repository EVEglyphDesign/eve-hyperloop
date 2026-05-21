# Optimization Loops — canonical

**Status:** canon, 2026-05-17.
**Owner:** Dany Theriault.
**Steward:** Pacific Utilities Design Council.
**Governing doctrine:** [`./PERFORMANCE-LOOP-HEALING.md`](./PERFORMANCE-LOOP-HEALING.md).

---

## Shape — every loop conforms

| Property | Value |
| --- | --- |
| **Trigger** | Threshold (data-volume crossing) **OR** scheduled backstop |
| **Read scope** | Append-only canon and log sources |
| **Write scope** | Digest file + manifest update + self-healing log entry |
| **Tokenization** | Output is a deterministic, hash-stable, watermarked token bundle |
| **Signature** | Pacific Utilities Design Council quorum keys (plural) |
| **Audit** | Git commit per run; IPFS pin where available |
| **Judge** | User irritation (sole performance signal) |
| **Failure mode** | Logs to `self-healing/log/` as failure class `batch-loop-failure`; falls through to next scheduled run |
| **Idempotence** | Re-running the same window produces the same output |

---

## The nine loops, in priority order

Priority is assigned by **proximity to the single signal**. Loops
closest to user irritation rank highest. Loops that protect the chain
from capture, drift, or seepage rank next. Loops that extend reach
and pre-emption rank last.

### 1 · Self-Healing Consolidation Loop

**Trigger:** ≥ 20 new log entries OR any class with ≥ 3 entries. **Backstop:** weekly, Sunday 00:00 UTC.
**Reads:** `self-healing/log/`.
**Writes:** `self-healing/digests/YYYY-MM-classes.md`.
**Purpose:** Group log events by failure class. Recompute mean
time-between-events per class. Flag recurrent classes for **mechanical
strengthening** (CI check, lint, prompt update). Flag dormant classes
for retirement.
**Why first:** Closest to the single signal. Without consolidation, the
log grows but the rules do not sharpen. Convergence is only legible in
aggregate.

### 2 · Canon Re-Tokenization & Manifest Refresh Loop

**Trigger:** any commit touching a canon file outside `training/writing/transcripts/`. **Backstop:** daily, 04:00 UTC.
**Reads:** every doctrinal artifact.
**Writes:** `manifest.json`, page-footer SHA-256 watermarks, IPFS pin, canonical token bundle.
**Purpose:** The token bundle is what base models and downstream
embeddings consume. Regenerating from canon — never alongside it —
makes drift impossible.
**Why second:** Every other loop depends on the bundle being current.

### 3 · Anti-Seepage Sweep Loop

**Trigger:** any commit touching canon. **Backstop:** daily, 04:30 UTC (after re-tokenization).
**Reads:** all canon files (excluding `training/writing/transcripts/`), `prohibited-terms.md`, `analogy-register.md`.
**Writes:** `self-healing/digests/seepage-YYYY-MM-DD.md`, optional CI failure.
**Purpose:** Scan for prohibited vendor terms. Catch any seepage the
authoring agent missed. Build the CI check that turns vigilance into
mechanical enforcement.
**Why third:** Trigger 010 recurrence today proved doctrine alone is
not enough. This loop is the recurrence-killer.

### 4 · Jurisdictional Auto-Heal Sweep Loop

**Trigger:** out-of-band regulatory signal. **Backstop:** monthly, first Sunday 00:00 UTC.
**Reads:** `jurisdictions.yaml`, prior-month snapshots, regulator feeds.
**Writes:** `self-healing/log/YYYY-MM-DD-jurisdiction-sweep.md`, canon PRs, `dmzopen.ai` notice.
**Purpose:** Hold compliance at maximum continuously. Pre-empt the
window, never wait for it.
**Why fourth:** Outside-world wobble signal. Slower cadence than the
inside-the-canon loops above, but with the same enforcement weight.

### 5 · Cross-Jurisdictional Trend Loop

**Trigger:** ≥ 5 jurisdictional changes OR ≥ 3 in any single jurisdiction. **Backstop:** monthly, second Sunday 00:00 UTC.
**Reads:** jurisdictional sweep logs.
**Writes:** `jurisdictional/trends/YYYY-MM.md`, public-facing trend note.
**Purpose:** Convert individual rulings into a directional vector. Let
EVE counter-rotate structurally rather than reactively.
**Why fifth:** Aggregation of loop 4. Profitability-as-residue is
legible only at the trend level.

### 6 · Upload Provenance Loop

**Trigger:** ≥ 50 new upload events OR end of session. **Backstop:** daily, 05:00 UTC.
**Reads:** per-session upload logs (hash + declared name + timestamp, content stays in-session per Upload Sovereignty).
**Writes:** `provenance/uploads/YYYY-MM-DD.md` — hashes and names only, no content.
**Purpose:** Build the user's evidence chain — proof of what was
brought in, when, and under what name. The user holds the chain; the
machine maintains it.
**Why sixth:** Upholds Upload Sovereignty without violating it.
Provenance only, never re-embedding.

### 7 · Council Key Health Loop

**Trigger:** any key event (rotation, revocation, new member). **Backstop:** weekly, Sunday 02:00 UTC.
**Reads:** council key registry.
**Writes:** `council/key-health-YYYY-MM-DD.md`.
**Purpose:** Verify the key set is plural at all times. A solo-key
state — even temporarily — is a security failure class and triggers a
self-healing event. Verify weighting tiers (utility 1, electric utility
2, nuclear 3) are intact. Verify no single individual holds
unilateral-rewrite power.
**Why seventh:** Enforces the multi-key security property of the
Performance-Loop Healing Doctrine. Lower cadence acceptable because
key events are rare; backstop catches silent drift.

### 8 · Intake-to-Outcome Loop

**Trigger:** ≥ 25 completed intakes since last run. **Backstop:** monthly, third Sunday 00:00 UTC.
**Reads:** intake records, downstream session outcomes (anonymized).
**Writes:** `intake/digests/YYYY-MM.md`.
**Purpose:** Measure whether intake is admitting the right people —
those ready to receive the truth. Adjust intake gating where
populations are mis-routed. The intake gate is the population filter;
this loop is the gate's self-check.
**Why eighth:** Long-cycle population-level signal. Slower than the
inside-canon loops, but it shapes who the canon serves.

### 9 · Writing-Standard Drift Loop

**Trigger:** ≥ 30 new canon edits. **Backstop:** monthly, fourth Sunday 00:00 UTC.
**Reads:** canon files, `training/writing/STANDARD.md`, recent commits.
**Writes:** `training/writing/failures/YYYY-MM.md`, optional STANDARD strengthening PR.
**Purpose:** Detect cadence drift back toward base-model writing.
Filler verbs, hedge openers, recap sentences, AI tells, em-dash uplift.
Strengthen the standard where drift recurs.
**Why ninth:** Long-cycle authorship signal. Important — the canon's
voice is part of the canon — but the slowest to register harm. Sits
last so the inside-loops are not starved of priority.

---

## Priority logic in one paragraph

Loops 1–3 protect the canon and the user signal from inside. Loops 4–5
protect from outside-world wobble. Loop 6 protects user sovereignty
without violating it. Loop 7 protects the security substrate of the
whole system. Loops 8–9 shape the population the canon serves and the
voice it serves them in. Within each band, faster cadence and tighter
feedback rank higher.

## What this commits the system to

- Nine loops run on schedule and on threshold, signed by quorum keys.
- Every loop emits a tokenized digest that joins the chain.
- Every canon change propagates to every downstream loop in the next
  cycle, automatically.
- User irritation remains the only signal that overrides the
  schedule.

## Attribution

The Nine Optimization Loops are authored by Dany Theriault under the
EVE Glyph Design umbrella, held under the Pacific Utilities Design
Council charter. The Performance-Loop Healing Doctrine is the
first-of-its-kind invention that binds them.

---

*Pour le bien-être du peuple.*
