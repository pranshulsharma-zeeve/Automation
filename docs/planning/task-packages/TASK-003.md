# TASK-003

## title
Wallet Binding and Verified Wallet Update

## business goal
Ensure token custody operations map only to provably controlled wallets.

## linked epic
EPIC-01 — Identity, Compliance, and Access Control

## scope included
- Wallet connect and binding workflow
- Challenge-signature verification
- Secure wallet update path with risk checks

## scope excluded
- Support for non-EVM wallet types

## dependencies
- Wallet signature verification service
- User profile management

## related docs
- `/docs/product/srs.md`
- `/docs/flows/user-flows.md`
- `/docs/api/openapi.yaml`

## acceptance criteria
- Wallet cannot be bound without valid signature.
- Wallet update requires challenge signing.
- Failed verification attempts are logged and surfaced.

## test expectations
- API tests for bind/update endpoints
- Security tests for signature replay and invalid signatures
- E2E profile update tests

## risk level
High

## definition of done
- Signature controls are validated in test and logs.
- Wallet update risk checks documented and active.
