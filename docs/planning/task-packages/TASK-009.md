# TASK-009

## title
Admin Policy Console and Versioned Config Publication

## business goal
Allow controlled updates to country policies, thresholds, and fees with auditability.

## linked epic
EPIC-05 — Admin Policy, Observability, and Readiness

## scope included
- Country list management (blacklist/greylist)
- Fee and threshold rule configuration
- Draft -> publish workflow with version tracking
- RBAC and audit logs for policy changes

## scope excluded
- Automated policy optimization recommendations

## dependencies
- Admin RBAC framework
- Policy storage and versioning model

## related docs
- `/docs/design/wireframes.md`
- `/docs/flows/process-flows.md`
- `/docs/api/openapi.yaml`

## acceptance criteria
- Only authorized admin roles can publish policy changes.
- Invalid configs are rejected with clear errors.
- Policy changes are versioned and traceable.

## test expectations
- RBAC tests for admin operations
- API tests for config validation/publish
- UI tests for draft/validation/publish states

## risk level
Medium

## definition of done
- Policy workflow operational with audit logs.
- Invalid and unauthorized scenarios covered by tests.
