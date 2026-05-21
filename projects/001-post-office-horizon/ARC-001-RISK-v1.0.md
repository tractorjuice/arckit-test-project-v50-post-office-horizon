# Risk Register

> **Template Origin**: Official | **ArcKit Version**: 5.0.2 | **Command**: `/arckit:risk`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-RISK-v1.0 |
| **Document Type** | Risk Register (HM Treasury Orange Book 2023) |
| **Project** | Post Office Horizon (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-05-21 |
| **Last Modified** | 2026-05-21 |
| **Review Cycle** | Monthly (Critical/High); Quarterly (Medium/Low) |
| **Next Review Date** | 2026-06-21 |
| **Owner** | Mark Craddock, Enterprise Architect |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING — Programme Senior Responsible Owner |
| **Distribution** | Post Office Horizon Programme — programme board, SRO, risk owners, DBT shareholder team, independent assurance |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial creation from `/arckit:risk` command | PENDING | PENDING |

---

## Executive Summary

### Risk Profile Overview

**Total Risks Identified:** 22 risks across all 6 Orange Book categories.

| Risk Level | Inherent | Residual | Change |
|------------|----------|----------|--------|
| **Critical** (20-25) | 3 | 0 | ↓ eliminated |
| **High** (13-19) | 8 | 3 | ↓ 63% |
| **Medium** (6-12) | 11 | 18 | — |
| **Low** (1-5) | 0 | 1 | ↑ |
| **TOTAL (sum of scores)** | 310 | 197 | ↓ 36% |

### Risk Category Distribution

| Category | Count | Avg Inherent | Avg Residual | Control Effectiveness |
|----------|-------|--------------|--------------|----------------------|
| **STRATEGIC** | 4 | 14.3 | 9.3 | 35% reduction |
| **OPERATIONAL** | 4 | 14.0 | 7.3 | 48% reduction |
| **FINANCIAL** | 3 | 13.3 | 9.3 | 30% reduction |
| **COMPLIANCE** | 4 | 13.3 | 7.0 | 47% reduction |
| **REPUTATIONAL** | 2 | 13.5 | 9.5 | 30% reduction |
| **TECHNOLOGY** | 5 | 16.6 | 11.2 | 33% reduction |

### Overall Risk Assessment

**Overall Residual Risk Score:** 197/550 (sum of 22 residual scores; theoretical maximum 22 × 25 = 550).
**Risk Reduction from Controls:** 36% reduction from inherent (310 → 197).
**Risk Profile Status:** ⚠️ **Concerning**

The profile is **Concerning, not Acceptable** — and this is an honest, deliberate assessment, not a presentational one. The programme is at requirements stage: its controls are **designed** (in `ARC-000-PRIN-v1.0` and `ARC-001-REQ-v1.0`) but **not yet operational or independently assured**. Residual scores credit those controls only partially. Eleven residual risks still exceed the inferred risk appetite (see Section G), and the three highest-residual risks — R-001 (premature go-live), R-018 (integrity not provable) and R-019 (covert write path) — are precisely the risks whose realisation would recreate the Horizon scandal. Presenting this register as "Acceptable" would itself be the optimism bias the Post Office Horizon IT Inquiry condemned.

### Risks Exceeding Appetite

**Number of risks exceeding the inferred organizational appetite:** 11 risks (see Section G for the full table).

### Top 5 Risks Requiring Immediate Attention

1. **R-019** (TECHNOLOGY, Inherent 25 / Residual 15 High): Covert write path to branch accounts exists in the delivered system — Owner: Post Office CTO — Status: Open.
2. **R-001** (STRATEGIC, Inherent 20 / Residual 15 High): Premature go-live forced by political or exit-date pressure — Owner: Programme SRO — Status: Open.
3. **R-018** (TECHNOLOGY, Inherent 15 / Residual 15 High): Transaction integrity cannot be proven and fails independent assurance — Owner: Post Office CTO — Status: Open.
4. **R-002** (STRATEGIC, Inherent 20 / Residual 12 Medium): Sub-postmaster trust not restored — programme perceived as "Horizon 2" — Owner: Service Owner — Status: Open.
5. **R-009** (FINANCIAL, Inherent 16 / Residual 12 Medium): Build cost overrun beyond the approved funding envelope — Owner: Finance & Commercial Director — Status: Open.

### Key Findings and Recommendations

**Key Findings:**

- The three highest residual risks are all integrity-or-trust risks central to the programme's purpose; their residual scores stay High because the controls that address them are designed but not yet built or assured.
- Technology risks carry the heaviest profile (avg residual 11.2) and are concentrated on a single owner (Post Office CTO owns 6 risks) — appropriate by domain, but a concentration to manage.
- No risk can be terminated and none meaningfully transferred — this is a must-deliver programme; 20 of 22 risks require active treatment.
- Eleven residual risks exceed the inferred appetite; a **formal, ratified risk appetite statement** is the most important governance gap.

**Recommendations:**

1. Ratify a formal risk appetite statement (`/arckit:principles` risk-appetite, or a Board paper) — this register currently uses an inferred appetite.
2. Treat R-001, R-018 and R-019 as standing Steering Committee agenda items; their residual scores fall only when controls are built and **independently assured** (PRIN Principle 23).
3. Re-baseline this register after the High-Level Design and the first independent assurance gate — residual scores should be re-scored on evidence, not design intent.

---

## A. Risk Matrix Visualization

### Inherent Risk Matrix (Before Controls)

```text
                                    IMPACT
              1-Negligible  2-Minor   3-Moderate   4-Major     5-Catastrophic
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │           │           │           │           │   R-019   │
Certain    │    5      │    10     │    15     │    20     │    25     │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │           │           │ R-004     │ R-005     │ R-001     │
           │           │           │ R-007     │ R-006     │ R-002     │
           │    4      │    8      │ R-017 (12)│ R-009     │   (20)    │
           │           │           │           │ R-012     │           │
           │           │           │           │ R-020 (16)│           │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │           │ R-003     │ R-008     │ R-011     │
K          │           │           │ R-010     │ R-013     │ R-016     │
E          │    3      │    6      │ R-015     │ R-014     │ R-018 (15)│
L          │           │           │ R-022 (9) │ R-021 (12)│           │
I          ├───────────┼───────────┼───────────┼───────────┼───────────┤
H 2-Unlikely│          │           │           │           │           │
O          │    2      │    4      │    6      │    8      │    10     │
O          ├───────────┼───────────┼───────────┼───────────┼───────────┤
D 1-Rare   │    1      │    2      │    3      │    4      │    5      │
           └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: ██ Critical (20-25)  ▓▓ High (13-19)  ░░ Medium (6-12)  ·· Low (1-5)
```

**Inherent zones:** Critical — R-019 (25), R-001 (20), R-002 (20). High — R-005, R-006, R-009, R-012, R-020 (16), R-011, R-016, R-018 (15). Medium — R-003, R-004, R-007, R-008, R-010, R-013, R-014, R-015, R-017, R-021, R-022.

### Residual Risk Matrix (After Designed Controls)

```text
                                    IMPACT
              1-Negligible  2-Minor   3-Moderate   4-Major     5-Catastrophic
           ┌───────────┬───────────┬───────────┬───────────┬───────────┐
5-Almost   │    5      │    10     │    15     │    20     │    25     │
Certain    ├───────────┼───────────┼───────────┼───────────┼───────────┤
4-Likely   │    4      │    8      │    12     │    16     │    20     │
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 3-Possible│          │           │ R-005     │ R-002     │ R-001     │
K          │           │           │ R-017 (9) │ R-009     │ R-018     │
E          │    3      │    6      │           │ R-020 (12)│ R-019 (15)│
L          ├───────────┼───────────┼───────────┼───────────┼───────────┤
I 2-Unlikely│          │ R-004 (4) │ R-003     │ R-006     │ R-011     │
H          │           │           │ R-007     │ R-012     │ R-016     │
O          │    2      │    4      │ R-008     │ R-013     │   (10)    │
O          │           │           │ R-010     │ R-021 (8) │           │
D          │           │           │ R-014     │           │           │
           │           │           │ R-015     │           │           │
           │           │           │ R-022 (6) │           │           │
           ├───────────┼───────────┼───────────┼───────────┼───────────┤
1-Rare     │    1      │    2      │    3      │    4      │    5      │
           └───────────┴───────────┴───────────┴───────────┴───────────┘

Legend: ██ Critical (20-25)  ▓▓ High (13-19)  ░░ Medium (6-12)  ·· Low (1-5)
```

**Risk Movement Analysis:**

- **All 3 inherent Critical risks moved out of Critical**: R-019 (25→15), R-001 (20→15), R-002 (20→12).
- **Residual High (3)**: R-001, R-018, R-019 — all integrity/trust-critical; residual stays High until controls are built and independently assured.
- **Largest reductions**: R-004 (12→4, supplier ambiguity resolves on confirmation), R-006 (16→8), R-012 (16→8).
- **Most resistant**: R-001, R-018, R-019 — design controls are strong but unproven; R-002 and R-009 reduce only modestly.

---

## B. Top 10 Risks (Ranked by Residual Score)

| Rank | ID | Title | Category | Inherent | Residual | Owner | Status | Response |
|------|----|-------|----------|----------|----------|-------|--------|----------|
| 1 | R-019 | Covert write path exists in delivered system | TECHNOLOGY | 25 | 15 | Post Office CTO | Open | Treat |
| 2 | R-001 | Premature go-live forced by political pressure | STRATEGIC | 20 | 15 | Programme SRO | Open | Treat |
| 3 | R-018 | Transaction integrity not provable at assurance | TECHNOLOGY | 15 | 15 | Post Office CTO | Open | Treat |
| 4 | R-002 | Sub-postmaster trust not restored ("Horizon 2") | STRATEGIC | 20 | 12 | Service Owner | Open | Treat |
| 5 | R-009 | Build cost overrun beyond funding envelope | FINANCIAL | 16 | 12 | Finance & Commercial Director | Open | Treat |
| 6 | R-020 | Integration complexity across 80+ components | TECHNOLOGY | 16 | 12 | Post Office CTO | Open | Treat |
| 7 | R-011 | Funding withdrawn after NAO/PAC criticism | FINANCIAL | 15 | 10 | Programme SRO | Open | Treat |
| 8 | R-016 | Post-go-live integrity incident reignites scandal | REPUTATIONAL | 15 | 10 | Programme SRO | Open | Treat |
| 9 | R-005 | Fujitsu transition non-cooperation / knowledge loss | OPERATIONAL | 16 | 9 | Post Office CTO | Open | Treat |
| 10 | R-017 | External reputational shock destabilises programme | REPUTATIONAL | 12 | 9 | Post Office Board / Chair | Open | Tolerate |

---

## C. Detailed Risk Register

### Risk Register Summary Table

| ID | Category | Title | Inh. L×I | Inh. | Controls effectiveness | Res. L×I | Res. | 4Ts | Owner | Status |
|----|----------|-------|----------|------|------------------------|----------|------|-----|-------|--------|
| R-001 | STRATEGIC | Premature go-live forced by political/exit-date pressure | 4×5 | 20 | Adequate | 3×5 | 15 | Treat | Programme SRO | Open |
| R-002 | STRATEGIC | Sub-postmaster trust not restored ("Horizon 2") | 4×5 | 20 | Adequate | 3×4 | 12 | Treat | Service Owner | Open |
| R-003 | STRATEGIC | Ministerial / policy / machinery-of-government change | 3×3 | 9 | Adequate | 2×3 | 6 | Tolerate | Programme SRO | Open |
| R-004 | STRATEGIC | Incoming supplier (Accenture/OVC) arrangement unconfirmed | 4×3 | 12 | Adequate | 2×2 | 4 | Treat | Finance & Commercial Director | Open |
| R-005 | OPERATIONAL | Fujitsu transition non-cooperation / knowledge loss | 4×4 | 16 | Adequate | 3×3 | 9 | Treat | Post Office CTO | Open |
| R-006 | OPERATIONAL | Branch service disruption during migration/cutover | 4×4 | 16 | Strong | 2×4 | 8 | Treat | Branch Operations Director | Open |
| R-007 | OPERATIONAL | Sub-postmaster readiness / training gap at go-live | 4×3 | 12 | Adequate | 2×3 | 6 | Treat | Service Owner | Open |
| R-008 | OPERATIONAL | Skills / capability gap for composable cloud rebuild | 3×4 | 12 | Adequate | 2×3 | 6 | Treat | Post Office CTO | Open |
| R-009 | FINANCIAL | Build cost overrun beyond approved funding envelope | 4×4 | 16 | Adequate | 3×4 | 12 | Treat | Finance & Commercial Director | Open |
| R-010 | FINANCIAL | Cloud / run-cost escalation post go-live | 3×3 | 9 | Adequate | 2×3 | 6 | Treat | Finance & Commercial Director | Open |
| R-011 | FINANCIAL | Funding withdrawn / reduced after NAO/PAC criticism | 3×5 | 15 | Adequate | 2×5 | 10 | Treat | Programme SRO | Open |
| R-012 | COMPLIANCE | UK GDPR / data protection breach during migration | 4×4 | 16 | Strong | 2×4 | 8 | Treat | Data Protection Officer / SIRO | Open |
| R-013 | COMPLIANCE | Inquiry recommendations not demonstrably embedded | 3×4 | 12 | Adequate | 2×4 | 8 | Treat | Programme SRO | Open |
| R-014 | COMPLIANCE | NCSC CAF / security compliance not met before go-live | 3×4 | 12 | Strong | 2×3 | 6 | Treat | CISO / SIRO | Open |
| R-015 | COMPLIANCE | HMT spend-control delay / procurement legal challenge | 3×3 | 9 | Adequate | 2×3 | 6 | Treat | Finance & Commercial Director | Open |
| R-016 | REPUTATIONAL | Post-go-live integrity incident reignites the scandal | 3×5 | 15 | Adequate | 2×5 | 10 | Treat | Programme SRO | Open |
| R-017 | REPUTATIONAL | External reputational shock destabilises the programme | 4×3 | 12 | Weak | 3×3 | 9 | Tolerate | Post Office Board / Chair | Open |
| R-018 | TECHNOLOGY | Transaction integrity not provable at independent assurance | 3×5 | 15 | Adequate | 3×5 | 15 | Treat | Post Office CTO | Open |
| R-019 | TECHNOLOGY | Covert write path to branch accounts exists | 5×5 | 25 | Adequate | 3×5 | 15 | Treat | Post Office CTO | Open |
| R-020 | TECHNOLOGY | Integration complexity across 80+ components | 4×4 | 16 | Adequate | 3×4 | 12 | Treat | Post Office CTO | Open |
| R-021 | TECHNOLOGY | Migration "launders" disputed historical balances | 3×4 | 12 | Strong | 2×4 | 8 | Treat | Post Office CTO | Open |
| R-022 | TECHNOLOGY | New single-supplier lock-in recreated | 3×3 | 9 | Adequate | 2×3 | 6 | Treat | Post Office CTO | Open |

> Per-risk profiles below. Each lists root cause, triggers, consequences, affected stakeholders, related goals, controls, response, appetite assessment and a named, dated mitigation action. Risk owners are drawn from the `ARC-001-STKE-v1.0` RACI matrix (Accountable role = Risk Owner).

### Risk R-001: Premature go-live forced by political or exit-date pressure

**Category:** STRATEGIC — **Status:** Open — **Risk Owner:** Programme SRO — **Action Owner:** Programme SRO

**Description:** Political pressure to show progress, or to hit a firm Fujitsu exit date, compresses independent assurance and the replacement is taken live before transaction integrity is proven.

**Root Cause:** Sustained ministerial, parliamentary and media pressure for visible delivery, against a multi-year assurance need.

**Triggers:** A fixed, publicly committed exit date; a slipping schedule meeting a political deadline; an assurance gate overruled.

**Consequences:** Recurrence of the Horizon/NBIT failure mode; an unsafe system in live branches; loss of all programme credibility; potential fresh injustice.

**Affected Stakeholders:** Sub-postmasters, Inquiry legacy, Minister/DBT, Programme SRO.

**Related Objectives:** Threatens STKE goals G-1, G-5; outcome O-1.

**Inherent:** L4 × I5 = **20 (Critical)** — strong, ongoing political pressure; the NBIT precedent shows the failure is real [POHR-C1].

**Designed Controls:** PRIN Principle 23 (independent assurance, gates with halt authority); REQ BR-010; STKE Conflict-1 resolution (assurance gates are the formal arbiter of pace) → REQ Conflict C-1 (phased, assurance-gated rollout). Effectiveness: **Adequate** — strong by design, unproven in operation.

**Residual:** L3 × I5 = **15 (High)** — likelihood falls only to "Possible"; impact stays catastrophic.

**4Ts Response:** **TREAT.** Tolerate rejected (catastrophic impact); Transfer/Terminate not viable.

**Appetite (inferred ≤ 9 Strategic):** ❌ **Exceeds** by 6 — escalate to Programme Board and DBT.

**Mitigation Action:** Constitute the independent assurance function with explicit, board-backed halt authority and a written rule that the Fujitsu exit date is assurance-conditional. Owner: Programme SRO. Target: **2026-09-30**. Target residual: 10 (Medium).

---

### Risk R-002: Sub-postmaster trust not restored ("Horizon 2")

**Category:** STRATEGIC — **Status:** Open — **Risk Owner:** Service Owner — **Action Owner:** Service Owner

**Description:** The replacement is technically delivered but sub-postmasters still distrust it — perceived as "Horizon 2" — because engagement was tokenistic or transparency incomplete.

**Root Cause:** A profound, justified trust deficit; the temptation to treat postmasters as recipients rather than partners.

**Triggers:** Co-design that does not change the product; central adjustments postmasters cannot see; an early discrepancy handled defensively.

**Consequences:** The programme's core purpose fails; political and reputational damage; postmasters disengage from the system and from disputes.

**Affected Stakeholders:** Sub-postmasters, representative bodies (NFSP/CWU/JFSA), Board, Minister.

**Related Objectives:** Threatens STKE goal G-3; outcome O-2.

**Inherent:** L4 × I5 = **20 (Critical)** — without genuine engagement, distrust is the default after Horizon.

**Designed Controls:** REQ BR-003, FR-010–FR-015 (complete visibility, explainability, fair dispute handling), NFR-U usability; baseline and tracked confidence surveys; co-design. Effectiveness: **Adequate**.

**Residual:** L3 × I4 = **12 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 9 Strategic):** ❌ **Exceeds** by 3 — escalate to Programme Board.

**Mitigation Action:** Stand up a genuine co-design programme with NFSP/CWU/JFSA and practising postmasters, with documented influence on the product; run a baseline confidence survey. Owner: Service Owner. Target: **2026-09-30**. Target residual: 8.

---

### Risk R-003: Ministerial / policy / machinery-of-government change

**Category:** STRATEGIC — **Status:** Open — **Risk Owner:** Programme SRO — **Action Owner:** Programme SRO

**Description:** A change of minister, government policy, or departmental machinery during the multi-year programme disrupts direction, funding or sponsorship.

**Root Cause:** Long programme duration spanning political cycles.

**Triggers:** General election; reshuffle; machinery-of-government reorganisation; a shift in the government's Post Office strategy.

**Consequences:** Re-baselining; sponsorship discontinuity; funding uncertainty.

**Affected Stakeholders:** Programme SRO, DBT, Minister, Board.

**Related Objectives:** Threatens stable delivery of all goals.

**Inherent:** L3 × I3 = **9 (Medium)** — possible over the programme life; moderate disruption.

**Designed Controls:** Cross-party consensus on the Horizon issue; DBT shareholder governance continuity; multi-year funding commitment. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TOLERATE** — largely outside programme control; monitor and maintain cross-party briefing.

**Appetite (inferred ≤ 9 Strategic):** ✅ **Within** appetite.

**Mitigation Action:** Maintain durable, non-partisan programme documentation and a standing cross-party briefing pack so a new minister can be oriented quickly. Owner: Programme SRO. Target: **Ongoing** (pack ready by 2026-09-30). Target residual: 6.

---

### Risk R-004: Incoming supplier (Accenture/OVC) arrangement unconfirmed

**Category:** STRATEGIC — **Status:** Open — **Risk Owner:** Finance & Commercial Director — **Action Owner:** Finance & Commercial Director

**Description:** The reported selection of Accenture and One View Commerce is not confirmed in commercial detail; planning on unverified scope, values or dates risks rework.

**Root Cause:** Reliance on same-day wire reporting rather than confirmed contract award [POHR-C8].

**Triggers:** Dependent decisions taken before contracts are signed; the reported arrangement changes.

**Consequences:** Re-baselining of plan and architecture assumptions; commercial misalignment.

**Affected Stakeholders:** Finance & Commercial, Post Office CTO, Programme SRO.

**Related Objectives:** Threatens STKE goals G-2, G-9.

**Inherent:** L4 × I3 = **12 (Medium)** — the ambiguity exists now.

**Designed Controls:** REQ Assumption A-1 and Risk R-4 — confirm from official Post Office/DBT sources and published award notices before dependent decisions. Effectiveness: **Adequate**.

**Residual:** L2 × I2 = **4 (Low)** — once contracts are confirmed the ambiguity disappears.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 9 Strategic):** ✅ **Within** appetite.

**Mitigation Action:** Confirm the supplier arrangement, scope split and dates against official announcements and Find a Tender / Contracts Finder award notices; re-baseline the plan. Owner: Finance & Commercial Director. Target: **2026-07-31**. Target residual: 4.

---

### Risk R-005: Fujitsu transition non-cooperation / knowledge loss

**Category:** OPERATIONAL — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Post Office CTO

**Description:** Fujitsu's commercial caution, or loss of key staff, impedes knowledge transfer, data access and an orderly exit.

**Root Cause:** Fujitsu's reputational/commercial position — it has acknowledged a "moral obligation" on redress but not paid, and is awaiting the Inquiry [POHR-C4]; staff attrition on a contract being wound down.

**Triggers:** Disputes over exit scope/cost; departure of critical Fujitsu staff; reluctance to disclose system knowledge.

**Consequences:** Delayed Fujitsu exit (target ~mid-2027 [POHR-C5]); migration jeopardised; further bridging-extension cost.

**Affected Stakeholders:** Post Office CTO, incoming suppliers, Programme SRO, Legal.

**Related Objectives:** Threatens STKE goals G-2, G-6, G-8.

**Inherent:** L4 × I4 = **16 (High)**.

**Designed Controls:** Contractual knowledge-transfer, data-access and disclosure obligations; joint transition governance with Legal oversight; INT-009 treats Fujitsu cooperation as a contractual dependency. Effectiveness: **Adequate**.

**Residual:** L3 × I3 = **9 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Operational):** ❌ **Exceeds** by 1 — monitor; escalate if it rises.

**Mitigation Action:** Make knowledge transfer, data access and defect disclosure explicit contractual transition obligations (not goodwill items) and begin early knowledge capture. Owner: Post Office CTO. Target: **2026-12-31**. Target residual: 6.

---

### Risk R-006: Branch service disruption during migration/cutover

**Category:** OPERATIONAL — **Status:** Open — **Risk Owner:** Branch Operations Director — **Action Owner:** Branch Operations Director

**Description:** Migration or cutover causes a service-affecting outage in branches, interrupting mail, banking, cash and government services.

**Root Cause:** The inherent complexity of migrating ~11,500 live branches off Horizon.

**Triggers:** A big-bang or compressed cutover; an untested migration step; branch connectivity failure.

**Consequences:** Customer harm (cash access, essential services); reputational damage; loss of postmaster confidence.

**Affected Stakeholders:** Customers/public, sub-postmasters, Branch Operations.

**Related Objectives:** Threatens STKE goal G-8; outcome O-6.

**Inherent:** L4 × I4 = **16 (High)**.

**Designed Controls:** REQ BR-006 (service continuity a hard go/no-go), FR-021 coexistence, FR-022 resilient offline operation, phased branch-by-branch migration; STKE Conflict-5 resolution. Effectiveness: **Strong**.

**Residual:** L2 × I4 = **8 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Operational):** ✅ **Within** appetite (at threshold).

**Mitigation Action:** Adopt a phased migration with branch-readiness gates and a tested rollback per branch; continuity as a release go/no-go criterion. Owner: Branch Operations Director. Target: **2026-12-31**. Target residual: 6.

---

### Risk R-007: Sub-postmaster readiness / training gap at go-live

**Category:** OPERATIONAL — **Status:** Open — **Risk Owner:** Service Owner — **Action Owner:** Service Owner

**Description:** Branch staff are insufficiently prepared for the replacement system at go-live, causing errors, poor service and dented confidence.

**Root Cause:** A large, dispersed network with wide variation in digital confidence.

**Triggers:** Compressed training schedule; training not matched to real workflows; go-live before readiness confirmed.

**Consequences:** Transaction errors; customer service failures; early erosion of trust (feeds R-002).

**Affected Stakeholders:** Sub-postmasters, counter staff, customers.

**Related Objectives:** Threatens STKE goals G-3, G-8.

**Inherent:** L4 × I3 = **12 (Medium)**.

**Designed Controls:** REQ FR-020 (isolated training/simulation mode), NFR-U-001/002 (usability, accessibility), branch-readiness gates, co-design. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Operational):** ✅ **Within** appetite.

**Mitigation Action:** Design a role-based training programme with the isolated training mode, and make demonstrated branch readiness a precondition of each branch go-live. Owner: Service Owner. Target: **2027-03-31**. Target residual: 6.

---

### Risk R-008: Skills / capability gap for a composable cloud rebuild

**Category:** OPERATIONAL — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Post Office CTO

**Description:** The Post Office and/or its suppliers lack the capability to deliver and sustain a composable, cloud-native architecture.

**Root Cause:** The in-house NBIT programme failed partly on capability; modern cloud and integrity engineering is specialised.

**Triggers:** Recruitment difficulty; supplier capability shortfalls; reliance on a thin pool of key individuals.

**Consequences:** Delivery delay; quality shortfalls; renewed dependence on a single supplier (feeds R-022).

**Affected Stakeholders:** Post Office CTO, DDaT, incoming suppliers.

**Related Objectives:** Threatens STKE goals G-2, G-5, G-9.

**Inherent:** L3 × I4 = **12 (Medium)**.

**Designed Controls:** Procurement-led delivery model (capable suppliers replacing the failed in-house build); DDaT capability building; architecture governance. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Operational):** ✅ **Within** appetite.

**Mitigation Action:** Confirm a capability plan covering supplier skills and retained Post Office intelligent-client capability; avoid single-individual dependencies. Owner: Post Office CTO. Target: **2026-12-31**. Target residual: 6.

---

### Risk R-009: Build cost overrun beyond the approved funding envelope

**Category:** FINANCIAL — **Status:** Open — **Risk Owner:** Finance & Commercial Director — **Action Owner:** Finance & Commercial Director

**Description:** Programme delivery cost exceeds the approved government funding envelope.

**Root Cause:** Large, complex transformation with integration uncertainty; the NBIT precedent of ~£1bn uncontrolled spend [POHR-C1].

**Triggers:** Scope creep; optimistic baseline estimates; integration cost surprises across 80+ components.

**Consequences:** Funding pressure; NAO/PAC criticism; potential descoping of non-integrity capability.

**Affected Stakeholders:** HM Treasury, DBT, Finance & Commercial, Programme SRO.

**Related Objectives:** Threatens STKE goal G-4; outcome O-4.

**Inherent:** L4 × I4 = **16 (High)**.

**Designed Controls:** REQ BR-004; staged funding released against assurance gates; competitive procurement; scope and change control; STKE Conflict-2 / REQ Conflict C-3 resolution. Effectiveness: **Adequate**.

**Residual:** L3 × I4 = **12 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Financial):** ❌ **Exceeds** by 4 — escalate to DBT/HM Treasury.

**Mitigation Action:** Produce a robust, optimism-bias-adjusted business case (`/arckit:sobc`) with gate-linked staged funding and disciplined change control. Owner: Finance & Commercial Director. Target: **2026-09-30**. Target residual: 8.

---

### Risk R-010: Cloud / run-cost escalation post go-live

**Category:** FINANCIAL — **Status:** Open — **Risk Owner:** Finance & Commercial Director — **Action Owner:** Finance & Commercial Director

**Description:** Operating costs of the cloud-hosted replacement escalate beyond forecast after go-live.

**Root Cause:** Cloud consumption cost variability; absence of cost discipline designed in early.

**Triggers:** Unoptimised architecture; demand growth; egress and licensing costs.

**Consequences:** Run-cost pressure; reduced value for money.

**Affected Stakeholders:** Finance & Commercial, HM Treasury, Post Office CTO.

**Related Objectives:** Threatens STKE goal G-4.

**Inherent:** L3 × I3 = **9 (Medium)**.

**Designed Controls:** Planned FinOps discipline (`/arckit:finops`); architecture cost-efficiency principle; contract structure. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Financial):** ✅ **Within** appetite.

**Mitigation Action:** Establish a FinOps cost model and run-cost forecast as part of the business case and architecture design. Owner: Finance & Commercial Director. Target: **2026-12-31**. Target residual: 6.

---

### Risk R-011: Funding withdrawn or reduced after NAO/PAC criticism

**Category:** FINANCIAL — **Status:** Open — **Risk Owner:** Programme SRO — **Action Owner:** Finance & Commercial Director

**Description:** Adverse NAO or Public Accounts Committee findings, or wider fiscal pressure, lead to funding being cut mid-programme.

**Root Cause:** Intense scrutiny of public-sector IT spend; the NBIT write-off as a live cautionary example.

**Triggers:** A critical NAO report; PAC hearing findings; a spending review.

**Consequences:** Programme cannot proceed as planned; loss of momentum; partial delivery.

**Affected Stakeholders:** Programme SRO, DBT, HM Treasury, NAO/Parliament.

**Related Objectives:** Threatens all goals via funding discontinuity.

**Inherent:** L3 × I5 = **15 (High)**.

**Designed Controls:** Honest, evidenced status reporting (PRIN Principle 23); auditable evidence trail; proactive DBT/Treasury/NAO engagement. Effectiveness: **Adequate**.

**Residual:** L2 × I5 = **10 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Financial):** ❌ **Exceeds** by 2 — escalate to DBT.

**Mitigation Action:** Maintain audit-ready evidence and a proactive NAO/PAC engagement plan; brief ahead of, not after, scrutiny. Owner: Finance & Commercial Director. Target: **Ongoing** (engagement plan by 2026-09-30). Target residual: 8.

---

### Risk R-012: UK GDPR / data protection breach during migration

**Category:** COMPLIANCE — **Status:** Open — **Risk Owner:** Data Protection Officer / SIRO — **Action Owner:** Data Protection Officer

**Description:** Migrating decades of personal and financial data — including data subject to redress, inquiry and litigation holds — results in a personal data breach.

**Root Cause:** Large-scale migration of sensitive historical data across legacy systems.

**Triggers:** Excessive personal data copied; weak access control in migration tooling; insecure transfer.

**Consequences:** ICO enforcement; harm to sub-postmasters and victims; reputational damage.

**Affected Stakeholders:** Sub-postmasters, customers, ICO, DPO/SIRO.

**Related Objectives:** Threatens STKE goal G-7; outcome O-6.

**Inherent:** L4 × I4 = **16 (High)**.

**Designed Controls:** REQ NFR-C-001 (UK GDPR), completed DPIA, DR-005/006/007/008 (classification, retention/legal hold, UK residency, minimisation), NFR-SEC-003 encryption; PRIN Principle 13. Effectiveness: **Strong**.

**Residual:** L2 × I4 = **8 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 6 Compliance):** ❌ **Exceeds** by 2 — escalate to SIRO.

**Mitigation Action:** Complete the DPIA before any migration; enforce data minimisation and encryption in migration tooling; ICO-aligned controls. Owner: Data Protection Officer. Target: **2026-09-30**. Target residual: 6.

---

### Risk R-013: Inquiry recommendations not demonstrably embedded

**Category:** COMPLIANCE — **Status:** Open — **Risk Owner:** Programme SRO — **Action Owner:** Enterprise Architect

**Description:** The programme cannot demonstrate that the Post Office Horizon IT Inquiry's recommendations are embedded in design and governance; later Inquiry volumes raise new expectations mid-programme.

**Root Cause:** Treating the Inquiry as a compliance checkbox; recommendations evolving as volumes publish.

**Triggers:** A later Inquiry volume; a public or parliamentary challenge on alignment.

**Consequences:** Political and reputational damage; perception the programme "did not learn".

**Affected Stakeholders:** Inquiry legacy, DBT, Minister, sub-postmasters.

**Related Objectives:** Threatens STKE goal G-10; outcome O-5.

**Inherent:** L3 × I4 = **12 (Medium)**.

**Designed Controls:** REQ BR-005, NFR-C-005 (recommendation traceability reporting); 19 Volume 1 recommendations, 18 accepted by government [POHR-C10]; PRIN-to-recommendation traceability. Effectiveness: **Adequate**.

**Residual:** L2 × I4 = **8 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 6 Compliance):** ❌ **Exceeds** by 2 — escalate to SRO.

**Mitigation Action:** Maintain a live Inquiry-recommendation traceability matrix, refreshed as later volumes publish. Owner: Enterprise Architect. Target: **Ongoing** (matrix established by 2026-09-30). Target residual: 6.

---

### Risk R-014: NCSC CAF / security compliance not met before go-live

**Category:** COMPLIANCE — **Status:** Open — **Risk Owner:** CISO / SIRO — **Action Owner:** Cyber Security Lead

**Description:** The replacement does not reach the agreed NCSC Cyber Assessment Framework profile before network go-live.

**Root Cause:** Security treated as a late gate rather than a design input.

**Triggers:** Late security testing; unremediated penetration-test findings; CAF outcomes not met.

**Consequences:** Go-live blocked or an insecure system in service; regulatory and reputational exposure.

**Affected Stakeholders:** CISO/SIRO, NCSC, Post Office CTO.

**Related Objectives:** Threatens STKE goal G-7.

**Inherent:** L3 × I4 = **12 (Medium)**.

**Designed Controls:** REQ NFR-SEC-001–006, NFR-C-003/004 (CAF, PCI-DSS); PRIN Principle 4 (Security by Design, non-negotiable); security testing gates. Effectiveness: **Strong**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 6 Compliance):** ✅ **Within** appetite (at threshold).

**Mitigation Action:** Treat CAF and security testing as design-stage activities with gates before pilot go-live. Owner: Cyber Security Lead. Target: **2027-03-31**. Target residual: 6.

---

### Risk R-015: HMT spend-control delay / procurement legal challenge

**Category:** COMPLIANCE — **Status:** Open — **Risk Owner:** Finance & Commercial Director — **Action Owner:** Finance & Commercial Director

**Description:** HM Treasury spending-control approvals are delayed, or the procurement is legally challenged, slowing the programme.

**Root Cause:** Government spend-control processes; procurement challenge risk on a high-value award.

**Triggers:** Incomplete approval submissions; an unsuccessful-bidder challenge.

**Consequences:** Schedule delay; commercial uncertainty.

**Affected Stakeholders:** Finance & Commercial, HM Treasury, suppliers.

**Related Objectives:** Threatens STKE goals G-2, G-4.

**Inherent:** L3 × I3 = **9 (Medium)**.

**Designed Controls:** Early HMT engagement; a sound, defensible business case; demonstrably compliant procurement. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 6 Compliance):** ✅ **Within** appetite (at threshold).

**Mitigation Action:** Engage HMT early on spend-control submissions; ensure procurement is fully documented and defensible. Owner: Finance & Commercial Director. Target: **2026-09-30**. Target residual: 6.

---

### Risk R-016: Post-go-live integrity incident reignites the scandal

**Category:** REPUTATIONAL — **Status:** Open — **Risk Owner:** Programme SRO — **Action Owner:** Post Office CTO

**Description:** An integrity defect or data error in the live replacement produces a wrong discrepancy or wrongful liability, re-traumatising sub-postmasters and reigniting the scandal.

**Root Cause:** Any residual defect in financial-accuracy logic; concealment if a defect is mishandled.

**Triggers:** A live financial-accuracy defect; an unexplained discrepancy; a defect handled defensively.

**Consequences:** Catastrophic reputational, political and human harm — set against ~£1.56bn redress already paid and ~£2bn estimated [POHR-C6]; potential fresh injustice.

**Affected Stakeholders:** Sub-postmasters, victims, Board, Minister, media.

**Related Objectives:** Threatens outcomes O-1, O-2.

**Inherent:** L3 × I5 = **15 (High)**.

**Designed Controls:** PRIN Category II (non-negotiable integrity principles); REQ FR-004–FR-016 (immutable record, tamper-evidence, BED register and disclosure); independent assurance; incident response. Effectiveness: **Adequate**.

**Residual:** L2 × I5 = **10 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 6 Reputational):** ❌ **Exceeds** by 4 — escalate to Programme Board and Post Office Board.

**Mitigation Action:** Mandate honest defect disclosure via the BED register (FR-016) and a rehearsed, transparent incident-response plan; no defect concealment — defects were known from 1999 and concealed [POHR-C9], and that must not recur. Owner: Post Office CTO. Target: **2027-03-31**. Target residual: 8.

---

### Risk R-017: External reputational shock destabilises the programme

**Category:** REPUTATIONAL — **Status:** Open — **Risk Owner:** Post Office Board / Chair — **Action Owner:** Programme SRO

**Description:** Later Inquiry volumes, the Metropolitan Police Operation Olympos investigation, or a redress-scheme controversy reignite public anger and destabilise the programme's operating environment.

**Root Cause:** The scandal's aftermath is ongoing — accountability volumes pending, a criminal investigation live [POHR-C7].

**Triggers:** Publication of a later Inquiry volume; charging decisions in Operation Olympos; a redress controversy.

**Consequences:** Heightened scrutiny; political instability around the programme; diversion of leadership attention.

**Affected Stakeholders:** Board, Minister, media, sub-postmasters.

**Related Objectives:** Indirectly threatens all goals via environmental instability.

**Inherent:** L4 × I3 = **12 (Medium)** — these events are expected to occur.

**Designed Controls:** Keep the programme's own conduct beyond reproach; maintain recommendation traceability so the programme is visibly part of the solution; prepared communications. Effectiveness: **Weak** (the events themselves are outside programme control).

**Residual:** L3 × I3 = **9 (Medium)**.

**4Ts Response:** **TOLERATE** — the triggering events cannot be treated; the programme treats only its own exposure and response.

**Appetite (inferred ≤ 6 Reputational):** ❌ **Exceeds** by 3 — note to Programme Board; accepted as an environmental risk.

**Mitigation Action:** Maintain a prepared, honest communications posture and recommendation-traceability evidence so the programme can respond credibly to any shock. Owner: Programme SRO. Target: **Ongoing**. Target residual: 9 (accepted).

---

### Risk R-018: Transaction integrity not provable at independent assurance

**Category:** TECHNOLOGY — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Post Office CTO

**Description:** The delivered system's tamper-evidence, immutability and point-in-time reconstruction design cannot be proven, and fails independent assurance.

**Root Cause:** Provable, cryptographically tamper-evident transaction integrity is hard engineering; design intent is not the same as assured delivery.

**Triggers:** An assurance review unable to confirm append-only/tamper-evidence; reconstruction not demonstrable.

**Consequences:** The programme's central guarantee fails; go-live cannot proceed safely; loss of credibility.

**Affected Stakeholders:** Sub-postmasters, Inquiry legacy, Post Office CTO, Programme SRO.

**Related Objectives:** Threatens STKE goal G-1; outcome O-1.

**Inherent:** L3 × I5 = **15 (High)**.

**Designed Controls:** PRIN Principle 6 (non-negotiable); REQ FR-004, FR-005, NFR-P-004, NFR-C-002, DR-001/002; independent assurance gate (BR-010). Effectiveness: **Adequate** — strong by design, unproven until built and assured.

**Residual:** L3 × I5 = **15 (High)** — residual stays High: until the design is built and independently verified, the likelihood of failing assurance remains "Possible" and impact catastrophic.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Technology; ≤ 6 for integrity-critical):** ❌ **Significantly exceeds** — escalate to Steering Committee as a standing item.

**Mitigation Action:** Prototype and independently verify the tamper-evident audit and reconstruction design at High-Level Design stage — do not defer integrity proof to late testing. Owner: Post Office CTO. Target: **2026-12-31** (HLD assurance). Target residual: 10.

---

### Risk R-019: Covert write path to branch accounts exists in the delivered system

**Category:** TECHNOLOGY — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** CISO / SIRO

**Description:** A support, maintenance, administrative or database-level path exists by which branch financial records can be created, altered or deleted without named attribution, immutable logging and visibility to the sub-postmaster.

**Root Cause:** Covert remote access existed in Horizon and was denied [POHR-C2]; conventional architectures grant privileged/DBA write access by default.

**Triggers:** A support process that bypasses application attribution; service-account write access; an unreviewed database path.

**Consequences:** Exact recurrence of the scandal's enabling condition; wrongful liability becomes possible again; total loss of trust.

**Affected Stakeholders:** Sub-postmasters, Inquiry legacy, Post Office CTO, CISO.

**Related Objectives:** Threatens STKE goal G-5; outcome O-1.

**Inherent:** L5 × I5 = **25 (Critical)** — without a deliberate control this is the default, and it is catastrophic.

**Designed Controls:** PRIN Principle 7 (non-negotiable); REQ BR-008, FR-006–FR-009, FR-018, NFR-SEC-006; threat modelling and independent assurance of every write channel. Effectiveness: **Adequate** — strong by design, unproven until built and assured.

**Residual:** L3 × I5 = **15 (High)** — residual stays High until an independent assurance audit confirms no covert write path exists in the built system.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Technology; ≤ 6 for integrity-critical):** ❌ **Significantly exceeds** — escalate to Steering Committee as a standing item.

**Mitigation Action:** Threat-model every write channel; design out privileged/DBA mutation of financial data; commission an independent assurance audit explicitly confirming the absence of covert write paths. Owner: CISO/SIRO with Post Office CTO. Target: **2026-12-31** (HLD assurance). Target residual: 10.

---

### Risk R-020: Integration complexity across 80+ components causes failure or delay

**Category:** TECHNOLOGY — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Post Office CTO

**Description:** The replacement must integrate with, and migrate from, an estate of more than 80 components under mixed ownership [POHR-C3]; this complexity causes integration failure or major delay.

**Root Cause:** A large, tightly coupled legacy estate; mixed supplier ownership.

**Triggers:** Undocumented dependencies; integration defects at scale; a component supplier unable to deliver.

**Consequences:** Delivery delay; cost overrun (feeds R-009); migration risk.

**Affected Stakeholders:** Post Office CTO, incoming suppliers, Branch Operations.

**Related Objectives:** Threatens STKE goals G-2, G-8.

**Inherent:** L4 × I4 = **16 (High)**.

**Designed Controls:** Composable, standards-based target architecture (PRIN Principles 3, 14); REQ NFR-I (open standards, integration); FR-021 phased coexistence; independent assurance. Effectiveness: **Adequate**.

**Residual:** L3 × I4 = **12 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Technology):** ❌ **Exceeds** by 4 — escalate to Programme Board.

**Mitigation Action:** Complete a full component and interface inventory; sequence integration into the phased migration; assure integration design at HLD. Owner: Post Office CTO. Target: **2026-12-31**. Target residual: 8.

---

### Risk R-021: Migration "launders" disputed historical balances

**Category:** TECHNOLOGY — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Enterprise Architect (data lead)

**Description:** Data migration silently carries forward disputed or unreliable historical balances as apparently clean opening balances, presenting contested figures as authoritative.

**Root Cause:** Decades of records of contested reliability across Legacy Horizon, Horizon Online/HNG and the pre-Horizon Capture system.

**Triggers:** Migration without provenance marking; disputed items not flagged; opening balances stated without basis.

**Consequences:** Re-harm to sub-postmasters; renewed disputes; undermining of the integrity guarantee.

**Affected Stakeholders:** Sub-postmasters, Inquiry legacy, Post Office CTO.

**Related Objectives:** Threatens STKE goal G-6; outcome O-1.

**Inherent:** L3 × I4 = **12 (Medium)**.

**Designed Controls:** REQ DR-003, DR-004, DR-009 (provenance markers, disputed-item flagging, lineage); PRIN Principle 11; migration assurance review. Effectiveness: **Strong**.

**Residual:** L2 × I4 = **8 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Technology):** ✅ **Within** appetite (at threshold).

**Mitigation Action:** Enforce provenance and reliability marking on every migrated record; flag all known disputed items; independently review migration logic. Owner: Enterprise Architect (data lead). Target: **2027-03-31**. Target residual: 6.

---

### Risk R-022: New single-supplier lock-in recreated

**Category:** TECHNOLOGY — **Status:** Open — **Risk Owner:** Post Office CTO — **Action Owner:** Finance & Commercial Director

**Description:** The replacement recreates deep single-supplier lock-in, so a future transition is again a multi-year, multi-hundred-million-pound undertaking.

**Root Cause:** Commercial pressure and contract terms that reward embedding; proprietary formats.

**Triggers:** Proprietary interfaces or data formats; contracts without tested exit provisions.

**Consequences:** Future inability to change supplier at acceptable cost — the Horizon lock-in repeated.

**Affected Stakeholders:** Post Office CTO, Finance & Commercial, HM Treasury.

**Related Objectives:** Threatens STKE goal G-9.

**Inherent:** L3 × I3 = **9 (Medium)**.

**Designed Controls:** REQ BR-007, NFR-I-001/002/003 (open standards, data portability, exit readiness); PRIN Principle 24; contractual exit clauses. Effectiveness: **Adequate**.

**Residual:** L2 × I3 = **6 (Medium)**.

**4Ts Response:** **TREAT.**

**Appetite (inferred ≤ 8 Technology):** ✅ **Within** appetite.

**Mitigation Action:** Mandate open standards and documented interfaces; include tested exit and data-portability provisions in every significant supplier contract. Owner: Finance & Commercial Director. Target: **2026-12-31**. Target residual: 6.

---

## D. Risk Category Analysis

### STRATEGIC Risks

**Total:** 4 — **Avg Inherent:** 15.3 — **Avg Residual:** 9.3 — **Control Effectiveness:** 39% reduction.
**Risks:** R-001 (15 High), R-002 (12 Medium), R-003 (6 Medium), R-004 (4 Low).
**Key Themes:** Political pressure on pace; the trust imperative; environmental and commercial uncertainty.
**Category Profile:** ⚠️ Concerning — R-001 and R-002 exceed appetite; both are existential to the programme.

### OPERATIONAL Risks

**Total:** 4 — **Avg Inherent:** 14.0 — **Avg Residual:** 7.3 — **Control Effectiveness:** 48% reduction.
**Risks:** R-005 (9 Medium), R-006 (8 Medium), R-007 (6 Medium), R-008 (6 Medium).
**Key Themes:** The Fujitsu exit; safe migration of a large network; capability and readiness.
**Category Profile:** ⚠️ Mostly within appetite — only R-005 marginally exceeds; strong control design.

### FINANCIAL Risks

**Total:** 3 — **Avg Inherent:** 13.3 — **Avg Residual:** 9.3 — **Control Effectiveness:** 30% reduction.
**Risks:** R-009 (12 Medium), R-010 (6 Medium), R-011 (10 Medium).
**Key Themes:** Cost control against the NBIT precedent; funding continuity under scrutiny.
**Category Profile:** ⚠️ Concerning — R-009 and R-011 exceed appetite; a robust SOBC is the key control.

### COMPLIANCE Risks

**Total:** 4 — **Avg Inherent:** 13.3 — **Avg Residual:** 7.0 — **Control Effectiveness:** 47% reduction.
**Risks:** R-012 (8 Medium), R-013 (8 Medium), R-014 (6 Medium), R-015 (6 Medium).
**Key Themes:** Data protection in migration; Inquiry alignment; security and procurement compliance.
**Category Profile:** ⚠️ Concerning — R-012 and R-013 exceed the very-low compliance appetite; strong control design.

### REPUTATIONAL Risks

**Total:** 2 — **Avg Inherent:** 13.5 — **Avg Residual:** 9.5 — **Control Effectiveness:** 30% reduction.
**Risks:** R-016 (10 Medium), R-017 (9 Medium).
**Key Themes:** A live integrity incident; external shocks from the ongoing scandal aftermath.
**Category Profile:** ❌ Both exceed the very-low reputational appetite; reputational harm is hard to recover — prevention is critical.

### TECHNOLOGY Risks

**Total:** 5 — **Avg Inherent:** 16.6 — **Avg Residual:** 11.2 — **Control Effectiveness:** 33% reduction.
**Risks:** R-018 (15 High), R-019 (15 High), R-020 (12 Medium), R-021 (8 Medium), R-022 (6 Medium).
**Key Themes:** Provable integrity; no covert access; integration complexity; sound migration; exit-readiness.
**Category Profile:** ❌ Highest-risk category — R-018 and R-019 carry the programme's defining risk and stay High until built and assured.

---

## E. Risk Ownership Matrix

| Stakeholder (Risk Owner) | Owned Risks | Critical | High (residual) | Medium | Low | Notes |
|--------------------------|-------------|----------|-----------------|--------|-----|-------|
| Programme SRO | R-001, R-003, R-011, R-013, R-016 | 0 | 1 (R-001) | 4 | 0 | Strategic, funding and reputational accountability |
| Post Office CTO | R-005, R-008, R-018, R-019, R-020, R-022 | 0 | 2 (R-018, R-019) | 4 | 0 | ⚠️ Heaviest concentration — all integrity/technology risk |
| Finance & Commercial Director | R-004, R-009, R-010, R-015 | 0 | 0 | 3 | 1 | Financial and commercial risk |
| Service Owner | R-002, R-007 | 0 | 0 | 2 | 0 | Trust and readiness |
| Branch Operations Director | R-006 | 0 | 0 | 1 | 0 | Service continuity |
| Data Protection Officer / SIRO | R-012 | 0 | 0 | 1 | 0 | Data protection |
| CISO / SIRO | R-014 | 0 | 0 | 1 | 0 | Security compliance (also action owner on R-019) |
| Post Office Board / Chair | R-017 | 0 | 0 | 1 | 0 | Environmental reputational risk |

**Concentration analysis:** The Post Office CTO owns 6 risks including the two highest residual (R-018, R-019). This is appropriate by domain but a single-point concentration — the CTO's risk load should be reviewed by the Programme Board, and integrity-critical risks (R-018, R-019) co-monitored with the CISO and independent assurance.

**Escalation paths:** Strategic/financial → Programme SRO → Programme Board → DBT → Minister. Technology/integrity → Post Office CTO → Steering Committee. Compliance → SIRO → Programme Board / DBT assurance.

---

## F. 4Ts Response Framework Summary

| Response | Count | % | Key Examples |
|----------|-------|---|--------------|
| **TOLERATE** | 2 | 9% | R-003 (policy change), R-017 (external shocks) — triggers outside programme control |
| **TREAT** | 20 | 91% | R-001, R-002, R-018, R-019 and all other risks — active mitigation |
| **TRANSFER** | 0 | 0% | No risk here is meaningfully transferable — integrity and reputational risk cannot be outsourced |
| **TERMINATE** | 0 | 0% | This is a must-deliver programme — no activity can be terminated |

**Response by category:**

| Category | Tolerate | Treat | Transfer | Terminate |
|----------|----------|-------|----------|-----------|
| STRATEGIC | 1 | 3 | 0 | 0 |
| OPERATIONAL | 0 | 4 | 0 | 0 |
| FINANCIAL | 0 | 3 | 0 | 0 |
| COMPLIANCE | 0 | 4 | 0 | 0 |
| REPUTATIONAL | 1 | 1 | 0 | 0 |
| TECHNOLOGY | 0 | 5 | 0 | 0 |

**Key insight:** 91% of risks require active treatment and none can be transferred or terminated — characteristic of a mandatory, high-stakes programme. The two Tolerate risks are tolerated only as to their *triggers* (which are external); the programme still actively manages its *exposure and response*.

---

## G. Risk Appetite Compliance

> ⚠️ **No formal organizational risk appetite statement exists** (`projects/000-global/policies/` is empty). The thresholds below are an **inferred appetite**, set deliberately low to reflect a programme whose purpose is to remediate one of the most serious miscarriages of justice in British legal history. They must be **ratified by the Programme Board / DBT** before this register is approved.

**Inferred risk appetite thresholds (residual score):**

| Category | Appetite | Threshold | Rationale |
|----------|----------|-----------|-----------|
| STRATEGIC | Low–Medium | ≤ 9 | Tolerance for delivery uncertainty, not for trust failure |
| OPERATIONAL | Low–Medium | ≤ 8 | Branch services are essential infrastructure |
| FINANCIAL | Low | ≤ 8 | Public money under intense scrutiny; NBIT precedent |
| COMPLIANCE | Very Low | ≤ 6 | Minimal tolerance for legal or regulatory breach |
| REPUTATIONAL | Very Low | ≤ 6 | Reputational harm is the scandal's lasting legacy |
| TECHNOLOGY | Low | ≤ 8 (≤ 6 for integrity-critical) | Effectively zero appetite for integrity failure |

**Risks exceeding the inferred appetite (11):**

| Risk ID | Category | Appetite | Residual | Excess | Escalation |
|---------|----------|----------|----------|--------|------------|
| R-001 | STRATEGIC | 9 | 15 | +6 | Programme Board + DBT |
| R-002 | STRATEGIC | 9 | 12 | +3 | Programme Board |
| R-005 | OPERATIONAL | 8 | 9 | +1 | Monitor; SRO note |
| R-009 | FINANCIAL | 8 | 12 | +4 | DBT + HM Treasury |
| R-011 | FINANCIAL | 8 | 10 | +2 | DBT |
| R-012 | COMPLIANCE | 6 | 8 | +2 | SIRO |
| R-013 | COMPLIANCE | 6 | 8 | +2 | Programme SRO |
| R-016 | REPUTATIONAL | 6 | 10 | +4 | Programme Board + Post Office Board |
| R-017 | REPUTATIONAL | 6 | 9 | +3 | Programme Board (accepted as environmental) |
| R-018 | TECHNOLOGY | 8 (6) | 15 | +7 (+9) | Steering Committee — standing item |
| R-019 | TECHNOLOGY | 8 (6) | 15 | +7 (+9) | Steering Committee — standing item |

**Overall appetite compliance:** ❌ 11 of 22 risks (50%) exceed the inferred appetite. Every category except OPERATIONAL contains at least one risk over appetite. This is consistent with an early-stage programme whose controls are designed but not yet operational — residual scores should fall as controls are built and assured, and the register must be re-scored on evidence at the first assurance gate.

---

## H. Prioritized Action Plan

### Priority 1: URGENT (Highest residual / integrity-critical)

| # | Action | Risk(s) | Owner | Target Date | Expected Impact |
|---|--------|---------|-------|-------------|-----------------|
| 1 | Prototype and independently verify the tamper-evident audit and reconstruction design at HLD | R-018 | Post Office CTO | 2026-12-31 | 15 → 10 |
| 2 | Threat-model all write channels; commission assurance audit confirming no covert write path | R-019 | CISO / Post Office CTO | 2026-12-31 | 15 → 10 |
| 3 | Constitute independent assurance with board-backed halt authority; make the exit date assurance-conditional | R-001 | Programme SRO | 2026-09-30 | 15 → 10 |

### Priority 2: HIGH (Exceeds appetite, high residual)

| # | Action | Risk(s) | Owner | Target Date | Expected Impact |
|---|--------|---------|-------|-------------|-----------------|
| 4 | Stand up genuine co-design with NFSP/CWU/JFSA and a baseline confidence survey | R-002 | Service Owner | 2026-09-30 | 12 → 8 |
| 5 | Produce an optimism-bias-adjusted SOBC with gate-linked staged funding | R-009 | Finance & Commercial Director | 2026-09-30 | 12 → 8 |
| 6 | Complete a component/interface inventory; sequence integration into phased migration | R-020 | Post Office CTO | 2026-12-31 | 12 → 8 |
| 7 | Complete the DPIA before migration; enforce minimisation and encryption in migration tooling | R-012 | Data Protection Officer | 2026-09-30 | 8 → 6 |

### Priority 3: MEDIUM (Treatment to bring within appetite)

| # | Action | Risk(s) | Owner | Target Date | Expected Impact |
|---|--------|---------|-------|-------------|-----------------|
| 8 | Make Fujitsu knowledge transfer / data access / disclosure contractual; begin early capture | R-005 | Post Office CTO | 2026-12-31 | 9 → 6 |
| 9 | Maintain audit-ready evidence and a proactive NAO/PAC engagement plan | R-011 | Finance & Commercial Director | 2026-09-30 | 10 → 8 |
| 10 | Establish a live Inquiry-recommendation traceability matrix | R-013 | Enterprise Architect | 2026-09-30 | 8 → 6 |
| 11 | Mandate rehearsed, transparent incident response and honest BED-register disclosure | R-016 | Post Office CTO | 2027-03-31 | 10 → 8 |

> Remaining risks (R-003, R-004, R-006, R-007, R-008, R-010, R-014, R-015, R-017, R-021, R-022) carry the mitigation actions named in their Section C profiles; they are within or close to appetite and managed via the routine review cycle.

**Action plan summary:** 11 priority actions; the most material — Priority 1 — target the three High residual risks and aim to bring all three to 10 (Medium) by the HLD assurance gate. A programme-validated cost for these actions is established via `/arckit:sobc` and `/arckit:plan`.

---

## I. Integration with SOBC

| SOBC Section | How this register feeds it |
|--------------|----------------------------|
| **Strategic Case** | Strategic risks (R-001, R-002, R-003) evidence the urgency and the "do it right" imperative |
| **Economic Case** | Financial risks (R-009, R-010, R-011) + HM Treasury optimism bias inform risk-adjusted costs and contingency |
| **Commercial Case** | R-004, R-005, R-022 inform the procurement and exit-management approach |
| **Management Case (Part E)** | The full register, Top 10, ownership matrix and monitoring framework form the risk-management section |
| **Recommendation** | The Concerning profile and 3 High residual risks should shape phasing and the go/no-go criteria |

---

## J. Monitoring and Review Framework

| Risk Level | Review Frequency | Reviewed By | Escalated To |
|------------|------------------|-------------|--------------|
| High (13-19) | Monthly (R-001, R-018, R-019 — standing Steering Committee item) | Risk Owner + Independent Assurance | Steering Committee |
| Medium (6-12) | Monthly | Risk Owner | Programme Board |
| Low (1-5) | Quarterly | Action Owner | Risk Owner |

**Escalation triggers:** any risk increasing by 3+ points; any new Critical risk; any High residual risk with no progressing mitigation; any risk exceeding appetite with no escalation recorded.

**Reporting:** Monthly — full register to the Programme Board; the three High residual risks to the Steering Committee. Quarterly — risk appetite compliance and trend analysis to DBT assurance.

**Re-baseline point:** This register must be **re-scored on evidence after the High-Level Design and the first independent assurance gate** — current residual scores credit designed, not operational, controls.

**Risk Register Owner:** Programme Management Office (PMO), on behalf of the Programme SRO. **Next Review Date:** 2026-06-21.

---

## K. Orange Book Compliance Checklist

**Part I — Risk Management Principles:**

- ✅ **Governance and Leadership** — every risk has an owner drawn from the `ARC-001-STKE-v1.0` RACI; escalation paths defined to Steering Committee, Programme Board, DBT and Minister.
- ✅ **Integration** — risks linked to stakeholder goals (G-1…G-10), requirements (`ARC-001-REQ-v1.0`) and the SOBC.
- ✅ **Collaboration and Best Information** — risks sourced from the stakeholder analysis (conflicts and drivers), the architecture principles and the background research; assessments justified.
- ✅ **Risk Management Processes** — systematic identification across all 6 categories; consistent 5×5 inherent/residual assessment; 4Ts responses applied.
- ✅ **Continual Improvement** — defined review cycle, escalation triggers, and an explicit evidence-based re-baseline point.

**Part II — Risk Control Framework:** risk appetite addressed (inferred, pending ratification); ownership and governance established; assessment methodology documented; control effectiveness measured (inherent vs residual).

---

## Appendix A: Risk Assessment Scales

### Likelihood (1-5)

| Score | Rating | Probability |
|-------|--------|-------------|
| 1 | Rare | < 5% |
| 2 | Unlikely | 5-25% |
| 3 | Possible | 25-50% |
| 4 | Likely | 50-75% |
| 5 | Almost Certain | > 75% |

### Impact (1-5)

| Score | Rating | Description |
|-------|--------|-------------|
| 1 | Negligible | Minimal impact, easily absorbed |
| 2 | Minor | Manageable within contingency |
| 3 | Moderate | Significant; requires management effort |
| 4 | Major | Severe; threatens objectives |
| 5 | Catastrophic | Existential; programme failure or fresh injustice |

### Risk Score

| Range | Level | Action |
|-------|-------|--------|
| 20-25 | 🟥 Critical | Immediate escalation |
| 13-19 | 🟧 High | Senior management attention, mitigation plan required |
| 6-12 | 🟨 Medium | Management monitoring |
| 1-5 | 🟩 Low | Routine monitoring |

---

## Appendix B: Stakeholder-Risk Linkage

| Stakeholder (from `ARC-001-STKE-v1.0`) | Driver / Concern | Risk(s) | Residual |
|----------------------------------------|------------------|---------|----------|
| Minister / DBT (SD-1, SD-2) | Visible delivery; sound stewardship | R-001, R-003, R-011 | 15, 6, 10 |
| Sub-postmasters & representative bodies (SD-6, SD-7) | A system they can trust | R-002, R-007, R-016, R-019, R-021 | 12, 6, 10, 15, 8 |
| HM Treasury / NAO (SD-8, SD-13) | Value for public money | R-009, R-010, R-011, R-015 | 12, 6, 10, 6 |
| Inquiry legacy (SD-9) | Recommendations honoured | R-013, R-016 | 8, 10 |
| Post Office CTO (SD-5) | Modern, exitable, sustainable architecture | R-008, R-018, R-019, R-020, R-022 | 6, 15, 15, 12, 6 |
| Fujitsu / incoming suppliers (SD-10, SD-11) | Orderly exit; commercial clarity | R-004, R-005 | 4, 9 |
| ICO (SD-12) | Lawful, proportionate data processing | R-012, R-014 | 8, 6 |
| Customers / public (SD-14) | Uninterrupted services | R-006 | 8 |

**Stakeholder conflicts mapped to risks** (from `ARC-001-STKE-v1.0` conflict analysis): pace vs assurance → R-001; cost vs doing it properly → R-009; incumbent caution vs transparency → R-005; exit pace vs continuity → R-006.

---

## Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| **Risk Register Owner (PMO)** | PENDING | PENDING | PENDING |
| **Enterprise Architect** | Mark Craddock | PENDING | PENDING |
| **Senior Responsible Owner** | PENDING | PENDING | PENDING |

---

## Next Steps

1. **This week:** Ratify a formal risk appetite statement; place R-001, R-018, R-019 as standing Steering Committee items; brief all risk owners.
2. **This month:** Initiate Priority 1 actions (R-018, R-019, R-001); validate the assessment with each risk owner.
3. **This quarter:** Feed the register into `/arckit:sobc` Management Case Part E; re-score residual risk on evidence after the High-Level Design and first assurance gate.

---

**END OF RISK REGISTER**

*This risk register follows HM Treasury Orange Book (2023) principles and integrates with ArcKit's stakeholder-driven architecture governance framework.*

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| POHR | post-office-horizon-research.md | Research / Reference | 000-global/external/ | Background research report on the Post Office Horizon IT system, the scandal, the inquiry, the redress schemes and the replacement programme |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| POHR-C1 | POHR | §6.1 NBIT | Risk Factor | "Post Office chairman Nigel Railton publicly stated NBIT was effectively 'set up to fail' ... a cited taxpayer cost reaching the order of £1bn." |
| POHR-C2 | POHR | §1.5 Remote access | Risk Factor | "Fujitsu, and to a lesser extent the Post Office, had remote access to branch records and could 'insert, inject, edit or delete transaction data or data in branch accounts.'" |
| POHR-C3 | POHR | §6.2 Target architecture | Risk Factor | "Post Office CTO Paul Anastassi has described Horizon as comprising more than 80 components, of which only about half are managed by Fujitsu." |
| POHR-C4 | POHR | §5.4 Fujitsu contribution | Risk Factor | "Fujitsu has publicly acknowledged a 'moral obligation' to contribute to redress costs but ... had not made any interim payment nor agreed a figure." |
| POHR-C5 | POHR | §6.2 Timeline | Procurement Constraint | "Fujitsu's exit was projected for roughly eight to twelve months after both contracts are signed (i.e. broadly mid-2027), with complete eradication of Horizon targeted by 2030." |
| POHR-C6 | POHR | §5.3 Redress schemes | Risk Factor | "combined redress of approximately £1.56 billion paid to over 12,300 claimants as of 30 April 2026 ... the government has estimated total redress at around £2 billion." |
| POHR-C7 | POHR | §5.4 Accountability | Risk Factor | "A Metropolitan Police-led criminal investigation, Operation Olympos, is examining potential offences of perjury and perverting the course of justice." |
| POHR-C8 | POHR | §6.3 Accenture involvement | Procurement Constraint | "the commercial specifics of the Accenture/One View Commerce Horizon engagement ... contract values, exact scope split, signature dates ... were not confirmed in the sources reviewed." |
| POHR-C9 | POHR | §2.1 Bugs, errors and defects | Risk Factor | "Evidence to the inquiry indicated Fujitsu was aware of bugs from as early as 1999, and that this knowledge was not properly disclosed to sub-postmasters or to the courts." |
| POHR-C10 | POHR | §4.3 Volume 1 | Compliance Constraint | "Sir Wyn Williams published Volume 1 of the inquiry's final report ... It made 19 recommendations." |

### Unreferenced Documents

| Filename | Source Location | Reason |
|----------|-----------------|--------|
| ARC-000-PRIN-v1.0.md | 000-global/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |
| ARC-001-STKE-v1.0.md | 001-post-office-horizon/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |
| ARC-001-REQ-v1.0.md | 001-post-office-horizon/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |

---

**Generated by**: ArcKit `/arckit:risk` command
**Generated on**: 2026-05-21
**ArcKit Version**: 5.0.2
**Project**: Post Office Horizon (Project 001)
**AI Model**: Claude Opus 4.7 (1M context)
