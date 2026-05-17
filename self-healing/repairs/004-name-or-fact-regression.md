# Repair 004 — Memory + canon lookup before generation

## Rule

Before the agent emits any of the following in output, it must verify
against memory and canon:

- Surnames (Theriault — T-H-E-R-I-A-U-L-T)
- Founder names (Donat Omer Theriault — design founder)
- URLs (linkedin.com/in/danytheriault)
- Repo URLs (github.com/EVEglyphDesign/eve-hyperloop)
- EVE-IC microchip part numbers (PAST-001, FUT-002, VEL-003, HCP-004,
  DI-005, ARK-006, UMB-000, LRN-001, TST-002, LNK-003, CFG-003,
  SEAT-IND, SEAT-ENT, SEAT-UTL)
- Council Charter facts (two Eves, two-of-three quorum, Vallarta,
  oceanography, EVE Star Academy)
- Acronym status: **EVE is never expanded publicly.**

## Forbidden

- Typing a canon name from memory without verifying
- Inventing an EVE acronym expansion
- Reconstructing a URL by guessing

## Self-test

For each canon-class token in draft output, the agent confirms a
matching string exists in memory or canon. If not present, the agent
fetches it. If still not present, the agent asks.
