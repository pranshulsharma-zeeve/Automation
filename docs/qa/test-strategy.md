# GolDefi Test Strategy

## Objectives
- Verify that MVP acceptance criteria are fully covered and repeatable.
- Protect high-risk flows (auth, payment, mint/burn, redemption, policy controls).
- Ensure traceability from requirements -> acceptance criteria -> test evidence.

## Test Scope
### In Scope (MVP)
- Auth/identity, KYC gates, wallet verification.
- Order/payment/mint lifecycle.
- Cash distributor OTP-protected workflow.
- Redemption lifecycle and state transitions.
- Audit submission and evidence metadata lifecycle.
- Admin config and RBAC enforcement.

### Later Phase
- Multi-vault routing behavior.
- Advanced risk-scoring pipeline.

## Test Levels
1. **Unit Tests**
   - Quote calculation, policy checks, state transition guards, idempotency handlers.
2. **Integration Tests**
   - KYC provider callbacks, payment webhooks, blockchain write orchestration, notification dispatch.
3. **Contract Tests**
   - OpenAPI request/response schema conformance; backward-compatibility checks.
4. **End-to-End Tests**
   - Full user journeys across portals and payment methods.
5. **Security Tests**
   - RBAC, OTP misuse prevention, signature validation, replay protections.
6. **Operational Tests**
   - Alerting, logging completeness, failure recovery drills.

## Acceptance Matrix Traceability
| Acceptance ID | Primary Test Suite | Environment |
|---|---|---|
| AC-01, AC-02, AC-03 | Auth + KYC + Wallet E2E | Staging |
| AC-04, AC-05 | Order/Payment/Tokenization Integration | Staging + pre-prod |
| AC-06 | Distributor Flow Security E2E | Staging |
| AC-07 | Redemption E2E + contract state checks | Staging + pre-prod |
| AC-08 | Audit Workflow API + UI tests | Staging |
| AC-09 | Admin RBAC + Config API tests | Staging |
| AC-10 | Notification integration tests | Staging |
| AC-11 | Observability smoke + chaos drills (bounded) | Pre-prod |

## Test Data Strategy
- Use synthetic user identities and masked test profiles.
- Maintain deterministic payment fixtures for each method.
- Use controlled blockchain test environment with replayable state.

## Entry Criteria
- Foundation Pack artifacts approved for MVP scope.
- API contracts versioned and available.
- Test environments configured with mock/stub providers where needed.

## Exit Criteria
- All MVP acceptance criteria passing.
- Zero unresolved Sev-1 and Sev-2 defects.
- No critical reconciliation drift in test runs.
- Required evidence captured in PR summary.

## Risks and Mitigation
- **Provider instability:** use stubs, retries, and replay tests.
- **Chain latency variance:** use timeout envelopes and delayed confirmation scenarios.
- **Compliance edge cases:** include policy-matrix test combinations.

## Ambiguities Identified
- Final CI stack and tooling ownership.
- Frequency and ownership for regression suites.
