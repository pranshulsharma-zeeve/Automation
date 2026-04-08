# Architecture Decisions (ADRs)

## ADR-001: Documentation-First Gating
- **Decision:** Backlog/task generation is blocked until Foundation Pack artifacts are complete and consistent.
- **Rationale:** Prevents premature implementation and rework.
- **Status:** Accepted.

## ADR-002: Markdown + YAML as Source of Truth
- **Decision:** Use Markdown for narrative artifacts and OpenAPI YAML for contract definitions.
- **Rationale:** Human-readable, version-control friendly, tool-compatible.
- **Status:** Accepted.

## ADR-003: Task Package Requirement
- **Decision:** Every implementation task must map to `/docs/planning/task-packages/<task-id>.md`.
- **Rationale:** Ensures traceability and execution context.
- **Status:** Accepted.

## ADR-004: Explicit Open Questions Registry
- **Decision:** Unresolved assumptions are centrally tracked in `/docs/product/open-questions.md`.
- **Rationale:** Makes ambiguity visible and actionable.
- **Status:** Accepted.

## ADR-005: Risk-Based Merge Controls
- **Decision:** High-risk domains (auth, billing, permissions, migrations, security) require stricter validation and no auto-merge.
- **Rationale:** Reduce probability/severity of production incidents.
- **Status:** Accepted.

## Deferred Decisions
- Identity provider and auth protocol.
- Multi-tenant vs single-tenant data partitioning.
- Event-driven vs request-driven integration model.
