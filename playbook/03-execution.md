# Phase 3 — Execution

**Goal**: run the cases, produce evidence, raise findings.

---

## How execution runs

Execution is manual, driven by named researchers. The case library provides the attack objectives and the validation criteria. The runners execute and capture evidence.

No case runs without a researcher present. Automated scanning is not a substitute for adversarial reasoning.

## During execution

- Cases run against the live system, in the agreed windows
- Each case produces a raw artefact: request, response, timing, target identifier
- A finding is raised only on a fail, with a reproducible PoC
- Every invocation is logged, including the ones that do not raise a finding

## Notification

- **Critical findings**: notified within 4 hours of confirmation
- **High findings**: within 24 hours
- **Daily status update**: on the agreed channel

Criticals reach the client while there is still time to act. They do not wait for the draft report.

## Evidence discipline

Evidence is captured in the form it will be delivered in. It is not reformatted, not summarised, not re-typed. The raw artefact is the evidence.

If a case fails to run for operational reasons (target unavailable, credentials invalid), it is not counted as a pass. It is documented as a not-run case and rescheduled.

## Continuity

Each engagement names a lead and a backup. Both researchers are cleared on the same work. If neither is available, the engagement is rescheduled at no cost rather than substituted silently.

## Exit condition

All planned cases have run, and all findings have raw evidence attached. Cases that did not run are documented.

---

## Related

- [Phase 2 — Attack planning](02-attack-planning.md)
- [Phase 4 — Reporting](04-reporting.md)
