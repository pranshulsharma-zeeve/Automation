# GolDefi Product Scope

## In Scope (MVP)

### User & Compliance
- User registration and email OTP verification.
- Login/session management and MFA capability.
- KYC integration and status-driven access controls.
- Wallet binding and verified wallet update flow.

### Purchase & Tokenization
- Order creation with fee and total payable visibility.
- Payment method handling (crypto/card/bank/cash per configured region).
- Payment confirmation state handling and mint trigger.
- Transaction status and confirmation notifications.

### Distributor Operations
- Distributor account lifecycle (invite, activation, access).
- Cash order lookup by order ID + user email.
- OTP-protected order disclosure and payment registration.
- Signed payment confirmation workflow.

### Redemption
- Redemption request capture and policy checks.
- Token lock and burn orchestration.
- Custodian fulfillment handoff and status progression.

### Audit & Governance
- Audit request lifecycle and report uploads.
- Inspector comments, status transitions, digital signatures.
- Evidence metadata and immutable-reference handling.
- Admin policy management (countries, fee rules, thresholds, config).

## Out of Scope (MVP)
- Exchange/secondary trading features.
- Automated distributor settlement reconciliation.
- Multi-vault production routing.
- Mobile-native apps.
- Automated hedging/treasury systems.

## Later-Phase Scope
- Multi-vault support and route optimization.
- Deeper observability and analytics automation.
- Risk scoring and anomaly detection enhancements.
- Expanded payment rails and regional compliance packs.

## Constraints
- High dependency on third-party provider reliability (KYC/payment).
- Regulatory changes can alter onboarding and redemption policies.
- Blockchain congestion can impact write confirmation latency.

## Ambiguities Identified
- Minimum redemption thresholds by geography.
- Final storage and retention policy by jurisdiction.
- Meta-transaction support scope for MVP.
