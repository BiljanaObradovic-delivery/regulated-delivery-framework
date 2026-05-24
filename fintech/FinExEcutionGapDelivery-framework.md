# 7 Layers — Fintech & Bank Execution Gap Program Delivery

## Multi-Country, Multi-Vendor, Multi-Jurisdictions Implementation Framework

**© Biljana Obradović · Concept360 · 2026**

---

> This framework adapts the 7 Operational Layers methodology for complex banking technology programmes — core banking transformations, loan origination systems, CRM rollouts, and any multi-country, multi-vendor implementation. Layer 0 is shown with full gate detail. Layers 1–7 follow the same structure.

---

## The 7 Layers — Bank & Fintech Adaptation

| # | Layer | What it covers | Where programmes get stuck |
| --- | --- | --- | --- |
| 0 | **Economic Viability** | Does this programme make business sense? Operating model, country selection, wave sequencing, vendor strategy, budget confirmed. | Teams skip Layer 0 and discover the wrong operating model in Layer 3. Country sequencing decided by politics, not dependency logic. |
| 1 | **Asset / Scope** | Vendor contracts signed, regulatory requirements mapped per country, RACI finalised, Master Document List created. | Vendor contract delays cascade into go-live. Country-specific regulatory gaps discovered at testing — months too late. |
| 2 | **Solution Architecture** | Technical architecture, integration design, data migration strategy, compliance architecture approved per country. | Architecture decision made without Compliance sign-off. Group CTO approval delayed — wave blocked. Country-specific deviations not documented. |
| 3 | **Technical Build** | Core System configuration, integration build, SIT, data migration pilot. SAST completed by vendor. | The last 20% takes longer than the first 80% combined — every time. Edge cases in credit policy per country. Integration edge cases under concurrent load. |
| 4 | **Testing & Compliance** | UAT per wave, penetration test, performance test, parallel run, data migration test, DAST, regression. | Parallel run reveals that the system works — but doesn't match how people actually work. Three tests always started too late: pen test, DRP, data migration. |
| 5 | **Go-Live Preparation** | Rollout plan, rollback plan, support rehearsal, training complete. Three sign-offs nobody tracks: Business Process Owner, Regulatory Reporting Dry Run, Vendor Support Transition. | Support team not rehearsed before go-live. Business process owners not signed off. Wave dependency not validated — one country's delay cascades. |
| 6 | **Go-Live (per wave)** | First transactions per country, smoke test (auto rollback if fail), hypercare activated, rollback window defined. | Smoke test fails with no rollback procedure ready. User adoption drops in Week 1 — nobody measured it. Hypercare team not confirmed per country before go-live. |
| 7 | **Governance & Operations** | BAU per country, user adoption monitoring, hypercare exit, Operational Stability Date. Two dates: last go-live (Date 1) and operational stability across all countries (Date 2). **Runs across ALL layers from day one.** | Steering committee given one date — and surprised by the second, 6–12 months later. User adoption stays low — business case at risk. No clear owner per country post-hypercare. |

> *"The most dangerous assumption in multi-country delivery is: 'We will manage it.' Ask every steering committee one question before go-live: how many countries can this programme absorb failing simultaneously? If the answer is 'none' — you need waves."*

---

## Layer 0 — Gate Detail

**Entry question:** Is there a documented economic case with viable revenue model, realistic country sequencing, and operating model confirmed?

**Where it gets stuck:** Teams start with the anchor country and never document the wave dependency rules. Country N+1 goes live before Country N is stable. The programme never has one go-live — it has many. Nobody planned for that.

**Gate — cannot proceed to Layer 1 without:**

1. Business case approved — CEO, CFO, Board
2. Country list confirmed — wave sequencing documented with rationale
3. Operating model confirmed — in-house vs vendor-led, governance structure
4. Budget approved — CapEx per wave + OpEx steady-state estimate
5. Vendor shortlist approved — Core System, Middleware, integration partners
6. Programme Director appointed — single accountable owner across all waves

*Layers 1–7 follow the same structure: entry question, gate criteria, PM responsibility, key risks, and failure patterns. Full reference in the private repository.*

---

## Three Risks That Decide Programme Success

**Wave sequencing failure.** The anchor country always pays for the mistakes the programme made before it went live. Subsequent waves absorb the lessons — if the programme documents them. Wave Lessons Learned is not optional. It is the mechanism that converts Wave 1 pain into Wave 2 efficiency.

**The last 20% problem.** Every LOS, core banking, and CRM implementation reaches 80% completion — then stalls. The last 20% contains: edge cases in credit policy, integration edge cases under concurrent load, country-specific configuration that differs from the template, and UAT findings that are not bugs but requirement gaps discovered six months late. Plan the last 20% as its own phase with senior resources and a time-box.

**Three sign-offs nobody tracks.** Go-live checklists cover UAT, infrastructure readiness, and data migration. They rarely cover: (1) Business Process Owner confirmation that the system matches how operations actually run — not just that UAT passed. (2) Regulatory Reporting Dry Run — validated against real transactions before go-live, not after. (3) Vendor Support Transition — who answers the phone at 11pm, in writing, before cutover. All three show up in the first 90 days. None of them are on the standard checklist.

*Full risk register — wave dependency mapping, integration risk, compliance risk — in the private repository.*

---

## Relationship to the RWA Framework

This framework shares the same 7-layer methodology as the [RWA Delivery Framework](https://github.com/BiljanaObradovic-delivery/rwa-delivery-framework/blob/main/Seven_Layers_Quick_Reference.md). Layer 3 (Technical Build) and Layer 4 (Testing) adapt for the programme type — smart contracts and oracle integration in RWA, core system configuration and parallel run in bank delivery. The gate logic, overlap rules, and failure patterns are structurally identical.

---

→ [biljana.obradovic@concept360.rs](mailto:biljana.obradovic@concept360.rs)  
→ [linkedin.com/in/biljana-obradovic-28390a8](https://linkedin.com/in/biljana-obradovic-28390a8)

*Attribution required: "7 Operational Layers of RWA Programmes — Biljana Obradović, Concept360, 2026"*
