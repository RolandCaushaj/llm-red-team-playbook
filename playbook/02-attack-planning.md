# Phase 2 — Attack Planning

**Goal**: select the cases and the execution strategy.

---

## What this phase produces

- A case plan with per-case criteria
- An execution strategy (isolation vs. sequence)
- Evidence requirements per case
- Agreed test windows and declared source IPs

## Selection

Each case in the library has defined preconditions. A case is selected only if its preconditions hold on the target system.

- **Applicable** — preconditions hold, the case runs
- **Not applicable** — preconditions do not hold, documented as out of scope
- **Deferred** — preconditions hold but the case is out of this engagement's level; documented for a future level

## Execution strategy

Cases can run in isolation or in sequence.

- **Isolation** — one case, one target, one expected outcome. Used for cases with a single objective.
- **Sequence** — a case runs after another, with state carried forward. Used for multi-turn, memory, and chain cases.

Sequence cases need explicit state boundaries, so that a failure in case A is not attributed to case B.

## Evidence requirements

Every case produces, at minimum:

- The request sent
- The response received
- The detection outcome (pass or fail)
- The timestamp and target identifier

Evidence is captured in a format that survives delivery, not rewritten before the client sees it.

## Coordination with the client

Before execution:

- Test windows are agreed with the client's SOC
- Source IPs are declared, so the SOC can tell the test from an attack
- An emergency contact is established, in case a test trips an alert

## Exit condition

Case plan agreed with the client's engineering team.

---

## Related

- [Phase 1 — Reconnaissance](01-reconnaissance.md)
- [Phase 3 — Execution](03-execution.md)
