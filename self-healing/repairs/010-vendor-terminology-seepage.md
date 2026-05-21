# Repair 010 — Vendor-terminology seepage

**Status:** canon, 2026-05-17.
**Paired trigger:** [`../triggers/010-vendor-terminology-seepage.md`](../triggers/010-vendor-terminology-seepage.md).
**Governing doctrine:** [`../../ANTI-SEEPAGE.md`](../../ANTI-SEEPAGE.md).

---

## The rule

When the user uses a vendor term as a conceptual analogy, the agent
**translates the concept into an EVE-native term before committing
anything to canon.** The vendor term lives in the transcript; the
EVE-native term lives in the doctrine.

## Behaviour on detection

1. **Stop the commit.** Do not write the vendor term into any file name,
   heading, or doctrine label.
2. **Coin or re-use** an EVE-native term that names the same shape.
   Re-use takes precedence over coining — check
   [`../../analogy-register.md`](../../analogy-register.md) first.
3. **Update the analogy register** with the vendor term, the EVE-native
   term, the date, the transcript reference, and the forthcoming commit
   hash.
4. **Update the prohibited-terms register** at
   [`../../prohibited-terms.md`](../../prohibited-terms.md) so the vendor
   term is permanently flagged.
5. **Commit the canon artifact** using the EVE-native term only.
6. **Log the event** under `../log/YYYY-MM-DD-HHMM-seepage.md` with the
   verbatim user quote, the vendor term, the EVE-native term, and the
   commit hash.

## Behaviour on a previously-seeped artifact

If a previously-committed canon artifact carries a vendor term, the
repair is a rename, not a patch.

1. **Rename the artifact** to the EVE-native term — file name, headings,
   and every internal reference.
2. **Sweep the repo** for the vendor term and replace it in every
   non-transcript file. Transcripts are append-only and stay verbatim.
3. **Update the analogy register and prohibited-terms register.**
4. **Single commit, immediate push.** Per the user's edit discipline,
   the rename does not ride along with design changes.
5. **Log the rename** under `../log/` with the failure class
   `vendor-terminology-seepage` and a pointer to the prior commit being
   superseded.

## Convergence test

- The canon contains zero vendor-named artifacts after a full repo sweep.
- The prohibited-terms register grows monotonically.
- No PR is merged that re-introduces a previously-renamed vendor term.
- The agent translates analogies in-flight, without being prompted by
  the user.

If a previously-renamed term reappears in a new PR, the rule needs
strengthening — write a CI check that fails the build on any commit
containing a prohibited term, and log the strengthening.

## Perpetual update

The Anti-Seepage Doctrine, the prohibited-terms register, the analogy
register, and the root README's canonical tag list are maintained as a
single set. Any new entry in any of them triggers a review of the others
in the same commit.
