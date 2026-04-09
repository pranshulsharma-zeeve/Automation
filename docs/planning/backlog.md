# GolDefi Delivery Backlog (MVP)

## Prioritization Model
- **Now (P0):** Must complete for MVP launch.
- **Next (P1):** Near-term post-MVP hardening.
- **Later (P2):** Deferred strategic enhancements.

## Backlog Items

| Backlog ID | Title | Epic | Priority | Task Package | Notes |
|---|---|---|---|---|---|
| BL-001 | Registration, OTP, and Session Security | EPIC-01 | P0 | TASK-001 | Foundation access layer |
| BL-002 | KYC Orchestration and Eligibility Gate | EPIC-01 | P0 | TASK-002 | Compliance gate before monetary ops |
| BL-003 | Wallet Binding and Verified Update Flow | EPIC-01 | P0 | TASK-003 | Signature-based wallet ownership |
| BL-004 | Quote/Order Lifecycle and Fee Calculation | EPIC-02 | P0 | TASK-004 | Entry point for purchases |
| BL-005 | Payment Callbacks, Idempotency, and Mint Trigger | EPIC-02 | P0 | TASK-005 | Core monetary integrity control |
| BL-006 | Redemption Lock/Burn/Fulfillment Pipeline | EPIC-03 | P0 | TASK-006 | Physical gold redemption path |
| BL-007 | Distributor Cash Workflow + OTP Assurance | EPIC-04 | P0 | TASK-007 | Region-configured assisted payments |
| BL-008 | Auditor Workflow and Evidence Integrity | EPIC-04 | P0 | TASK-008 | Trust and verification operations |
| BL-009 | Admin Policy Console and Config Versioning | EPIC-05 | P0 | TASK-009 | Country/fee/threshold governance |
| BL-010 | Observability, Alerts, and Ops Readiness | EPIC-05 | P0 | TASK-010 | SLO/incident readiness baseline |
| BL-011 | NFR Performance and Reliability Hardening | EPIC-05 | P1 | TASK-011 | Post-MVP resilience expansion |
| BL-012 | Multi-vault Routing Foundation | EPIC-03 | P2 | TASK-012 | Deferred by scope |

## Sequencing Guidance
1. Complete EPIC-01 tasks first to establish secure eligibility and custody controls.
2. Execute EPIC-02 next for monetization and token issuance integrity.
3. Implement EPIC-03/04 for redemption and operations readiness.
4. Complete EPIC-05 for governance and release operations.

## Release Gate
Backlog items are implementation-ready only when corresponding task package DoD and acceptance criteria are satisfied.
