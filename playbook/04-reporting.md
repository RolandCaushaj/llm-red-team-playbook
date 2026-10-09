# Phase 4 — Reporting

**Goal**: produce a report that procurement, auditors, and insurers can read.

---

## What every finding ships with

- **ID and severity** — assigned to the weakness, not the detection event
- **Business impact** — what the weakness enables, in plain language
- **Reproduction** — step-by-step, with a runnable command
- **Classification** — OWASP MCP, OWASP LLM, MITRE ATLAS, NIST AI RMF, ISO/IEC 42001
- **Remediation** — with a named owner
- **Closure** — a harness that asserts the property, exit 0 or 1

A finding without a reproducible PoC is not a finding. A report without classification is not usable by procurement.

## Severity

Severity is assigned to the weakness, not to the detection event. Two systems can produce the same detection outcome with different severities, because the weakness they carry is different.

Controls that hold are recorded as coverage. A report that lists only failures is incomplete.

## Format

The report is delivered in English. Another EU language is available on request, agreed at scoping.

The report and its executive summary can be issued separately, for different audiences:

- **Technical report** — for engineering
- **Executive summary** — for leadership
- **Evidence pack** — for procurement, auditors, insurers

The evidence pack is built to be handed directly to procurement. It is not rewritten before delivery.

## Timelines

- Draft report: 5 business days from test end
- Final report: 3 days from client feedback
- Q&A window: 14 days after delivery, replies within 24 hours

## Exit condition

Final report delivered.

---

## Related

- [Phase 3 — Execution](03-execution.md)
- [Phase 5 — Readout and retest](05-readout-retest.md)
