# Project Requirements: Post Office Horizon

> **Template Origin**: Official | **ArcKit Version**: 5.0.2 | **Command**: `/arckit:requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.0 |
| **Document Type** | Business and Technical Requirements |
| **Project** | Post Office Horizon (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-05-21 |
| **Last Modified** | 2026-05-21 |
| **Review Cycle** | 30 days (under active pre-approval review) |
| **Next Review Date** | 2026-06-20 |
| **Owner** | Mark Craddock (Enterprise Architect) |
| **Reviewed By** | [PENDING] |
| **Approved By** | [PENDING] |
| **Distribution** | Post Office Horizon Programme — programme board, architecture, delivery, security and assurance teams; vendor RFP recipients on issue |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial creation from `/arckit:requirements` command | [PENDING] | [PENDING] |

## Document Purpose

This document defines the business and technical requirements for the Post Office Horizon replacement programme — the procurement and delivery of a replacement for the Fujitsu-operated Horizon branch IT system, and the exit from Fujitsu. It will be used as the basis for vendor RFPs, architecture reviews, design, testing and acceptance. Requirements trace to the stakeholder goals in `ARC-001-STKE-v1.0` and align with the architecture principles in `ARC-000-PRIN-v1.0`.

---

## Executive Summary

### Business Context

The Horizon IT system is the branch accounting and electronic point-of-sale (EPOS) platform used across roughly 11,500 Post Office branches. Defects in Horizon produced apparent cash shortfalls in sub-postmasters' branch accounts; rather than treating these as system faults, the Post Office held sub-postmasters liable and prosecuted hundreds — one of the most extensive miscarriages of justice in British legal history. A central, established fact is that Fujitsu (and to a lesser extent the Post Office) could alter branch accounts remotely while denying that this was possible [POHR-C1].

The Post Office must now replace Horizon and exit Fujitsu. An earlier in-house replacement, the New Branch IT (NBIT) programme, was abandoned at a reported taxpayer cost of the order of £1bn after the Post Office chairman judged it to have been "set up to fail" [POHR-C6]. The current approach is a competitive procurement of a composable, standards-based replacement, with migration to the cloud [POHR-C4].

These requirements exist to ensure the replacement is **demonstrably trustworthy** — that it provably guarantees transaction integrity and attributable, transparent access, so that no sub-postmaster is ever again held liable for a system-caused discrepancy.

### Objectives

- Deliver a branch IT system with provable, tamper-evident transaction integrity and no covert remote access.
- Give sub-postmasters complete, real-time, intelligible visibility of their accounts and a fair dispute process.
- Exit Fujitsu and eradicate Horizon while maintaining uninterrupted branch services.
- Honour the Post Office Horizon IT Inquiry's recommendations in design and governance.
- Deliver within the approved public funding envelope, under independent assurance, with no single-supplier lock-in.

### Expected Outcomes

- Zero liability actions resting on unverifiable or system-caused account data (Outcome O-1).
- Sub-postmaster confidence in branch IT sustained at ≥ 80% (Outcome O-2).
- Fujitsu exited (~mid-2027) and Horizon fully eradicated by 2030 (Outcome O-3) [POHR-C5].
- Delivery within the approved funding envelope, with no adverse NAO value-for-money finding (Outcome O-4).

### Project Scope

**In Scope**:

- Replacement branch IT system: branch accounting/ledger and EPOS across the ~11,500-branch network.
- Transaction integrity, immutable audit, postmaster account visibility, discrepancy and dispute handling.
- Migration of branch and account data from Legacy Horizon and Horizon Online/HNG, and exit from Fujitsu.
- Sub-postmasters, counter assistants, branch/field managers and Post Office operational staff as users.
- Integrations required for branch services (banking, mails/parcels, payments, government services).

**Out of Scope**:

- The Horizon redress/compensation schemes (separate government and Post Office schemes).
- The Post Office Horizon IT Inquiry and the Operation Olympos criminal investigation.
- Wider Post Office back-office IT modernisation (a related but separately procured initiative) [POHR-C9].
- Retail product and commercial strategy for Post Office services.

---

## Stakeholders

| Stakeholder | Role | Organization | Involvement Level |
|-------------|------|--------------|-------------------|
| Programme SRO | Senior Responsible Owner | Post Office | Decision maker / accountable |
| Post Office CTO | Technology leadership | Post Office | Technical oversight |
| Enterprise Architect | Architecture governance | Post Office | Requirements & technical oversight |
| Service Owner | End-to-end branch IT service | Post Office | Requirements definition, user outcomes |
| Sub-postmaster representatives | NFSP / CWU / JFSA liaison | External | Requirements input, user acceptance |
| CISO / SIRO | Security & information risk | Post Office | Security review |
| Data Protection Officer | UK GDPR compliance | Post Office | Regulatory compliance |
| DBT shareholder team | Shareholder & funder | Department for Business and Trade | Funding governance, assurance |
| Independent assurance lead | Technical assurance | Independent | Assurance gates |

> Full stakeholder driver analysis, power-interest grid and RACI: see `ARC-001-STKE-v1.0`.

---

## Business Requirements

### BR-001: Demonstrably trustworthy branch IT system

**Description**: The replacement must provably guarantee transaction integrity and attributable, transparent access, satisfying every NON-NEGOTIABLE principle in `ARC-000-PRIN-v1.0`, verified by independent assurance before any branch go-live.

**Rationale**: This is the core purpose of the programme — to remove the systemic conditions that produced the Horizon scandal. Traces to STKE goal G-1 and outcome O-1.

**Success Criteria**:

- 100% of PRIN Category II validation gates passed and independently verified before go-live.
- Independent assurance sign-off that integrity and attribution are provable.

**Priority**: MUST_HAVE

**Stakeholder**: Programme SRO; sub-postmasters; Inquiry legacy.

---

### BR-002: Exit Fujitsu and eradicate Horizon

**Description**: The Post Office must end Fujitsu's operational responsibility for branch IT (target ~mid-2027) and fully eradicate the Horizon system (target by 2030), with no loss of branch service [POHR-C5].

**Rationale**: Ending the Fujitsu/Horizon era is the headline organisational and political objective. Traces to STKE goals G-2, G-8 and outcome O-3.

**Success Criteria**:

- Fujitsu operational responsibility for Horizon ended by the agreed, assurance-conditional transition date.
- 100% of Horizon components decommissioned by 2030.

**Priority**: MUST_HAVE

**Stakeholder**: Minister / DBT; Programme SRO; Post Office Board.

---

### BR-003: Restore and sustain sub-postmaster trust

**Description**: The programme must achieve and sustain measured sub-postmaster confidence of at least 80% in the accuracy and transparency of branch IT within 12 months of network rollout.

**Rationale**: A technically sound system that postmasters still distrust is a failure. Traces to STKE goal G-3 and outcome O-2.

**Success Criteria**:

- Sub-postmaster confidence survey score ≥ 80%, sustained.
- Sub-postmasters and Horizon victims involved in design and acceptance testing.

**Priority**: MUST_HAVE

**Stakeholder**: Post Office Board; sub-postmaster representative bodies.

---

### BR-004: Deliver within the approved public funding envelope

**Description**: The replacement must be delivered within the approved government funding envelope, with funding released against assurance gates and no unapproved cost escalation.

**Rationale**: Avoids a repeat of the NBIT cost failure (~£1bn, abandoned) [POHR-C6] and satisfies Treasury, DBT and NAO scrutiny. Traces to STKE goal G-4 and outcome O-4.

**Success Criteria**:

- Actual spend within the approved envelope (within agreed tolerance).
- No adverse NAO value-for-money finding.

**Priority**: MUST_HAVE

**Stakeholder**: HM Treasury; DBT; Finance & Commercial.

---

### BR-005: Honour the Post Office Horizon IT Inquiry recommendations

**Description**: The programme must maintain explicit, auditable traceability from the relevant Post Office Horizon IT Inquiry findings and recommendations to architecture principles, design decisions and governance controls [POHR-C10].

**Rationale**: Honouring the Inquiry in substance is how the programme demonstrates a genuine break with the past. Traces to STKE goal G-10 and outcome O-5.

**Success Criteria**:

- 100% of in-scope Inquiry recommendations traced to a principle, design decision or governance control.
- Traceability refreshed as later Inquiry volumes are published.

**Priority**: MUST_HAVE

**Stakeholder**: DBT; Minister; Inquiry legacy.

---

### BR-006: Maintain uninterrupted branch services

**Description**: Branch services (mails, banking, cash, bill payment, government services, retail) must continue without service-affecting disruption throughout the Fujitsu exit and migration.

**Rationale**: Branches are essential community infrastructure, especially for cash access and digitally excluded customers. Traces to STKE goal G-8 and outcome O-6.

**Success Criteria**:

- Zero service-affecting outages attributable to the transition.
- Branch service availability and customer satisfaction maintained or improved.

**Priority**: MUST_HAVE

**Stakeholder**: Branch Operations; customers; sub-postmasters.

---

### BR-007: Avoid single-supplier lock-in

**Description**: The replacement must be built on open standards and modular components, with a tested exit strategy and data portability for every significant supplier relationship.

**Rationale**: Exiting Fujitsu has taken a decade and hundreds of millions; the replacement must not recreate that lock-in. Traces to STKE goal G-9 and aligns with PRIN Principle 24.

**Success Criteria**:

- Documented and tested exit/portability path for each significant supplier.
- No proprietary data formats without an open export capability.

**Priority**: MUST_HAVE

**Stakeholder**: Post Office CTO; HM Treasury; Finance & Commercial.

---

### BR-008: Eliminate covert remote access to branch accounts

**Description**: It must be impossible, by design, for any party to create, alter or delete a branch's financial records without authentication, named attribution, immutable logging and visibility to the affected sub-postmaster.

**Rationale**: Covert remote access was the single most damaging fact established about Horizon [POHR-C1]. Traces to STKE goal G-5; aligns with PRIN Principle 7 (NON-NEGOTIABLE).

**Success Criteria**:

- Independent confirmation of zero covert/unattributed write paths to branch financial data.
- 100% of externally initiated entries attributed and notified to the branch.

**Priority**: MUST_HAVE

**Stakeholder**: Sub-postmasters; Inquiry legacy; Programme SRO.

---

### BR-009: Fair treatment of sub-postmasters in discrepancy handling

**Description**: An apparent shortfall must be treated as an event requiring investigation, not as presumptive evidence of fault, and no liability may attach while a genuine dispute is unresolved.

**Rationale**: The Post Office reversed the burden of proof; the replacement must not. Traces to STKE goal G-3; aligns with PRIN Principle 9.

**Success Criteria**:

- 100% of detected discrepancies enter a defined dispute lifecycle before any recovery action.
- No recovery action or liability raised against an open, genuine dispute.

**Priority**: MUST_HAVE

**Stakeholder**: Sub-postmasters; representative bodies; Legal & General Counsel.

---

### BR-010: Independent assurance governs delivery

**Description**: Programme delivery and the readiness for each go-live must be governed by genuine independent technical assurance with honest, evidenced status reporting and gates that can halt or re-scope delivery.

**Rationale**: Horizon went live over its specialists' objections, and NBIT was "set up to fail" [POHR-C6]; honest assurance prevents recurrence. Traces to STKE goal G-10 and outcome O-5; aligns with PRIN Principle 23.

**Success Criteria**:

- Independent assurance function established, demonstrably independent of delivery, reporting unfiltered to the programme board.
- No go-live without independent assurance sign-off.

**Priority**: MUST_HAVE

**Stakeholder**: Programme SRO; DBT; NAO.

---

## Functional Requirements

### User Personas

#### Persona 1: Sub-postmaster (branch operator)

- **Role**: Operates and is accountable for a Post Office branch and its accounts.
- **Goals**: Serve customers; keep an accurate branch account; understand and resolve any discrepancy.
- **Pain Points**: Historic inability to see or challenge system-driven discrepancies; profound distrust of branch IT.
- **Technical Proficiency**: Low to Medium (varies widely across the network).

#### Persona 2: Counter assistant

- **Role**: Serves customers at the counter under the sub-postmaster.
- **Goals**: Process customer transactions quickly and correctly.
- **Pain Points**: Slow or confusing workflows; unclear error handling.
- **Technical Proficiency**: Low to Medium.

#### Persona 3: Branch / field manager

- **Role**: Supports and oversees a group of branches.
- **Goals**: Monitor branch health; support postmasters; assist with readiness and disputes.
- **Technical Proficiency**: Medium.

#### Persona 4: Post Office operations / finance operator

- **Role**: Performs central reconciliation, corrections and settlement.
- **Goals**: Reconcile network accounts; post necessary corrections — transparently and attributably.
- **Technical Proficiency**: Medium to High.

#### Persona 5: Support / helpdesk agent

- **Role**: Provides operational support to branches.
- **Goals**: Diagnose and resolve branch issues.
- **Pain Points**: Must help without any covert ability to alter branch accounts.
- **Technical Proficiency**: Medium to High.

#### Persona 6: Independent auditor / assurance reviewer

- **Role**: Verifies system integrity and reconstructs account history.
- **Goals**: Independently confirm records are complete, attributed and unaltered.
- **Technical Proficiency**: High.

---

### Use Cases

#### UC-1: Process a counter transaction

**Actor**: Counter assistant / Sub-postmaster.

**Preconditions**: User authenticated to the branch terminal; branch open for trading.

**Main Flow**:

1. User selects the product or service for the customer.
2. System calculates the amount and any associated fees.
3. User confirms and takes payment (cash or card).
4. System records the transaction and updates the branch account.
5. System writes an immutable, attributed audit record and confirms completion.

**Postconditions**: Branch account updated; tamper-evident audit record created; receipt issued.

**Alternative Flows**: *Alt 1a*: Network unavailable — transaction is queued locally and safely (see FR-022), then reconciled on reconnection.

**Exception Flows**: *Ex 1*: Payment fails — transaction is not posted; the attempt is logged; no partial entry is created.

**Business Rules**: Every posted transaction is attributable, idempotent and immutably recorded.

**Priority**: CRITICAL

---

#### UC-2: Complete end-of-day balancing and raise a discrepancy

**Actor**: Sub-postmaster.

**Preconditions**: Trading period closing; user authenticated.

**Main Flow**:

1. User initiates branch balancing for the period.
2. System presents the expected vs. counted position with full transaction detail.
3. User reviews; if a discrepancy exists, system shows the contributing entries and their sources.
4. User can investigate each entry and, if unexplained, raise a discrepancy/dispute case.
5. System records the balancing outcome and any dispute case immutably.

**Postconditions**: Branch trading statement produced; any dispute case opened with status and ownership.

**Alternative Flows**: *Alt 3a*: Discrepancy traced to an externally initiated entry — system shows attribution and notification history.

**Exception Flows**: *Ex 1*: Balancing cannot complete — branch is left in a defined, recoverable state; no figure is silently adjusted.

**Business Rules**: A discrepancy is presumed to require investigation; no liability attaches while a genuine dispute is open (BR-009).

**Priority**: CRITICAL

---

#### UC-3: Post a central correction with attribution and notification

**Actor**: Post Office operations / finance operator.

**Preconditions**: Operator authenticated with named, authorised write permission; a correction is justified and documented.

**Main Flow**:

1. Operator identifies the branch and the correction required.
2. Operator records the correction with reason and supporting reference.
3. System posts the correction as a first-class, attributed transaction (a compensating entry, never an overwrite).
4. System immutably logs the change and notifies the affected sub-postmaster.
5. The correction appears on the sub-postmaster's account view in real time.

**Postconditions**: Correction posted, attributed, logged and visible to the branch.

**Exception Flows**: *Ex 1*: Operator lacks named write authorisation — the action is refused and logged.

**Business Rules**: No financial change without authentication, named attribution, immutable logging and branch visibility (BR-008).

**Priority**: CRITICAL

---

### Functional Requirements Detail

#### FR-001: Counter transaction processing (EPOS)

**Description**: The system must process the full range of Post Office counter transactions — mails and parcels, banking and cash, bill payments, foreign currency, government services and retail — via branch terminals.

**Relates To**: BR-006, UC-1

**Acceptance Criteria**:

- [ ] Given a customer transaction, when the user completes it, then the branch account and audit record are updated atomically.
- [ ] Given a transaction type in the service catalogue, when selected, then correct pricing, fees and rules are applied.
- [ ] Edge case: a transaction interrupted mid-flow leaves no partial financial entry.

**Data Requirements**: Inputs — product/service, amount, tender. Outputs — posted transaction, receipt, audit record. Validations — catalogue, tender and limit rules.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: FR-004, INT-001..INT-005 — **Assumptions**: service catalogue is maintained centrally.

---

#### FR-002: Branch cash and stock management

**Description**: The system must track branch cash holdings and stock, including movements, remittances and declarations.

**Relates To**: BR-006, UC-2

**Acceptance Criteria**:

- [ ] Given a cash or stock movement, when recorded, then holdings update and an attributed audit record is written.
- [ ] Given a remittance to/from a cash centre, when processed, then it reconciles against the cash-centre record.

**Data Requirements**: Inputs — movements, counts, remittances. Outputs — holdings, audit records. Validations — non-negative holdings, reconciliation tolerances.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-004, INT-006 — **Assumptions**: cash-centre interfaces available.

---

#### FR-003: End-of-day and period branch balancing

**Description**: The system must support branch balancing and produce a branch trading statement for each trading period.

**Relates To**: BR-001, BR-009, UC-2

**Acceptance Criteria**:

- [ ] Given a trading period, when the user balances, then expected vs. actual position is shown with full transaction detail.
- [ ] Given a discrepancy, when balancing, then the user is shown contributing entries and is not forced to accept liability.
- [ ] Edge case: balancing that cannot complete leaves the branch in a defined, recoverable state.

**Data Requirements**: Inputs — period transactions, counts. Outputs — trading statement, balancing record. Validations — completeness of period data.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: FR-001, FR-002, FR-013 — **Assumptions**: none.

---

#### FR-004: Immutable, append-only transaction record

**Description**: The system must record every transaction and every adjustment in an append-only store; posted entries must never be updated or deleted.

**Relates To**: BR-001, BR-008

**Acceptance Criteria**:

- [ ] Given a posted entry, when any actor attempts to update or delete it, then the operation is impossible (no such code path exists).
- [ ] Given a correction, when applied, then it is a new, linked compensating entry.
- [ ] Edge case: a failed transaction creates no partial entry.

**Data Requirements**: Inputs — transactions, corrections. Outputs — immutable entries. Validations — append-only enforcement.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: none — **Assumptions**: aligns with PRIN Principle 6 (NON-NEGOTIABLE).

---

#### FR-005: Tamper-evident audit trail and point-in-time reconstruction

**Description**: The system must maintain a cryptographically tamper-evident audit trail and allow definitive reconstruction of any branch's accounts at any point in time.

**Relates To**: BR-001, BR-009

**Acceptance Criteria**:

- [ ] Given the audit trail, when any record is altered, then the alteration is detectable by independent verification.
- [ ] Given any branch and date, when reconstruction is requested, then the exact account state is produced from the audit record.
- [ ] Edge case: an attempted out-of-band edit is detected and flagged.

**Data Requirements**: Inputs — audit records. Outputs — verification result, reconstructed state. Validations — chain/integrity verification.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: FR-004 — **Assumptions**: aligns with PRIN Principle 6.

---

#### FR-006: Corrections via attributed compensating entries only

**Description**: Any correction to a branch account must be made by a new, attributed compensating entry, leaving both the original entry and the correction permanently visible.

**Relates To**: BR-008, UC-3

**Acceptance Criteria**:

- [ ] Given an error to correct, when a correction is posted, then the original entry remains and a linked compensating entry is created.
- [ ] Given a correction, when posted, then it carries who, what, when, where and why.

**Data Requirements**: Inputs — correction, reason, reference. Outputs — compensating entry. Validations — authorisation, linkage.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-004, FR-007 — **Assumptions**: none.

---

#### FR-007: Attributed, authenticated financial change

**Description**: Every creation or change of branch financial data must be authenticated and attributed to a named individual, with the originating channel recorded.

**Relates To**: BR-008, UC-1, UC-3

**Acceptance Criteria**:

- [ ] Given any financial write, when performed, then it is attributed to a named, authenticated identity.
- [ ] Given a shared or anonymous identity, when it attempts a financial write, then the write is refused.

**Data Requirements**: Inputs — identity, action. Outputs — attributed entry. Validations — authentication, named-identity enforcement.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: NFR-SEC-001, NFR-SEC-002 — **Assumptions**: aligns with PRIN Principle 7.

---

#### FR-008: Centrally initiated entries notified to the branch

**Description**: Any centrally or remotely initiated entry affecting a branch account must be treated as a first-class attributed transaction and notified to the affected sub-postmaster.

**Relates To**: BR-008, UC-3

**Acceptance Criteria**:

- [ ] Given a central entry, when posted, then the affected sub-postmaster is notified and the entry appears on their account view.
- [ ] Given a central entry, when viewed by the branch, then its origin, reason and author are visible.

**Data Requirements**: Inputs — central entry. Outputs — notification, account-view entry. Validations — attribution completeness.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-007, FR-010 — **Assumptions**: none.

---

#### FR-009: No covert write path

**Description**: The system must ensure there is no support, maintenance, administrative or database-level path that can alter branch financial data outside the attribution controls of FR-007.

**Relates To**: BR-008

**Acceptance Criteria**:

- [ ] Given all write channels, when independently assessed, then none can mutate financial data without named attribution and immutable logging.
- [ ] Given a support action, when it touches financial data, then it follows FR-007 and FR-008.

**Data Requirements**: Inputs — n/a. Outputs — n/a. Validations — channel inventory, threat-model review.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: FR-007, NFR-SEC-006 — **Assumptions**: aligns with PRIN Principle 7 (NON-NEGOTIABLE).

---

#### FR-010: Complete, real-time postmaster account view

**Description**: The system must give sub-postmasters a complete, real-time view of everything affecting their accounts, including centrally and remotely initiated entries.

**Relates To**: BR-003, BR-008

**Acceptance Criteria**:

- [ ] Given any entry affecting a branch account, when it is posted, then it is visible to that branch in real time.
- [ ] Given the account view, when compared with the audit record, then no entry is omitted.

**Data Requirements**: Inputs — account entries. Outputs — branch account view. Validations — completeness against audit record.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-004, FR-008 — **Assumptions**: none.

---

#### FR-011: Plain-language explanation of entries

**Description**: The system must present every entry type with a plain-language explanation of its origin, cause and supporting detail, accessible in-product to the sub-postmaster.

**Relates To**: BR-003, BR-009

**Acceptance Criteria**:

- [ ] Given any entry, when the user requests detail, then a plain-language explanation and supporting records are shown.
- [ ] Given a discrepancy, when displayed, then it includes the investigative context needed to understand it.

**Data Requirements**: Inputs — entry, metadata. Outputs — explanation view. Validations — explanation present for all entry types.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-010 — **Assumptions**: aligns with PRIN Principle 8.

---

#### FR-012: Postmaster self-service data export

**Description**: Sub-postmasters must be able to export their own transaction and audit data in an open, machine-readable format.

**Relates To**: BR-003, BR-009

**Acceptance Criteria**:

- [ ] Given a sub-postmaster, when they request an export, then their transaction and audit data is provided in an open format.
- [ ] Given an export, when produced, then it is complete and consistent with the account view.

**Data Requirements**: Inputs — date range. Outputs — open-format export. Validations — completeness.

**Priority**: SHOULD_HAVE — **Complexity**: LOW — **Dependencies**: FR-010 — **Assumptions**: none.

---

#### FR-013: Discrepancy detection and presentation

**Description**: The system must detect account discrepancies and present them with the contributing entries, their sources and the context needed to investigate.

**Relates To**: BR-009, UC-2

**Acceptance Criteria**:

- [ ] Given a discrepancy, when detected, then contributing entries and sources are shown — never a bare net figure.
- [ ] Given a discrepancy, when displayed, then a route to investigate or query each entry is available.

**Data Requirements**: Inputs — account entries. Outputs — discrepancy view. Validations — completeness of contributing detail.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-003, FR-011 — **Assumptions**: none.

---

#### FR-014: Dispute case lifecycle management

**Description**: The system must manage a defined discrepancy/dispute lifecycle with status, ownership, timescales and an independent review/escalation route.

**Relates To**: BR-009

**Acceptance Criteria**:

- [ ] Given a discrepancy, when raised as a dispute, then a case is created with state, owner and SLA.
- [ ] Given a dispute, when escalated, then an independent review route is available and recorded.
- [ ] Edge case: dispute history is immutable and auditable.

**Data Requirements**: Inputs — dispute details. Outputs — dispute case, history. Validations — lifecycle state rules.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-013 — **Assumptions**: aligns with PRIN Principle 9.

---

#### FR-015: Block liability action during an open dispute

**Description**: The system must prevent any "make good" demand, debt recovery or liability action against a branch while a genuine discrepancy is in an open dispute.

**Relates To**: BR-009

**Acceptance Criteria**:

- [ ] Given an open dispute, when recovery action is attempted, then it is blocked and the block is logged.
- [ ] Given a dispute, when closed with a documented outcome, then any subsequent action references that outcome.

**Data Requirements**: Inputs — dispute status. Outputs — block decision. Validations — dispute-state checks.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-014 — **Assumptions**: none.

---

#### FR-016: Bugs, Errors and Defects (BED) register and disclosure

**Description**: The system must maintain a register of bugs, errors and defects affecting financial accuracy, with impact, affected branches and remediation status, and support disclosure to affected sub-postmasters and assurance bodies.

**Relates To**: BR-001, BR-005

**Acceptance Criteria**:

- [ ] Given a financial-accuracy defect, when identified, then it is recorded in the BED register with impact and affected branches.
- [ ] Given a BED entry, when relevant, then affected sub-postmasters and assurance bodies can access it.
- [ ] Edge case: a defect affecting open disputes flags those disputes.

**Data Requirements**: Inputs — defect detail. Outputs — BED register, disclosure. Validations — completeness of impact data.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: none — **Assumptions**: aligns with PRIN Principle 10. Horizon defects were known from 1999 and concealed [POHR-C2].

---

#### FR-017: Branch, user and role administration

**Description**: The system must support administration of branches, users and roles using role-based access control with least privilege.

**Relates To**: BR-008

**Acceptance Criteria**:

- [ ] Given a user, when assigned a role, then permissions reflect least privilege for that role.
- [ ] Given a role change, when applied, then it is logged and effective immediately.

**Data Requirements**: Inputs — user, role, branch. Outputs — access configuration. Validations — least-privilege rules.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: NFR-SEC-002 — **Assumptions**: none.

---

#### FR-018: Support / helpdesk function without covert write access

**Description**: The system must provide support staff with read-by-default diagnostic access; any exceptional write to financial data must follow FR-007 and FR-008 (named, authorised, logged, branch-notified).

**Relates To**: BR-008

**Acceptance Criteria**:

- [ ] Given a support agent, when diagnosing an issue, then they have read access without the ability to covertly alter financial data.
- [ ] Given an exceptional support write, when performed, then it is attributed, logged and notified to the branch.

**Data Requirements**: Inputs — support context. Outputs — diagnostic view, attributed writes. Validations — read/write separation.

**Priority**: MUST_HAVE — **Complexity**: MEDIUM — **Dependencies**: FR-007, FR-009 — **Assumptions**: none.

---

#### FR-019: Branch and network reporting / management information

**Description**: The system must provide reporting and management information for branches, field managers and central operations, drawn from read-only derived data.

**Relates To**: BR-006

**Acceptance Criteria**:

- [ ] Given a reporting need, when a report is run, then it draws from a read-only derived store, not the live ledger.
- [ ] Given a report, when produced, then figures reconcile with the system of record.

**Data Requirements**: Inputs — query parameters. Outputs — reports/MI. Validations — reconciliation with source.

**Priority**: SHOULD_HAVE — **Complexity**: MEDIUM — **Dependencies**: DR-009 — **Assumptions**: none.

---

#### FR-020: Training and simulation mode

**Description**: The system must provide a training/simulation mode that is fully isolated from live branch accounts.

**Relates To**: BR-003, BR-006

**Acceptance Criteria**:

- [ ] Given training mode, when used, then no entry affects any live branch account.
- [ ] Given training mode, when active, then it is clearly indicated to the user.

**Data Requirements**: Inputs — training scenarios. Outputs — simulated results. Validations — isolation from live data.

**Priority**: SHOULD_HAVE — **Complexity**: LOW — **Dependencies**: none — **Assumptions**: none.

---

#### FR-021: Coexistence with Horizon during phased migration

**Description**: The system must coexist with the Horizon system during a phased branch-by-branch migration, so branches can move to the replacement without a network-wide cutover.

**Relates To**: BR-002, BR-006

**Acceptance Criteria**:

- [ ] Given a phased migration, when a branch moves to the replacement, then other branches continue unaffected.
- [ ] Given coexistence, when central reconciliation runs, then both systems' branches reconcile correctly.

**Data Requirements**: Inputs — branch migration state. Outputs — reconciled positions. Validations — cross-system consistency.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: INT-009, DR-003 — **Assumptions**: Horizon remains operable during transition.

---

#### FR-022: Resilient branch operation during connectivity loss

**Description**: The system must allow a branch to continue recording transactions safely during loss of central connectivity, with idempotent reconciliation on reconnection and no duplicated or lost entries.

**Relates To**: BR-006

**Acceptance Criteria**:

- [ ] Given a network outage, when transactions are taken, then they are recorded safely and reconciled exactly once on reconnection.
- [ ] Given repeated user actions during a freeze, when processed, then no transaction is duplicated (idempotency).
- [ ] Edge case: the Dalmellington-type "repeat on re-press" failure mode is prevented by design.

**Data Requirements**: Inputs — offline transactions. Outputs — reconciled entries. Validations — idempotency keys, exactly-once reconciliation.

**Priority**: MUST_HAVE — **Complexity**: HIGH — **Dependencies**: FR-004, NFR-A-003 — **Assumptions**: aligns with PRIN Principle 2.

---

## Non-Functional Requirements (NFRs)

### Performance Requirements

#### NFR-P-001: Counter response time

**Requirement**: Interactive counter operations must complete within **< 2 seconds at the 95th percentile** under peak load, including the synchronous, durable recording of the transaction and its integrity guarantee.

**Measurement Method**: Application performance monitoring at the branch terminal; load testing.

**Load Conditions**: Peak — network-wide benefit-day and December postal-peak volumes; sized with headroom.

**Priority**: HIGH

---

#### NFR-P-002: Transaction throughput

**Requirement**: The system must sustain peak network-wide transaction throughput across ~11,500 branches with at least 50% headroom above the highest observed Horizon peak.

**Scalability**: Throughput must scale horizontally without architectural change.

**Priority**: HIGH

---

#### NFR-P-003: Branch balancing window

**Requirement**: End-of-day branch balancing and trading-statement production must complete within the agreed branch operational window for 99% of branches.

**Measurement Method**: Batch/process timing telemetry.

**Priority**: MEDIUM

---

#### NFR-P-004: Integrity processing within latency budget

**Requirement**: The append-only, tamper-evident recording of a transaction (FR-004, FR-005) must complete within the NFR-P-001 latency budget. Where a genuine trade-off arises, transaction integrity takes precedence over latency and the latency target is adjusted — integrity is never weakened to meet performance (PRIN Principle 6).

**Measurement Method**: Component-level latency profiling of the audit-commit path.

**Priority**: CRITICAL

---

### Availability and Resilience Requirements

#### NFR-A-001: Availability target

**Requirement**: Branch-critical services must achieve **≥ 99.9% availability** during branch operating hours.

**Maintenance Windows**: Planned maintenance outside branch operating hours; communicated in advance.

**Priority**: CRITICAL

---

#### NFR-A-002: Disaster recovery

**RPO (Recovery Point Objective)**: **Zero loss** of committed transaction data.

**RTO (Recovery Time Objective)**: Branch-critical services restored within **2 hours**.

**Backup Requirements**: Continuous protection of transaction data; geographically separate UK locations; backups encrypted.

**Failover Requirements**: Automatic failover to a secondary region; failover within RTO.

**Priority**: CRITICAL

---

#### NFR-A-003: Fault tolerance and graceful degradation

**Requirement**: The system must degrade gracefully when dependencies fail, never silently corrupting branch accounts, and must support resilient branch operation (FR-022).

**Resilience Patterns Required**:

- [ ] Circuit breakers and timeouts on all remote calls.
- [ ] Retry with exponential backoff and idempotency.
- [ ] Bulkhead isolation so one branch or service cannot cascade failure.
- [ ] Defined degraded mode that preserves transaction integrity over availability.

**Priority**: CRITICAL

---

### Scalability Requirements

#### NFR-S-001: Horizontal scaling for the branch network

**Requirement**: The system must scale horizontally, without code change, to serve the full ~11,500-branch network and absorb demand peaks [POHR-C3].

**Growth Projections**: Sized for the current network with headroom for network and transaction-volume change over a 5-year horizon.

**Scaling Triggers**: Demand-based auto-scaling with defined thresholds.

**Priority**: HIGH

---

#### NFR-S-002: Data volume scaling

**Requirement**: The system must handle the growth of immutable transaction and audit data over a multi-decade retention horizon, using appropriate storage tiers without compromising integrity or retrievability.

**Data Archival Strategy**: Tiered storage; archived data remains tamper-evident and retrievable for reconstruction.

**Priority**: MEDIUM

---

### Security Requirements

#### NFR-SEC-001: Authentication

**Requirement**: All human users must authenticate via industry-standard protocols; multi-factor authentication is required for privileged and remote access. Counter authentication must be strong yet ergonomic (see Conflict C-5).

**Session Management**: Inactivity and absolute session timeouts; re-authentication for sensitive operations.

**Priority**: CRITICAL

---

#### NFR-SEC-002: Authorization

**Requirement**: Role-based access control with least privilege; write access to branch financial data requires named, authorised permission and is exceptional.

**Privilege Elevation**: Time-boxed, logged, and reviewed.

**Priority**: CRITICAL

---

#### NFR-SEC-003: Data encryption

**Requirement**: All data encrypted in transit (current strong TLS) and at rest (strong symmetric encryption); keys held in a managed vault.

**Encryption Scope**: Databases, the audit store, backups, file storage, and field-level encryption for personal data.

**Priority**: CRITICAL

---

#### NFR-SEC-004: Secrets management

**Requirement**: No secrets in code or configuration; all secrets held in a managed vault with automated rotation.

**Priority**: HIGH

---

#### NFR-SEC-005: Vulnerability management

**Requirement**: Dependency scanning, SAST and DAST in the CI/CD pipeline; independent penetration testing before each go-live and at least annually thereafter.

**Remediation SLA**: Critical — 24 hours; High — 7 days; Medium — 30 days.

**Priority**: HIGH

---

#### NFR-SEC-006: Prevention of covert access (security control)

**Requirement**: Security controls must enforce FR-009 — no privileged, support or database-level path may mutate branch financial data outside named attribution and immutable logging. Verified by threat modelling and independent assurance.

**Measurement Method**: Threat model review; write-channel audit; independent assurance.

**Priority**: CRITICAL

---

### Compliance and Regulatory Requirements

#### NFR-C-001: Data privacy compliance (UK GDPR / DPA 2018)

**Applicable Regulations**: UK GDPR; Data Protection Act 2018.

**Compliance Requirements**:

- [ ] Data subject rights supported.
- [ ] Privacy by design and by default.
- [ ] Personal data breach notification within statutory timescales.
- [ ] Data Protection Impact Assessment (DPIA) completed before go-live.

**Data Residency**: UK (see DR-007). **Data Retention**: per DR-006.

**Priority**: CRITICAL

---

#### NFR-C-002: Tamper-evident audit logging

**Requirement**: Comprehensive, tamper-evident audit logging of all financial and security-significant operations, recording who, what, when, where, why and result.

**Log Retention**: Transaction audit records retained long-term under legal-hold rules (DR-006), in immutable storage.

**Log Integrity**: Cryptographically tamper-evident (see FR-005).

**Priority**: CRITICAL

---

#### NFR-C-003: NCSC Cyber Assessment Framework

**Requirement**: The system must achieve the agreed target profile against the NCSC Cyber Assessment Framework (CAF) before network go-live.

**Report Types**: CAF assessment and remediation evidence to the SIRO and DBT assurance.

**Priority**: HIGH

---

#### NFR-C-004: Payment card compliance (PCI-DSS)

**Requirement**: All processing, storage and transmission of payment card data must comply with the current PCI-DSS standard; card data scope must be minimised.

**Priority**: CRITICAL

---

#### NFR-C-005: Inquiry recommendation and regulatory reporting

**Requirement**: The system and programme must support reporting that evidences traceability of Post Office Horizon IT Inquiry recommendations [POHR-C10] to design and governance, and any FCA-relevant reporting for banking services.

**Report Types**: Inquiry-recommendation traceability matrix (per BR-005); regulatory reports as required.

**Priority**: HIGH

---

### Usability Requirements

#### NFR-U-001: User experience for varied digital confidence

**Requirement**: Branch interfaces must be usable, with minimal training, by sub-postmasters and counter staff across a wide range of digital confidence; critical workflows (transactions, balancing, disputes) must be clear and use plain language.

**User Onboarding**: Contextual help and training mode (FR-020).

**Priority**: HIGH

---

#### NFR-U-002: Accessibility

**Requirement**: User-facing interfaces must conform to **WCAG 2.2 Level AA**, tested with assistive technologies and with users of varied ability.

**Accessibility Features**: Keyboard operability, screen-reader compatibility, sufficient contrast, scalable text.

**Priority**: HIGH

---

### Maintainability and Supportability Requirements

#### NFR-M-001: Observability

**Requirement**: All services must emit structured logs, metrics and distributed traces with correlation IDs, feeding dashboards and SLO-based alerting; business events (transactions, adjustments) must be observable.

**Priority**: HIGH

---

#### NFR-M-002: Documentation

**Requirement**: Current architecture, interface, operational and user documentation must be maintained, including ADRs for significant decisions.

**Documentation Currency**: Updated in step with change.

**Priority**: MEDIUM

---

#### NFR-M-003: Operational runbooks

**Requirement**: Runbooks must exist for deployment, rollback, backup/restore, incident response, scaling and disaster recovery.

**Priority**: MEDIUM

---

### Portability and Interoperability Requirements

#### NFR-I-001: Open standards and API design

**Requirement**: All system boundaries must use open, documented, versioned interfaces; the architecture must be composable, modular and standards-based, consistent with the stated target architecture [POHR-C4].

**API Design Principles**: Published contracts; explicit versioning and backward-compatibility strategy; no cross-system database coupling.

**Priority**: HIGH

---

#### NFR-I-002: Integration capabilities

**Requirement**: The system must integrate with the external systems in the Integration Requirements section using event-driven and standard request/response patterns with durable delivery for financially significant events.

**Integration SLA**: Defined per integration (see INT-001..INT-009).

**Priority**: HIGH

---

#### NFR-I-003: Data portability and exit readiness

**Requirement**: All Post Office data must be exportable in open, documented formats, and a tested exit/portability path must exist for each significant supplier (BR-007).

**Export Formats**: Open, machine-readable. **Import Capability**: Bulk import from open formats.

**Priority**: HIGH

---

## Integration Requirements

### External System Integrations

#### INT-001: Banking and cash services (Post Office Banking Framework)

**Purpose**: Enable everyday banking, cash deposits and withdrawals for partner banks at the counter.

**Integration Type**: Real-time API. **Data Exchanged**: Banking transactions and balances both directions. **Authentication**: Mutual authentication / signed tokens. **Error Handling**: Retry with idempotency; reconciliation. **SLA**: Real-time; high availability. **Owner**: Banking partners / Banking Framework. **Priority**: CRITICAL.

---

#### INT-002: Mails and parcels (Royal Mail and parcel carriers)

**Purpose**: Accept, price, label and track mail and parcels.

**Integration Type**: Real-time API and batch. **Data Exchanged**: Item acceptance, pricing, tracking data. **Authentication**: API credentials / signed tokens. **Error Handling**: Retry; manual fallback. **SLA**: Real-time pricing; near-real-time tracking. **Owner**: Royal Mail / carriers. **Priority**: CRITICAL.

---

#### INT-003: Card payment acquiring

**Purpose**: Process card payments at the counter.

**Integration Type**: Real-time API to acquirer/payment schemes. **Data Exchanged**: Authorisation requests/responses, settlement data. **Authentication**: PCI-DSS-compliant secure channel. **Error Handling**: Decline handling; reconciliation. **SLA**: Real-time authorisation. **Owner**: Card acquirer. **Priority**: CRITICAL.

---

#### INT-004: Bill payments and top-ups

**Purpose**: Process bill payments and mobile/utility top-ups for billers.

**Integration Type**: Real-time API via the payments network. **Data Exchanged**: Payment instructions, confirmations. **Authentication**: Signed tokens. **Error Handling**: Retry; reversal handling. **SLA**: Real-time confirmation. **Owner**: Payments network / billers. **Priority**: HIGH.

---

#### INT-005: Government services (DVLA, HM Passport Office and others)

**Purpose**: Deliver counter government services (e.g. vehicle excise duty, passport Check & Send).

**Integration Type**: Real-time API and document handling. **Data Exchanged**: Service requests, confirmations, status. **Authentication**: Government-standard secure integration. **Error Handling**: Retry; manual fallback. **SLA**: Real-time where the service requires. **Owner**: Respective government bodies. **Priority**: HIGH.

---

#### INT-006: Cash management and cash centres

**Purpose**: Reconcile branch cash holdings, remittances and deliveries.

**Integration Type**: Batch and event-driven. **Data Exchanged**: Cash movements, remittance records. **Authentication**: Signed tokens. **Error Handling**: Reconciliation; exception handling. **SLA**: Daily reconciliation. **Owner**: Cash management providers. **Priority**: HIGH.

---

#### INT-007: Post Office finance, settlement and ERP

**Purpose**: Feed settlement and financial accounting from branch transaction data.

**Integration Type**: Event-driven and batch. **Data Exchanged**: Settlement and financial postings. **Authentication**: Internal service authentication. **Error Handling**: Reconciliation; dead-letter handling. **SLA**: Daily settlement. **Owner**: Post Office Finance. **Priority**: HIGH.

---

#### INT-008: Identity provider for staff and postmasters

**Purpose**: Authenticate and attribute Post Office staff, sub-postmasters and counter assistants.

**Integration Type**: Real-time authentication (industry-standard protocols). **Data Exchanged**: Identity assertions, role claims. **Authentication**: Standards-based with MFA. **Error Handling**: Fail-closed for financial writes. **SLA**: Real-time; high availability. **Owner**: Post Office identity service. **Priority**: CRITICAL.

---

#### INT-009: Legacy Horizon migration and coexistence interface

**Purpose**: Enable phased migration and coexistence with Horizon (FR-021), including extraction of branch and account data.

**Integration Type**: Batch extraction and reconciliation. **Data Exchanged**: Branch, account and historical transaction data from Horizon. **Authentication**: Secured, audited access. **Error Handling**: Reconciliation; provenance capture. **SLA**: Per migration plan. **Owner**: Fujitsu (incumbent) and the programme. **Priority**: MUST-have for transition — **CRITICAL**.

---

## Data Requirements

### Data Entities

#### Entity 1: Branch Transaction

**Description**: An individual financial transaction recorded at, or affecting, a branch.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique identifier | Primary key |
| branch_id | String | Yes | Branch reference | Indexed |
| type | Enum | Yes | Transaction/service type | Catalogue-controlled |
| amount | Decimal | Yes | Monetary amount | Currency-typed |
| posted_by | Identity | Yes | Named, authenticated actor | Not null |
| channel | Enum | Yes | Originating channel | Counter / central / support |
| posted_at | Timestamp | Yes | Posting time (UTC) | Immutable, indexed |
| audit_ref | Hash | Yes | Link to audit record | Tamper-evident chain |

**Relationships**: Many-to-one with Branch Account; one-to-one with Audit Record.

**Data Classification**: RESTRICTED (financial). **Data Retention**: Long-term under legal hold (DR-006).

---

#### Entity 2: Audit Record

**Description**: An immutable, tamper-evident record of a transaction or adjustment.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique identifier | Primary key, append-only |
| event | Enum | Yes | Event type | Not null |
| actor | Identity | Yes | Named actor | Not null |
| occurred_at | Timestamp | Yes | Event time (UTC, ms) | Immutable |
| prev_hash | Hash | Yes | Previous-record hash | Chain integrity |
| record_hash | Hash | Yes | This record's hash | Tamper-evident |

**Relationships**: One-to-one with Branch Transaction or Adjustment.

**Data Classification**: RESTRICTED. **Data Retention**: Long-term; never purged while under hold.

---

#### Entity 3: Discrepancy / Dispute Case

**Description**: A case raised to investigate and resolve an account discrepancy.

**Attributes**:

| Attribute | Type | Required | Description | Constraints |
|-----------|------|----------|-------------|-------------|
| id | UUID | Yes | Unique identifier | Primary key |
| branch_id | String | Yes | Branch reference | Indexed |
| status | Enum | Yes | Lifecycle state | State-machine controlled |
| owner | Identity | Yes | Case owner | Not null |
| opened_at | Timestamp | Yes | Open time | Immutable |
| resolution | Text | No | Documented outcome | Set on closure |

**Relationships**: Many-to-one with Branch Account; references contributing Branch Transactions.

**Data Classification**: CONFIDENTIAL (may include personal data). **Data Retention**: Long-term under legal hold.

---

### Data Requirements Detail

#### DR-001: Immutable, append-only transaction and ledger data model

**Description**: The transaction and ledger data model must be append-only; posted entries are immutable, with corrections as linked compensating entries.

**Acceptance Criteria**: No update/delete path exists for posted entries; corrections are linked compensating entries.

**Priority**: MUST_HAVE — **Rationale**: foundation of provable integrity (BR-001, FR-004; PRIN Principle 6).

---

#### DR-002: Tamper-evident audit data store

**Description**: Audit records must be held in a cryptographically tamper-evident, append-only store supporting independent integrity verification.

**Acceptance Criteria**: Any alteration is independently detectable; point-in-time reconstruction is possible.

**Priority**: MUST_HAVE — **Rationale**: BR-001, FR-005, NFR-C-002.

---

#### DR-003: Historical data migration with provenance markers

**Description**: Branch and account data migrated from Legacy Horizon and Horizon Online/HNG [POHR-C8] must carry provenance markers (source system, migration date, reliability status).

**Acceptance Criteria**: 100% of migrated records carry provenance metadata; migration logic is version-controlled and independently reviewed.

**Priority**: MUST_HAVE — **Rationale**: BR-002, FR-021; PRIN Principle 11.

---

#### DR-004: Flagging of disputed and contested historical items

**Description**: Disputed or unverified historical items — including data from the pre-Horizon Capture system, whose reliability is itself contested [POHR-C7] — must be explicitly flagged and never silently presented as authoritative.

**Acceptance Criteria**: 100% of known disputed items flagged; opening balances state their basis and confidence.

**Priority**: MUST_HAVE — **Rationale**: BR-001, BR-009; PRIN Principle 11. The replacement must not "launder" disputed historical figures.

---

#### DR-005: Data classification

**Description**: All data must be classified; branch financial and payment-card data classified RESTRICTED, personal data CONFIDENTIAL, with access controls enforcing the classification.

**Acceptance Criteria**: Every data store classified; access controls reflect classification.

**Priority**: MUST_HAVE — **Rationale**: NFR-C-001; PRIN Principle 13.

---

#### DR-006: Data retention and legal hold

**Description**: Retention must be policy-governed, with transaction and audit data retained long-term and protected by legal-hold rules covering inquiry, redress and litigation; in-scope data must never be deleted while under hold.

**Acceptance Criteria**: Retention rules configured; legal hold overrides deletion for in-scope data.

**Priority**: MUST_HAVE — **Rationale**: BR-005, NFR-C-001; ongoing inquiry/redress context.

---

#### DR-007: UK data residency

**Description**: Personal and financial data must reside in the United Kingdom; any cross-border processing requires a documented lawful basis.

**Acceptance Criteria**: Data residency confirmed UK; no undocumented cross-border transfer.

**Priority**: MUST_HAVE — **Rationale**: NFR-C-001; UK government data expectations.

---

#### DR-008: Personal data minimisation

**Description**: Only personal data necessary for branch services and obligations may be collected and processed; migration must not copy excessive personal data.

**Acceptance Criteria**: Data minimisation evidenced in the DPIA; migration scoped to necessary data.

**Priority**: SHOULD_HAVE — **Rationale**: NFR-C-001; UK GDPR minimisation principle.

---

#### DR-009: Data lineage and source-to-target traceability

**Description**: End-to-end data lineage must be captured and queryable for all data flows, including derived reporting stores.

**Acceptance Criteria**: Lineage queryable source-to-target; derived stores labelled read-only.

**Priority**: SHOULD_HAVE — **Rationale**: FR-019; PRIN Principle 11, 12.

---

#### DR-010: BED register data

**Description**: The bugs, errors and defects register (FR-016) must hold defect detail, financial-accuracy impact, affected branches and remediation status, and be retained and disclosable.

**Acceptance Criteria**: BED data complete and queryable; disclosable to affected parties and assurance bodies.

**Priority**: MUST_HAVE — **Rationale**: BR-001, FR-016; PRIN Principle 10.

---

### Data Quality Requirements

**Data Accuracy**: Validation enforced at source; reconciliation against integrations (INT-001..INT-009).
**Data Completeness**: Required fields enforced; no silent null in financial fields.
**Data Consistency**: Cross-system reconciliation, including during Horizon coexistence (FR-021).
**Data Timeliness**: Branch account view updated in real time (FR-010).
**Data Lineage**: Source-to-target lineage captured (DR-009).

### Data Migration Requirements

**Migration Scope**: Branch, account and historical transaction data from Legacy Horizon and Horizon Online/HNG; awareness of contested pre-Horizon Capture data.
**Migration Strategy**: Phased, branch-by-branch, with coexistence (FR-021) — not big-bang.
**Data Transformation**: Provenance and reliability marking (DR-003, DR-004); auditable, version-controlled logic.
**Data Validation**: Reconciliation of migrated balances against source; independent assurance review.
**Rollback Plan**: Per-branch migration is reversible until confirmed; source data retained.
**Migration Timeline**: Aligned to the phased rollout (mid-2026 to end-2028 indicative); see Timeline and Milestones.

---

## Constraints and Assumptions

### Technical Constraints

**TC-1**: The architecture must be composable, event-driven, standards-based and cloud-hosted, consistent with the stated target architecture [POHR-C4] and `ARC-000-PRIN-v1.0`.

**TC-2**: Transaction integrity principles (PRIN Principles 6, 7) are NON-NEGOTIABLE — no design may compromise them.

**TC-3**: The replacement must coexist and integrate with the Horizon system for the duration of the phased migration (FR-021, INT-009).

### Business Constraints

**BC-1**: Delivery is funded from a government funding envelope and subject to spending controls and assurance gates (BR-004).

**BC-2**: The Fujitsu exit (~mid-2027) and Horizon eradication (by 2030) are programme targets [POHR-C5], conditional on independent assurance evidence (BR-010).

**BC-3**: The programme must demonstrably honour the Post Office Horizon IT Inquiry's accepted recommendations (BR-005).

### Assumptions

**A-1**: The reported selection of Accenture and One View Commerce to operate and help build the replacement is **not yet confirmed** in commercial detail [POHR-C9]; supplier scope, contract values and dates are assumed to be confirmed via official Post Office/DBT announcements and award notices before dependent decisions are taken.

**A-2**: Horizon remains operable and supportable by Fujitsu under bridging arrangements throughout the phased transition.

**A-3**: Fujitsu cooperates with contractually defined knowledge transfer and data access for migration (INT-009).

**Validation Plan**: A-1 validated against official sources; A-2/A-3 validated through transition contracts and governance.

---

## Success Criteria and KPIs

### Business Success Metrics

| Metric | Baseline | Target | Timeline | Measurement Method |
|--------|----------|--------|----------|--------------------|
| Liability actions on unverifiable/system-caused data | Historically hundreds of prosecutions / thousands of demands | Zero | From go-live, sustained | Dispute & liability case records |
| Sub-postmaster confidence in branch IT | To be baselined at outset | ≥ 80% | Within 12 months of rollout | Independent survey |
| Fujitsu exit / Horizon eradication | Fujitsu operating Horizon | Fujitsu exit ~mid-2027; eradication by 2030 | Per plan | Transition & decommissioning registers |
| Delivery vs approved funding envelope | NBIT ~£1bn, abandoned | Within envelope; no adverse NAO finding | Programme duration | Financial reporting; NAO review |

### Technical Success Metrics

| Metric | Target | Measurement Method |
|--------|--------|--------------------|
| Branch-critical availability | ≥ 99.9% (operating hours) | Uptime monitoring |
| Counter response time (p95) | < 2 seconds | APM tooling |
| Committed transaction data loss | Zero (RPO = 0) | DR testing |
| Covert write paths to financial data | Zero (independently confirmed) | Threat model; assurance audit |
| PRIN Category II validation gates passed | 100% before go-live | Independent assurance |

### User Adoption Metrics

| Metric | Target | Timeline | Measurement Method |
|--------|--------|----------|--------------------|
| Branches migrated to the replacement | 100% of network | By end-2028 (indicative) | Migration tracker |
| Postmasters able to understand/challenge a discrepancy | ≥ 90% | 6 months post-rollout | Usability research / survey |
| Sub-postmaster confidence score | ≥ 80% | 12 months post-rollout | Independent survey |

---

## Dependencies and Risks

### Dependencies

| Dependency | Description | Owner | Target Date | Status | Impact if Delayed |
|------------|-------------|-------|-------------|--------|-------------------|
| Supplier contracts | Replacement operator/builder and EPOS supplier contracts signed | Post Office / DBT | Summer 2026 (reported) | At Risk | HIGH |
| Architecture principles | `ARC-000-PRIN-v1.0` ratified | Enterprise Architecture | In progress | On Track | HIGH |
| Fujitsu transition cooperation | Knowledge transfer and data access for migration | Fujitsu / programme | Through transition | At Risk | HIGH |
| Independent assurance function | Assurance function established and resourced | Programme SRO | Programme start | On Track | HIGH |

### Risks

| Risk ID | Description | Probability | Impact | Mitigation Strategy | Owner |
|---------|-------------|-------------|--------|---------------------|-------|
| R-1 | Sub-postmaster trust not restored — programme seen as "Horizon 2" | MEDIUM | HIGH | Genuine co-design; complete visibility; baseline & track confidence | Service Owner |
| R-2 | Political pressure forces a premature go-live | MEDIUM | HIGH | Assurance gates with halt authority as the arbiter of pace | Programme SRO |
| R-3 | Fujitsu transition non-cooperation / knowledge loss | MEDIUM | HIGH | Contractual knowledge-transfer & data-access obligations | Post Office CTO |
| R-4 | Incoming supplier arrangement unconfirmed (A-1) | MEDIUM | MEDIUM | Confirm from official sources before dependent decisions | Finance & Commercial |
| R-5 | Cost overrun triggers loss of funding confidence (NBIT precedent) | MEDIUM | HIGH | Staged funding against gates; scope & change control | Finance & Commercial |
| R-6 | Integration complexity across 80+ legacy components | MEDIUM | HIGH | Phased migration; coexistence (FR-021); independent assurance | Post Office CTO |

> Full programme risk management is produced via `/arckit:risk`.

---

## Requirement Conflicts & Resolutions

> Conflicts originate from the conflict analysis in `ARC-001-STKE-v1.0`. Trade-offs are stated transparently.

### Conflict C-1: Delivery pace vs. assurance

**Conflicting Requirements**:

- **Requirement A**: BR-002 — exit Fujitsu by ~mid-2027 and eradicate Horizon by 2030.
- **Requirement B**: BR-001 / BR-010 — integrity proven and independently assured before any go-live.

**Stakeholders Involved**: Minister/DBT want visible, fast delivery; the SRO, sub-postmasters and Inquiry legacy want delivery governed by assurance evidence.

**Nature of Conflict**: A fixed exit date can pressure go-live before integrity is proven — the failure mode of both Horizon and NBIT [POHR-C6].

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| Prioritise pace | Meets political timeline | Risk of unproven go-live | Repeats the original failure |
| Prioritise assurance | Integrity protected | Exit date may slip | Political discomfort |
| Phase (chosen) | Evidenced progress without compressing assurance | Requires disciplined gates | Both broadly satisfied |

**Resolution Strategy**: PHASE

**Decision**: Assurance-gated, phased rollout (pilot → controlled rollout → network). The Fujitsu exit date is a planning target **conditional on assurance evidence**, not an override of it.

**Rationale**: Phased delivery gives political stakeholders continuous, evidenced progress while integrity assurance governs each go-live.

**Decision Authority**: Programme SRO with the programme board (per STKE RACI).

**Impact on Requirements**: BR-002 framed as assurance-conditional; FR-021 (coexistence) enables phasing.

**Stakeholder Management**: Minister/DBT (pace) — given a phased plan with visible milestones and the NBIT precedent as justification.

**Future Consideration**: Re-baseline exit timing if assurance evidence requires.

---

### Conflict C-2: Synchronous integrity recording vs. counter response time

**Conflicting Requirements**:

- **Requirement A**: FR-004 / FR-005 / NFR-C-002 — synchronous immutable, tamper-evident recording.
- **Requirement B**: NFR-P-001 — counter operations complete in < 2 seconds (p95).

**Stakeholders Involved**: Sub-postmasters and the Inquiry legacy require provable integrity; counter staff and customers require fast service.

**Nature of Conflict**: Cryptographic chaining and durable recording add latency to the transaction path.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| Weaken/defer audit for speed | Faster counter | Integrity not provable | Unacceptable — breaches PRIN Principle 6 |
| Accept slower counter | Integrity protected | Poorer counter experience | Acceptable fallback |
| Innovate (chosen) | Speed AND integrity | Higher design effort | Both satisfied |

**Resolution Strategy**: INNOVATE (with a precedence rule)

**Decision**: NFR-P-004 mandates that integrity recording completes within the latency budget by design (efficient durable commit and chaining). Where a genuine trade-off remains, **integrity takes precedence** and NFR-P-001's target is adjusted — integrity is never weakened.

**Rationale**: PRIN Category II is NON-NEGOTIABLE; performance must be achieved with integrity intact, not at its expense.

**Decision Authority**: Post Office CTO / Enterprise Architecture (per STKE RACI).

**Impact on Requirements**: NFR-P-004 added; NFR-P-001 is conditional on integrity being met first.

**Stakeholder Management**: Counter staff — engaged on ergonomic design so the latency impact is minimal in practice.

**Future Consideration**: Validate the latency budget against pilot performance data.

---

### Conflict C-3: Cost control vs. integrity, assurance and co-design investment

**Conflicting Requirements**:

- **Requirement A**: BR-004 — deliver within the funding envelope.
- **Requirement B**: BR-001 / BR-003 / BR-010 — integrity, co-design and independent assurance, all of which cost time and money.

**Stakeholders Involved**: HM Treasury, DBT and NAO drive cost control; sub-postmasters, the Inquiry legacy and the SRO drive integrity and assurance investment.

**Nature of Conflict**: A pure cost-minimisation stance would cut exactly the investment that makes the system trustworthy.

**Trade-off Analysis**:

| Option | Pros | Cons | Impact |
|--------|------|------|--------|
| Minimise cost | Lower headline spend | Undermines the programme's purpose | Unacceptable |
| Prioritise integrity/assurance (chosen) | Trustworthy outcome | Higher spend on assurance/co-design | Treasury must be satisfied on control |

**Resolution Strategy**: PRIORITISE (integrity and assurance), with cost controlled elsewhere.

**Decision**: Integrity, independent assurance and co-design are protected scope. Cost is controlled by prioritising non-integrity functional scope (SHOULD/COULD requirements deferrable) and staged, gate-linked funding — framed as risk reduction against ~£2bn of redress and the ~£1bn NBIT write-off [POHR-C6].

**Rationale**: Integrity and assurance are the purpose of the programme; cutting them would repeat the scandal.

**Decision Authority**: Programme SRO with DBT and HM Treasury (per STKE RACI).

**Impact on Requirements**: SHOULD_HAVE/COULD_HAVE functional scope (e.g. FR-012, FR-019, FR-020) is the deferrable buffer; MUST_HAVE integrity/assurance requirements are protected.

**Stakeholder Management**: HM Treasury (cost) — given gate-linked funding and transparent forecasting so control is demonstrable.

**Future Consideration**: Re-prioritise deferred scope at each funding gate.

---

### Conflict C-4: Exit pace vs. branch service continuity

**Conflicting Requirements**:

- **Requirement A**: BR-002 — exit Fujitsu quickly.
- **Requirement B**: BR-006 / FR-021 — uninterrupted branch services through a careful, phased migration.

**Stakeholders Involved**: Minister/DBT want a fast exit; customers and sub-postmasters need uninterrupted service.

**Nature of Conflict**: An aggressive cutover risks branch outages and under-prepared staff.

**Resolution Strategy**: PHASE

**Decision**: Phased, branch-by-branch migration with coexistence (FR-021) and branch-readiness gates; service continuity (BR-006) is a hard go/no-go criterion, not a target.

**Rationale**: Branches are essential community infrastructure; disruption would harm customers and confidence.

**Decision Authority**: Programme board (per STKE RACI).

**Impact on Requirements**: FR-021 and INT-009 enable phasing; BR-006 is a release gate.

**Stakeholder Management**: Minister/DBT — phased migration still delivers the exit, with lower risk.

---

### Conflict C-5: Security/attribution friction vs. counter usability

**Conflicting Requirements**:

- **Requirement A**: NFR-SEC-001 / FR-007 — strong authentication and named attribution of every financial action.
- **Requirement B**: NFR-U-001 — fast, easy counter operation for staff of varied digital confidence.

**Stakeholders Involved**: CISO/SIRO and the integrity agenda require strong authentication; counter staff require speed and simplicity.

**Nature of Conflict**: Heavy authentication friction at the counter slows service and frustrates staff.

**Resolution Strategy**: COMPROMISE

**Decision**: Risk-based, ergonomic authentication — strong, named authentication that is fast at the counter; full MFA for privileged, remote and central operations; re-authentication only for sensitive actions.

**Rationale**: Attribution is non-negotiable, but it can be delivered with low everyday friction; usability is preserved for routine counter work.

**Decision Authority**: CISO/SIRO with the Post Office CTO (per STKE RACI).

**Impact on Requirements**: NFR-SEC-001 specifies counter authentication as "strong yet ergonomic"; NFR-U-001 retained in full.

**Stakeholder Management**: Both stakeholders broadly satisfied; validate authentication ergonomics in usability testing.

---

## Requirements Traceability Matrix

| Requirement group | Traces to STKE goals | Traces to STKE outcomes | Aligns with PRIN principles |
|-------------------|----------------------|-------------------------|------------------------------|
| BR-001, FR-004–FR-009, NFR-P-004, NFR-C-002, DR-001/002 | G-1, G-5 | O-1, O-5 | 6, 7 (NON-NEGOTIABLE), 23 |
| BR-002, FR-021, INT-009, DR-003 | G-2, G-8 | O-3 | 3, 14, 24 |
| BR-003, FR-010–FR-014, NFR-U-001/002 | G-3 | O-2 | 8, 9, 19 |
| BR-004 | G-4 | O-4 | 23 |
| BR-005, FR-016, NFR-C-005, DR-010 | G-10 | O-5 | 10, 23 |
| BR-006, FR-001–FR-003, FR-019–FR-022, NFR-A-001/002/003 | G-8 | O-6 | 1, 2, 17 |
| BR-007, NFR-I-001/002/003 | G-9 | O-4 | 3, 14, 24 |
| BR-008, FR-006–FR-009, FR-018, NFR-SEC-006 | G-5 | O-1 | 7 (NON-NEGOTIABLE) |
| BR-009, FR-013–FR-015, DR-004 | G-3 | O-1, O-2 | 9, 11 |
| BR-010 | G-10 | O-5 | 23 |
| NFR-SEC-001–005, NFR-C-001/003/004, DR-005–008 | G-7 | O-6 | 4, 13 |
| NFR-M-001–003, FR-017 | G-5, G-9 | O-5, O-6 | 5, 18, 20–22 |

> Full forward/backward traceability (requirements → design → test) is produced via `/arckit:traceability`.

---

## Timeline and Milestones

### High-Level Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Requirements Approval | Stakeholder sign-off on this document | 2026-06-20 (review target) | This document |
| Supplier contracts signed | Operator/builder and EPOS supplier contracts | Summer 2026 (reported) | Procurement |
| Design Complete | HLD and DLD approved, assured | To be set in `/arckit:plan` | Requirements |
| Pilot go-live | First branches on the replacement | To be set in `/arckit:plan` | Design, assurance gate |
| Fujitsu operational exit | Fujitsu ceases operating branch IT | ~Mid-2027 (assurance-conditional) | Pilot success, rollout |
| Network rollout complete | All branches migrated | End-2028 (indicative) | Phased migration |
| Horizon eradication | All Horizon components decommissioned | By 2030 | Rollout complete |

---

## Budget

### Cost Estimate

A programme-validated cost estimate is **not yet established**; it is produced through the Strategic Outline Business Case (`/arckit:sobc`). Publicly reported figures provide context only and are not a programme cost baseline:

| Category | Reported public context | Notes |
|----------|-------------------------|-------|
| Government funding commitment | ~£483m (reported Feb 2026); total investment reported as exceeding £700m | External reporting; to be validated |
| Operations / transition procurement lot | ~£323m (reported) | External reporting; commercial detail unconfirmed [POHR-C9] |
| EPOS replacement procurement lot | ~£160m–£169m (reported) | External reporting; commercial detail unconfirmed |
| Prior NBIT programme (abandoned) | ~£1bn taxpayer cost | Cautionary precedent, not part of this estimate [POHR-C6] |

### Ongoing Operational Costs

Run costs (cloud hosting, support, licences) are to be modelled in the Strategic Outline Business Case and validated against supplier contracts. They are not yet established.

---

## Approval

### Requirements Review

| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| [PENDING] | Programme SRO | [ ] Approved | [PENDING] | |
| [PENDING] | Post Office CTO | [ ] Approved | [PENDING] | |
| Mark Craddock | Enterprise Architect | [ ] Approved | [PENDING] | |
| [PENDING] | CISO / SIRO | [ ] Approved | [PENDING] | |
| [PENDING] | Data Protection Officer | [ ] Approved | [PENDING] | |

### Sign-Off

By signing below, stakeholders confirm that requirements are complete, understood, and approved to proceed to design phase.

| Stakeholder | Signature | Date |
|-------------|-----------|------|
| Programme SRO | _________ | [PENDING] |
| Post Office CTO | _________ | [PENDING] |

---

## Appendices

### Appendix A: Glossary

| Term | Definition |
|------|------------|
| Horizon | The Post Office branch accounting and EPOS system being replaced. |
| Legacy Horizon | The original Horizon generation (c.1999/2000–2010), Riposte-based with offline branch servers. |
| Horizon Online / HNG-X / HNG-A | The online Horizon generation (from 2010) with a central Branch Database. |
| EPOS | Electronic Point of Sale — the counter sales/accounting application. |
| Sub-postmaster | The operator accountable for a Post Office branch. |
| Branch accounting | The recording and reconciliation of a branch's cash, stock and ledger. |
| BED | Bugs, Errors and Defects — defects in Horizon affecting account accuracy. |
| NBIT | New Branch IT — the abandoned in-house Horizon replacement programme. |
| Capture | A pre-Horizon Post Office accounting product (1990s) of contested reliability. |
| Inquiry | The Post Office Horizon IT Inquiry (Sir Wyn Williams). |

### Appendix B: Reference Documents

- `ARC-000-PRIN-v1.0` — Enterprise Architecture Principles.
- `ARC-001-STKE-v1.0` — Stakeholder Drivers & Goals Analysis.
- `projects/000-global/external/post-office-horizon-research.md` — Post Office Horizon background research report.

### Appendix C: Wireframes and Mockups

Not produced at requirements stage; user-interface design follows in the design phase.

### Appendix D: Data Models

Indicative entities are listed in the Data Requirements section. A comprehensive data model is produced via `/arckit:data-model`.

---

**Document History**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial DRAFT issued for stakeholder review |

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| POHR | post-office-horizon-research.md | Research / Reference | 000-global/external/ | Background research report on the Post Office Horizon IT system, the scandal, the inquiry and the replacement programme |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| POHR-C1 | POHR | §1.5 Remote access | Security Requirement | "Fujitsu, and to a lesser extent the Post Office, had remote access to branch records and could 'insert, inject, edit or delete transaction data or data in branch accounts.'" |
| POHR-C2 | POHR | §2.1 Bugs, errors and defects | Functional Requirement | "Evidence to the inquiry indicated Fujitsu was aware of bugs from as early as 1999, and that this knowledge was not properly disclosed to sub-postmasters or to the courts." |
| POHR-C3 | POHR | §1.1 What it is | Non-Functional Requirement | "At its peak it spanned roughly 11,500 to 14,000 branches." |
| POHR-C4 | POHR | §6.2 Target architecture | Design Decision | "The stated target architecture is a composable, event-driven, service-oriented architecture built from standards-based modular components, including migration from on-premise data centres to the cloud." |
| POHR-C5 | POHR | §6.2 Timeline | Procurement Constraint | "Fujitsu's exit was projected for roughly eight to twelve months after both contracts are signed (i.e. broadly mid-2027), with complete eradication of Horizon targeted by 2030." |
| POHR-C6 | POHR | §6.1 NBIT | Risk Factor | "Post Office chairman Nigel Railton publicly stated NBIT was effectively 'set up to fail' ... a cited taxpayer cost reaching the order of £1bn." |
| POHR-C7 | POHR | §5.5 Capture | Data Requirement | "Forensic firm Kroll concluded there is a 'reasonable likelihood' Capture could also have caused shortfalls." |
| POHR-C8 | POHR | §1.4 Major versions | Data Requirement | "Horizon Online / HNG-X (from 2010). A complete rewrite by Fujitsu ... moving to a fully online architecture with branch data held centrally in a single Branch Database (BRDB)." |
| POHR-C9 | POHR | §6.3 Accenture involvement | Procurement Constraint | "the commercial specifics of the Accenture/One View Commerce Horizon engagement ... contract values, exact scope split, signature dates ... were not confirmed in the sources reviewed." |
| POHR-C10 | POHR | §4.3 Volume 1 | Compliance Constraint | "Sir Wyn Williams published Volume 1 of the inquiry's final report ... It made 19 recommendations." |

### Unreferenced Documents

| Filename | Source Location | Reason |
|----------|-----------------|--------|
| ARC-000-PRIN-v1.0.md | 000-global/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |
| ARC-001-STKE-v1.0.md | 001-post-office-horizon/ | ArcKit sibling artifact, not external source material — referenced inline, not cited. |

---

**Generated by**: ArcKit `/arckit:requirements` command
**Generated on**: 2026-05-21 GMT
**ArcKit Version**: 5.0.2
**Project**: Post Office Horizon (Project 001)
**AI Model**: Claude Opus 4.7 (1M context)
**Generation Context**: Derived from ARC-001-STKE-v1.0 (stakeholder analysis), ARC-000-PRIN-v1.0 (architecture principles), and the background research report at projects/000-global/external/post-office-horizon-research.md.
