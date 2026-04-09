# GolDefi Architecture Decisions (ADRs)

## ADR-001: Compliance-First Purchase Gating
- **Status:** Accepted
- **Decision:** Users cannot execute purchase flows until KYC state is approved.
- **Rationale:** Regulatory compliance and risk containment.
- **Consequence:** Conversion may reduce, but legal and fraud risk are controlled.

## ADR-002: Event-Driven Payment-to-Mint Orchestration
- **Status:** Accepted
- **Decision:** Payment confirmations are processed asynchronously with idempotent handlers before mint request execution.
- **Rationale:** Improves resilience to callback retries/out-of-order events.
- **Consequence:** Requires robust correlation IDs and replay protections.

## ADR-003: Controlled Mint/Burn Permissions
- **Status:** Accepted
- **Decision:** Smart contract mint/burn functions are callable only by authorized service role(s).
- **Rationale:** Prevent unauthorized token supply changes.
- **Consequence:** Operational key management and rotation become critical controls.

## ADR-004: Audit Evidence Integrity via Hash-Reference Pattern
- **Status:** Accepted
- **Decision:** Audit evidence is stored off-chain with immutable hash/reference anchoring.
- **Rationale:** Balances storage practicality with non-repudiation.
- **Consequence:** Requires deterministic hashing and retention policy governance.

## ADR-005: Role-Segmented Portals with RBAC
- **Status:** Accepted
- **Decision:** Separate role experiences (user/distributor/auditor/admin) with strict permission boundaries.
- **Rationale:** Reduces blast radius and supports least privilege.
- **Consequence:** Increases UX and authorization testing scope.

## ADR-006: Single-Vault MVP, Multi-Vault Ready Design
- **Status:** Accepted
- **Decision:** Launch MVP with single vault while preserving abstraction for later multi-vault support.
- **Rationale:** Reduces launch complexity without architectural dead-end.
- **Consequence:** Vault interface contracts must remain stable.

## ADR-007: No Backlog Generation Without Foundation Consistency
- **Status:** Accepted
- **Decision:** Implementation planning requires completion and consistency of all foundation artifacts.
- **Rationale:** Reduces rework and planning churn.
- **Consequence:** Additional upfront documentation effort.

## Deferred Decisions
1. Final chain/network production target and fallback chain strategy.
2. Meta-transaction inclusion in MVP.
3. Jurisdiction-specific data residency architecture.
