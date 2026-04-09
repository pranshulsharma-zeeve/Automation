# GolDefi User Flows

## Flow UF-01 — User Registration and KYC (MVP)
1. User opens GolDefi site and selects **Sign Up**.
2. User enters DOB and country.
3. System checks country policy (blacklist/greylist/allowed).
4. If blacklisted, registration is blocked with clear message.
5. User enters professional activity, sector, revenue, declaration.
6. User enters identity credentials (name, email, phone, password).
7. System sends email OTP; user verifies OTP.
8. User signs in successfully.
9. User connects wallet.
10. User starts KYC flow; provider captures required docs.
11. System receives KYC status update.
12. If approved, buy/redeem capabilities unlock; otherwise pending/retry path shown.

## Flow UF-02 — Buy GDI via Crypto/Card/Bank (MVP)
1. Approved user navigates to **Buy GDI**.
2. User enters token quantity and chooses payment method.
3. System calculates fees and shows total payable.
4. User confirms order.
5. System initiates payment flow for selected method.
6. Provider confirmation is received/validated.
7. System runs compliance and threshold checks.
8. Tokenization service mints GDI to bound wallet.
9. User receives success notification with transaction reference.

## Flow UF-03 — Buy GDI via Cash + Distributor (MVP, region-configured)
1. User places cash order and receives order ID.
2. User visits distributor and provides order ID + email.
3. Distributor searches order using both fields.
4. OTP is sent to user email.
5. User shares OTP with distributor.
6. Distributor validates OTP and records cash received.
7. Distributor signs payment confirmation.
8. System validates submission and mints tokens.
9. User receives payment confirmation and mint status.

## Flow UF-04 — Wallet Address Update (MVP)
1. User navigates to profile settings.
2. User submits new wallet address.
3. System issues signing challenge.
4. User signs challenge from new wallet.
5. System verifies signature and risk flags.
6. If required, re-verification/KYC trigger is initiated.
7. Wallet binding is updated and user notified.

## Flow UF-05 — Redemption Request (MVP)
1. User selects **Redeem** and enters redemption amount.
2. System checks balance, thresholds, and policy constraints.
3. User confirms shipping/profile details.
4. System locks token amount for redemption.
5. Burn request is executed on-chain.
6. Fulfillment order is sent to custodian.
7. User tracks status until completion.

## Flow UF-06 — Auditor Submission (MVP)
1. Auditor opens assigned audit request.
2. Auditor performs physical check and fills findings.
3. Auditor uploads documents and metadata.
4. Auditor digitally signs report submission.
5. System stores records and evidence references.
6. Audit status transitions to completed/exception.

## Later-Phase User Flows
- Multi-vault selection/optimization during redemption.
- Assisted meta-transaction purchases for users without native gas.
- Enhanced self-service dispute resolution.

## Ambiguities Identified
- Whether MFA is mandatory for end users at launch.
- Jurisdiction-specific onboarding differences not fully finalized.
