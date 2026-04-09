# TASK-007

## title
Distributor Cash Payment Workflow with OTP Assurance

## business goal
Enable secure assisted cash purchasing without exposing order data or enabling fraud.

## linked epic
EPIC-04 — Distributor and Audit Operations

## scope included
- Distributor order lookup by order ID + user email
- OTP challenge flow for disclosure
- Cash payment registration with digital signature
- Distributor suspension/lockout enforcement

## scope excluded
- Distributor settlement financial reconciliation automation

## dependencies
- Distributor account lifecycle management
- OTP notification infrastructure

## related docs
- `/docs/flows/user-flows.md`
- `/docs/flows/process-flows.md`
- `/docs/api/openapi.yaml`

## acceptance criteria
- Order lookup requires dual-field matching and valid OTP.
- Suspended distributors cannot register payments.
- Cash payment registration is auditable and triggers mint path.

## test expectations
- E2E tests for OTP success/failure states
- Security tests for OTP replay and lockout
- API tests for distributor role authorization

## risk level
High

## definition of done
- Fraud controls and OTP protections verified.
- Role-based restrictions tested and documented.
