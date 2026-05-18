# The 7-Layer Governance Model
**Applied to RWA Tokenisation and Core Banking Delivery programmes.**

Every regulated programme — regardless of technology stack, jurisdiction, or scale — must address seven operational layers. The sequence matters. Skipping a layer doesn't remove it; it relocates the problem to a later, more expensive stage.

---

## Layer Overview

| Layer | RWA Tokenisation | Core Banking Delivery |
|---|---|---|
| **L0 — Operating Model** | Governance, RACI, decision rights, custody model selection | Governance, RACI, wave structure, country sequencing |
| **L1 — Regulatory & Legal** | MiCA, DORA, eWpG, BaFin licensing, AML programme | Per-country regulatory mapping, PSD2, local banking law |
| **L2 — Structure & Contracts** | SPV, legal opinion, token classification, vendor MSA | Vendor contracts, SLA framework, integration agreements |
| **L3 — Technical Architecture** | SC design, oracle selection, custody architecture, chain config | Core system design, middleware strategy, API architecture |
| **L4 — Build & Audit** | SC development, SC audit #1, pen test, SAST/DAST | Core build, T24/MuleSoft/Azure integration per country |
| **L5 — Integration & Testing** | End-to-end, settlement, PoR baseline, SC audit #2 | UAT, end-to-end per wave, gate sign-off, rollback plan |
| **L6 — Go-Live & Operations** | G-OPS gate, hypercare, steady state, DORA monitoring | Wave activation, hypercare, BAU transition, Date 2 |

---

## Key Principles

**Layer 0 is never optional.**
The operating model, RACI, and decision rights must be defined before any technical work begins. This is where most programmes fail — not at Layer 4.

**Layers overlap by design.**
L2 architecture begins at 50% of L1. L4 testing begins at 70% of L3. L6 operations begins at L6 go-live per wave — not after the last wave closes.

**Compliance is a delivery task, not a dependency.**
MiCA, DORA, and per-country regulatory requirements are embedded as gate criteria — not treated as external dependencies that arrive late.

---

## Gate Logic

Each layer has explicit exit criteria. A gate cannot be passed without documented sign-off. Missing a gate criterion does not delay the gate — it blocks it.

The full gate framework — including per-layer delivery plans, KPI/KRI definitions, RACI matrices, and escalation logic — is proprietary to Concept360.

> For the full framework — contact me directly.

---

*Biljana Obradović · Concept360 · 2026*
