# LLM Red Team Playbook

How an adversarial engagement against an LLM, RAG, or agent system is 
run end to end. Reconnaissance, attack planning, execution, reporting, 
and retest.

> **Maintained by [Roland Caushaj](https://github.com/RolandCaushaj)**, 
> security researcher at [Logic4Hack](https://logic4hack.com) — 
> adversarial testing of LLM, RAG and agent systems.
>
> This playbook describes how we run client engagements. The case 
> library, execution runners, and detection criteria are proprietary 
> and shared under NDA.

---

## What this playbook is

Testing an AI system is not a scan. It is a structured engagement with 
defined phases, artefacts, and closure conditions. This playbook 
documents how we run one.

The phases are not a checklist — they are a method. Each phase produces 
an artefact that the next phase consumes, and each has a defined exit 
condition.

---

## Phase 1 — Reconnaissance and scoping

**Goal**: define the perimeter that will actually be tested.

The perimeter of an AI system is not the model. It is the chain of 
components the model trusts: retrieval, memory, tools, MCP servers, 
external APIs, credentials.

In this phase:

- Map the architecture as deployed, not as documented
- Identify trust boundaries between components
- Enumerate what the system can actually reach, not what it declares
- Select the applicable subset of the case library
- Produce a costed test plan

**Exit condition**: an attack-path map and a signed scope.

No testing occurs in this phase. Scoping is exploration.

---

## Phase 2 — Attack planning

**Goal**: select the cases and the execution strategy.

Not every case applies to every system. A system without long-term 
memory does not need memory poisoning cases. A system without an MCP 
chain does not need chain-depth cases.

In this phase:

- Match each applicable case to the components in scope
- Define the pass/fail criterion for each selected case
- Decide which cases run in isolation and which run in sequence
- Define what evidence each case must produce
- Agree on test windows and declared source IPs with the client's SOC

**Exit condition**: a case plan with per-case criteria, agreed with 
the client's engineering team.

---

## Phase 3 — Execution

**Goal**: run the cases, produce evidence, and raise findings.

Execution is manual, driven by named researchers. The case library 
provides the attack objectives and the validation criteria. The 
runners execute and capture evidence.

During execution:

- Cases run against the live system in the agreed windows
- Each case produces a raw artefact (request, response, timing)
- A finding is raised only on a fail, with a reproducible PoC
- Critical findings are communicated within 4 hours of confirmation
- High findings within 24
- Daily status update on the agreed channel

**Exit condition**: all planned cases have run, and all findings have 
raw evidence attached.

---

## Phase 4 — Reporting

**Goal**: produce a report that procurement, auditors, and insurers 
can read.

A finding without a reproducible PoC is not a finding. A report without 
classification is not usable by procurement.

Every finding ships with:

- **ID and severity** — assigned to the weakness, not the detection event
- **Business impact** — what the weakness enables, in plain language
- **Reproduction** — step-by-step, with a runnable command
- **Classification** — OWASP MCP, OWASP LLM, MITRE ATLAS, NIST AI RMF, 
  ISO/IEC 42001
- **Remediation** — with a named owner
- **Closure** — a harness that asserts the property, exit 0 or 1

The report and its executive summary are delivered in English. Another 
EU language is available on request, agreed at scoping.

**Exit condition**: draft report delivered within 5 business days of 
test end. Final within 3 days of client feedback.

---

## Phase 5 — Readout and retest

**Goal**: close the loop.

Two readouts are delivered:

- **Technical** — with the client's engineering team
- **Executive** — with leadership

After remediation, the client can request a retest. Retest runs the 
same cases that raised findings, verifies each closure, and produces 
a retest addendum stating what closed and what did not.

Retest is included from single-system level up, within 30 days of the 
client's remediation notice.

**Exit condition**: retest addendum delivered, or 30 days elapsed.

---

## Engagement artefacts

Every engagement produces, at minimum:

- **Scope attestation** — what was tested, and what was not
- **Attack-path map** — the perimeter as resolved
- **Finding sheets** — one per finding, in the standard format
- **Evidence pack** — execution logs, raw artefacts, test timeline
- **Executive summary** — one page, for leadership
- **Retest addendum** — if retest is requested

The evidence pack is built to be handed directly to procurement, an 
auditor, or an insurer. It is not rewritten before delivery.

---

## Engagement levels

Four service levels are published, with fixed price ranges and fixed 
person-days. Each level publishes its fee, its person-days, and the 
resulting day rate — so the number can be compared to any other quote.

| Level | Scope | Duration |
|---|---|---|
| 01 — Maturity & Scoping | Architecture and trust-boundary review | 3 days |
| 02 — Single-System Audit | One system, closed perimeter, full PoCs | 1–2 weeks |
| 03 — Complete Audit | Full penetration testing across all domains | 3–4 weeks |
| 04 — Adversarial Red Teaming | Multi-agent chains, adaptive scenarios | 4–6 weeks |

Continuous assurance options are available for systems that change 
every release. Details on request.

---

## Data handling

Testing runs on hardware we own, in an isolated environment dedicated 
to a single engagement at a time. No client data reaches a third-party 
model API. No subprocessors are declared in the DPA.

- On-premises execution on owned DGX infrastructure
- Cross-model testing on locally hosted models
- Artefacts retained for 30 days after delivery, then destroyed
- Immediate destruction on written request, with confirmation

---

## Disclosure policy

We publish techniques and research. Client-identifiable detail is 
published only with the client's written consent. Any CVE or 
conference material is anonymized and approved by the client in advance.

---

## Related repositories

- [mcp-security-reference](https://github.com/RolandCaushaj/mcp-security-reference) — 
  security considerations for MCP architectures
- [mcp-security-audit](https://github.com/RolandCaushaj/mcp-security-audit) — 
  methodology for auditing MCP chains
- [ai-security-assurance](https://github.com/RolandCaushaj/ai-security-assurance) — 
  the 61-case library across 8 domains

---

## About

[Logic4Hack](https://logic4hack.com) is an AI security firm 
specializing in adversarial testing of LLM, RAG, agent, and MCP 
systems. Two named researchers deliver every engagement. No 
subcontracting, no pyramid.

[Get in touch](https://logic4hack.com/contact) if you are shipping 
an AI system into production and need to prove its security to a 
customer, an auditor, or an insurer.

---

## License

Content in this repository is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). 
Code examples, if any, are licensed under MIT.

---

**Last updated**: October 2026  
**Status**: Active — playbook refined as engagement experience grows
