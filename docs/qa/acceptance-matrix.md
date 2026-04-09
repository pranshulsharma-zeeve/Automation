# GolDefi Acceptance Matrix

| Feature ID | Feature | MVP/Later | Acceptance Criteria | Validation Method |
|---|---|---|---|---|
| AC-01 | Registration + OTP | MVP | User can register, receive OTP, and verify account; blacklisted countries are blocked. | API + E2E |
| AC-02 | KYC gating | MVP | Unapproved KYC users cannot buy/redeem; approved users can proceed. | Integration + E2E |
| AC-03 | Wallet binding/update | MVP | Wallet bind requires valid signature; wallet update triggers verification workflow. | API + Security |
| AC-04 | Buy flow quote/order | MVP | User receives deterministic fee/total quote and can create order with selected payment method. | API + E2E |
| AC-05 | Payment-to-mint integrity | MVP | Mint occurs only after verified payment and policy checks; tx hash recorded. | Integration + Ledger verify |
| AC-06 | Cash distributor flow | MVP | Distributor must use orderId+email and OTP before payment registration; suspended distributor is blocked. | E2E + Security |
| AC-07 | Redemption lifecycle | MVP | Redemption enforces validate -> lock -> burn -> fulfillment state sequence with exception handling. | E2E + Contract |
| AC-08 | Audit workflow | MVP | Auditor can submit signed findings with document references; missing docs/signature invalid paths are blocked. | API + Process test |
| AC-09 | Admin policy controls | MVP | Admin can configure country controls, thresholds, and fees with audit logs and versioned publish events. | API + RBAC |
| AC-10 | Notifications | MVP | Users receive status notifications for registration, payment, mint, redemption, and delay exceptions. | E2E |
| AC-11 | Webhook authenticity | MVP | Payment and KYC webhooks require signature verification and reject invalid signatures. | Integration + Security |
| AC-12 | Idempotency behavior | MVP | Duplicate order/cash-payment/redemption submissions with same key are safely deduplicated. | API + Integration |
| AC-13 | State coverage in UI | MVP | Required state matrix is implemented for KYC/order/redemption/distributor/audit/admin flows. | UI review + E2E |
| AC-14 | Observability and SLOs | MVP | Critical flow alerts are emitted <5 min; payment->mint p95 <3 min under test load profile. | Ops test |
| AC-15 | Multi-vault routing | Later | System can allocate transactions across multiple vaults by policy. | Integration |
| AC-16 | Advanced risk scoring | Later | Risk engine flags anomalous activity and supports decisioning. | Model + Integration |

## Notes
- AC-11 to AC-14 close previously identified critical audit gaps around async behavior, reliability guardrails, and state completeness.
