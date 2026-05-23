# Banking Access & SPV Screening — Overview
**MiCA · eWpG · SPV Structure · 7-Layer Delivery Framework · Concept360**

---

## What This Is

A structural overview of SPV banking access as a delivery workstream — covering why banks reject tokenisation SPVs, the parallel screening strategy, timeline expectations, documentation requirements, and what a PM must track from Week 1.

This is a teaser document. Full detail is available on engagement — see below.

---

## Why Banking Access Is the Most Underestimated Blocker

In every regulated tokenisation programme, banking access for the SPV is on the critical path. It is also consistently the workstream that starts latest.

The pattern:
- Programme starts at Layer 0
- Banking access is flagged as a Layer 4 or Layer 5 task
- First bank approach happens at Layer 3 or later
- First rejection arrives 6–8 weeks after first approach
- Second approach starts 2 weeks after first rejection
- Go-live date is missed by 3–5 months

**Banking access must start at Layer 1.** Not Layer 3. Not Layer 4. Layer 1 — in parallel with legal structuring and regulatory work. It is a 6–20 week process with no acceleration mechanism once it starts.

---

## Why Banks Reject Tokenisation SPVs

Understanding the rejection logic is the first step in building a screening strategy that works.

**Reason 1 — AML programme not in place**
The SPV cannot open a bank account without a board-approved AML programme and an appointed MLRO. Banks require evidence of AML controls before account opening. If these are not in place at the time of the first banking approach, the application fails at screening.

**Reason 2 — Business model not understood**
Tokenisation is new. Many bank compliance teams do not have a framework for assessing tokenised securities or digital asset SPVs. The application is referred up the chain, assessed by people unfamiliar with the model, and rejected on risk grounds — not legal grounds.

**Reason 3 — Token classification ambiguous**
If the token's MiCA classification (ART, EMT, or security token under eWpG) is not confirmed and documented at the time of the banking approach, the bank cannot assess the product. Ambiguity is treated as risk.

**Reason 4 — Jurisdiction mismatch**
A German SPV holding eWpG-registered electronic securities needs a bank that understands the eWpG framework. A Luxembourg SPV needs CSSF-regulated banking context. Approaching a bank without jurisdiction-specific context results in a generic rejection.

**Reason 5 — Corporate structure opacity**
UBO chain not fully documented. Ownership structure involves offshore entities. Beneficial ownership is unclear or multi-layered. Banks apply enhanced due diligence and reject at the first gap.

**Reason 6 — Infrastructure provider relationship not established**
The bank needs to understand the relationship between the issuer SPV, the infrastructure provider (CASP), and the token platform. If this relationship is not documented — who holds the CASP licence, what the platform does, what the SPV's role is — the bank cannot model the risk.

---

## The Parallel Screening Strategy

A single-bank approach to SPV banking is a programme risk. One rejection sets the programme back 6–10 weeks. The correct strategy is parallel engagement of minimum three banks from Week 1.

### Why Three Banks Minimum

- Rejection rate for first-time tokenisation SPV applications at major banks is significant — plan for it, not around it
- Each rejection and re-approach cycle takes 6–10 weeks
- Running three in parallel means at least one approval is statistically probable within the first screening round
- It also creates negotiating leverage: a bank that knows you are talking to others moves faster

### Bank Selection Criteria

Not all banks are equal for tokenisation SPV banking. Selection criteria:

| Criterion | What to Look For |
|---|---|
| Digital asset experience | Bank has existing tokenisation or crypto-asset clients |
| eWpG/MiCA familiarity | Compliance team has framework for electronic securities |
| Jurisdiction alignment | Regulated in the same jurisdiction as the SPV |
| Account opening timeline | Some banks take 12 weeks; others 6 — ask before engaging |
| Settlement rail compatibility | ISO 20022, SEPA, and any jurisdiction-specific payment rails |
| Promotional bank model | Some tokenisation-friendly banks offer structured SPV banking products |

### Engagement Sequencing

```
Week 1–2    Identify 3–5 candidate banks
            Prepare information pack (see Documentation section below)
            Initiate contact with relationship managers — not compliance directly

Week 2–4    Initial meetings: explain SPV structure, token classification, 
            AML programme, infrastructure provider relationship
            Submit information pack

Week 4–8    Bank compliance review
            Expect information requests — respond within 48h (slow response = deprioritised)
            Do not wait for one bank before approaching the next

Week 6–10   First decisions expected
            Rejection: document reasons, address gaps, approach next candidate
            Approval in principle: move to account opening documentation

Week 8–14   Account opening documentation
            KYB, UBO chain, board resolutions, authorised signatories
            AML programme evidence
            CASP relationship documentation

Week 12–20  Account live and tested
            Settlement rails tested
            Integration with platform confirmed
```

**Total realistic timeline: 8–20 weeks from first approach to live account.** Starting at Layer 3 means arriving at G-OPS Gate without a bank account.

---

## Documentation — What the Bank Needs

A complete banking information pack reduces the rejection rate and speeds the compliance review. It should be prepared before the first bank approach and maintained as a living document throughout the screening process.

**Corporate Documentation**
- Certificate of incorporation, articles of association
- Register of directors and shareholders
- UBO declaration (all beneficial owners ≥25%)
- Group structure chart — issuer SPV, infrastructure provider, CASP relationship
- Board resolution authorising account opening

**AML & Compliance**
- Board-approved AML programme (summary for external use)
- MLRO appointment letter and contact details
- KYC/AML procedures summary
- Evidence of regulatory engagement (NCA correspondence, CASP application status)

**Business & Product**
- SPV business description — what it does, what it does not do
- Token classification document — MiCA asset type, eWpG classification
- Whitepaper (draft or approved)
- Infrastructure provider overview — CASP licence, platform description
- Projected transaction volume and flow of funds

**Financial**
- Projected P&L (3 years)
- Capitalisation evidence
- Source of funds for initial capitalisation

---

## What the PM Tracks — Week by Week

Banking access is not a legal workstream. It is a delivery workstream with a PM owner.

**Week 1**
- Bank longlist created (5+ candidates)
- Information pack preparation started
- Legal confirms SPV structure is bankable
- AML programme and MLRO confirmed (if not: this is now the priority)

**Week 2**
- First bank contacts initiated (minimum 3 simultaneous)
- Information pack version 1 complete
- Response tracking log active

**Week 4**
- First meetings completed
- Information requests logged and assigned
- Bank 4 and 5 initiated if any of first 3 not progressing

**Week 6**
- Compliance review status from each bank — push for update
- Any rejection: document reason, assess if addressable, initiate replacement candidate
- Programme Director notified if all three banks in uncertainty

**Week 8**
- First decisions expected
- Approval in principle: move to account opening documentation immediately
- Rejection pattern analysis: if 2+ rejections share the same reason — address root cause, do not just approach more banks

**Week 12**
- If no approval in principle yet: escalate to Programme Director
- Review information pack for gaps
- Consider specialist banking intermediary

**Week 14–20**
- Account opening documentation submitted
- Settlement rail testing scheduled
- Integration test with platform planned

---

## G-OPS Gate — Banking Blocker

SPV bank account confirmed and live is a **G-OPS Gate blocker**. The programme cannot proceed to Layer 6 (Go-Live) without:

- Bank account open and operational
- Settlement rails tested
- Platform integration confirmed
- First test transaction completed

If banking access is not confirmed at G-OPS Gate, go-live is deferred. No exceptions.

---

## Key References

- MiCA Art.59–68 — CASP authorisation (relevant to bank's assessment of infrastructure provider)
- eWpG — Electronic securities register (Germany) — relevant for bank's product assessment
- AMLD6 — AML obligations (required for bank's compliance assessment)
- FATF Recommendations — Source of funds and UBO documentation standards

---

## More Detail

Concept360 works with tokenisation platforms and infrastructure providers on post-licensing operational setup — building the delivery structures, compliance workflows, governance models, and control frameworks that make a regulated digital asset operation functionally ready.

If you are past the licensing stage and need to build what was promised in the application, that is where this work starts.

→ [biljana.obradovic@concept360.rs](mailto:biljana.obradovic@concept360.rs)
→ [linkedin.com/in/biljana-obradovic-28390a8](https://linkedin.com/in/biljana-obradovic-28390a8)

---

*Part of the 7-Layer RWA Delivery Framework · Concept360 · 2026*
*© Biljana Obradović · All rights reserved · For discussion purposes only*
