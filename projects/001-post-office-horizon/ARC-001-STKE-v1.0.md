# Stakeholder Drivers & Goals Analysis: Post Office Horizon

> **Template Origin**: Official | **ArcKit Version**: 5.0.2 | **Command**: `/arckit:stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| Document ID | ARC-001-STKE-v1.0 |
| Document Type | Stakeholder Drivers & Goals Analysis |
| Project | Post Office Horizon (Project 001) |
| Classification | OFFICIAL |
| Status | DRAFT |
| Version | 1.0 |
| Created Date | 2026-05-21 |
| Last Modified | 2026-05-21 |
| Review Cycle | Quarterly (stakeholder drivers evolve as context changes) |
| Next Review Date | 2026-08-21 |
| Owner | Mark Craddock, Enterprise Architect |
| Reviewed By | PENDING |
| Approved By | PENDING — Programme Senior Responsible Owner |
| Distribution | Post Office Horizon Programme — programme board, architecture, delivery, assurance and governance teams; DBT shareholder team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial creation from `/arckit:stakeholders`; same-day refresh to add traceability into `ARC-001-REQ-v1.0` (requirements coverage per goal; stakeholder conflicts mapped to the REQ conflict set) | PENDING | PENDING |

---

## Executive Summary

### Purpose

This document identifies the stakeholders of the Post Office Horizon replacement programme, their underlying drivers (motivations, concerns and pressures), how those drivers manifest into goals, and the measurable outcomes that will satisfy them. It provides traceability from individual stakeholder concerns to programme success metrics, and — following the requirements specification — onward into the requirements that implement each goal (`ARC-001-REQ-v1.0`).

This is not a routine technology programme. It replaces the system at the heart of the most extensive miscarriage of justice in British legal history. Every stakeholder's drivers are shaped by that history, by the Post Office Horizon IT Inquiry, and by sustained political, parliamentary and media scrutiny.

### Key Findings

The dominant synergy is that almost every stakeholder ultimately wants the **same destination** — a branch IT system that is demonstrably trustworthy and never again the basis of wrongful liability. The dominant conflict is over **pace and cost versus assurance and integrity**: ministerial and Treasury pressure for visible, affordable delivery sits against the lesson that the original Horizon went live over its own specialists' objections and the in-house NBIT replacement was judged "set up to fail" [POHR-C1]. Sub-postmasters and the Inquiry's legacy are now powerful stakeholders whose trust must be earned, not assumed.

The 10 goals in this analysis are now implemented by the 79 requirements in `ARC-001-REQ-v1.0`; the requirements-coverage line under each goal records the linkage, and the five stakeholder conflicts below are carried through into the requirements conflict set (REQ Conflicts C-1 to C-5).

### Critical Success Factors

- The replacement provably guarantees transaction integrity and attributable, transparent access — and is seen by sub-postmasters to do so (not merely asserted to).
- Delivery pace is governed by independent assurance evidence, never by political deadline alone — the failure mode that produced both Horizon and NBIT is not repeated.
- The programme stays within its government funding envelope and withstands NAO and Public Accounts Committee scrutiny.
- The Inquiry's relevant recommendations and the spirit of its findings are demonstrably embedded in the design and governance.
- Branch service continuity for customers is maintained throughout the Fujitsu exit and migration.

### Stakeholder Alignment Score

**Overall Alignment**: MEDIUM

Alignment on the *end state* is unusually high — a trustworthy system serves shareholder, minister, postmaster, regulator and supplier alike. Alignment on the *path* is weaker: genuine, structural tension exists between speed/cost and assurance/integrity, and between the incumbent supplier's caution and the transparency the programme requires. These conflicts are manageable but must be governed openly (see Conflict Analysis).

---

## Stakeholder Identification

> The Post Office (Post Office Limited) is a private company **wholly owned by the UK Government**, with the shareholding held by the Department for Business and Trade (DBT) and managed via UK Government Investments (UKGI). It is not a government department; UK Government Functional Standards (GovS 005, GovS 007) therefore apply directly to the DBT/government side and are adopted by the programme as good practice and as a condition of government funding.

### Internal Stakeholders

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|----------------|-----------|----------|---------------------|
| Post Office Board & Chair | Corporate governance (Chair: Nigel Railton) | HIGH | HIGH | Board reporting, major decision authority |
| Post Office CEO & Executive | Executive leadership | HIGH | HIGH | Executive steering, accountability for delivery |
| Programme SRO | Senior Responsible Owner, Horizon replacement | HIGH | HIGH | Manage closely — chairs programme board, owns spend |
| Post Office CTO & DDaT | Technology leadership (CTO: Paul Anastassi) | HIGH | HIGH | Architecture and delivery authority |
| Enterprise Architecture team | Architecture governance | MEDIUM | HIGH | Day-to-day collaboration, design assurance |
| Branch / Field Operations | Network operations & postmaster support | MEDIUM | HIGH | Transition planning, runbooks, readiness |
| Finance & Commercial | Funding, business case, contracts | HIGH | MEDIUM | Budget checkpoints, commercial governance |
| Legal & General Counsel | Legal, redress liaison, disclosure | HIGH | MEDIUM | Legal risk, disclosure obligations |
| CISO / SIRO | Information & cyber security risk | HIGH | MEDIUM | Security gates, risk acceptance |
| Data Protection Officer | UK GDPR compliance | MEDIUM | MEDIUM | DPIA sign-off, data governance |

### External Stakeholders

| Stakeholder | Organization | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| Department for Business and Trade (DBT) | UK Government | Shareholder & funder | HIGH | HIGH |
| UK Government Investments (UKGI) | UK Government | Shareholder management | HIGH | MEDIUM |
| Minister / Secretary of State for Business and Trade | UK Government | Political accountability | HIGH | HIGH |
| HM Treasury | UK Government | Funding & spending control | HIGH | MEDIUM |
| Parliament (PAC, Business & Trade Select Committee) | UK Parliament | Scrutiny | HIGH | MEDIUM |
| National Audit Office (NAO) | UK Parliament | Audit & value-for-money | HIGH | MEDIUM |
| Sub-postmasters & branch network | ~11,500 branches | Operators / users | HIGH | HIGH |
| Sub-postmaster representative bodies | NFSP, CWU, JFSA | Representation & campaigning | HIGH | HIGH |
| Horizon victims / redress claimants | Affected individuals | Affected community | MEDIUM | HIGH |
| Post Office Horizon IT Inquiry legacy | Inquiry (Sir Wyn Williams) | Recommendations & scrutiny | HIGH | MEDIUM |
| Fujitsu | Incumbent supplier | Outgoing operator | HIGH | MEDIUM |
| Incoming delivery suppliers | Reported as Accenture & One View Commerce | New operator / builder | HIGH | HIGH |
| EPOS replacement supplier | To be confirmed | Component supplier | MEDIUM | HIGH |
| Information Commissioner's Office (ICO) | Regulator | Data protection oversight | HIGH | MEDIUM |
| National Cyber Security Centre (NCSC) | UK Government | Cyber assurance | MEDIUM | MEDIUM |
| Financial Conduct Authority (FCA) | Regulator | Banking / access-to-cash oversight | MEDIUM | LOW |
| Customers / the public | Branch users | Beneficiary | LOW | MEDIUM |
| Media & public scrutiny | Notably Computer Weekly | Scrutiny | MEDIUM | HIGH |

### UK Government Digital Roles (GovS 005)

> Applied by the programme as good practice and as a condition of government funding. The Post Office is a government-owned company; these roles are filled within the Post Office and/or DBT.

| Role | Responsibility | Typical Power/Interest | Engagement Strategy |
|------|---------------|----------------------|---------------------|
| Senior Responsible Owner (SRO) | Accountable for programme outcomes and spend | HIGH / HIGH | Manage Closely — chairs programme board, decision escalation |
| Service Owner | Owns the end-to-end branch IT service and postmaster outcomes | HIGH / HIGH | Manage Closely — regular service reviews |
| Product Manager | Prioritises capability against postmaster and policy needs | MEDIUM / HIGH | Keep Informed — roadmap and sprint reviews |
| Delivery Manager | Manages delivery cadence, risks and dependencies | MEDIUM / HIGH | Keep Informed — delivery reporting, risk log |
| DBT digital / commercial assurance | Spend control and cross-government standards on the shareholder side | HIGH / MEDIUM | Keep Satisfied — spend control submissions, assurance gates |
| DDaT Profession Lead | Digital, data & technology capability | LOW / MEDIUM | Monitor — capability and resourcing input |

### UK Government Security Roles (GovS 007)

| Role | Responsibility | Typical Power/Interest | Engagement Strategy |
|------|---------------|----------------------|---------------------|
| Senior Security Risk Owner (SSRO) | Owns protective security risk at board level | HIGH / MEDIUM | Keep Satisfied — security risk escalation, quarterly review |
| Senior Information Risk Owner (SIRO) | Owns information & cyber risk, signs risk acceptance | HIGH / MEDIUM | Keep Satisfied — information risk decisions, DPIA sign-off |
| Departmental Security Officer (DSO) equivalent | Day-to-day security coordination and policy | HIGH / MEDIUM | Keep Satisfied — compliance gates, incident reporting |
| Cyber Security Lead | Operational cyber, NCSC CAF assessment liaison | MEDIUM / HIGH | Keep Informed — security architecture reviews, testing |

### Stakeholder Power-Interest Grid

```text
                          INTEREST
              Low                          High
        ┌──────────────────────┬──────────────────────┐
        │   KEEP SATISFIED     │   MANAGE CLOSELY     │
        │                      │                      │
        │ • NAO                │ • DBT (shareholder)  │
   High │ • Parliament PAC/BTSC│ • Minister / SoS     │
        │ • ICO                │ • Post Office Board  │
        │ • Inquiry legacy     │ • Programme SRO      │
 P      │ • Fujitsu (exit)     │ • Post Office CTO    │
 O      │ • HM Treasury *      │ • Sub-postmasters &  │
 W      │                      │   representative bds │
 E      │                      │ • Incoming suppliers │
 R      ├──────────────────────┼──────────────────────┤
        │      MONITOR         │    KEEP INFORMED     │
        │                      │                      │
        │ • Industry / standards│ • Branch operations  │
   Low  │   bodies             │ • Enterprise Arch.   │
        │ • FCA (low interest  │ • Horizon claimants  │
        │   in build detail)   │ • Customers / public │
        │                      │ • Media scrutiny     │
        └──────────────────────┴──────────────────────┘

  * HM Treasury sits on the Keep Satisfied / Manage Closely
    boundary — high interest at funding decision points.
```

| Stakeholder | Power | Interest | Quadrant | Engagement Strategy |
|-------------|-------|----------|----------|---------------------|
| DBT (shareholder & funder) | HIGH | HIGH | Manage Closely | Shareholder reviews, funding governance |
| Minister / Secretary of State | HIGH | HIGH | Manage Closely | Briefings, milestone assurance, PQ support |
| Post Office Board & Chair | HIGH | HIGH | Manage Closely | Board reporting, major decisions |
| Programme SRO | HIGH | HIGH | Manage Closely | Programme board chair, weekly steering |
| Post Office CTO & DDaT | HIGH | HIGH | Manage Closely | Architecture & delivery authority |
| Sub-postmasters & representative bodies | HIGH | HIGH | Manage Closely | Co-design, transparent engagement, trust-building |
| Incoming delivery suppliers | HIGH | HIGH | Manage Closely | Joint delivery governance, contract management |
| HM Treasury | HIGH | MEDIUM | Keep Satisfied | Spending control submissions, funding gates |
| NAO | HIGH | MEDIUM | Keep Satisfied | Audit readiness, evidence packs |
| Parliament (PAC / BTSC) | HIGH | MEDIUM | Keep Satisfied | Evidence, transparency, hearing preparation |
| ICO | HIGH | MEDIUM | Keep Satisfied | DPIA, data protection compliance evidence |
| Inquiry legacy & recommendations | HIGH | MEDIUM | Keep Satisfied | Recommendation traceability, design evidence |
| Fujitsu (incumbent, exiting) | HIGH | MEDIUM | Keep Satisfied | Transition governance, knowledge transfer |
| Enterprise Architecture team | MEDIUM | HIGH | Keep Informed | Design assurance, architecture reviews |
| Branch / Field Operations | MEDIUM | HIGH | Keep Informed | Readiness planning, release communication |
| Horizon victims / redress claimants | MEDIUM | HIGH | Keep Informed | Transparent, sensitive communication |
| Customers / the public | LOW | MEDIUM | Keep Informed | Service-continuity messaging |
| Media & public scrutiny | MEDIUM | HIGH | Keep Informed | Proactive, accurate, transparent disclosure |
| FCA | MEDIUM | LOW | Monitor | Access-to-cash / banking compliance touchpoints |

**Quadrant Interpretation:**

- **Manage Closely** (High Power, High Interest): Key decision-makers requiring active engagement.
- **Keep Satisfied** (High Power, Lower Interest): Influential stakeholders needing periodic, evidenced updates.
- **Keep Informed** (Lower Power, High Interest): Engaged stakeholders needing regular, honest communication.
- **Monitor** (Lower Power, Lower Interest): Minimal engagement, watch for changes in position.

---

## Stakeholder Drivers Analysis

### SD-1: Minister / Secretary of State for Business and Trade — Political delivery and accountability

**Stakeholder**: Minister / Secretary of State for Business and Trade.

**Driver Category**: RISK (political) / STRATEGIC

**Driver Statement**: Demonstrate visible, credible progress on ending the Horizon era and exiting Fujitsu, while avoiding a further public failure on their watch.

**Context & Background**: The Horizon scandal is a sustained, high-profile political issue with cross-party attention, frequent parliamentary questions, and an ITV-drama-level of public awareness. Ministers are accountable to Parliament for the government's response and for the substantial public funding committed. A replacement that is late, over budget or — worst of all — repeats Horizon's failures would be politically severe.

**Driver Intensity**: CRITICAL

**Enablers**: Clear, evidenced milestones; a credible exit plan from Fujitsu; visible alignment with the Inquiry's recommendations; honest reporting that survives scrutiny.

**Blockers**: Slippage and cost overrun (the NBIT precedent [POHR-C1]); any new integrity incident; perception that the programme is "Horizon 2".

**Related Stakeholders**: DBT, HM Treasury, Parliament, sub-postmaster representative bodies (politically powerful), Inquiry legacy.

---

### SD-2: Department for Business and Trade (DBT) — Sound stewardship of a government-owned company

**Stakeholder**: DBT, as shareholder and funder (with UKGI managing the shareholding).

**Driver Category**: RISK / COMPLIANCE (accountability)

**Driver Statement**: Ensure the programme is properly governed, delivers value for public money, and discharges the government's commitment to the Inquiry's findings and to affected sub-postmasters.

**Context & Background**: DBT owns the Post Office and funds the transformation. It responded to the Inquiry's Volume 1 report on 12 February 2026, accepting 18 of 19 recommendations [POHR-C3]; it must now show those commitments are honoured. DBT carries the accountability if the programme fails, and answers to Parliament and the NAO.

**Driver Intensity**: CRITICAL

**Enablers**: Robust programme governance; independent assurance; transparent status reporting; a defensible business case.

**Blockers**: Opaque reporting; cost escalation; loss of confidence among sub-postmasters or Parliament.

**Related Stakeholders**: Minister, HM Treasury, UKGI, Programme SRO, NAO.

---

### SD-3: Programme SRO — Accountable, defensible delivery

**Stakeholder**: Senior Responsible Owner for the Horizon replacement programme.

**Driver Category**: RISK / PERSONAL (accountability)

**Driver Statement**: Deliver the programme to a standard that is personally defensible before Parliament, the NAO and public scrutiny — getting it *right*, not merely *done*.

**Context & Background**: The SRO is the named, accountable owner of programme outcomes and spend. Given the scrutiny, the SRO role here carries unusual personal and reputational exposure. The SRO's strongest interest is honest assurance: NBIT was judged "set up to fail" [POHR-C1] precisely because uncomfortable truths did not surface in time.

**Driver Intensity**: CRITICAL

**Enablers**: Genuine independent assurance; realistic governance gates with halt authority; a culture where bad news travels upward.

**Blockers**: Pressure to report green status against the evidence; gates that cannot stop delivery; concealment lower in the supply chain.

**Related Stakeholders**: DBT, Minister, Post Office Board, Enterprise Architecture team, Inquiry legacy.

---

### SD-4: Post Office Board & Chair — Restore the organisation's legitimacy

**Stakeholder**: Post Office Board and Chair (Nigel Railton).

**Driver Category**: STRATEGIC / RISK

**Driver Statement**: Rebuild the Post Office as a trustworthy institution and put the technology foundations of the scandal permanently behind it.

**Context & Background**: The Board governs an organisation whose conduct caused the scandal. The current leadership has publicly disowned the prior approach — the Chair stated NBIT was "set up to fail" and building in-house was "fundamentally wrong in hindsight" [POHR-C1]. The Board needs the replacement to be both technically sound and a visible break with the past.

**Driver Intensity**: HIGH

**Enablers**: A credible procurement-led strategy; demonstrable cultural change; transparent treatment of sub-postmasters.

**Blockers**: Any sign of the old culture (concealment, defensiveness); further commercial or delivery missteps.

**Related Stakeholders**: SRO, DBT, sub-postmasters, CTO & DDaT.

---

### SD-5: Post Office CTO & DDaT — A modern, sustainable, exitable architecture

**Stakeholder**: Post Office CTO (Paul Anastassi) and the DDaT function.

**Driver Category**: STRATEGIC / OPERATIONAL

**Driver Statement**: Replace a tightly coupled legacy estate with a composable, standards-based, cloud-native architecture that the Post Office can sustain, assure and evolve.

**Context & Background**: Horizon comprises 80-plus components under mixed ownership. The stated target is a composable, event-driven, service-oriented architecture with migration to the cloud [POHR-C8]. The CTO must deliver this while keeping ~11,500 branches running and meeting the integrity principles in ARC-000-PRIN-v1.0.

**Driver Intensity**: HIGH

**Enablers**: Open standards and clear interface contracts; capable suppliers; sound architecture governance.

**Blockers**: Lock-in to a single supplier; pressure to lift-and-shift rather than re-architect; integration debt.

**Related Stakeholders**: Enterprise Architecture team, incoming suppliers, Fujitsu, branch operations.

---

### SD-6: Sub-postmasters & the branch network — A system they can trust and operate safely

**Stakeholder**: Sub-postmasters and counter staff across ~11,500 branches.

**Driver Category**: OPERATIONAL / PERSONAL (trust and livelihood)

**Driver Statement**: Operate a branch IT system that is accurate, transparent and explainable — one that can never again make them liable for shortfalls they did not cause.

**Context & Background**: Sub-postmasters were held personally liable, pursued and prosecuted for discrepancies materially caused by system defects, while being told — falsely — that branch accounts could not be altered remotely [POHR-C7]. Their driver is existential: their livelihoods, homes and reputations were destroyed. They will judge the replacement by whether they, personally, can see and trust their own accounts.

**Driver Intensity**: CRITICAL

**Enablers**: Provable transaction integrity; complete, plain-language visibility of their accounts; a fair dispute process; genuine co-design.

**Blockers**: Any opacity; central adjustments they cannot see; being asked to trust the system on assurance alone.

**Related Stakeholders**: Representative bodies, Horizon claimants, branch operations, Inquiry legacy.

---

### SD-7: Sub-postmaster representative bodies & Horizon victims — Justice embedded, not just promised

**Stakeholder**: NFSP, CWU, the Justice for Subpostmasters Alliance (JFSA, founded by Alan Bates), and the wider community of Horizon victims and redress claimants.

**Driver Category**: RISK (justice & trust) / CUSTOMER

**Driver Statement**: Ensure the replacement structurally prevents a recurrence — and that the programme treats sub-postmasters as partners, not as a problem to be managed.

**Context & Background**: These bodies and campaigners exposed the scandal and remain highly effective, credible and politically influential. Combined redress had reached ~£1.56bn to 12,300+ claimants by 30 April 2026 [POHR-C4]; the human cost is still being addressed. They will scrutinise the replacement closely and can shape political and public opinion decisively.

**Driver Intensity**: CRITICAL

**Enablers**: Transparent engagement; victims and postmasters involved in design and testing; honest acknowledgement of the past.

**Blockers**: Tokenistic consultation; defensiveness; any perception the programme prioritises cost or speed over integrity.

**Related Stakeholders**: Sub-postmasters, Minister, Parliament, media, Inquiry legacy.

---

### SD-8: HM Treasury — Value for public money

**Stakeholder**: HM Treasury.

**Driver Category**: FINANCIAL

**Driver Statement**: Ensure the substantial public investment delivers a controlled, value-for-money outcome and does not become an open-ended liability.

**Context & Background**: Government has committed substantial funding to Post Office IT transformation (reported commitments include £483m in February 2026, with total investment reported as exceeding £700m) on top of ~£2bn estimated total redress [POHR-C4]. The abandoned NBIT programme cost the order of £1bn [POHR-C1]. Treasury applies spending controls and will resist cost escalation.

**Driver Intensity**: HIGH

**Enablers**: A robust business case; staged funding tied to assurance gates; competitive procurement; cost transparency.

**Blockers**: Scope creep; cost overrun; a repeat of NBIT-style uncontrolled spend.

**Related Stakeholders**: DBT, NAO, Programme SRO, Finance & Commercial.

---

### SD-9: Post Office Horizon IT Inquiry legacy — Recommendations honoured in substance

**Stakeholder**: The legacy of the Post Office Horizon IT Inquiry (Sir Wyn Williams) and its recommendations.

**Driver Category**: COMPLIANCE / ASSURANCE

**Driver Statement**: Ensure the lessons of the Inquiry are embedded in the design, governance and culture of the replacement — not just acknowledged.

**Context & Background**: Volume 1 of the Inquiry's final report (8 July 2025) made 19 recommendations [POHR-C2], 18 accepted by government [POHR-C3]; later volumes on systemic and individual accountability are expected. While the Inquiry is not a programme governance body, its findings are the benchmark against which the public, Parliament and media will judge whether the replacement truly breaks with the past.

**Driver Intensity**: HIGH

**Enablers**: Explicit traceability from Inquiry findings to architecture principles and design decisions; independent assurance.

**Blockers**: Treating the Inquiry as a compliance checkbox; design choices that recreate concealment or covert-access risk.

**Related Stakeholders**: DBT, Minister, sub-postmasters, Enterprise Architecture team.

---

### SD-10: Incoming delivery suppliers — Commercially successful, reputationally safe delivery

**Stakeholder**: Incoming delivery suppliers — reported as Accenture and One View Commerce (OVC) [POHR-C5].

**Driver Category**: STRATEGIC (commercial) / OPERATIONAL

**Driver Statement**: Deliver the replacement profitably and to time, while building rather than damaging reputation on one of the most scrutinised programmes in the UK.

**Context & Background**: Reporting on 21 May 2026 indicates the Post Office has named Accenture and OVC to take over operating Horizon and to help build its replacement [POHR-C5]; commercial detail, scope split and signature dates were not confirmed at the time of this analysis. Whoever the supplier(s), they inherit intense scrutiny: success is reputationally valuable, visible failure is reputationally toxic.

**Driver Intensity**: HIGH

**Enablers**: Clear scope and contracts; realistic timelines; transparent joint governance; access to Fujitsu knowledge.

**Blockers**: Ambiguous scope; pressure to over-commit; a contract structure that rewards lock-in over the programme's exit-readiness principle.

**Related Stakeholders**: Post Office CTO, Fujitsu, EPOS supplier, Programme SRO, Finance & Commercial.

---

### SD-11: Fujitsu — Orderly exit while managing reputation and liability

**Stakeholder**: Fujitsu, the incumbent supplier.

**Driver Category**: RISK (reputational & commercial)

**Driver Statement**: Exit the Horizon contract in an orderly way while limiting further reputational and financial damage and awaiting the Inquiry's conclusions.

**Context & Background**: Fujitsu is central to the scandal. It has acknowledged a "moral obligation" to contribute to redress but, per reporting through March 2026, had not made an interim payment or agreed a figure, citing the unfinished Inquiry [POHR-C6]. Its commercial caution can sit in tension with the openness and knowledge transfer the transition needs.

**Driver Intensity**: MEDIUM (HIGH during the transition window)

**Enablers**: Clear transition contracts and exit terms; defined knowledge-transfer obligations.

**Blockers**: Disputes over exit scope or cost; reluctance to share information; reputational defensiveness.

**Related Stakeholders**: Incoming suppliers, Post Office CTO, Legal & General Counsel, Minister.

---

### SD-12: Information Commissioner's Office (ICO) — Lawful, proportionate data processing

**Stakeholder**: ICO.

**Driver Category**: COMPLIANCE / REGULATORY

**Driver Statement**: Ensure personal data of sub-postmasters, staff and customers is processed lawfully, securely and proportionately throughout the build and migration.

**Context & Background**: The replacement processes personal and financial data at scale and migrates decades of historical records. The ICO expects data protection by design, completed DPIAs, and sound handling of data subject to redress, inquiry and litigation holds.

**Driver Intensity**: MEDIUM

**Enablers**: Early DPIA; data minimisation; clear retention and legal-hold rules; secure migration.

**Blockers**: Migration that copies excessive personal data; weak access controls; unmanaged retention.

**Related Stakeholders**: Data Protection Officer, CISO/SIRO, Enterprise Architecture team.

---

### SD-13: NAO & Parliament — Demonstrable value for money and no repeat failure

**Stakeholder**: National Audit Office and parliamentary committees (Public Accounts Committee; Business & Trade Select Committee).

**Driver Category**: COMPLIANCE (accountability & scrutiny)

**Driver Statement**: Confirm that public money is well spent and that the programme is not heading toward another high-profile public-sector IT failure.

**Context & Background**: Horizon's origins lie in the Pathway PFI failure that the Public Accounts Committee called one of the biggest public-sector IT failures; NBIT later cost ~£1bn [POHR-C1]. The NAO and committees will examine this programme, and their findings shape political and Treasury confidence.

**Driver Intensity**: HIGH

**Enablers**: An auditable evidence trail; honest reporting; independent assurance; controlled spend.

**Blockers**: Opaque governance; cost overrun; optimism bias in status reporting.

**Related Stakeholders**: HM Treasury, DBT, Programme SRO, Minister.

---

### SD-14: Customers & the public — Uninterrupted, reliable branch services

**Stakeholder**: Customers and the public who use Post Office branches.

**Driver Category**: CUSTOMER

**Driver Statement**: Continue to access mail, banking, cash, bill payment and government services at the Post Office without disruption.

**Context & Background**: Branches are essential community infrastructure, particularly for cash access and for people who are digitally or financially excluded. Customers have no interest in the technology change itself — only in services continuing to work through the transition.

**Driver Intensity**: MEDIUM

**Enablers**: Careful, low-disruption migration; well-prepared branch staff; resilient services.

**Blockers**: Outages or service gaps during cutover; under-trained staff at go-live.

**Related Stakeholders**: Branch operations, sub-postmasters, FCA (access to cash).

---

## Driver-to-Goal Mapping

> Each goal records the requirements that implement it in `ARC-001-REQ-v1.0` (the **Requirements coverage** line). Business Requirements (BR) are the primary trace; supporting FR / NFR / DR identifiers are listed where they materially deliver the goal.

### Goal G-1: Provably trustworthy branch IT system

**Derived From Drivers**: SD-1, SD-3, SD-6, SD-7, SD-9

**Goal Owner**: Programme SRO (architecture: Post Office CTO)

**Goal Statement**: Deliver a replacement branch IT system that provably guarantees transaction integrity and attributable, transparent access — meeting every NON-NEGOTIABLE principle in ARC-000-PRIN-v1.0 — verified by independent assurance before go-live.

**Why This Matters**: This is the core of restoring trust and preventing recurrence; it directly satisfies the existential driver of sub-postmasters and the Inquiry's legacy.

**Success Metrics**: Primary — 100% of PRIN Category II validation gates passed and independently verified. Secondary — zero covert write paths confirmed; point-in-time account reconstruction demonstrated.

**Baseline**: Legacy Horizon — covert remote access existed and was denied; integrity unprovable.

**Target**: Independent assurance sign-off that integrity and attribution are provable, before any branch go-live.

**Measurement Method**: Independent technical assurance review against ARC-000-PRIN-v1.0 validation gates; security testing evidence.

**Dependencies**: Architecture principles ratified; capable suppliers; assurance function established.

**Risks to Achievement**: Schedule pressure compresses assurance; integration complexity across 80+ components.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-001; FR-004–FR-009 (immutable record, tamper-evident audit, attributed change); NFR-P-004 (integrity within latency budget); NFR-C-002 (tamper-evident logging); DR-001, DR-002.

---

### Goal G-2: Complete, orderly exit from Fujitsu and Horizon

**Derived From Drivers**: SD-1, SD-2, SD-4, SD-5

**Goal Owner**: Programme SRO

**Goal Statement**: Complete Fujitsu's exit from Horizon operations by mid-2027 and fully eradicate the Horizon system by 2030, with no loss of branch service [POHR-C9].

**Why This Matters**: Ending the Fujitsu/Horizon era is the visible political and organisational objective and the precondition for a clean break.

**Success Metrics**: Primary — Fujitsu operational responsibility for Horizon ended by the agreed transition date. Secondary — % of Horizon components decommissioned; zero service-affecting incidents attributable to transition.

**Baseline**: Fujitsu operating Horizon under bridging contract extensions to ~March 2027.

**Target**: Fujitsu exit ~mid-2027; Horizon fully eradicated by 2030.

**Measurement Method**: Transition milestone tracking; component decommissioning register.

**Dependencies**: Supplier contracts signed; knowledge transfer from Fujitsu; replacement capability operational.

**Risks to Achievement**: Fujitsu transition non-cooperation; replacement not ready, forcing further bridging extensions.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-002; FR-021 (Horizon coexistence for phased migration); INT-009 (legacy Horizon migration interface); DR-003.

---

### Goal G-3: Restore and sustain sub-postmaster trust

**Derived From Drivers**: SD-6, SD-7, SD-4, SD-9

**Goal Owner**: Service Owner

**Goal Statement**: Achieve and sustain a measured sub-postmaster confidence score of at least 80% in the accuracy and transparency of branch IT within 12 months of network rollout.

**Why This Matters**: Trust is the outcome the whole programme exists to restore; a technically sound system that postmasters still distrust is a failure.

**Success Metrics**: Primary — sub-postmaster confidence survey score (target ≥ 80%). Secondary — % of postmasters reporting they can understand and challenge a discrepancy; co-design participation rate.

**Baseline**: To be established by a baseline confidence survey at programme outset.

**Target**: ≥ 80% confidence, sustained.

**Measurement Method**: Independent periodic survey of sub-postmasters; usability research.

**Dependencies**: G-1 achieved; genuine co-design; honest engagement (SD-7 enablers).

**Risks to Achievement**: Engagement perceived as tokenistic; an early integrity incident.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-003, BR-009; FR-010–FR-015 (account visibility, explainability, discrepancy and dispute handling); NFR-U-001, NFR-U-002 (usability and accessibility).

---

### Goal G-4: Deliver within the approved public funding envelope

**Derived From Drivers**: SD-2, SD-8, SD-13

**Goal Owner**: Finance & Commercial Director (accountable: Programme SRO)

**Goal Statement**: Deliver the replacement within the approved government funding envelope, with funding released against assurance gates and no unapproved cost escalation.

**Why This Matters**: Satisfies Treasury, DBT and NAO drivers and avoids a repeat of the NBIT cost failure.

**Success Metrics**: Primary — actual spend within approved envelope (variance within agreed tolerance). Secondary — % of funding released against met assurance gates; forecast accuracy.

**Baseline**: NBIT — ~£1bn taxpayer cost, abandoned [POHR-C1].

**Target**: Delivery within the approved envelope; no adverse NAO value-for-money finding.

**Measurement Method**: Programme financial reporting; spend-control submissions; NAO review.

**Dependencies**: Robust business case (see `/arckit:sobc`); controlled scope; competitive procurement.

**Risks to Achievement**: Scope creep; optimistic baseline estimates; integration cost surprises.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-004. Note — a programme-validated cost estimate is deferred to the Strategic Outline Business Case; REQ records only reported public funding context.

---

### Goal G-5: Eliminate covert remote access to branch accounts

**Derived From Drivers**: SD-6, SD-7, SD-9, SD-3

**Goal Owner**: Post Office CTO

**Goal Statement**: Ensure that, by design, no party can create, alter or delete a branch's financial records without authentication, named attribution, immutable logging and visibility to the affected sub-postmaster — verified by independent assurance.

**Why This Matters**: Covert remote access was the single most damaging fact established about Horizon [POHR-C7]; eliminating it is non-negotiable.

**Success Metrics**: Primary — independent confirmation of zero covert/unattributed write paths. Secondary — 100% of externally initiated entries attributed and notified to the branch.

**Baseline**: Horizon — remote alteration possible and concealed.

**Target**: Covert mutation architecturally impossible; confirmed by assurance and threat modelling.

**Measurement Method**: Threat model review; security testing; assurance audit of all write channels.

**Dependencies**: PRIN Principle 7; architecture and security design.

**Risks to Achievement**: Support/database access paths that bypass application attribution controls.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-008; FR-006–FR-009, FR-018 (compensating-entry corrections, attributed change, no covert write path, support without covert write); NFR-SEC-006.

---

### Goal G-6: Migrate historical data with full provenance

**Derived From Drivers**: SD-6, SD-9, SD-12, SD-5

**Goal Owner**: Post Office CTO (data lead)

**Goal Statement**: Migrate branch and account data from Legacy Horizon, Horizon Online/HNG-A (and account for contested pre-Horizon Capture data) with every record carrying provenance and reliability markers, and disputed items explicitly flagged.

**Why This Matters**: The replacement must not "launder" disputed historical figures into apparently clean opening balances.

**Success Metrics**: Primary — 100% of migrated records carry provenance metadata. Secondary — 100% of known disputed items flagged; migration logic version-controlled and independently reviewed.

**Baseline**: Decades of records of contested reliability across multiple legacy systems.

**Target**: Fully provenance-marked migration; no disputed item silently presented as authoritative.

**Measurement Method**: Migration assurance review; data lineage audit.

**Dependencies**: PRIN Principle 11; access to legacy data and Fujitsu cooperation.

**Risks to Achievement**: Legacy data quality; loss of source-system context during migration.

**Requirements coverage** (`ARC-001-REQ-v1.0`): DR-003 (provenance markers), DR-004 (disputed-item flagging), DR-009 (lineage); FR-021 (coexistence).

---

### Goal G-7: Achieve security and data protection compliance

**Derived From Drivers**: SD-12, SD-8 (risk), SD-2

**Goal Owner**: CISO / SIRO

**Goal Statement**: Achieve a satisfactory NCSC Cyber Assessment Framework posture and full UK GDPR / Data Protection Act 2018 compliance (with FCA-relevant controls for banking services) before network go-live, with completed DPIA.

**Why This Matters**: Satisfies the ICO and security drivers and protects sub-postmaster, staff and customer data.

**Success Metrics**: Primary — NCSC CAF outcomes met at the agreed target profile; DPIA approved. Secondary — zero serious data protection incidents; penetration test findings remediated.

**Baseline**: To be assessed against the legacy estate.

**Target**: Satisfactory CAF posture; approved DPIA; clean security testing gate.

**Measurement Method**: CAF assessment; DPIA review; independent security testing.

**Dependencies**: PRIN Principle 4, 13; security architecture.

**Risks to Achievement**: Security treated as a late gate rather than a design input.

**Requirements coverage** (`ARC-001-REQ-v1.0`): NFR-SEC-001–006; NFR-C-001 (UK GDPR), NFR-C-003 (NCSC CAF), NFR-C-004 (PCI-DSS); DR-005–DR-008.

---

### Goal G-8: Maintain branch service continuity through transition

**Derived From Drivers**: SD-14, SD-6, SD-1

**Goal Owner**: Branch / Field Operations Director

**Goal Statement**: Maintain branch service availability and customer service levels throughout the Fujitsu exit and migration, with no service-affecting outage attributable to the transition.

**Why This Matters**: Branches are essential community infrastructure; disruption would harm customers and undermine confidence.

**Success Metrics**: Primary — zero service-affecting outages attributable to transition. Secondary — branch IT availability maintained at or above current levels; customer satisfaction maintained.

**Baseline**: Current Horizon availability and customer satisfaction levels.

**Target**: Maintained or improved throughout transition.

**Measurement Method**: Availability monitoring; customer satisfaction tracking; incident analysis.

**Dependencies**: Phased migration; branch staff training; resilient design (PRIN Principle 2, 17).

**Risks to Achievement**: Big-bang cutover; under-prepared branch staff.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-006; FR-001–FR-003 (counter, cash/stock, balancing), FR-019–FR-022 (reporting, training mode, coexistence, resilient offline operation); NFR-A-001/002/003.

---

### Goal G-9: Avoid single-supplier lock-in

**Derived From Drivers**: SD-5, SD-2, SD-8

**Goal Owner**: Post Office CTO (commercial: Finance & Commercial)

**Goal Statement**: Build the replacement on open standards and modular components with a tested exit strategy and data portability for every significant supplier relationship, so a future transition is straightforward.

**Why This Matters**: Exiting Fujitsu has taken a decade and hundreds of millions; the replacement must not recreate that lock-in.

**Success Metrics**: Primary — documented and tested exit/portability path for each significant supplier. Secondary — % of interfaces using open, published standards; no proprietary data formats without export.

**Baseline**: Horizon — deep single-supplier lock-in.

**Target**: Exit-ready architecture verified by assurance.

**Measurement Method**: Architecture review against PRIN Principle 3, 14, 24; exit-test evidence.

**Dependencies**: Contract structure; open-standards design.

**Risks to Achievement**: Commercial pressure or contract terms that reward lock-in.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-007; NFR-I-001 (open standards/API), NFR-I-002 (integration capabilities), NFR-I-003 (data portability and exit readiness).

---

### Goal G-10: Honour the Inquiry's recommendations in design and governance

**Derived From Drivers**: SD-9, SD-1, SD-2, SD-7

**Goal Owner**: Programme SRO

**Goal Statement**: Maintain explicit, auditable traceability from the relevant Post Office Horizon IT Inquiry findings and recommendations to the programme's architecture principles, design decisions and governance arrangements.

**Why This Matters**: Honouring the Inquiry in substance is how the programme demonstrates a genuine break with the past.

**Success Metrics**: Primary — 100% of in-scope Inquiry recommendations traced to a principle, design decision or governance control. Secondary — independent confirmation that no design choice recreates concealment or covert-access risk.

**Baseline**: 19 Volume 1 recommendations, 18 accepted by government [POHR-C3]; later volumes pending.

**Target**: Full, maintained traceability, refreshed as later Inquiry volumes are published.

**Measurement Method**: Recommendation traceability matrix; independent assurance.

**Dependencies**: Inquiry outputs; architecture principles; assurance function.

**Risks to Achievement**: Treating the Inquiry as a checkbox; later volumes introducing new expectations mid-programme.

**Requirements coverage** (`ARC-001-REQ-v1.0`): BR-005, BR-010; FR-016 (bugs/errors/defects register and disclosure); NFR-C-005 (Inquiry recommendation traceability reporting).

---

## Goal-to-Outcome Mapping

### Outcome O-1: No wrongful liability — ever again

**Supported Goals**: G-1, G-5, G-6, G-10

**Outcome Statement**: No sub-postmaster is held liable for a discrepancy on the basis of an unverifiable or system-caused account, because the system's records are provably correct, provably unaltered, and fully explainable.

**Measurement Details**: KPI — number of liability actions resting on unverifiable or unexplained system data. Current value — historically hundreds of prosecutions and thousands of recovery demands on exactly that basis. Target — zero. Frequency — continuous; reported quarterly. Data source — dispute and liability case records; integrity assurance reports. Report owner — Service Owner / Legal & General Counsel.

**Business Value**: Financial — avoids future redress liability and litigation cost. Strategic — removes the systemic cause of the scandal. Operational — trustworthy discrepancy handling. Customer — a fair relationship between the Post Office and its postmasters.

**Timeline**: Phase 1 (design) — integrity and attribution provable in design and assurance. Phase 2 (pilot) — demonstrated in pilot branches. Phase 3 (rollout) — sustained network-wide. Sustainment — maintained and independently re-verified.

**Stakeholder Benefits**: Sub-postmasters — protection from wrongful liability. Minister / DBT — the defining proof the scandal cannot recur.

**Leading Indicators**: PRIN Category II gates passed; zero covert write paths confirmed.

**Lagging Indicators**: Sustained absence of liability actions resting on unverifiable data.

---

### Outcome O-2: Sub-postmaster trust restored

**Supported Goals**: G-1, G-3, G-5

**Outcome Statement**: Sub-postmasters demonstrably trust the branch IT system, evidenced by a sustained confidence score of at least 80%.

**Measurement Details**: KPI — sub-postmaster confidence score. Current value — baseline to be established at programme outset. Target — ≥ 80%, sustained. Frequency — quarterly during rollout, then half-yearly. Data source — independent sub-postmaster survey. Report owner — Service Owner.

**Business Value**: Strategic — restored legitimacy of the Post Office. Operational — postmasters engage constructively with the system and disputes. Customer — confident branch staff deliver better service.

**Timeline**: Phase 1 — baseline survey completed. Phase 2 — confidence rising in pilot branches. Phase 3 — ≥ 80% network-wide within 12 months of rollout. Sustainment — sustained ≥ 80%.

**Stakeholder Benefits**: Sub-postmasters & representative bodies — evidence that concerns were heard and addressed. Board / Minister — visible proof of cultural and technical change.

**Leading Indicators**: Co-design participation; positive pilot feedback.

**Lagging Indicators**: Sustained confidence score; reduction in unresolved disputes.

---

### Outcome O-3: Fujitsu exited and Horizon eradicated

**Supported Goals**: G-2, G-8

**Outcome Statement**: Fujitsu no longer operates Post Office branch IT, and the Horizon system is fully eradicated, with branch services uninterrupted throughout.

**Measurement Details**: KPI — Fujitsu/Horizon decommissioning completion (%). Current value — Fujitsu operating Horizon under bridging extensions. Target — 100% — Fujitsu exit ~mid-2027, Horizon eradication by 2030 [POHR-C9]. Frequency — monthly. Data source — transition and decommissioning registers. Report owner — Programme SRO.

**Business Value**: Strategic — a clean break from the systems and supplier of the scandal. Financial — ends bridging-extension costs. Operational — modern, supportable estate.

**Timeline**: Phase 1 — supplier contracts signed (reported summer 2026). Phase 2 — Fujitsu operational exit (~mid-2027). Phase 3 — Horizon component decommissioning. Sustainment — full eradication by 2030.

**Stakeholder Benefits**: Minister / DBT — delivery of the headline political objective. Post Office CTO — a sustainable estate.

**Leading Indicators**: Contracts signed; knowledge transfer progressing.

**Lagging Indicators**: Fujitsu exit complete; Horizon components decommissioned.

---

### Outcome O-4: Value for public money demonstrated

**Supported Goals**: G-4, G-9

**Outcome Statement**: The programme is delivered within its approved funding envelope and withstands NAO and Public Accounts Committee scrutiny without an adverse value-for-money finding.

**Measurement Details**: KPI — spend variance against approved envelope; NAO/PAC findings. Current value — NBIT ~£1bn, abandoned [POHR-C1]. Target — within envelope; no adverse VfM finding. Frequency — monthly financial reporting; per audit cycle. Data source — programme finance; spend-control records; NAO reports. Report owner — Finance & Commercial Director.

**Business Value**: Financial — controlled, predictable public expenditure. Strategic — restored confidence in Post Office programme delivery.

**Timeline**: Phase 1 — approved business case and funding envelope. Phase 2 — funding released against met assurance gates. Phase 3 — delivery within tolerance. Sustainment — sustainable run costs.

**Stakeholder Benefits**: HM Treasury / DBT — controlled spend. NAO / Parliament — an auditable, defensible programme.

**Leading Indicators**: Forecast accuracy; gates met before funding release.

**Lagging Indicators**: Final spend within envelope; clean audit outcome.

---

### Outcome O-5: Independent assurance and Inquiry-aligned governance

**Supported Goals**: G-1, G-10, G-4

**Outcome Statement**: The programme is governed by genuine independent assurance with honest reporting, and every in-scope Inquiry recommendation is traceably reflected in the design and governance.

**Measurement Details**: KPI — assurance gate pass rate on evidence; recommendation traceability coverage. Current value — not yet established (new programme). Target — 100% recommendation traceability; assurance gates with halt authority operating. Frequency — per gate; quarterly traceability review. Data source — independent assurance reports; recommendation traceability matrix. Report owner — Programme SRO.

**Business Value**: Strategic — demonstrable break with the culture the Inquiry exposed. Operational — problems surface early enough to act on.

**Timeline**: Phase 1 — assurance function and traceability matrix established. Phase 2 — gates operating with evidence-based decisions. Phase 3 — sustained through rollout. Sustainment — refreshed as later Inquiry volumes publish.

**Stakeholder Benefits**: SRO / DBT / Minister — a defensible programme. Sub-postmasters / Inquiry legacy — evidence the lessons were learned.

**Leading Indicators**: Assurance function independent and resourced; honest RAG reporting.

**Lagging Indicators**: No concealed-status incidents; full recommendation traceability.

---

### Outcome O-6: Secure, compliant, resilient service

**Supported Goals**: G-7, G-8

**Outcome Statement**: The replacement operates securely and lawfully, with strong data protection and resilient branch services, evidenced by a satisfactory CAF posture, an approved DPIA and no serious data or security incidents.

**Measurement Details**: KPI — NCSC CAF posture; data/security incident count; branch IT availability. Current value — baseline against legacy estate to be assessed. Target — satisfactory CAF profile; zero serious incidents; availability maintained or improved. Frequency — continuous; reported monthly. Data source — security monitoring; CAF assessment; availability monitoring. Report owner — CISO / SIRO.

**Business Value**: Operational — reliable, secure branch services. Compliance — ICO, NCSC and FCA expectations met.

**Timeline**: Phase 1 — security and data protection designed in; DPIA completed. Phase 2 — CAF and security testing gates passed. Phase 3 — sustained secure operation through rollout. Sustainment — continuous monitoring and reassessment.

**Stakeholder Benefits**: ICO / NCSC / FCA — compliance evidence. Customers / sub-postmasters — reliable, safe services.

**Leading Indicators**: DPIA completed early; security testing on track.

**Lagging Indicators**: Sustained satisfactory CAF posture; zero serious incidents.

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| Minister / SoS | SD-1 | Visible, credible delivery; no repeat failure | G-2 | Exit Fujitsu / Horizon | O-3 | Fujitsu exited, Horizon eradicated |
| Minister / SoS | SD-1 | Visible, credible delivery; no repeat failure | G-1 | Trustworthy system | O-1 | No wrongful liability |
| DBT | SD-2 | Sound stewardship & VfM | G-4 | Within funding envelope | O-4 | Value for money demonstrated |
| DBT | SD-2 | Honour Inquiry commitments | G-10 | Honour Inquiry recommendations | O-5 | Inquiry-aligned governance |
| Programme SRO | SD-3 | Defensible, assured delivery | G-1 | Trustworthy system | O-5 | Independent assurance |
| Post Office Board | SD-4 | Restore institutional legitimacy | G-3 | Restore postmaster trust | O-2 | Trust restored |
| Post Office CTO | SD-5 | Modern, exitable architecture | G-9 | Avoid lock-in | O-4 | Value for money / exit-ready |
| Post Office CTO | SD-5 | Sustainable estate | G-6 | Provenance-marked migration | O-1 | No wrongful liability |
| Sub-postmasters | SD-6 | A system they can trust | G-1, G-5 | Integrity; no covert access | O-1, O-2 | No wrongful liability; trust restored |
| Representative bodies / victims | SD-7 | Justice embedded structurally | G-3, G-10 | Trust; honour Inquiry | O-2, O-5 | Trust restored; Inquiry-aligned |
| HM Treasury | SD-8 | Value for public money | G-4 | Within funding envelope | O-4 | Value for money demonstrated |
| Inquiry legacy | SD-9 | Recommendations honoured in substance | G-10 | Honour Inquiry recommendations | O-5 | Inquiry-aligned governance |
| Incoming suppliers | SD-10 | Profitable, reputationally safe delivery | G-2 | Exit Fujitsu / build replacement | O-3 | Fujitsu exited; replacement delivered |
| Fujitsu | SD-11 | Orderly exit | G-2 | Exit Fujitsu / Horizon | O-3 | Fujitsu exited |
| ICO | SD-12 | Lawful, proportionate data processing | G-7 | Security & data compliance | O-6 | Secure, compliant service |
| NAO / Parliament | SD-13 | VfM; no repeat failure | G-4 | Within funding envelope | O-4 | Value for money demonstrated |
| Customers / public | SD-14 | Uninterrupted branch services | G-8 | Service continuity | O-6 | Resilient service |

### Goal → Requirements Coverage (`ARC-001-REQ-v1.0`)

> Onward traceability into the requirements specification. Confirms each stakeholder goal is implemented by named requirements; the requirements document carries the full forward/backward matrix.

| Goal | Primary Business Requirement(s) | Key supporting requirements |
|------|-------------------------------|------------------------------|
| G-1 Trustworthy system | BR-001 | FR-004–FR-009, NFR-P-004, NFR-C-002, DR-001/002 |
| G-2 Exit Fujitsu / Horizon | BR-002 | FR-021, INT-009, DR-003 |
| G-3 Restore postmaster trust | BR-003, BR-009 | FR-010–FR-015, NFR-U-001/002 |
| G-4 Within funding envelope | BR-004 | (cost estimate deferred to SOBC) |
| G-5 Eliminate covert access | BR-008 | FR-006–FR-009, FR-018, NFR-SEC-006 |
| G-6 Provenance-marked migration | BR-002 (migration) | DR-003, DR-004, DR-009, FR-021 |
| G-7 Security & data compliance | BR-004 (assurance) | NFR-SEC-001–006, NFR-C-001/003/004, DR-005–008 |
| G-8 Service continuity | BR-006 | FR-001–FR-003, FR-019–FR-022, NFR-A-001/002/003 |
| G-9 Avoid lock-in | BR-007 | NFR-I-001/002/003 |
| G-10 Honour the Inquiry | BR-005, BR-010 | FR-016, NFR-C-005 |

All 10 goals have requirements coverage — there are no uncovered goals. Conversely, the `/arckit:health` scan flags all 79 requirements as not yet referenced by an ADR; that gap closes once `/arckit:adr` is run.

### Conflict Analysis

**Competing Drivers**:

- **Conflict 1 — Pace vs. assurance.** The Minister (SD-1) and, to a degree, DBT (SD-2) are driven toward visible, fast delivery and a firm Fujitsu exit date; the SRO (SD-3), sub-postmasters (SD-6/SD-7) and the Inquiry legacy (SD-9) are driven toward delivery governed by integrity and assurance evidence. The original Horizon went live over its specialists' objections and NBIT was "set up to fail" [POHR-C1] — both are cautionary precedents.
  - **Resolution Strategy**: Make assurance gates the explicit arbiter of pace. Publish a phased plan (pilot → controlled rollout) so political stakeholders see continuous, evidenced progress without compressing assurance. Independent assurance reports go unfiltered to the programme board (PRIN Principle 23). The Fujitsu exit date is a planning target conditional on assurance, not an override of it.
  - **In requirements**: carried through as **REQ Conflict C-1** (Delivery pace vs. assurance) — resolved by PHASE (assurance-gated rollout; BR-002 made assurance-conditional).

- **Conflict 2 — Cost control vs. doing it properly.** HM Treasury, DBT and NAO (SD-8, SD-2, SD-13) drive hard on cost; integrity, independent assurance, co-design and careful migration all cost money and time.
  - **Resolution Strategy**: Frame integrity and assurance spend as risk reduction against ~£2bn of redress liability and the ~£1bn NBIT write-off [POHR-C1][POHR-C4]. Tie staged funding release to met assurance gates so cost control and quality reinforce rather than oppose each other.
  - **In requirements**: carried through as **REQ Conflict C-3** (Cost control vs. integrity/assurance/co-design) — resolved by PRIORITISE (integrity and assurance are protected scope; SHOULD/COULD functional scope is the deferrable buffer).

- **Conflict 3 — Incumbent caution vs. transition transparency.** Fujitsu (SD-11) is commercially and reputationally cautious and is awaiting the Inquiry before agreeing a redress contribution [POHR-C6]; the programme needs open knowledge transfer and full disclosure during exit.
  - **Resolution Strategy**: Make knowledge-transfer obligations, data access and defect disclosure explicit, contractual transition requirements rather than goodwill items; manage via joint transition governance with Legal oversight.
  - **In requirements**: not a formal REQ requirement-conflict; addressed by REQ Assumption A-3 and Risk R-3, and by INT-009 (legacy migration interface) treating Fujitsu cooperation as a contractual dependency.

- **Conflict 4 — Supplier commercial incentive vs. exit-readiness.** Incoming suppliers (SD-10) have a natural commercial interest in becoming embedded; the programme's Principle 24 demands no lock-in.
  - **Resolution Strategy**: Bake open standards, documented interfaces, data portability and a tested exit plan into contracts and architecture governance, so exit-readiness is contractually enforced, not optional.
  - **In requirements**: addressed directly by BR-007 and NFR-I-001/002/003 (open standards, integration capability, data portability and exit readiness) rather than as a standing REQ conflict.

- **Conflict 5 — Exit pace vs. service continuity.** The drive to leave Fujitsu quickly (SD-1) can pressure a faster cutover than safe migration and branch readiness allow (SD-14, SD-6).
  - **Resolution Strategy**: Phased, low-disruption migration with branch-readiness gates; no big-bang cutover; continuity treated as a hard go/no-go criterion.
  - **In requirements**: carried through as **REQ Conflict C-4** (Exit pace vs. branch service continuity) — resolved by PHASE (continuity is a release gate).

> The requirements specification additionally surfaced two **technical** conflicts that do not originate in stakeholder drivers: REQ Conflict C-2 (immutable cryptographic audit vs. counter response time — resolved INNOVATE, integrity takes precedence) and REQ Conflict C-5 (security/attribution friction vs. counter usability — resolved COMPROMISE). These are tracked in `ARC-001-REQ-v1.0` and need no stakeholder-level resolution.

**Synergies**:

- **Synergy 1**: Sub-postmasters (SD-6), representative bodies/victims (SD-7), the Inquiry legacy (SD-9) and the Enterprise Architecture team all want provable transaction integrity and transparency — a powerful coalition behind PRIN Category II and Goals G-1, G-3, G-5.
- **Synergy 2**: DBT (SD-2), HM Treasury (SD-8) and NAO/Parliament (SD-13) all want value for money and no repeat failure — aligned behind G-4 and disciplined, assured governance.
- **Synergy 3**: The Minister (SD-1) and sub-postmasters (SD-6/SD-7) ultimately share the destination — a trustworthy system and a clean break from the scandal. The conflict is over path, not goal, which makes it resolvable through transparent, phased delivery.

---

## Communication & Engagement Plan

### Stakeholder-Specific Messaging

#### Minister / Secretary of State & DBT

**Primary Message**: The programme is delivering a visible, credible break from Horizon and Fujitsu — and is being done in a way that will withstand the Inquiry's legacy, Parliament and the NAO.

**Key Talking Points**: Phased, evidenced milestones; assurance-gated delivery prevents a repeat of Horizon/NBIT; Inquiry recommendations are traceably embedded.

**Communication Frequency**: Monthly briefings; immediate escalation of material risks.

**Preferred Channel**: Briefings, milestone assurance reports, dashboard.

**Success Story**: A pilot branch operating on the replacement, with postmasters confirming they can see and trust their accounts.

#### Programme SRO & Post Office Board

**Primary Message**: Honest, evidence-based status — including bad news — with assurance gates that genuinely govern pace and spend.

**Key Talking Points**: Independent assurance findings unfiltered; risks surfaced early; decisions defensible before Parliament and the NAO.

**Communication Frequency**: Weekly programme board; monthly Board reporting.

**Preferred Channel**: Programme board, assurance reports, risk log.

**Success Story**: An assurance gate that held delivery until an integrity risk was resolved — and was supported, not overridden.

#### Sub-postmasters & Representative Bodies (NFSP, CWU, JFSA)

**Primary Message**: This system is being designed *with* you and *for* you — you will be able to see and challenge everything that affects your accounts, and you can never again be held liable for the system's errors.

**Key Talking Points**: Co-design and testing involvement; complete account visibility; fair dispute handling; no covert remote access.

**Communication Frequency**: Regular, throughout — co-design sessions, network updates.

**Preferred Channel**: Direct engagement, co-design workshops, plain-language updates.

**Success Story**: Postmasters in co-design seeing their feedback change the product.

#### HM Treasury, NAO & Parliament

**Primary Message**: Public money is controlled and the programme is auditable, assured and on a fundamentally sounder footing than NBIT.

**Key Talking Points**: Funding released against assurance gates; competitive procurement; transparent evidence trail.

**Communication Frequency**: Per spend-control and audit cycle; ahead of hearings.

**Preferred Channel**: Spend-control submissions, evidence packs, audit liaison.

**Success Story**: A clean NAO progress review.

#### Incoming Suppliers & Fujitsu

**Primary Message (incoming)**: Clear scope, fair contracts, transparent joint governance — and exit-readiness built in from day one.

**Primary Message (Fujitsu)**: An orderly, contractually clear exit with defined knowledge-transfer and disclosure obligations.

**Communication Frequency**: Weekly delivery / transition governance.

**Preferred Channel**: Joint governance forums, contract management.

**Success Story**: A clean transition milestone with full knowledge transfer evidenced.

#### Customers / Public & Media

**Primary Message**: Branch services continue uninterrupted; the Post Office is replacing Horizon openly and carefully.

**Key Talking Points**: Service continuity; transparency; honest progress reporting.

**Communication Frequency**: At milestones and as needed; proactive with media.

**Preferred Channel**: Public statements, GOV.UK / corporate communications, proactive media engagement.

**Success Story**: A rollout milestone reported accurately, with no service disruption.

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| Sub-postmasters | Operate Horizon; deep distrust | Operate a transparent, trusted system | HIGH | MEDIUM | Co-design, training, complete visibility, honest engagement |
| Branch / Field Operations | Support Horizon processes | Support new system & transition | HIGH | MEDIUM | Early involvement, runbooks, phased readiness |
| Post Office CTO & DDaT | Manage legacy estate & Fujitsu | Govern modern multi-supplier estate | HIGH | LOW | Architecture governance, capability building |
| Fujitsu | Incumbent operator | Exited supplier | HIGH | MEDIUM | Clear, contractual transition and exit terms |
| Finance & Commercial | NBIT-era cost exposure | Assurance-gated funding | MEDIUM | LOW | Staged funding model, transparent reporting |
| Customers / public | Use branch services | Same services, new system behind them | LOW | LOW | Service-continuity focus, low-disruption migration |

### Change Readiness

**Champions** (Enthusiastic supporters):

- Enterprise Architecture team — the integrity principles are theirs to uphold.
- Sub-postmaster representative bodies / JFSA — provided engagement is genuine; strong advocates for a trustworthy outcome.
- Programme SRO and current Post Office Board — publicly committed to a break with the past.

**Fence-sitters** (Neutral, need convincing):

- Individual sub-postmasters — supportive of the goal but sceptical after Horizon; convinced only by visible, working transparency.
- HM Treasury — supportive if cost control is demonstrably real.
- Media — will support a genuinely transparent programme and scrutinise a defensive one.

**Resisters** (Opposed or sceptical):

- Pockets of legacy organisational culture — defensiveness and optimism bias. *Strategy*: independent assurance, honest-reporting standards, and visible leadership modelling of "bad news travels up".
- Fujitsu, on disclosure and redress contribution — cautious pending the Inquiry [POHR-C6]. *Strategy*: make obligations contractual rather than discretionary.

---

## Risk Register (Stakeholder-Related)

### Risk R-1: Sub-postmaster trust is not restored

**Related Stakeholders**: Sub-postmasters, representative bodies, Minister, Board.

**Risk Description**: The replacement is technically delivered but postmasters still distrust it — perceived as "Horizon 2" — because engagement felt tokenistic or transparency is incomplete.

**Impact on Goals**: G-3, and the credibility of G-1.

**Probability**: MEDIUM — **Impact**: HIGH

**Mitigation Strategy**: Genuine co-design; complete, plain-language account visibility; baseline and track confidence; involve postmasters and victims in testing.

**Contingency Plan**: Independent review of engagement; pause network rollout pending remediation if confidence is below threshold in pilots.

---

### Risk R-2: Political pressure forces a premature go-live

**Related Stakeholders**: Minister, DBT, SRO, sub-postmasters.

**Risk Description**: Pressure to hit a visible date or a firm Fujitsu exit deadline compresses assurance and the system goes live before integrity is proven — the exact failure mode of Horizon and NBIT [POHR-C1].

**Impact on Goals**: G-1, G-5, and ultimately O-1.

**Probability**: MEDIUM — **Impact**: HIGH

**Mitigation Strategy**: Assurance gates with explicit halt authority; gates as the formal arbiter of pace; unfiltered assurance reporting to the board; phased rollout that gives political stakeholders evidenced progress without compressing assurance.

**Contingency Plan**: SRO and Board formally hold the gate; extend Fujitsu bridging arrangements rather than go live unproven.

---

### Risk R-3: Fujitsu transition non-cooperation or knowledge loss

**Related Stakeholders**: Fujitsu, incoming suppliers, Post Office CTO.

**Risk Description**: Fujitsu's commercial caution, or loss of key staff, impedes knowledge transfer and orderly exit.

**Impact on Goals**: G-2, G-6, G-8.

**Probability**: MEDIUM — **Impact**: HIGH

**Mitigation Strategy**: Contractual knowledge-transfer, data-access and disclosure obligations; joint transition governance; early knowledge capture.

**Contingency Plan**: Targeted retention of critical knowledge; legal escalation if obligations are unmet.

---

### Risk R-4: Ambiguity over the incoming supplier arrangement

**Related Stakeholders**: Incoming suppliers (reported Accenture/OVC), Post Office CTO, Finance & Commercial.

**Risk Description**: As of this analysis, the Accenture/OVC role is reported but contract value, scope split and signature dates are unconfirmed [POHR-C5]; planning on unverified assumptions risks rework.

**Impact on Goals**: G-2, G-9, G-10.

**Probability**: MEDIUM — **Impact**: MEDIUM

**Mitigation Strategy**: Confirm the arrangement from official Post Office/DBT sources and published award notices before committing dependent decisions; keep scope and exit-readiness clauses explicit in contracts.

**Contingency Plan**: Re-baseline the programme plan once contracts are confirmed.

---

### Risk R-5: Cost overrun triggers loss of funding confidence

**Related Stakeholders**: HM Treasury, DBT, NAO, Parliament.

**Risk Description**: Cost escalation echoes the NBIT failure [POHR-C1], prompting NAO/PAC criticism and pressure on funding.

**Impact on Goals**: G-4, and programme continuity.

**Probability**: MEDIUM — **Impact**: HIGH

**Mitigation Strategy**: Robust business case; staged funding against assurance gates; disciplined scope and change control; transparent forecasting.

**Contingency Plan**: Early re-baselining and scope re-prioritisation; proactive engagement with Treasury and the NAO.

---

### Risk R-6: A reputational shock mid-programme

**Related Stakeholders**: Minister, Board, media, sub-postmasters.

**Risk Description**: Later Inquiry volumes, the Operation Olympos criminal investigation, or a redress controversy reignite public anger and destabilise the programme environment.

**Impact on Goals**: Indirectly all — through political and stakeholder confidence.

**Probability**: MEDIUM — **Impact**: MEDIUM

**Mitigation Strategy**: Keep the programme's own conduct beyond reproach (transparency, honest reporting); maintain Inquiry-recommendation traceability so the programme can show it is part of the solution; prepared, honest communications.

**Contingency Plan**: Rapid, accurate communication; reaffirm assurance and traceability evidence.

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Programme funding & business case | Finance & Commercial | Programme SRO | HM Treasury, DBT, Post Office Board | NAO, Parliament |
| Supplier selection & contract award | Finance & Commercial | Programme SRO | Post Office CTO, Legal, DBT | Incoming suppliers, Fujitsu |
| Architecture & integrity design decisions | Post Office CTO / Enterprise Architecture | Post Office CTO | CISO/SIRO, Branch Operations, suppliers | Programme board |
| Data migration approach & provenance rules | Enterprise Architecture (data lead) | Post Office CTO | DPO, Legal, independent assurance | Programme board, ICO |
| Transaction-integrity assurance sign-off | Independent assurance function | Programme SRO | Post Office CTO, sub-postmaster representatives | DBT, Minister, Board |
| Go / No-go for pilot and network go-live | Programme board | Programme SRO | Independent assurance, Branch Operations, CISO/SIRO | DBT, Minister, all stakeholders |
| Fujitsu exit timing | Programme board | Programme SRO | Post Office CTO, incoming suppliers, Fujitsu | DBT, Minister |
| Stakeholder engagement & co-design approach | Service Owner | Programme SRO | Representative bodies, Branch Operations | Sub-postmasters, Board |

### Escalation Path

1. **Level 1 — Delivery Manager / Product Manager**: day-to-day delivery decisions, risks and dependencies.
2. **Level 2 — Programme Board (chaired by SRO)**: scope, schedule, budget variances, assurance-gate decisions, conflict resolution.
3. **Level 3 — Post Office Board and DBT (shareholder)**: strategic direction, major funding decisions, unresolved conflicts.
4. **Level 4 — Minister / Secretary of State**: matters of political accountability or major public-interest significance.

Independent assurance findings are reported in parallel, unfiltered, to the Programme Board and Post Office Board, and may not be filtered or softened en route (PRIN Principle 23).

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| Programme SRO | Pending | Awaiting review | PENDING REVIEW |
| Post Office CTO | Pending | Awaiting review | PENDING REVIEW |
| Service Owner | Pending | Awaiting review | PENDING REVIEW |
| Sub-postmaster representative body liaison | Pending | Awaiting review | PENDING REVIEW |
| DBT shareholder team | Pending | Awaiting review | PENDING REVIEW |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Programme SRO | PENDING | PENDING | PENDING |
| Post Office CTO | PENDING | PENDING | PENDING |
| Enterprise Architect | Mark Craddock | PENDING | PENDING |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

No stakeholder interviews had been conducted at the time of this analysis. This document is derived from project context, the architecture principles (ARC-000-PRIN-v1.0), the requirements specification (ARC-001-REQ-v1.0) and the background research report (`post-office-horizon-research.md`).

**Recommended priority interviews** to validate and deepen this analysis:

- Programme SRO — to confirm governance, assurance arrangements and risk appetite.
- Sub-postmaster representative bodies (NFSP, CWU, JFSA) — to validate the trust drivers and co-design expectations.
- Post Office CTO & DDaT — to confirm the target architecture and exit assumptions.
- DBT shareholder team — to confirm funding governance and Inquiry-commitment expectations.
- A sample of practising sub-postmasters — to ground the user drivers in lived experience.

### Appendix B: Survey Results

No stakeholder survey had been conducted at the time of this analysis. A **baseline sub-postmaster confidence survey** is recommended at programme outset to establish the baseline for Goal G-3 and Outcome O-2.

### Appendix C: References

- `ARC-000-PRIN-v1.0` — Post Office Horizon Programme Enterprise Architecture Principles.
- `ARC-001-REQ-v1.0` — Business and Technical Requirements (10 goals mapped to 79 requirements; 5 requirement conflicts).
- `projects/000-global/external/post-office-horizon-research.md` — Post Office Horizon background research report.
- Post Office Horizon IT Inquiry — Volume 1 of the final report (8 July 2025) and the government response (12 February 2026).
- Government Functional Standard GovS 005 (Digital) and GovS 007 (Security).
- Recommended next ArcKit artifacts: ARC-001-ADR (Architecture Decision Records), ARC-001-RISK (Risk Register), ARC-001-SOBC (Strategic Outline Business Case).

---

## Revision History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial DRAFT; same-day refresh adding requirements traceability into ARC-001-REQ-v1.0 |

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| POHR | post-office-horizon-research.md | Research / Reference | 000-global/external/ | Background research report on the Post Office Horizon IT system, the scandal, the statutory inquiry, the redress schemes and the replacement programme |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| POHR-C1 | POHR | §6.1 NBIT | Risk Factor | "Post Office chairman Nigel Railton publicly stated NBIT was effectively 'set up to fail,' and that the decision to build the replacement in-house was 'fundamentally wrong in hindsight.' ... a cited taxpayer cost reaching the order of £1bn." |
| POHR-C2 | POHR | §4.3 Volume 1 | Compliance Constraint | "It made 19 recommendations, focused on making redress faster and fairer." |
| POHR-C3 | POHR | §4.4 Government response | Compliance Constraint | "The Department for Business and Trade responded on 12 February 2026, accepting 18 of the 19 recommendations and rejecting one (Recommendation 13 ...)." |
| POHR-C4 | POHR | §5.3 Redress schemes | Risk Factor | "combined redress of approximately £1.56 billion paid to over 12,300 claimants as of 30 April 2026 ... the government has estimated total redress at around £2 billion." |
| POHR-C5 | POHR | §6.3 Accenture involvement | Procurement Constraint | "wire-service coverage ... stated that the Post Office has named Accenture and One View Commerce (OVC) as the suppliers selected to take over operating Horizon from Fujitsu and to ... build the technology intended to replace it." |
| POHR-C6 | POHR | §5.4 Fujitsu contribution | Risk Factor | "Fujitsu has publicly acknowledged a 'moral obligation' to contribute to redress costs but ... had not made any interim payment nor agreed a figure, stating it would await the conclusion of the inquiry." |
| POHR-C7 | POHR | §1.5 Remote access | Stakeholder Need | "Fujitsu, and to a lesser extent the Post Office, had remote access to branch records and could 'insert, inject, edit or delete transaction data or data in branch accounts.'" |
| POHR-C8 | POHR | §6.2 Target architecture | Design Decision | "The stated target architecture is a composable, event-driven, service-oriented architecture built from standards-based modular components, including migration from on-premise data centres to the cloud." |
| POHR-C9 | POHR | §6.2 Timeline | Procurement Constraint | "Fujitsu's exit was projected for roughly eight to twelve months after both contracts are signed (i.e. broadly mid-2027), with complete eradication of Horizon targeted by 2030." |

### Unreferenced Documents

| Filename | Source Location | Reason |
|----------|-----------------|--------|
| ARC-000-PRIN-v1.0.md | 000-global/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |
| ARC-001-REQ-v1.0.md | 001-post-office-horizon/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |

---

**Generated by**: ArcKit `/arckit:stakeholders` command
**Generated on**: 2026-05-21
**ArcKit Version**: 5.0.2
**Project**: Post Office Horizon (Project 001)
**AI Model**: Claude Opus 4.7 (1M context)
