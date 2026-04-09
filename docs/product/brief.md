# GolDefi Product Brief

## Product Name
GolDefi — Blockchain-based Digital Gold Tokenization Platform

## Problem Statement
Investors want exposure to physical gold with lower operational friction, fractional ownership, and transparent reserve integrity. Traditional flows are slow, opaque, and operationally heavy. GolDefi solves this by issuing gold-backed tokens with compliance gates and redeemability.

## Product Vision
Enable compliant users to purchase, hold, and redeem fractional gold through digital tokens where lifecycle events (mint, transfer, burn, redemption) are auditable and policy-controlled.

## Target Users
1. **Retail/Professional Investors (Users):** buy and hold GDI tokens.
2. **Distributors:** register verified cash payments for assisted purchase.
3. **Auditors/Inspectors:** verify physical reserves and publish evidence.
4. **Operations/Admin:** govern policies, limits, fees, and exceptions.
5. **Compliance Team:** enforce KYC/AML and sanctions controls.

## Value Proposition
- Fractional gold ownership with digital settlement convenience.
- Compliance-first operations with role-based control.
- Physical reserve trust via audit workflows and evidence integrity.
- Physical redemption path for token holders.

## Business Outcomes
- Improve onboarding and conversion for compliant users.
- Maintain strong reserve confidence through auditable operations.
- Reduce payment-to-mint latency and operational exception handling time.
- Create a scalable platform for multi-vault and additional payment rails in later phases.

## MVP Goals
- Registration, email verification, login, and profile management.
- KYC gating for purchase eligibility.
- Wallet binding and update verification.
- Purchase flow with supported payment methods.
- Mint orchestration after validated payment.
- Redemption workflow with lock -> burn -> fulfillment handoff.
- Audit workflow with document metadata and immutable reference handling.
- Admin policy controls (country lists, fees, thresholds, distributor management).

## Later-Phase Goals
- Multi-vault routing and reserve optimization.
- Advanced analytics and risk scoring.
- Automated treasury/reconciliation and expanded integration coverage.
- Mobile-native applications.

## Non-Goals (Current Foundation Pack)
- Secondary market exchange functionality.
- On-platform distributor financial settlement automation.
- Full hedging/treasury automation.
- Global jurisdiction-specific legal automation.

## Success Metrics (Initial Targets)
- KYC completion >= 75% of initiated applicants.
- Purchase conversion >= 60% of approved users.
- Payment confirmation to mint p95 < 3 minutes.
- Redemption initiation p95 < 15 minutes after approval checks.
- Monthly uptime >= 99.9%.

## Ambiguities Identified
- Final jurisdiction and compliance baseline per market.
- Exact MVP payment-provider stack (card/bank vendors).
- Whether meta-transactions are MVP or later-phase.
- Operational ownership boundaries for exception approvals.
