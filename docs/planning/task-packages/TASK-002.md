# TASK-002

## title
KYC Orchestration and Transaction Eligibility Gate

## business goal
Ensure only KYC-approved users can perform purchase and redemption operations.

## linked epic
EPIC-01 — Identity, Compliance, and Access Control

## scope included
- KYC session initiation and status retrieval
- Provider callback processing for KYC state updates
- Eligibility checks before order creation/redemption submission

## scope excluded
- Jurisdiction-specific enhanced due diligence custom engines

## dependencies
- KYC provider callback contract
- Compliance policy definitions

## related docs
- `/docs/product/srs.md`
- `/docs/flows/process-flows.md`
- `/docs/api/openapi.yaml`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- Unapproved users cannot purchase or redeem.
- Approved users can proceed without manual bypass.
- KYC callback events are authenticated and logged.

## test expectations
- Integration tests for KYC callback handling
- E2E test for blocked vs approved user paths
- Negative tests for forged callback signatures

## risk level
High

## definition of done
- Eligibility gate fully enforced across write operations.
- Callback signature validation implemented and tested.
- Compliance sign-off recorded.
