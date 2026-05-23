# Custody Sequencing Overview
**MiCA Art.70 · Wallet Architecture · Key Ceremony · 7-Layer Delivery Framework · Concept360**

---

## What This Is

A structural overview of custody decision-making and wallet architecture sequencing for regulated tokenisation infrastructure providers. Covers the custody model decision, wallet types, key ceremony coordination, and how custody sequencing maps to the 7-Layer Delivery Framework.

This is a teaser document. Full detail is available on engagement — see below.

---

## Why Custody Sequencing Matters

Custody is not a technical decision made at Layer 3. It is a **legal, regulatory, and operational decision made at Layer 2** — and it locks every downstream workstream.

Get it wrong or late and the consequences compound:

- Layer 3 (Technical Architecture) cannot be finalised without knowing the custody model
- Smart contract audit scope depends on custody architecture
- Layer 5 investor onboarding requires custody infrastructure live and tested
- G-OPS Gate (Layer 6) cannot be signed off without key ceremony completed and cold/hot ratio confirmed

**Custody decision is a Layer 2 gate blocker.** It cannot be deferred.

---

## The Custody Decision Tree

### Step 1 — Model Selection

Three models available under MiCA Art.70:

| Model | Description | When It Fits |
|---|---|---|
| **Self-Custody** | Infrastructure provider holds keys directly via HSM | Full control, highest operational burden, requires in-house key management capability |
| **Third-Party Custody** | Licensed custodian holds keys (MPC/HSM) | Fastest path to MiCA Art.70 compliance; custodian must hold valid BaFin/NCA licence |
| **Hybrid** | Platform keys for operational wallets; third-party for investor asset segregation | Most common for infrastructure providers with multiple issuer types |

**Decision criteria:**
- Does the provider have in-house HSM capability?
- What is the issuer's regulatory requirement (eWpG, MiCA, VARA)?
- Does the investor profile require segregated custody (institutional vs retail)?
- What is the timeline pressure — third-party custody is faster to deploy

This decision is made at **Layer 2 (Asset & Legal Structure)** and signed off by CISO + Legal PM before Layer 3 begins.

---

### Step 2 — Wallet Architecture

A regulated tokenisation platform requires multiple wallet types. Each has a distinct role, risk profile, and custody requirement:

**Platform Wallets (Infrastructure Provider)**

| Wallet | Function | Storage | Standard |
|---|---|---|---|
| SC Registry Wallet | eWpG electronic securities registry filing | Cold | eWpG, KWG |
| Platform Hot Wallet | Gas fees, daily operational transactions | Hot (≤20%) | DORA Art.9 |
| Oracle Coordination Wallet | NAV feed signing, PoR coordination | Warm | MiCA Art.76 |

**Issuer Wallets (Per Token / Per Issuer)**

| Wallet | Function | Storage | Standard |
|---|---|---|---|
| Treasury Wallet | Primary token holdings, mint/burn authority | Cold (≥80%) | MiCA Art.70 |
| SPV Distribution Wallet | Yield and dividend distribution | Warm | MiCA |
| Investor Custody Wallet | Segregated per investor (institutional) | External custodian | MiCA Art.70 |

**KRI: Cold/Hot Ratio ≥ 80% Cold at all times.** Monitoring must be active from Day 1 of live operations. Alert threshold configured before G-OPS Gate.

---

### Step 3 — Multi-Signature Model

Treasury and registry wallets operate on a multi-signature model. Minimum configuration:

- **3-of-5 multi-sig** for treasury wallet (3 keyholders must sign any transaction)
- **2-of-3 multi-sig** for operational wallets
- Key shards distributed across geographically separated HSMs
- No single point of failure in the signing chain

Multi-sig configuration is defined at **Layer 3** and tested at **Layer 5**.

---

## Key Ceremony — Coordination Sequence

The key ceremony is the most operationally sensitive event in the custody setup. It cannot be rushed, delegated informally, or repeated without significant cost.

**Prerequisites (must be confirmed before ceremony date is set):**
- Custody model decision signed off (Layer 2)
- HSM hardware procured and tested
- All keyholders identified, fit & proper confirmed
- Ceremony protocol documented and reviewed by Legal
- CISO sign-off on ceremony procedure
- Witnesses confirmed (minimum 2 independent)

**Ceremony sequence:**

```
Week -4   Custody model approved · HSM procured
Week -3   Keyholder identification confirmed · Legal review of ceremony protocol
Week -2   HSM tested · Environment security audit · Witnesses confirmed
Week -1   Dry run (no live keys) · Documentation finalised
Day 0     Key ceremony: key generation, shard distribution, multi-sig setup, HSM verification
Day +1    PoR test: verify custody wallet operational · Oracle coordination wallet activated
Day +3    Cold/hot ratio baseline established and KRI configured
Day +7    Key ceremony documentation signed, witnessed, stored (WORM audit log)
```

**Common failure pattern:** Ceremony scheduled before custody model is legally confirmed. Legal disputes the model post-ceremony → ceremony must be repeated. Cost: 4–6 weeks delay.

---

## Layer-by-Layer Custody Sequencing

```
L0 — Governance
     Custody governance policy established
     CISO identified as custody owner

L1 — Regulatory
     MiCA Art.70 requirements documented
     eWpG custody obligations confirmed (if DE jurisdiction)
     Third-party custodian licence verification initiated

L2 — Asset & Legal Structure  ← CUSTODY DECISION GATE
     Self / Third-Party / Hybrid model decided
     Legal structure for asset segregation confirmed
     Custodian contracted (if third-party)
     ⛔ Gate blocker: No custody model = Layer 3 cannot start

L3 — Technical Architecture
     Wallet architecture designed (platform + issuer wallets)
     Multi-sig model defined
     HSM specification confirmed
     Smart contract audit scope includes custody architecture

L4 — Build & SC Audit
     Wallet infrastructure deployed (non-production)
     Multi-sig configuration tested
     SC audit covers custody-related contract functions
     Key ceremony scheduled

L5 — Integration & Testing  ← KEY CEREMONY
     Key ceremony completed (see sequence above)
     PoR infrastructure live and tested
     Cold/hot ratio KRI configured
     Investor custody onboarding tested end-to-end
     External custodian integration verified (MiCA Art.70 segregation)

L6 — Go-Live (G-OPS Gate)  ← CUSTODY SIGN-OFF
     Key ceremony documentation in audit log
     Cold/hot ratio ≥80% confirmed
     PoR reconciliation active and passing
     Annual custody audit scheduled
     ⛔ Gate blocker: Key ceremony incomplete = G-OPS Gate blocked

L7 — Steady State
     Monthly PoR reconciliation vs bank records
     Annual custody audit (CISO owner)
     Cold/hot KRI monitoring continuous
     Key rotation schedule active
```

---

## PM Checklist — Custody Workstream

**Layer 2 (complete before L3 starts)**
- [ ] Custody model decision documented and signed off (CISO + Legal PM)
- [ ] MiCA Art.70 segregation requirements mapped to chosen model
- [ ] Third-party custodian contracted and licence verified (if applicable)
- [ ] eWpG custody obligations confirmed (DE jurisdiction)

**Layer 3**
- [ ] Wallet architecture document produced (all wallet types, roles, storage class)
- [ ] Multi-sig configuration defined (threshold, keyholder count, geography)
- [ ] HSM specification confirmed and procurement initiated
- [ ] SC audit brief includes custody architecture scope

**Layer 4**
- [ ] Wallet infrastructure deployed in non-production
- [ ] Multi-sig tested (all signing paths, including failure scenarios)
- [ ] Key ceremony date set (minimum 4 weeks lead time from L4 start)
- [ ] Keyholders formally identified and confirmed

**Layer 5**
- [ ] Key ceremony completed per protocol
- [ ] Key ceremony documentation signed, witnessed, and stored
- [ ] PoR infrastructure live: oracle connected, Merkle tree active
- [ ] Cold/hot ratio baseline established (target ≥80% cold)
- [ ] KRI configured: alert if cold ratio drops below 80%
- [ ] Investor custody onboarding tested (end-to-end)
- [ ] External custodian MiCA Art.70 segregation verified

**Layer 6 / G-OPS Gate**
- [ ] Key ceremony documentation in immutable audit log
- [ ] Cold/hot ratio confirmed ≥80%
- [ ] PoR reconciliation passing (no mismatches)
- [ ] Annual custody audit scheduled (12 months from key ceremony)
- [ ] CISO sign-off on custody readiness

---

## What Goes Wrong

**Custody model decided too late.** The most common pattern: custody is treated as a technical decision and deferred to Layer 3. By then, the SC audit scope is wrong, the legal structure is incomplete, and the key ceremony is 6 weeks behind programme schedule.

**Key ceremony underestimated.** Keyholders are unavailable, HSM arrives late, legal review of ceremony protocol is not scheduled. Ceremony delayed by 3–4 weeks. Everything downstream shifts.

**Cold/hot ratio not monitored.** Ratio drifts below 80% during operational ramp-up. No KRI in place. Discovered in audit. Remediation requires temporary operational halt.

**Third-party custodian not contracted early enough.** Custodian onboarding (KYB, contract negotiation, technical integration) takes 6–10 weeks. If started at Layer 4, it becomes a Layer 5 blocker.

---

## Key References

- MiCA Art.70 — Custody and administration of crypto-assets
- MiCA Art.76 — Oracle and reserve requirements
- eWpG Section 8 — Electronic securities register (Germany)
- DORA Art.9 — ICT risk management (wallet infrastructure)
- ISO 27001 — Key management controls

---

## More Detail

Concept360 works with tokenisation platforms and infrastructure providers on post-licensing operational setup — building the delivery structures, compliance workflows, governance models, and control frameworks that make a regulated digital asset operation functionally ready.

If you are past the licensing stage and need to build what was promised in the application, that is where this work starts.

→ [biljana.obradovic@concept360.rs](mailto:biljana.obradovic@concept360.rs)
→ [linkedin.com/in/biljana-obradovic-28390a8](https://linkedin.com/in/biljana-obradovic-28390a8)

---

*Part of the 7-Layer RWA Delivery Framework · Concept360 · 2026*
*© Biljana Obradović · All rights reserved · For discussion purposes only*
