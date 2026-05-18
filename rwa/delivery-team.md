# RWA Delivery Team Architecture

**Concept360 · Biljana Obradović · 2026**

> *"No single PM covers all seven layers. The Programme Director is the only role present in all three phases and all eight layers — from the first business case decision to the last audit."*

---

## Key Role Definitions

**Program Director** — Orchestrates all workstreams. Sequences dependencies. Owns escalation. The only role in all three phases and all eight layers.

**SC Engineer** — Writes Solidity/Rust/Vyper. Implements ERC-3643, ERC-20, or ERC-7518. Builds whitelist, PoR integration, pause/upgrade mechanisms, admin wallet multi-sig. Must understand reentrancy, access control, flash loan vectors.

**MLRO** — Named individual. NCA-notified before first investor. Owns all SAR/STR decisions. Key ceremony participant. Cannot be delegated. NCA approval for replacement: 4–8 weeks.

**IAM Engineer** — Role-based access for operational systems. Privileged access for key holders (SC admin, custody multi-sig). Audit trail for every privileged action.

**Key Ceremony Coordinator** — Convenes all multi-sig key holders. Tests signing authority. Documents protocol. Custodian present. Owned by CISO on Small/Medium.

**Exchange Reporting Officer** — Trade reports per CEX rulebook. Suspicious trading escalation to MLRO. Monthly market maker SLA review.

**Regulatory Reporting Manager** *(Large)* — Owns regulatory calendar. Coordinates NCA, DORA, FATCA/CRS, SAR, exchange reporting. Reports to CCO.

---

## PM Profiles — What RWA Programs Need

| Profile | What makes them effective |
|---------|--------------------------|
| **Governance PM** | Designs how the program works. Holds the line under commercial pressure. |
| **Regulatory PM** | Reads MiCA and translates it into a delivery artefact. Compliance as dependency, not checkpoint. |
| **Integration PM** | Operates in the gaps between legal, compliance, tech, and banking. Owns contested outcomes. |
| **Operations PM** | Runs reporting calendar, wallet reconciliation, vendor SLAs without PD involvement. |

---

## Three Phases

| Phase | Layers | Core Team |
|-------|--------|-----------|
| **Pre-Programme** | Layer 0 | Programme Director + Solution Architect + C-suite + external advisors |
| **Implementation** | Layers 1–6 | Full delivery team — scale depends on TVL |
| **Post-Implementation** | Layer 7 (ongoing) | Operations team — PD hands over to Operations PM at Day 30 |

---

## Roles by Layer — Who Must Be Present

| Layer | Cannot proceed without |
|-------|------------------------|
| **L0** | Programme Director · CEO · CFO · CTO · Legal Counsel · Regulatory Advisor · CRO |
| **L1** | + Legal PM · Banking PM · Regulatory PM · CCO · BizDev Director |
| **L2** | + Notary *(RE)* · RICS Valuator *(RE)* · ESG Verifier *(carbon)* · Oracle contracted · Wallet policy drafted |
| **L3** | + Technical PM · CISO · SC Engineers · Cloud/DevOps · SC Audit Firms x2 · Pen Test Firm · Internal Audit · IAM Engineer · DPO · Key Ceremony planned |
| **L4** | + MLRO *(named, NCA-notified)* · Compliance PM · Blockchain Monitoring · KYC/AML Vendor · Custodian · Investor wallet onboarding live |
| **L5** | + Community PM · Investor Support · Exchange Reporting Officer · Key Ceremony completed |
| **L6** | + Banking Partner *(live)* · Market Maker · Liquidity Manager · Transfer Agent · Treasury wallet live · PoR confirmed |
| **L7** | + Operations PM · Regulatory Reporting Manager *(Large)* · ISO 27001 Auditor *(annual)* · External Auditor *(annual)* |


*Full RACI matrix, integration register, and engagement model available upon qualified engagement.*
Biljana Obradović, Concept360, 2026"*

