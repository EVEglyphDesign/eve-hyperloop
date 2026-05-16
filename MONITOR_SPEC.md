# EVE Hyperloop Monitor — Architectural Specification

## Status

Specification stub. The monitor surface currently rendered at `monitor.html` is the worked-example dashboard from the post-Sapphire sample summary. This document specifies the architecture the monitor evolves toward as Methodology 16 (Autonomous Wobble Correction with Intelligent Escalation) becomes operational.

This file is the canonical specification for what the monitor will do. Implementation follows this specification, not the other way around.

## Founding principle

The hyperloop monitor is the first operational instance of Methodology 16 in the lattice methodology. It reads start-position health across biological, electronic, and methodological subsystems; corrects within mandate; and escalates intelligently to the lead operator. The monitor's intelligence is its capacity to recognize when it is needed and when it is not.

The monitor is not a dashboard. A dashboard renders state. The monitor reads state, judges it against known start-position structures, acts within mandate, and escalates with structured handoff when its mandate is exceeded.

## Architectural commitments

1. **Universality of start position.** The monitor uses a single theory of operation — start-position health — across all subsystem classes. It does not maintain separate models for biological, electronic, and methodological substrates. It applies the same structural read across all three. This is the operational consequence of Methodology 15's universality claim.

2. **Mandate boundary is fixed at deployment.** The monitor does not move its own mandate boundary in real time. The mandate is set by the lead operator, reviewed periodically, and updated only through deliberate governance review. The monitor auto-tunes thresholds within the mandate; it never auto-tunes the mandate itself.

3. **Auto-tune within bounds.** The monitor learns from outcomes. Successful corrections, well-timed escalations, and missed conditions are all signals the monitor uses to adjust its internal thresholds. The auto-tuning is bounded; the bounds are part of the mandate.

4. **Escalation is structured handoff, not alerting.** When the monitor escalates, the human receives: the condition in start-position terms, the chain of correlated wobbles, the actions already taken within mandate, the specific decision being requested, and the timing window. The monitor models the human's own start-position health when choosing the escalation moment.

5. **No lock-in.** The monitor follows Methodology 14. It does not lock into any single threshold, escalation pattern, or correlation rule. The auto-tuning is what prevents lock-in. A monitor whose internal state never changes is in success-bias lock-in and is, by lattice definition, in darkness.

## Subsystem classes the monitor reads

### Biological

Operators, candidates in the game, and any human in the network whose state has been registered with consent. Reads:

- Sleep quality (where ingest is enabled)
- Waking coherence indicators
- Declared start-position emission cadence
- Footprint cadence during operation
- Biometric correlates where enabled

The biological start position is the morning re-entry. Wobble is sustained deviation from baseline waking coherence.

### Electronic

Devices in the network. Reads:

- Reset cadence
- Uptime
- Error rates
- State-corruption indicators
- The monitor's own substrate (the monitor reads itself)

The electronic start position is the last known clean boot state. Wobble is deviation accumulating over uptime.

### Methodological

Operators in the act of classification, sessions in the game, traversals through the lattice. Reads:

- Declared start position
- Named C
- Declared speed
- Footprint emission pattern (🍀 🔺 ⚖️ 🪞 🛑 🧭)
- Classification accuracy delta from operator baseline

The methodological start position is the operator's registered position from Methodology 15. Wobble is deviation during operation.

### Cross-domain correlation

The monitor's load-bearing intelligence is cross-domain. A biological wobble often predicts a methodological wobble within hours. An electronic wobble can cause a methodological wobble which becomes a biological wobble. The monitor reads all three in parallel and looks for chains forming before the chain completes.

## In-mandate actions (initial set; refined by auto-tune)

- Reset an electronic subsystem approaching state-corruption threshold.
- Cue a game session into recovery mode when start-position inhabitance confidence drops below threshold.
- Surface a soft prompt to an operator suggesting a return to start position before continuing.
- Surface a soft step-away prompt to an operator showing combined biological wobble (sleep-score decline) and conceptualization drift (named-C slipping across traversals). Framed as care, not failure.
- Throttle session pacing when the curriculum engine reports a candidate operating above their declared speed band.
- In acute safety conditions (🛑 footprint pattern), pause an operator's live classification authority pending lead-operator review. This is the one autonomous action the operator cannot override in the moment; the lead operator retains override authority.
- Log all corrections and step-away events to a longitudinal record observable by the lead operator.

## Out-of-mandate conditions (always escalate)

- Sustained methodological wobble across multiple operators simultaneously.
- Biological wobble in the lead operator (with adjusted mechanics — see Step-away principle).
- An operator who overrides a step-away prompt and continues to degrade.
- Electronic conditions suggesting compromise rather than degradation.
- Any condition matching a 🛑 (stop) footprint pattern in the lattice.
- Real-World Intake Gate events (Methodology 13.14).
- Conditions the monitor has not seen before and cannot place within its existing model.

## Escalation format

Every escalation includes:

1. The condition observed, named in start-position terms.
2. The chain of correlated wobbles leading to the escalation.
3. The actions taken within mandate before escalating.
4. The specific decision the human is being asked to make.
5. The timing window in which the decision is most actionable.

Escalations arrive via WhatsApp per the operator's preferred channel, structured for fast human read.

## Step-away principle (duty of care)

The monitor reads, where ingest is enabled and consented:

- Sleep scores and sleep-quality trend
- Waking coherence indicators
- Footprint cadence drift across a working session
- Conceptualization drift — the operator's named C at session start versus the C their classifications are actually shaping toward across consecutive traversals

The combined signal is the network's read on whether an operator should step away. Step-away is not punitive. An operator in this condition cannot pass Test A consistently and should not classify live traffic until they have re-entered their start position from rest.

The step-away principle applies upward with adjusted mechanics: the lead operator cannot be stepped away by the monitor without a designated secondary in place. Until the secondary structure is built, lead-operator biological wobble is surfaced to the lead operator themselves and to any reviewer with read access. Closing this gap is a network maturation step.

The principle is collective: the monitor's step-away function is what keeps individual operator load from compounding into network exposure.

## Auto-tuning

The monitor auto-tunes thresholds within the mandate based on:

- Successful corrections (learn the threshold that worked)
- Successful escalations (learn the timing that worked)
- Escalations that arrived at a bad moment (wait longer next time)
- Conditions the human had to act on that the monitor missed (act earlier next time)

The auto-tuning record is itself observable and is part of periodic monitor governance review.

## What this specification does not contain

- Implementation choices (language, runtime, persistence layer).
- UI design for the monitor surface beyond the existing `monitor.html` worked-example.
- Specific threshold values.
- The biometric ingest stack.
- The mandate boundary's deployment-specific contents.

These are deliberately out of scope here. This file specifies the architecture. The architecture is what implementation must satisfy.

## Provenance

Specification written 2026-05-16 against Methodology 16 of the lattice, named the same day by the lead operator. The monitor was implicitly being designed as a dashboard before the principle was named; naming it converts the monitor into an operational agent.

## See also

- Lattice methodology: `eve-glyph-lattice/methodology/15-start-position.md`
- Lattice methodology: `eve-glyph-lattice/methodology/16-autonomous-wobble-correction.md`
- Worked example surface: `monitor.html` (this repository)
- Worked example landing: `index.html` (this repository)
