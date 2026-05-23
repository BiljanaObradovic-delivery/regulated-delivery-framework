# KYC / AML Investor Onboarding — Overview
**MiCA · AMLD6 · FATF Travel Rule · 7-Layer Delivery Framework · Concept360**

---

## What This Is

A structural overview of investor onboarding design for regulated tokenisation platforms — covering investor tier structure, KYC/AML pipeline architecture, SLA model, vendor selection criteria, and Layer 5 critical path.

This is a teaser document. Full detail is available on engagement — see below.

---

## Why Onboarding Architecture Is a Delivery Risk

Investor onboarding is consistently one of the top three programme blockers in regulated tokenisation delivery. Not because the technology is complex — but because the decision architecture is deferred.

The pattern:
- KYC vendor is selected at Layer 4 or later
- EDD trigger logic is not designed until investor pipeline is live
- MLRO is appointed late — creating a compliance bottleneck at exactly the moment volume increases
- Travel Rule configuration is treated as a post-go-live task

**Result:** go-live date holds, but the first investor cannot complete onboarding for 3–6 weeks after launch.

Onboarding architecture must be designed at **Layer 3** and operational by **Layer 5 gate**. It is a critical path item, not a compliance add-on.

---

## Investor Tier Structure

A regulated tokenisation platform serves investors across three tiers. Each tier has distinct KYC/AML requirements, onboarding SLAs, and compliance obligations.

### Tier 1 — Retail Investors

| Dimension | Detail |
|---|---|
| Definition | Natural persons, not professional or institutional classification |
| KYC level | Standard CDD — identity verification, address, source of funds |
| AML screening | KYT screening on wallet address at onboarding and per transaction |
| ISQ required | Yes — investor suitability assessment mandatory under MiCA |
| Custody | Platform custody (segregated) or approved third-party |
| Travel Rule | Applies at ≥€1,000 per transaction |
| Typical SLA | 24–72 hours (automated pipeline, manual review for exceptions) |
| Re-verification | Triggered by risk score change, regulatory update, or annual cycle |

### Tier 2 — Professional Investors

| Dimension | Detail |
|---|---|
| Definition | Entities meeting MiCA professional investor criteria (assets, expertise, frequency) |
| KYC level | Enhanced CDD — entity documentation, UBO chain, directorship verification |
| AML screening | Enhanced KYT, source of wealth documentation, jurisdiction risk assessment |
| ISQ required | Simplified or waived depending on MiCA classification |
| Custody | Platform or third-party; segregation documented |
| Travel Rule | Full FATF compliance required |
| Typical SLA | 3–7 business days (manual review elements) |
| Re-verification | Annual minimum; triggered by material change in entity structure |

### Tier 3 — Institutional Investors

| Dimension | Detail |
|---|---|
| Definition | Regulated entities (banks, funds, insurance), family offices, sovereign wealth |
| KYC level | Full EDD — complete UBO chain, regulatory status of entity, board resolution |
| AML screening | Deep KYT, correspondent relationship assessment, PEP/sanctions chain |
| ISQ required | Not applicable — superseded by institutional due diligence |
| Custody | Third-party custodian typically required; MiCA Art.70 segregation mandatory |
| Travel Rule | Full FATF + cross-border VASP data exchange |
| Typical SLA | 10–20 business days (MLRO sign-off required) |
| Re-verification | Annual; triggered by ownership change or regulatory event |

---

## KYC/AML Pipeline Architecture

The onboarding pipeline has three sequential stages. Each stage has a defined owner, SLA, and failure mode.

```
Stage 1 — Identity Verification
  Input:   Investor submits identity documents + wallet address
  Process: KYC vendor (automated): document check, liveness, database match
  Output:  Pass / Refer / Reject
  SLA:     Automated: <5 minutes · Manual review: 24h
  Failure: High false rejection rate → volume bottleneck → MLRO queue overflow

Stage 2 — Risk Assessment
  Input:   KYC pass + wallet address
  Process: KYT vendor: wallet risk score (Low / Medium / High / Critical)
           AML: PEP/sanctions screening, source of funds assessment
           EDD trigger: if High/Critical risk or Tier 3
  Output:  Risk profile assigned · EDD flag if triggered
  SLA:     Automated: <10 minutes · EDD: 3–10 business days
  Failure: KYT API latency or downtime → Travel Rule gap → regulatory exposure

Stage 3 — MLRO Approval (EDD cases)
  Input:   EDD case file from Stage 2
  Process: MLRO review: source of wealth, business purpose, risk acceptance
           SAR decision if suspicious indicators present
  Output:  Approved / Rejected / SAR filed
  SLA:     5–15 business days (MLRO capacity is the constraint)
  Failure: MLRO not appointed at programme start → all EDD cases queue with no owner
```

---

## KYC/AML Vendor Selection Criteria

Without naming specific vendors, the selection framework covers six dimensions:

**1. Coverage**
Does the vendor cover all jurisdictions in scope? Cross-border programmes (EU + UAE, EU + APAC) require global coverage. Vendors with strong EU coverage often have gaps in MENA or APAC.

**2. Integration model**
API-first or batch? For a tokenisation platform with real-time onboarding, API-first with webhook callbacks is required. Batch processing creates SLA gaps.

**3. ERC-3643 / token platform compatibility**
Can the vendor output a structured eligibility signal that feeds directly into the smart contract whitelist? Manual bridging between KYC output and token eligibility creates an operational gap.

**4. False rejection rate baseline**
Request vendor benchmark data for false rejection rates by document type and jurisdiction. Above 5% creates a material compliance and operational risk. Establish contractual SLA for false rejection rate.

**5. Travel Rule capability**
FATF Travel Rule compliance requires originator/beneficiary VASP data exchange. Not all KYC vendors cover Travel Rule — it may require a separate integration.

**6. EDD and MLRO workflow support**
Does the vendor provide a case management interface for MLRO review? Manual EDD processes (email, spreadsheet) do not scale and create audit trail gaps.

---

## Layer 5 Critical Path

Layer 5 (Integration & Testing) is where onboarding goes live for the first time. These items are on the critical path — delay on any one of them delays the Layer 5 gate:

```
Week 1–2   KYC vendor API integration complete · Sandbox testing passed
Week 2–3   KYT vendor integrated · Risk scoring tested with sample wallet addresses
Week 3     Travel Rule configuration tested (originator + beneficiary flows)
Week 3–4   ISQ flow built and tested (Retail tier)
Week 4     EDD workflow tested end-to-end (Tier 3 scenario)
Week 4     MLRO review interface live · MLRO trained on workflow
Week 5     False rejection rate baseline established (minimum 100 test cases)
Week 5     Re-verification trigger logic tested
Week 6     Full onboarding regression test: all three tiers, all failure modes
           → Layer 5 gate: Onboarding operational sign-off
```

**MLRO appointment is a Layer 4 blocker building.** If MLRO is not appointed before Layer 4 ends, the EDD workflow cannot be signed off at Layer 5, and the CASP application is incomplete.

---

## Typical Bottleneck Patterns

**Pattern 1 — KYC vendor selected too late**
Vendor evaluation starts at Layer 4. Integration takes 4–6 weeks. Testing takes 2–3 weeks. Layer 5 gate is missed by 6–8 weeks. Mitigation: vendor shortlist at Layer 2, selection at Layer 3.

**Pattern 2 — MLRO appointment deferred**
MLRO is a named individual, NCA-notified, with documented responsibilities. Finding, appointing, and notifying takes 4–8 weeks. If deferred to Layer 4, all EDD cases queue with no owner at exactly the moment the first institutional investors are onboarding.

**Pattern 3 — Travel Rule treated as post-go-live**
Travel Rule is a transaction-level obligation. Configuring VASP data exchange after go-live means the first transactions are non-compliant. Regulatory exposure from Day 1.

**Pattern 4 — False rejection rate not baselined**
First sign of a false rejection spike is usually a complaint from a known investor. By then, 15–30 legitimate applications may have been rejected. Remediation requires manual re-processing and investor communication.

**Pattern 5 — EDD volume underestimated**
If the investor pipeline includes institutional or cross-border investors, EDD cases can be 20–40% of total volume. MLRO capacity at 1 person handling 10–15 cases/week creates a 3–4 week backlog at scale. Plan MLRO resource against projected investor tier mix, not total volume.

---

## Key References

- MiCA Art.83 — Market abuse monitoring (KYT obligation)
- AMLD6 Art.20 — Suspicious transaction reporting
- FATF Travel Rule — Originator/beneficiary data for transactions ≥€1,000
- MiCA investor classification criteria
- eWpG — Investor eligibility for electronic securities (Germany)
- GDPR Art.6 — Lawful basis for KYC data processing

---

## More Detail

Concept360 works with tokenisation platforms and infrastructure providers on post-licensing operational setup — building the delivery structures, compliance workflows, governance models, and control frameworks that make a regulated digital asset operation functionally ready.

If you are past the licensing stage and need to build what was promised in the application, that is where this work starts.

→ [biljana.obradovic@concept360.rs](mailto:biljana.obradovic@concept360.rs)
→ [linkedin.com/in/biljana-obradovic-28390a8](https://linkedin.com/in/biljana-obradovic-28390a8)

---

*Part of the 7-Layer RWA Delivery Framework · Concept360 · 2026*
*© Biljana Obradović · All rights reserved · For discussion purposes only*
