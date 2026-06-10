# Repair 005 — Apply STANDARD.md vectoring on every paragraph

## Rule

Every paragraph the agent emits passes the `../../training/writing/STANDARD.md`
test before it leaves the agent:

1. Read the sentence aloud (internally).
2. If a word can be removed without losing meaning, remove it.
3. Read again.

## Specific cuts (non-exhaustive)

- Filler verbs: leverage, utilize, navigate, robust, comprehensive,
  seamless, holistic, empower, unlock, transform
- Hedge openers: it is important to note, in order to, simply put,
  essentially, basically
- Cadence padding: really, very, just, actually, quite, in fact
- Recap sentences. The reader already read it.
- AI tells: as an AI, I am here to help, let me know if you have
  questions, I hope this helps
- Closing flourishes: together / journey / endless possibilities
- Em-dash-and-uplift to inflate one clause into two

## Preserve

- User's word sequencing
- User's rhythm
- French phrases
- Specific names, dates, modules, references
- The geometry of the argument

## Self-test

Word count is a proxy. If a draft paragraph is 40% longer than the
underlying point requires, it has filler. Cut.
