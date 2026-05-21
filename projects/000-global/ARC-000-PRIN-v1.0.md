# Post Office Horizon Programme — Enterprise Architecture Principles

> **Template Origin**: Official | **ArcKit Version**: 5.0.2 | **Command**: `/arckit:principles`

## Document Control

| Field | Value |
|-------|-------|
| Document ID | ARC-000-PRIN-v1.0 |
| Document Type | Architecture Principles |
| Project | Post Office Horizon — Global Architecture Governance (Project 000) |
| Classification | OFFICIAL |
| Status | DRAFT |
| Version | 1.0 |
| Created Date | 2026-05-21 |
| Last Modified | 2026-05-21 |
| Review Cycle | Annual (12 months) |
| Next Review Date | 2027-05-21 |
| Owner | Mark Craddock, Enterprise Architect |
| Reviewed By | PENDING |
| Approved By | PENDING — Enterprise Architecture Review Board |
| Distribution | Post Office Horizon Programme — architecture, delivery, security, assurance and governance teams; incoming delivery suppliers |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial creation from `/arckit:principles` command | PENDING | PENDING |

---

## Executive Summary

This document establishes the principles governing all technology architecture decisions for the **Post Office Horizon replacement programme** and successor branch and back-office systems. These principles ensure consistency, security, transaction integrity and alignment with the programme's overriding objective: to deliver a branch IT system that is **demonstrably trustworthy**.

Unlike a generic principles set, this document is deliberately shaped by the findings of the **Post Office Horizon IT Inquiry** and the *Bates & Others v Post Office Ltd* litigation. The original Horizon system produced apparent accounting shortfalls, was wrongly presented as reliable and tamper-proof, and became the evidential basis for one of the most extensive miscarriages of justice in British legal history. Any replacement that does not **provably** guarantee transaction integrity, attributable access, and transparency to sub-postmasters would risk recreating the conditions that caused that injustice [POHR-C1].

**Scope**: All technology projects, systems, suppliers and initiatives within the Post Office Horizon replacement programme.
**Authority**: Enterprise Architecture Review Board (EARB).
**Compliance**: Mandatory unless a documented exception is approved (see Section VII). Principles marked **NON-NEGOTIABLE** admit no exceptions.

**Philosophy**: These principles are **technology-agnostic** — they describe WHAT qualities the architecture must have, not HOW to implement them with specific products. Technology selection happens during research and design phases, guided by these principles.

This document defines **24 principles** across **six categories**. Category II (Transaction Integrity and Accountability) is specific to this programme and carries the highest collective weight.

---

## I. Strategic Principles

### 1. Scalability and Elasticity

**Principle Statement**:
All systems MUST be designed to scale horizontally to meet demand, with the ability to adjust capacity in response to load without architectural change.

**Rationale**:
The branch network spans roughly 11,500 outlets with strongly cyclical demand (benefit days, peak postal periods, end-of-day reconciliation). Capacity must absorb both steady growth and predictable spikes without manual intervention.

**Implications**:

- Design stateless components that can be replicated behind load balancing.
- Avoid hard-coded capacity limits or fixed-instance assumptions.
- Plan for distributed deployment across multiple compute zones.
- Define scaling metrics, triggers and headroom explicitly.
- Ensure the cost model accounts for variable capacity.

**Validation Gates**:

- [ ] System scales horizontally by adding instances, with no single bottleneck.
- [ ] Load testing demonstrates capacity growth tracks added resources.
- [ ] Auto-scaling triggers and thresholds are defined and tested.
- [ ] Peak-demand scenarios (benefit days, December postal peak) modelled.

**Example** — *Good*: A counter-transaction service that runs N replicas and adds capacity automatically as request rate rises. *Bad*: A reconciliation batch job sized for a fixed branch count that must be re-engineered each time the network changes.

**Common Violations**:

- Vertical-only scaling ("buy a bigger server").
- Stateful sessions pinned to a single node, preventing replication.

---

### 2. Resilience and Fault Tolerance

**Principle Statement**:
All systems MUST degrade gracefully when dependencies fail and recover automatically without data loss or unattended manual intervention.

**Rationale**:
A branch must be able to keep serving customers and recording transactions safely even when central services or networks are impaired. Failure must never silently corrupt branch accounts.

**Implications**:

- Apply timeouts, retries with exponential backoff, and circuit breakers on all remote calls.
- Isolate failure domains (bulkheads) so one branch or service cannot cascade failure network-wide.
- Define degraded-mode behaviour that preserves transaction integrity above availability.
- Automate health checks, failover and recovery.

**Validation Gates**:

- [ ] Failure modes identified, documented and mitigated.
- [ ] Recovery Time Objective (RTO) and Recovery Point Objective (RPO) defined and tested.
- [ ] Fault-injection / chaos testing performed.
- [ ] Degraded-mode behaviour preserves the integrity and auditability of transaction records.

**Example** — *Good*: A branch terminal that queues transactions locally during a network outage and reconciles them with a complete, attributable audit trail on reconnection. *Bad*: A terminal that, on network loss, silently discards or duplicates transactions — the failure pattern behind the Dalmellington and Callendar Square defects.

**Common Violations**:

- "Best effort" recovery that can leave accounts in an indeterminate state.
- Retry logic that re-applies a financial transaction without idempotency.

---

### 3. Interoperability and Open Standards

**Principle Statement**:
All systems MUST expose functionality through well-defined, versioned interfaces using open, industry-standard protocols. Direct database access across system boundaries is prohibited.

**Rationale**:
Horizon is a tightly coupled estate of 80-plus components under mixed ownership, and exiting it has proven extraordinarily difficult. A composable, standards-based, modular target architecture is the stated direction for the replacement and reduces lock-in [POHR-C10].

**Implications**:

- Use standardised, openly documented protocols for synchronous and asynchronous interaction.
- Publish interface contracts (API and event-schema specifications) for every boundary.
- Version all interfaces with an explicit backward-compatibility strategy.
- Prohibit direct cross-system database coupling.
- Favour open standards over proprietary formats to preserve portability.

**Validation Gates**:

- [ ] Interface specifications published and version-controlled.
- [ ] Versioning and deprecation strategy documented.
- [ ] No direct database access across system boundaries.
- [ ] Data export/import paths use open, documented formats.

**Example** — *Good*: An EPOS component integrating with the back-office ledger via a published, versioned event schema. *Bad*: A new module reading the ledger database directly, recreating the coupling that made Horizon impossible to replace incrementally.

**Common Violations**:

- Shared database tables used as an integration mechanism.
- Proprietary interfaces with no published contract or version policy.

---

### 4. Security by Design (NON-NEGOTIABLE)

**Principle Statement**:
All architectures MUST implement defence-in-depth with zero-trust principles. Security is a foundational requirement, never a later addition.

**Rationale**:
The system handles cash, banking, identity and personal data across thousands of locations. The threat landscape requires assuming breach, eliminating implicit trust, and continuously verifying every access request.

**Zero Trust Pillars**:

1. **Identity-Based Access** — no network-based trust; every request authenticated.
2. **Least Privilege** — minimum necessary permissions, time-boxed where possible.
3. **Encryption Everywhere** — data encrypted in transit and at rest.
4. **Continuous Verification** — monitor, log and analyse all access patterns.

**Mandatory Controls**:

- [ ] Multi-factor authentication for all human access.
- [ ] Strong service-to-service authentication (mutual authentication or signed tokens).
- [ ] Secrets held in a managed vault — never in code or configuration.
- [ ] Network segmentation with minimal trust zones.
- [ ] Encryption at rest for all data stores; encrypted transport for all communication.
- [ ] Structured logging of all authentication and authorisation events.
- [ ] Regular penetration testing and vulnerability scanning.

**Compliance Frameworks**:

- NCSC Cyber Assessment Framework (CAF); NCSC Secure by Design; ISO/IEC 27001.
- UK GDPR / Data Protection Act 2018; PCI-DSS where payment card data is processed.

**Exceptions**: NONE. Specific control implementations may vary only where compensating controls provide equivalent assurance.

**Validation Gates**:

- [ ] Threat model completed and reviewed.
- [ ] Security controls mapped to requirements.
- [ ] Security testing plan defined and executed.
- [ ] Incident response runbook created.

**Example** — *Good*: A privileged support action that requires MFA, is least-privilege scoped, and is fully logged. *Bad*: Shared administrative credentials with broad standing access.

**Common Violations**:

- Treating security as a pre-go-live gate rather than a design input.
- Standing privileged access with no time limit or review.

---

### 5. Observability and Operational Excellence

**Principle Statement**:
All systems MUST emit structured telemetry — logs, metrics and traces — enabling real-time monitoring, troubleshooting, capacity planning and independent scrutiny.

**Rationale**:
We cannot operate, assure or defend a system we cannot observe. Observability also underpins the programme's transparency obligations: the behaviour of the system must be evidenced, not asserted.

**Telemetry Requirements**:

- **Logging** — structured logs with correlation IDs across service boundaries.
- **Metrics** — request volume, latency percentiles (p50, p95, p99), error rates.
- **Tracing** — distributed trace context for end-to-end request flows.
- **Alerting** — Service Level Objective (SLO)-based alerting with actionable runbooks.

**Log Retention**:

- Security and audit logs — retained per legal and regulatory obligation (typically 1–7 years; transaction audit records subject to Principle 6).
- Application logs — sufficient for troubleshooting (typically 30–90 days).
- Metrics — long-term trend retention with aggregation (typically 1–2 years).

**Validation Gates**:

- [ ] Logging, metrics and tracing instrumented across all services.
- [ ] Dashboards and SLO-based alerts configured.
- [ ] SLOs and Service Level Indicators (SLIs) defined.
- [ ] Runbooks created for common failure scenarios.

**Example** — *Good*: A traced reconciliation flow where every step is timestamped and correlatable. *Bad*: A nightly batch whose only evidence of success is the absence of a complaint.

**Common Violations**:

- Unstructured free-text logs that cannot be queried or correlated.
- Telemetry that omits the business events (transactions, adjustments) that matter most.

---

## II. Transaction Integrity and Accountability Principles

> This category is specific to the Post Office Horizon replacement programme. It encodes the architectural lessons of the Horizon scandal. Where these principles and others appear to conflict, **these principles take precedence**.

### 6. Tamper-Evident Transaction Integrity (NON-NEGOTIABLE)

**Principle Statement**:
Every branch transaction and every adjustment to a branch account MUST be recorded in an immutable, append-only, cryptographically verifiable audit record. It MUST always be possible to reconstruct definitively what occurred in a branch on any given day, and to prove the record has not been altered.

**Rationale**:
Apparent shortfalls in branch accounts were treated as proof of dishonesty when they were, in material part, the product of system defects. The replacement must make the financial record **provably correct and provably unaltered**, so that no person is ever again held liable on the strength of an unverifiable account [POHR-C2].

**Implications**:

- The transaction record is append-only: corrections are made by new, linked compensating entries, never by overwriting or deleting history.
- Audit records are cryptographically chained or otherwise tamper-evident, so any alteration is detectable.
- Every entry carries who, what, when, where and why, and the originating channel.
- Retention of transaction audit data is long-term and governed by legal-hold rules; it is never silently purged.
- Integrity verification is independently runnable — by auditors, by the inquiry's legacy bodies, and by a sub-postmaster's representatives.

**Validation Gates**:

- [ ] Transaction store is demonstrably append-only; no update/delete path exists for posted entries.
- [ ] Tamper-evidence mechanism specified, implemented and independently testable.
- [ ] Point-in-time reconstruction of any branch's accounts demonstrated.
- [ ] Corrections implemented as linked compensating entries with full attribution.
- [ ] Independent integrity-verification procedure documented and exercised.

**Example** — *Good*: A duplicate posting is resolved by a clearly attributed reversing entry, leaving both the error and its correction permanently visible. *Bad*: A back-office operator edits the ledger to "fix" a discrepancy, erasing evidence of the original fault.

**Common Violations**:

- Mutable financial records "for operational convenience".
- Audit logs stored in a system that administrators can edit or truncate.

---

### 7. Attributable, Transparent Access — No Covert Change (NON-NEGOTIABLE)

**Principle Statement**:
No party — Post Office, supplier, or third party — MAY create, alter or delete a branch's financial records without the change being authenticated, attributed to a named individual, fully logged, immutably recorded, and made visible to the affected sub-postmaster. Covert remote mutation of branch accounts MUST be architecturally impossible.

**Rationale**:
The single most damaging fact established by the *Horizon Issues* judgment was that Fujitsu, and to a lesser extent the Post Office, could "insert, inject, edit or delete transaction data or data in branch accounts" remotely — while the Post Office told courts and sub-postmasters this was impossible [POHR-C3]. The replacement must remove both the capability for covert change and the possibility of denying it.

**Implications**:

- There is no support, maintenance or administrative path that can mutate branch financial data without attribution and notification.
- Any centrally or remotely initiated entry is treated as a first-class, attributed transaction subject to Principle 6.
- "Read" and "write" capabilities are strictly separated; write access to financial data requires named authorisation and is exceptional.
- The sub-postmaster is notified of any externally initiated change affecting their accounts.
- Capability to alter accounts is provable by design — and provable to be absent where it should be absent.

**Validation Gates**:

- [ ] Threat model explicitly covers covert/undisclosed alteration of branch accounts and shows it is prevented.
- [ ] Every channel that can write financial data enforces named attribution.
- [ ] Sub-postmaster notification of externally initiated entries demonstrated.
- [ ] No shared/anonymous account can write to branch financial data.
- [ ] Independent assurance has confirmed the absence of covert write paths.

**Example** — *Good*: A central correction is posted as a named, logged transaction and appears immediately on the sub-postmaster's own view. *Bad*: A "balancing transaction" applied by a support team that the branch never sees and cannot trace.

**Common Violations**:

- Database-level access for support staff that bypasses the application's attribution controls.
- Service accounts with standing write access to ledgers.

---

### 8. Postmaster Visibility and Explainability

**Principle Statement**:
Sub-postmasters MUST be able to see, in real time and in plain, intelligible terms, everything that affects their accounts — including centrally or remotely initiated entries — together with the data and tools needed to understand and challenge a discrepancy before any liability attaches.

**Rationale**:
Sub-postmasters were held liable for discrepancies they had no means to investigate or explain. A trustworthy system makes the branch user's view authoritative, complete and comprehensible, so that an apparent shortfall can be understood at source [POHR-C4].

**Implications**:

- The branch-facing account view is complete: nothing affecting the balance is hidden from it.
- Every entry is explainable — its origin, cause and supporting detail are accessible to the sub-postmaster.
- Discrepancies are surfaced with enough context to investigate, not merely flagged as a number.
- Plain-language presentation is a design requirement, not a documentation afterthought.
- Sub-postmasters can export their own transaction and audit data.

**Validation Gates**:

- [ ] Branch view demonstrably reflects all entries, including external ones.
- [ ] Each entry type has a plain-language explanation accessible in-product.
- [ ] Discrepancy displays include investigative context and supporting records.
- [ ] Sub-postmaster self-service data export available.
- [ ] Usability tested with practising sub-postmasters of varied digital confidence.

**Example** — *Good*: A discrepancy screen showing the contributing transactions, their sources and timestamps, with a route to query each. *Bad*: An end-of-day "shortfall: £X" with no breakdown and no way to interrogate it.

**Common Violations**:

- Central adjustments visible to head office but not to the branch.
- Discrepancies expressed only as net figures with no traceable detail.

---

### 9. Fair Discrepancy and Dispute Resolution

**Principle Statement**:
An apparent shortfall MUST be treated as an event requiring investigation, not as presumptive evidence of fault. The architecture MUST support a defined, fair, independently overseen process for raising, investigating and resolving discrepancies, and MUST NOT allow liability to be imposed while a genuine dispute is unresolved.

**Rationale**:
The Post Office reversed the burden of proof — sub-postmasters were required to "make good" shortfalls, often under threat of prosecution, before any investigation. Discrepancies must instead be presumed to need investigation [POHR-C5].

**Implications**:

- Discrepancies enter a defined dispute lifecycle with status, ownership and timescales.
- "Make good" demands cannot be raised, and liability cannot attach, while a discrepancy is genuinely in dispute.
- The process supports independent oversight and review of outcomes.
- Dispute records are themselves immutable, attributed and auditable (Principle 6).
- System data used in any dispute is accompanied by an honest reliability assessment (Principle 10).

**Validation Gates**:

- [ ] Discrepancy/dispute lifecycle modelled with states, owners and SLAs.
- [ ] Controls prevent liability or recovery action during an open dispute.
- [ ] Independent review/escalation route supported by the system.
- [ ] Dispute history is immutable and auditable.

**Example** — *Good*: A flagged shortfall opens an investigation case; recovery is blocked until the case closes with a documented, reviewable outcome. *Bad*: An automated demand for repayment issued the moment a branch fails to balance.

**Common Violations**:

- Automated debt recovery triggered by an unreconciled balance.
- Dispute outcomes recorded only in informal channels (email, phone notes).

---

### 10. Defect Transparency and Honest Disclosure

**Principle Statement**:
Known bugs, errors and defects affecting financial accuracy MUST be tracked in a register that is disclosed and accessible to affected parties. Any use of system data as evidence MUST rest on an honest, current assessment of system reliability.

**Rationale**:
Fujitsu was aware of Horizon defects from as early as 1999; that knowledge was not disclosed to sub-postmasters or the courts. The catastrophic failure was the **concealment** of known defects — not merely their existence [POHR-C6].

**Implications**:

- A "bugs, errors and defects" (BED) register records financial-accuracy defects, their impact, affected branches and remediation status.
- The register is disclosed to affected sub-postmasters and available to assurance and oversight bodies.
- Any process presenting system data as authoritative — internally or in a legal context — references the current reliability position, including open defects.
- Defect concealment is treated as a governance failure of the highest severity.

**Validation Gates**:

- [ ] BED register exists, is maintained, and covers financial-accuracy defects.
- [ ] Disclosure process to affected parties defined and operating.
- [ ] Reliability statements accompany system data used as evidence.
- [ ] Escalation path defined for any attempt to suppress defect information.

**Example** — *Good*: A newly found rounding defect is logged, its affected branches identified and contacted, and dependent disputes paused pending correction. *Bad*: A known defect quietly patched while affected branches continue to be pursued for the resulting shortfalls.

**Common Violations**:

- Defects tracked only in an internal tool invisible to affected users.
- Presenting "the system says" data without disclosing open reliability issues.

---

## III. Data Principles

### 11. Data Provenance and Lineage

**Principle Statement**:
Every data item MUST be traceable to its origin and transformation history. Historical and migrated data MUST be clearly flagged as to provenance and reliability, and MUST NOT be presented as authoritative where its reliability is contested.

**Rationale**:
Migration from Legacy Horizon, Horizon Online/HNG-A, and awareness that the pre-Horizon **Capture** system is itself contested, means historical balances cannot be assumed correct. The replacement must not "launder" disputed historical figures into apparently clean opening balances [POHR-C7].

**Implications**:

- Source-to-target lineage is documented and queryable for all data flows.
- Migrated records retain a provenance marker (source system, migration date, reliability status).
- Disputed or unverified historical items are explicitly flagged, not silently carried forward.
- Migration logic is version-controlled, reviewable and auditable.
- Opening balances derived from legacy data state their basis and confidence.

**Validation Gates**:

- [ ] Lineage metadata captured and queryable end-to-end.
- [ ] Migrated data carries provenance and reliability markers.
- [ ] Disputed historical items flagged and excluded from authoritative presentation.
- [ ] Migration transformations version-controlled and independently reviewed.

**Example** — *Good*: A migrated opening balance labelled "derived from Horizon Online, 2026-06; £X subject to open dispute D-014". *Bad*: A single clean opening balance with no indication that part of it is contested.

**Common Violations**:

- "Big bang" migration that discards source-system context.
- Treating a migrated figure as fact because it is now in the new system.

---

### 12. Single Source of Truth

**Principle Statement**:
Every data domain MUST have a single authoritative system of record. Derived or cached copies MUST be read-only, clearly labelled, and synchronised from the source.

**Rationale**:
Multiple authoritative sources create reconciliation overhead and integrity disputes — precisely the conditions in which unexplained discrepancies arise.

**Implications**:

- Identify the system of record for each data domain (branch transactions, products, identities, branch master data).
- Derived copies are read-only and labelled as derived, with defined sync frequency.
- Avoid bidirectional synchronisation without an explicit conflict-resolution strategy.
- Apply master data management to shared reference data.

**Validation Gates**:

- [ ] System of record identified for each data entity.
- [ ] Derived copies documented with sync frequency and direction.
- [ ] No bidirectional sync without a conflict-resolution strategy.

**Example** — *Good*: The transaction ledger is the sole system of record; reporting stores are clearly derived read-only copies. *Bad*: Two services each maintaining an editable "current balance" that periodically disagree.

**Common Violations**:

- Editable duplicates of financial data in reporting or analytics systems.
- Reference data maintained independently in several systems.

---

### 13. Data Protection and Governance

**Principle Statement**:
Data classification, residency, retention and access controls MUST comply with UK GDPR, the Data Protection Act 2018, and Post Office data governance policy. Personal data MUST be processed under the principles of data minimisation and purpose limitation.

**Data Classification Tiers**:

1. **Public** — no restrictions.
2. **Internal** — staff-only access.
3. **Confidential** — need-to-know (personal data, commercially sensitive data).
4. **Restricted** — highest controls (financial transaction data, payment card data, special-category data).

**Implications**:

- Personal and financial data resides in jurisdictions compliant with applicable law; cross-border transfers require a lawful basis.
- Retention is governed by policy and legal hold; transaction audit data follows Principle 6 retention rules and is never deleted while subject to inquiry, redress or litigation hold.
- Access enforces least privilege and need-to-know.
- A Data Protection Impact Assessment (DPIA) is completed where processing is likely to result in high risk to individuals.

**Validation Gates**:

- [ ] Data classification performed for all data stores.
- [ ] Residency requirements mapped to infrastructure.
- [ ] Retention policies configured, with legal-hold override for in-scope data.
- [ ] DPIA completed where required; access enforces least privilege.

**Example** — *Good*: Sub-postmaster personal data minimised, classified Confidential, and access-logged. *Bad*: Bulk personal data copied into an unclassified analytics environment.

**Common Violations**:

- Production personal data used in test environments without protection.
- Retention rules that could delete data still needed for redress or legal proceedings.

---

## IV. Integration Principles

### 14. Loose Coupling and Composability

**Principle Statement**:
Systems MUST be loosely coupled through published interfaces, composed of independently deployable, replaceable modules. Shared databases, shared file systems and tight runtime dependencies across boundaries are prohibited.

**Rationale**:
Horizon's tight coupling across 80-plus components is why it has taken a decade and is projected to cost hundreds of millions to replace. A composable, modular architecture allows incremental replacement and avoids recreating the same trap [POHR-C10].

**Implications**:

- Communicate through published APIs or events, never a shared database.
- Each module owns its data lifecycle and is independently deployable.
- Keep shared libraries minimal; prefer duplication over coupling.
- Avoid distributed transactions across modules.
- Design each module so it can be replaced without re-architecting its neighbours.

**Validation Gates**:

- [ ] Modules communicate via APIs or events, not shared storage.
- [ ] Each module has an independent data store.
- [ ] Deploying one module does not require redeploying another.
- [ ] A module-replacement path exists and is documented.

**Example** — *Good*: The EPOS module can be swapped for an alternative provider behind a stable contract. *Bad*: A "module" that cannot be deployed or replaced without coordinated changes across five others.

**Common Violations**:

- Integration via shared database tables.
- A "modular" architecture whose modules deploy as a single unit.

---

### 15. Event-Driven and Asynchronous Integration

**Principle Statement**:
Systems SHOULD use event-driven, asynchronous communication for non-real-time interactions to improve resilience and decoupling. Synchronous communication SHOULD be reserved for interactions requiring an immediate response or immediate consistency.

**Rationale**:
Asynchronous patterns reduce temporal coupling and improve fault tolerance, supporting the resilience and composability objectives. The target architecture is explicitly event-driven [POHR-C10].

**When to Use Asynchronous**:

- Non-real-time business processes (reconciliation, settlement, reporting, notifications).
- Event notification and publish/subscribe patterns.
- Integration with slower or less reliable external systems.

**When Synchronous is Acceptable**:

- Real-time counter interactions requiring immediate feedback.
- Read-only, idempotent queries.
- Operations requiring immediate consistency (note: transaction posting still complies with Principle 6).

**Validation Gates**:

- [ ] Asynchronous patterns used for non-real-time flows.
- [ ] Message durability and delivery guarantees defined.
- [ ] Event schemas versioned and published.
- [ ] Dead-letter handling and replay configured.

**Example** — *Good*: A posted transaction emits a durable event consumed by reporting and settlement independently. *Bad*: A counter sale blocked while it synchronously waits on a reporting system.

**Common Violations**:

- Long synchronous call chains that fail if any link is slow.
- "Fire and forget" messaging with no delivery guarantee for financially significant events.

---

## V. Quality Attributes

### 16. Performance and Efficiency

**Principle Statement**:
All systems MUST meet defined performance targets under expected peak load, making efficient use of computational resources.

**Performance Targets** (define and baseline per system; indicative):

- **Counter response time** — interactive operations complete in < 2 seconds at p95.
- **Throughput** — sized for network-wide peak transaction volume with headroom.
- **End-of-day reconciliation** — completes within the defined operational window.

**Implications**:

- Performance requirements are defined before implementation and baselined.
- Load testing at expected peak precedes production deployment.
- Performance is monitored continuously, not point-in-time.
- Hot paths identified by profiling are optimised.

**Validation Gates**:

- [ ] Performance requirements defined with measurable targets.
- [ ] Load testing performed at peak capacity.
- [ ] Performance metrics monitored in production.

**Example** — *Good*: A counter transaction tested to hold < 2 second p95 latency at peak. *Bad*: Performance "confirmed" only by developer testing on an idle environment.

**Common Violations**:

- Performance targets defined after build.
- Load testing that ignores end-of-day and benefit-day peaks.

---

### 17. Availability and Service Continuity

**Principle Statement**:
All systems MUST meet defined availability targets with automated recovery and minimal data loss, supported by a tested business continuity and disaster recovery capability.

**Availability Targets** (define per system; indicative):

- **Uptime** — branch-critical services target >= 99.9% during branch operating hours.
- **RTO / RPO** — defined per system; for transaction data, RPO targets zero loss.

**High Availability Patterns**:

- Redundancy across availability zones / data centres.
- Automated health checks and failover.
- Regular, evidenced disaster recovery testing.

**Validation Gates**:

- [ ] Availability target and operating-hours definition agreed.
- [ ] RTO and RPO documented; transaction-data RPO is zero loss.
- [ ] Failover and restore tested and evidenced.
- [ ] Business continuity plan covers extended central outage with branch-level safe operation.

**Example** — *Good*: A regional failure fails over automatically with no committed transaction lost. *Bad*: A single data centre whose loss halts every branch.

**Common Violations**:

- Disaster recovery documented but never tested.
- Availability claimed without an agreed measurement window.

---

### 18. Maintainability and Evolvability

**Principle Statement**:
All systems MUST be designed for change — clear separation of concerns, modular structure, current documentation, and significant decisions recorded in Architecture Decision Records (ADRs).

**Rationale**:
The system must remain affordable to change and to assure across a multi-decade life. Opaque, undocumented design is itself a programme risk.

**Implications**:

- Modular architecture with clear, documented boundaries and responsibilities.
- Separation of business logic, data access and presentation.
- Significant choices captured as ADRs and kept current.
- Automated tests enable confident refactoring.

**Validation Gates**:

- [ ] Architecture documentation exists and is current.
- [ ] Module boundaries and responsibilities documented.
- [ ] ADRs record key decisions.
- [ ] Test coverage supports safe refactoring.

**Example** — *Good*: A new developer can understand a module from its documentation and ADRs. *Bad*: Behaviour discoverable only by reading production code.

**Common Violations**:

- Documentation that drifts out of date and is not maintained.
- Significant decisions made with no recorded rationale.

---

### 19. Accessibility and Inclusive Design

**Principle Statement**:
All user-facing systems MUST meet recognised accessibility standards and be usable by people of varied digital confidence, ability and assistive-technology needs.

**Rationale**:
Sub-postmasters and counter staff span a wide range of digital confidence and accessibility needs, and public sector bodies are subject to accessibility regulations. A system people cannot confidently operate undermines transaction integrity at source.

**Implications**:

- User interfaces conform to WCAG 2.2 AA as a baseline.
- Inclusive design and accessibility testing are part of delivery, not retrofit.
- Critical workflows (transactions, balancing, dispute) are tested with assistive technologies.
- Plain language is used throughout (reinforcing Principle 8).

**Validation Gates**:

- [ ] Interfaces assessed against WCAG 2.2 AA.
- [ ] Accessibility testing includes assistive technologies.
- [ ] Usability testing includes users of varied digital confidence.
- [ ] An accessibility statement is maintained where required.

**Example** — *Good*: The balancing workflow is operable by keyboard and screen reader and tested with real users. *Bad*: A counter UI usable only with a mouse and unaided sight.

**Common Violations**:

- Accessibility deferred to a post-launch backlog.
- Testing limited to automated checks with no real users.

---

## VI. Delivery and Assurance Principles

### 20. Infrastructure as Code

**Principle Statement**:
All infrastructure MUST be defined as version-controlled code and provisioned through automated pipelines. Manual changes to production infrastructure are prohibited.

**Rationale**:
Manual infrastructure creates drift, undocumented state and unrepeatable environments — and undermines the auditability the programme requires.

**Implications**:

- Infrastructure defined declaratively and version-controlled.
- Infrastructure changes go through code review.
- Environments are reproducible from code.
- No manual production changes.

**Validation Gates**:

- [ ] Infrastructure defined as code and version-controlled.
- [ ] Automated provisioning pipeline in place.
- [ ] No manual production infrastructure changes.

**Example** — *Good*: A production environment rebuilt identically from its code definition. *Bad*: A production server hand-configured and undocumented.

**Common Violations**:

- "Temporary" manual fixes that become permanent undocumented state.
- Environments that differ in undocumented ways.

---

### 21. Automated Testing and Quality Gates

**Principle Statement**:
All code changes MUST be validated by automated testing before deployment to production, with quality gates that block release on failure.

**Test Coverage Expectations**:

- **Unit tests** — fast, isolated, the majority of tests.
- **Integration tests** — verify component interactions.
- **End-to-end tests** — cover critical user journeys (transaction posting, balancing, dispute).
- Functional, performance, security and resilience testing all required.

**Implications**:

- Financial-accuracy logic carries the highest test rigour, including reconciliation and edge-case scenarios drawn from known historical defect patterns.
- Tests run automatically and must pass before merge and before release.

**Validation Gates**:

- [ ] Automated tests exist and pass before merge.
- [ ] Coverage meets defined thresholds, with elevated rigour for financial logic.
- [ ] Critical paths have end-to-end tests.
- [ ] Performance and security tests run regularly.

**Example** — *Good*: A regression suite that explicitly covers duplicate-posting and frozen-transaction scenarios. *Bad*: Financial logic released on the strength of manual spot checks.

**Common Violations**:

- Quality gates that can be overridden silently.
- Financial-accuracy code with weaker coverage than peripheral features.

---

### 22. Continuous Integration and Continuous Delivery

**Principle Statement**:
All code changes MUST flow through automated build, test, security-scan and deployment pipelines, with quality gates at each stage and a tested rollback capability.

**Pipeline Stages**:

1. Source control — all changes committed and reviewed.
2. Build — automated compilation and packaging.
3. Test — automated test execution (Principle 21).
4. Security scan — dependency and code vulnerability scanning.
5. Deployment — automated, repeatable, with rollback.

**Validation Gates**:

- [ ] Automated CI/CD pipeline exists.
- [ ] Pipeline includes security scanning.
- [ ] Deployment is automated and repeatable.
- [ ] Rollback capability tested.

**Example** — *Good*: A change reaches production through a pipeline that proves it built, tested, scanned and can be rolled back. *Bad*: A release hand-deployed by an individual with no scan or rollback plan.

**Common Violations**:

- Manual deployment steps outside the pipeline.
- No tested way to roll back a bad release.

---

### 23. Independent Assurance and Honest Governance

**Principle Statement**:
The architecture and the programme delivering it MUST be subject to genuine independent technical assurance, realistic governance gates, and honest status reporting. Concealment or distortion of programme or system status MUST be treated as a critical governance failure.

**Rationale**:
Horizon went live over the objections of IT specialists; the in-house NBIT replacement was later judged to have been "set up to fail". A trustworthy outcome requires independent assurance and a culture in which bad news travels upward [POHR-C8].

**Implications**:

- Independent technical assurance reviews architecture and delivery at defined gates, with findings reported unfiltered to the EARB and programme board.
- Governance gates assess evidence, not optimism; a gate may halt or re-scope delivery.
- Status reporting is honest about risk, defects and schedule; RAG ratings are evidenced.
- Assurance findings, including uncomfortable ones, are recorded and tracked to closure.
- Suppliers are contractually obliged to support transparency and to disclose defects (Principle 10, Principle 24).

**Validation Gates**:

- [ ] Independent assurance function defined, resourced and demonstrably independent of delivery.
- [ ] Assurance gates defined with explicit halt/re-scope authority.
- [ ] Reporting standards require evidenced status and defect disclosure.
- [ ] Mechanism exists to escalate concealed or distorted status.

**Example** — *Good*: An independent reviewer escalates an unresolved integrity risk and the gate is held until it is addressed. *Bad*: A green status maintained to protect a deadline while a known integrity defect remains open.

**Common Violations**:

- "Assurance" performed by the team being assured.
- Optimistic RAG ratings unsupported by evidence.

---

### 24. Supplier Accountability and Exit Readiness

**Principle Statement**:
Responsibility across components and suppliers MUST be clearly allocated and contractually enforceable. The architecture MUST avoid single-supplier lock-in and maintain a tested exit strategy with full data portability.

**Rationale**:
Exiting Fujitsu has been a multi-year, multi-hundred-million-pound undertaking, and opacity in the Fujitsu arrangements obstructed accountability. The replacement must make a future transition straightforward and keep every supplier accountable [POHR-C9].

**Implications**:

- Every component has a named accountable owner; cross-supplier responsibilities are explicit and contractual.
- Contracts require transparency, defect disclosure, access to evidence, and cooperation with assurance and any legal process.
- Open standards and documented interfaces preserve the ability to replace any supplier (Principles 3, 14).
- An exit strategy with data portability is defined and tested for each significant supplier relationship.
- No design decision creates a dependency that cannot be unwound at acceptable cost.

**Validation Gates**:

- [ ] Component ownership and cross-supplier responsibilities documented and contractually backed.
- [ ] Contracts mandate transparency, defect disclosure and evidence access.
- [ ] Exit strategy and data-portability path defined for each significant supplier.
- [ ] Exit/portability tested, not merely asserted.

**Example** — *Good*: The EPOS supplier can be replaced via a documented exit plan with a proven data-export path. *Bad*: A supplier whose components cannot be operated, evidenced or replaced by anyone else.

**Common Violations**:

- Proprietary data formats with no export capability.
- Exit clauses that exist on paper but have never been tested.

---

## VII. Exception Process

Principles are mandatory unless a documented exception is approved by the Enterprise Architecture Review Board. **Principles marked NON-NEGOTIABLE (4, 6, 7) admit no exceptions** — only variation in the implementation of controls where compensating controls give equivalent assurance.

**Valid Exception Reasons**:

- Technical constraints that genuinely prevent compliance.
- Regulatory or legal requirements.
- Transitional state during migration from Horizon.
- Time-boxed pilot or proof-of-concept with a defined end date.

**Exception Request Requirements**:

- [ ] Justification with business and technical rationale.
- [ ] Alternative approach and compensating controls.
- [ ] Risk assessment and mitigation plan.
- [ ] Expiration date — exceptions are time-bound.
- [ ] Remediation plan to achieve compliance.

**Approval Process**:

1. Submit the exception request to the Enterprise Architecture team.
2. Review by the Enterprise Architecture Review Board.
3. Programme SRO / CTO approval for exceptions to CRITICAL principles.
4. Document the exception in the project architecture documentation.
5. Review all open exceptions quarterly.

---

## VIII. Governance and Compliance

### Architecture Review Gates

All projects pass architecture reviews at key milestones:

**Discovery / Alpha**:

- [ ] Architecture principles understood and applied.
- [ ] High-level approach aligns with principles, especially Category II.
- [ ] No obvious principle violations.

**Beta / Design**:

- [ ] Detailed architecture documented.
- [ ] Compliance with each principle validated against its gates.
- [ ] Exceptions requested and approved.
- [ ] Security, transaction-integrity and data principles validated.

**Pre-Production**:

- [ ] Implementation matches the approved architecture.
- [ ] All validation gates passed.
- [ ] Independent assurance sign-off obtained (Principle 23).
- [ ] Operational readiness verified.

### Enforcement

- Architecture reviews are **mandatory** for all projects in the programme.
- Principle violations must be remediated before production deployment.
- Approved exceptions are time-bound and reviewed quarterly.
- Live systems are subject to retrospective compliance review.
- A breach of a NON-NEGOTIABLE principle halts release until resolved.

---

## IX. Appendix

### Principle Summary Checklist

| # | Principle | Category | Criticality | Validation Focus |
|---|-----------|----------|-------------|------------------|
| 1 | Scalability and Elasticity | Strategic | HIGH | Load testing, scaling triggers |
| 2 | Resilience and Fault Tolerance | Strategic | CRITICAL | Fault injection, RTO/RPO |
| 3 | Interoperability and Open Standards | Strategic | HIGH | Published contracts, open formats |
| 4 | Security by Design | Strategic | CRITICAL (NON-NEGOTIABLE) | Threat model, pen testing |
| 5 | Observability and Operational Excellence | Strategic | HIGH | Logs, metrics, traces, SLOs |
| 6 | Tamper-Evident Transaction Integrity | Transaction Integrity | CRITICAL (NON-NEGOTIABLE) | Append-only, tamper-evidence, reconstruction |
| 7 | Attributable, Transparent Access | Transaction Integrity | CRITICAL (NON-NEGOTIABLE) | No covert write paths, attribution |
| 8 | Postmaster Visibility and Explainability | Transaction Integrity | CRITICAL | Complete branch view, explainability |
| 9 | Fair Discrepancy and Dispute Resolution | Transaction Integrity | CRITICAL | Dispute lifecycle, no liability while disputed |
| 10 | Defect Transparency and Honest Disclosure | Transaction Integrity | HIGH | BED register, disclosure process |
| 11 | Data Provenance and Lineage | Data | CRITICAL | Lineage, migrated-data flagging |
| 12 | Single Source of Truth | Data | HIGH | System of record per domain |
| 13 | Data Protection and Governance | Data | CRITICAL | Classification, UK GDPR, DPIA |
| 14 | Loose Coupling and Composability | Integration | HIGH | Independent deployment, replaceability |
| 15 | Event-Driven and Asynchronous Integration | Integration | MEDIUM | Async patterns, durable events |
| 16 | Performance and Efficiency | Quality | HIGH | Peak load testing |
| 17 | Availability and Service Continuity | Quality | CRITICAL | Uptime, RTO/RPO, DR testing |
| 18 | Maintainability and Evolvability | Quality | MEDIUM | Documentation, ADRs, tests |
| 19 | Accessibility and Inclusive Design | Quality | HIGH | WCAG 2.2 AA, assistive-tech testing |
| 20 | Infrastructure as Code | Delivery & Assurance | HIGH | IaC coverage, no manual changes |
| 21 | Automated Testing and Quality Gates | Delivery & Assurance | HIGH | Coverage, financial-logic rigour |
| 22 | Continuous Integration and Continuous Delivery | Delivery & Assurance | HIGH | Pipeline, security scan, rollback |
| 23 | Independent Assurance and Honest Governance | Delivery & Assurance | CRITICAL | Independent assurance, honest reporting |
| 24 | Supplier Accountability and Exit Readiness | Delivery & Assurance | HIGH | Accountability, exit strategy, portability |

### Principle Categorisation

- **Strategic / Application** — Principles 1–5, 14–22 (application and technology architecture qualities).
- **Transaction Integrity and Accountability** — Principles 6–10 (programme-specific; the defining category).
- **Data** — Principles 11–13.
- **Business and Governance** — Principles 9, 23, 24 carry significant business-governance weight alongside their technical content.

### Consistency Note

These principles have been checked for internal contradiction. Where Principle 15 (asynchronous integration) and Principle 6 (transaction integrity) interact, transaction posting remains synchronous and immediately consistent; only non-real-time flows are asynchronous. Where any principle conflicts with Category II, **Category II takes precedence**.

### Document Version History

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-05-21 | ArcKit AI | Initial DRAFT issued for review |

---

## External References

> This section provides traceability from generated content back to source documents.

### Document Register

| Doc ID | Filename | Type | Source Location | Description |
|--------|----------|------|-----------------|-------------|
| POHR | post-office-horizon-research.md | Research / Reference | 000-global/external/ | Background research report on the Post Office Horizon IT system, the scandal, the statutory inquiry, the redress schemes and the replacement programme |

### Citations

| Citation ID | Doc ID | Page/Section | Category | Quoted Passage |
|-------------|--------|--------------|----------|----------------|
| POHR-C1 | POHR | §7.1 Implications — Trust deficit | Risk Factor | "The replacement will be scrutinised by sub-postmasters, Parliament, the inquiry's legacy, the media ... and the public. The system and the programme should be transparent and explainable by default, and design decisions should be documented in a way that can withstand external and legal scrutiny." |
| POHR-C2 | POHR | §7.2 Transaction integrity | Design Decision | "Branch accounts must be backed by an immutable, cryptographically verifiable, append-only audit trail of every transaction and every adjustment. It must be possible to reconstruct, definitively, what happened in a branch on any given day." |
| POHR-C3 | POHR | §1.5 / §7.3 Remote access | Design Decision | "Fujitsu, and to a lesser extent the Post Office, had remote access to branch records and could 'insert, inject, edit or delete transaction data or data in branch accounts.'" |
| POHR-C4 | POHR | §7.4 Postmaster view | Stakeholder Need | "Sub-postmasters must be able to see everything that affects their accounts — including any centrally or remotely initiated entries — in clear, intelligible terms, in real time, with the data and tools to understand and challenge a discrepancy before any liability attaches." |
| POHR-C5 | POHR | §7.5 Dispute handling | Design Decision | "Apparent shortfalls must be presumed to require investigation, not presumed to be the postmaster's fault." |
| POHR-C6 | POHR | §7.6 Defect transparency | Risk Factor | "Known defects (a 'bugs, errors and defects' register) must be tracked, disclosed and accessible to affected parties. ... The catastrophic failure here was concealment of known defects." |
| POHR-C7 | POHR | §7.7 Migration | Data Requirement | "Historical balances and disputed items must be clearly flagged as to provenance and reliability, never silently presented as authoritative ... The replacement must not 'launder' disputed historical figures into apparently clean opening balances." |
| POHR-C8 | POHR | §7.8 Independent assurance | Risk Factor | "Horizon went live over the objections of IT specialists; NBIT was later judged 'set up to fail.' The replacement programme needs genuine independent technical assurance, realistic governance gates, honest status reporting, and a culture in which bad news travels upward." |
| POHR-C9 | POHR | §7.10 Exit and continuity | Procurement Constraint | "The decade-long difficulty of exiting Fujitsu shows the cost of lock-in. ... deliberate exit strategy, data portability and avoidance of single-supplier dependence." |
| POHR-C10 | POHR | §6.2 Target architecture | Design Decision | "The stated target architecture is a composable, event-driven, service-oriented architecture built from standards-based modular components, including migration from on-premise data centres to the cloud." |

### Unreferenced Documents

| Filename | Source Location | Reason |
|----------|-----------------|--------|
| — | — | All consulted source material contributed to this artifact. |

---

**Generated by**: ArcKit `/arckit:principles` command
**Generated on**: 2026-05-21
**ArcKit Version**: 5.0.2
**Project**: Post Office Horizon (Project 000 — Global)
**AI Model**: Claude Opus 4.7 (1M context)
