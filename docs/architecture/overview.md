# GolDefi Architecture Overview

## Architecture Goals
1. Enforce compliance and policy gates before monetary operations.
2. Keep token lifecycle (mint/burn) auditable and strongly traceable.
3. Support modular service boundaries for future multi-vault expansion.
4. Maintain high availability and operational observability.

## System Context
GolDefi provides multi-portal web access (user, distributor, auditor, admin) backed by domain services for identity, KYC, orders, payments, tokenization, redemption, and audits. External integrations include KYC provider(s), payment rails, blockchain RPC/indexing, and custodian operations.

## Logical Components
- **API Gateway:** entry point, auth checks, throttling, routing.
- **Identity & Access Service:** account lifecycle, OTP/MFA, sessions, RBAC.
- **KYC Orchestrator:** applicant lifecycle and provider callback processing.
- **Order Service:** quotes, order lifecycle, status model.
- **Payment Service:** method-specific confirmation and webhook processing.
- **Tokenization Service:** mint orchestration, on-chain writes, ledger sync.
- **Redemption Service:** request validation, lock/burn lifecycle, fulfillment handoff.
- **Audit Service:** audit workflows, document metadata, signatures.
- **Policy/Config Service:** country controls, limits, fee rules, admin configs.
- **Notification Service:** email/SMS lifecycle notifications.

## Data and Platform
- **Operational DB:** relational store for user/order/redemption/audit state.
- **Cache/Session Store:** low-latency session and short-lived workflow state.
- **Event Bus/Queue:** asynchronous processing for callbacks and retries.
- **Object/IPFS-compatible Storage:** audit/compliance evidence storage.
- **Blockchain Layer:** smart contract reads/writes + indexer for event ingestion.

## Cross-Cutting Controls
- Centralized authZ/authN policy enforcement.
- Idempotency keys for payment and mint operations.
- Structured logging, tracing, and alerting.
- Encryption at rest and in transit; key management via KMS/HSM.
- Replay protection for provider callbacks and signed requests.

## Deployment Topology (Target)
- Frontend apps behind CDN + WAF.
- Backend services in containerized orchestration environment.
- Isolated environments for dev/staging/prod.
- Observability stack with dashboards and on-call alerts.
- DR pattern: warm-standby secondary environment with RPO <= 15 min and RTO <= 60 min.

## External Dependency Contracts (MVP)
- **KYC Provider:** status callbacks signed, 99.5% monthly availability target.
- **Payment Providers:** callback signature + replay window enforcement; retry-safe events.
- **Blockchain Provider:** transaction broadcast + receipt retrieval with fallback RPC endpoint.
- **Custodian Ops:** redemption fulfillment acknowledgements and exception feedback loop.
- **Email/SMS:** OTP delivery and transactional notifications.

## NFR Baseline (MVP, testable)
| Area | Target |
|---|---|
| API latency (non-chain) | p95 < 500ms |
| Payment confirmed -> Minted | p95 < 3 minutes |
| Redemption initiation post-approval | p95 < 15 minutes |
| Platform availability | >= 99.9% monthly |
| Logging coverage for critical flows | 100% of payment/mint/burn/redemption transitions |
| Alerting latency for critical failures | < 5 minutes |

## MVP vs Later-Phase Architecture
### MVP
- Single-vault operational model.
- Primary payment providers only.
- Baseline reconciliation jobs and alerting.

### Later Phase
- Multi-vault orchestration/routing.
- Provider redundancy and failover automation.
- Deeper risk analytics pipeline.

## Dependencies Resolved from SRS
- Compliance-first purchase gate is mandatory.
- Cash distributor OTP model is retained.
- Redemption requires lock -> burn -> fulfillment sequence.
- Audit evidence integrity workflow is mandatory.
