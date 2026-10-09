# Phase 1 — Reconnaissance and Scoping

**Goal**: define the perimeter that will actually be tested.

---

## What scoping is not

Scoping is not a scan. It is not a test. It is exploration. The deliverable is a test plan, not a result.

## What scoping produces

- An attack-path map of the system as deployed
- A selection of the applicable cases from the 61-case library
- A costed test plan, with person-days fixed before work starts
- A signed scope, agreed by both parties

## What to map

The perimeter is not the system. It is the chain the system trusts.

- **Components** — LLM, retrieval, memory, tools, external APIs
- **Trust boundaries** — where one component trusts another
- **Credentials** — what flows where, and who can use it
- **Reachability** — what the system can actually reach, not what it declares

## What to select

Not every case applies to every system. A system without long-term memory does not need memory poisoning cases. A system without an MCP chain does not need chain-depth cases.

The selection is made against the components in scope, not against the case count.

## Exit condition

Scope signed by both parties. No testing occurs in this phase.

---

## Related

- [Phase 2 — Attack planning](02-attack-planning.md)
- [Case library](https://github.com/RolandCaushaj/ai-security-assurance)
