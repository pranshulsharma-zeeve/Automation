# TASK-004

## title
Quote and Order Lifecycle with Fee Transparency

## business goal
Enable users to create purchase orders with transparent fees and deterministic totals.

## linked epic
EPIC-02 — Purchase, Payments, and Token Minting

## scope included
- Quote generation by payment method
- Fee and total payable calculation
- Order creation and state transitions to payment pending

## scope excluded
- Promotional pricing/discount engine

## dependencies
- Fee and threshold policy rules
- Product pricing source integration

## related docs
- `/docs/product/srs.md`
- `/docs/design/wireframes.md`
- `/docs/api/openapi.yaml`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- Users receive quote with amount, fee, and total.
- Order states transition correctly to payment pending.
- Policy limits are enforced before order acceptance.

## test expectations
- Unit tests for fee calculations
- API contract tests for quote/order endpoints
- E2E tests for buy flow pre-payment states

## risk level
Medium

## definition of done
- Fee logic and order states validated in staging.
- API schema and UI copy aligned to totals shown.
