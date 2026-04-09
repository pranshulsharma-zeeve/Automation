# GolDefi Process Flows

## PF-01 — Onboarding Governance Process (MVP)
1. Product/compliance define onboarding policy and country controls.
2. Admin configures blacklist/greylist and documentation rules.
3. User registrations flow into KYC queue.
4. KYC provider callbacks update eligibility status.
5. Exceptions are routed to compliance review.
6. Final approved state unlocks transactional capability.

### Exception States
- KYC callback timeout -> manual review queue after timeout threshold.
- KYC rejected -> remediation required state with re-submission guidance.

## PF-02 — Payment to Mint Process (MVP)
1. Order is created and assigned correlation ID.
2. Payment method-specific flow is initiated.
3. Provider callback/webhook is received.
4. Payment service validates signature, timestamp, and idempotency key.
5. Compliance + threshold checks run.
6. Tokenization service submits mint transaction.
7. On-chain confirmation is indexed.
8. Order state updates to minted; user notified.

### Exception States
- Duplicate callback -> idempotent ignore with audit log.
- Payment confirmed but mint failed -> retry queue with capped attempts, then manual ops case.
- No callback within SLA -> payment_pending_timeout state and user notice.

## PF-03 — Cash Distributor Assurance Process (MVP)
1. Distributor receives user-presented order details.
2. Dual-field lookup (order ID + email) validates request context.
3. OTP challenge protects order disclosure.
4. Distributor marks payment received and signs declaration.
5. System validates distributor privileges and order state.
6. Mint is triggered only on successful validation.

### Exception States
- Distributor account suspended -> request denied and logged.
- OTP mismatch/replay -> lookup blocked and lockout threshold applied.

## PF-04 — Redemption Fulfillment Process (MVP)
1. User submits redemption request.
2. System verifies eligibility, limits, and balance.
3. Tokens are locked for redemption.
4. Burn transaction is submitted and confirmed.
5. Fulfillment request is sent to custodian/vault operations.
6. Shipping status updates are captured and surfaced.
7. Request closes at successful delivery or exception resolution.

### Exception States
- Burn failure -> locked state rollback process and incident creation.
- Custodian SLA breach -> escalation to operations owner with user notification.

## PF-05 — Audit and Evidence Process (MVP)
1. Audit request is created with planned scope.
2. Inspector performs physical verification.
3. Findings and documents are uploaded.
4. Evidence metadata and hash references are registered.
5. Inspector digitally signs submission.
6. Audit status transitions to completed/exception.
7. Exception cases trigger admin/compliance follow-up.

### Exception States
- Missing mandatory document -> submission blocked.
- Signature verification failed -> submission rejected with remediation guidance.

## PF-06 — Configuration Change Process (MVP)
1. Admin drafts policy/config change.
2. Impact is reviewed by compliance/ops.
3. Approved change is published with timestamp/version.
4. Affected workflows enforce new policy immediately or at scheduled time.
5. All changes are audit-logged.

### Exception States
- Unauthorized publisher attempt -> denied via RBAC and security alert.
- Invalid threshold configuration -> validation error and rollback to previous version.

## SLA Ownership (MVP)
- Payment callback timeout handling: Payments Ops
- Mint retry queue and incident handling: Blockchain Ops
- Redemption fulfillment delays: Custodian Operations + Customer Support
- KYC exception handling: Compliance Team
