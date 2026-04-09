# GolDefi Acceptance Matrix

| Feature ID | Feature | MVP/Later | Acceptance Criteria | Validation Method |
|---|---|---|---|---|
| AC-01 | Registration + OTP | MVP | User can register, receive OTP, and verify account; blacklisted countries are blocked. | API + E2E |
| AC-02 | KYC gating | MVP | Unapproved KYC users cannot buy/redeem; approved users can proceed. | Integration + E2E |
| AC-03 | Wallet binding/update | MVP | Wallet bind requires valid signature; wallet update triggers verification workflow. | API + Security |
| AC-04 | Buy flow quote/order | MVP | User receives deterministic fee/total quote and can create order with selected payment method. | API + E2E |
| AC-05 | Payment-to-mint integrity | MVP | Mint occurs only after verified payment and policy checks; tx hash recorded. | Integration + Ledger verify |
| AC-06 | Cash distributor flow | MVP | Distributor must use orderId+email and OTP before payment registration; unauthorized access blocked. | E2E + Security |
| AC-07 | Redemption lifecycle | MVP | Redemption enforces validate -> lock -> burn -> fulfillment state sequence. | E2E + Contract |
| AC-08 | Audit workflow | MVP | Auditor can submit signed findings with document references and status updates. | API + Process test |
| AC-09 | Admin policy controls | MVP | Admin can configure country controls, thresholds, and fees with audit logs. | API + RBAC |
| AC-10 | Notifications | MVP | Users receive status notifications for key lifecycle events (registration, payment, mint, redemption). | E2E |
| AC-11 | Observability baseline | MVP | Critical failures emit alerts and traceable logs for payments/mints/redemptions. | Ops validation |
| AC-12 | Multi-vault routing | Later | System can allocate transactions across multiple vaults by policy. | Integration |
| AC-13 | Advanced risk scoring | Later | Risk engine flags anomalous activity and supports decisioning. | Model + Integration |

## Ambiguities Identified
- Ownership of final acceptance sign-off (Product vs Compliance vs Operations).
- Threshold values for non-functional alerting and error budgets.
