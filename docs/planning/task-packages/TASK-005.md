# TASK-005

## title
Payment Callback Validation, Idempotency, and Mint Trigger

## business goal
Protect monetary integrity so minting occurs exactly once after verified payment.

## linked epic
EPIC-02 — Purchase, Payments, and Token Minting

## scope included
- Webhook endpoints for payment callbacks
- Signature verification and replay protection
- Idempotency key enforcement
- Mint trigger orchestration after payment confirmation

## scope excluded
- Advanced dispute resolution automation

## dependencies
- Payment provider callback payload/signature specs
- Tokenization service and blockchain connectivity

## related docs
- `/docs/api/openapi.yaml`
- `/docs/flows/process-flows.md`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- Invalid callback signatures are rejected.
- Duplicate callbacks do not double-process orders.
- Mint is triggered only after confirmed and compliant payment state.
- Tx hash is persisted to order record.

## test expectations
- Integration tests for callbacks and idempotency
- Ledger consistency tests for payment->mint mapping
- Negative tests for replay/duplicate events

## risk level
High

## definition of done
- Callback security and idempotency verified.
- Mint trigger path is auditable and deterministic.
