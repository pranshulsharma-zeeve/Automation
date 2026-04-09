# GolDefi Wireframes (Textual)

## Screen Inventory

### MVP Screens
1. Public Landing + Signup
2. Email OTP Verification
3. Login + MFA
4. User Dashboard
5. KYC Status + KYC Start
6. Buy GDI (multi-method payment)
7. Orders & Transaction History
8. Redemption Request + Tracking
9. Profile & Wallet Management
10. Distributor Search/OTP/Payment Registration
11. Auditor Audit Submission
12. Admin Policy & Configuration Console

### Later-Phase Screens
1. Multi-vault routing configuration
2. Risk analytics dashboard
3. Provider SLA/health cockpit

---

## Wireframe WF-01 — User Dashboard
```text
+--------------------------------------------------------------------------------+
| GolDefi | Dashboard | Buy | Redeem | Orders | Profile | Notifications          |
+------------------------+------------------------------------------+-------------+
| Portfolio Snapshot     | Holdings: 12,540 GDI                    | KYC: Approved|
| Equivalent Gold Weight | Mint/Burn Activity Feed                 | Wallet: Linked|
| Current Status Cards   | Recent Orders (Pending/Minted/Redeemed) | Alerts       |
+------------------------+------------------------------------------+-------------+
```

## Wireframe WF-02 — Buy GDI
```text
+--------------------------------------------------------------------------------+
| Buy GDI Tokens                                                                 |
+--------------------------------------------------------------------------------+
| Token Amount [________]  Gold Eq. [auto]  Fee [auto]  Total [auto]            |
| Payment Method: ( ) Crypto  ( ) Card  ( ) Bank  ( ) Cash                      |
| If Cash selected: distributor guidance + order handling steps                  |
| [Get Quote]                                                     [Confirm Order]|
+--------------------------------------------------------------------------------+
```

## Wireframe WF-03 — Redemption
```text
+--------------------------------------------------------------------------------+
| Redeem GDI                                                                      |
+--------------------------------------------------------------------------------+
| Redeem Amount [________]  Eligible? [auto-check]  Min Threshold [value]        |
| Delivery Address [stored/verified] [Edit -> requires verification if changed]  |
| Steps: Validate -> Lock -> Burn -> Fulfillment                                 |
| [Submit Request]                                                  [Cancel]      |
+--------------------------------------------------------------------------------+
```

## Wireframe WF-04 — Distributor Cash Registration
```text
+--------------------------------------------------------------------------------+
| Distributor Console                                                             |
+--------------------------------------------------------------------------------+
| Order ID [________]   User Email [__________________]  [Search]                |
| OTP [______] [Validate OTP]                                                     |
| Cash Received [amount]   Signature [Capture]                                    |
| Status: Awaiting OTP / Verified / Rejected                                      |
| [Register Payment]                                               [Reset]        |
+--------------------------------------------------------------------------------+
```

## Wireframe WF-05 — Auditor Submission
```text
+--------------------------------------------------------------------------------+
| Audit Request #A-204                                                            |
+--------------------------------------------------------------------------------+
| Vault Name [____]  Audit Date [____]  Auditor [auto]                            |
| Findings [text area]                                                            |
| Documents [Upload]  Metadata [auto/manual]                                      |
| Status: Draft / Pending / Audited / Exception                                   |
| [Sign & Submit]                                                  [Save Draft]   |
+--------------------------------------------------------------------------------+
```

## Wireframe WF-06 — Admin Policy Console
```text
+--------------------------------------------------------------------------------+
| Admin > Compliance & Policy                                                     |
+--------------------------------------------------------------------------------+
| Country Controls: [Blacklist] [Greylist + extra docs]                           |
| Fee Rules: [Tier Config]                                                        |
| Thresholds: [Purchase Min/Max] [Redemption Min/Max]                             |
| Distributor Management: [Invite] [Deactivate]                                   |
| [Save Draft]                                                   [Publish Policy] |
+--------------------------------------------------------------------------------+
```

## Ambiguities Identified
- Final mobile responsiveness breakpoints.
- Which screens require mandatory MFA re-authentication.
