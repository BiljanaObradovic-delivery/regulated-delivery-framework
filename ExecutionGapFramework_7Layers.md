# The Execution Gap Framework — 7 Operational Layers
**Concept360 · Biljana Obradović · © 2026**

Applied to RWA tokenization and regulated fintech delivery programs.

Every regulated program — regardless of technology stack, jurisdiction, or scale — must address seven operational layers. The sequence matters. Skipping a layer doesn't remove it; it relocates the problem to a later, more expensive stage.

---

## Layer Overview

| Layer | RWA Tokenization | Regulated Fintech / Core Banking |
|---|---|---|
| **L0 — Foundation & Operating Model** | Business case, board approval, governance, RACI, OKR framework, budget management, custody model selection | Business case, wave structure, country sequencing, governance, RACI, OKR framework, budget management |
| **L1 — Regulatory & Legal** | MiCA/CASP, DORA, eWpG, BaFin/NCA licensing, MLRO appointment, AML program, multi-jurisdiction mapping | PSD2, per-country regulatory mapping, local banking law, DORA, AML program, MLRO |
| **L2 — Structure & Contracts** | SPV incorporation, legal opinion, token classification, vendor MSA, SLA framework, decision tracking | Vendor contracts, SLA framework, integration agreements, decision tracking, assumption log |
| **L3 — Technical Architecture** | SC design, oracle selection, custody architecture, chain configuration, KYC/KYT integration, API governance | Core system design, middleware strategy, API architecture, vendor governance, KYC/AML pipeline |
| **L4 — Build & Audit** | SC development, SC audit #1, pen test, SAST/DAST, DORA ICT third-party register, ISO 27001 gap | Core build, T24/MuleSoft/Azure integration per country, pen test, DORA ICT, security audit |
| **L5 — Integration & Testing** | End-to-end testing, settlement, PoR baseline, SC audit #2, UAT, rollback plan, gate sign-off | UAT per wave, end-to-end integration, gate sign-off, rollback plan, regulatory test filing |
| **L6 — Go-Live & Operations** | G-OPS gate, hypercare, KPI/KRI monitoring, change & incident management, DORA monitoring, regulatory reporting | Wave activation, hypercare, BAU transition, KPI/KRI monitoring, change & incident management |

---

## Key Principles

**L0 is never optional.**
The foundation — business case, operating model, RACI, OKR framework, and budget management — must be defined before any technical work begins. Most programs fail here, not at L4. A weak L0 means every subsequent layer inherits its structural problems.

**Layers overlap by design.**
L2 architecture begins at 50% of L1. L4 testing begins at 70% of L3. L6 operations begins at go-live per wave — not after the last wave closes. Compliance is embedded as a delivery dependency at each layer, not treated as an external requirement that arrives late.

**Compliance is a delivery task, not a dependency.**
MiCA, DORA, and per-country regulatory requirements are gate criteria — not external dependencies. Missing a compliance gate criterion blocks the gate. It does not simply delay it.

**Vendor governance runs across all layers.**
Multi-vendor coordination, SLA management, escalation ownership, and third-party risk tracking are not L2 or L3 tasks — they are continuous from L0 through L6. Vendor escalation fragmentation is one of the most common causes of operational drift in regulated programs.

**Change and incident management starts at L0.**
A change management process that does not exist at L0 cannot be retrofitted at L5. Incident classification, escalation paths, and regulatory notification obligations must be defined before go-live — not after the first incident.

---
> For the full framework — [Start the conversation](https://biljanaobradovic-delivery.github.io/execution-gap-framework/#contact)

---

*Biljana Obradović · Concept360 · 2026*
*RWA Execution Gap Methodology © Biljana Obradović · Concept360 · 2026*
