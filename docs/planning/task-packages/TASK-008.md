# TASK-008

## title
Audit Workflow, Signed Submission, and Evidence Integrity

## business goal
Provide verifiable reserve-audit operations to support trust and compliance.

## linked epic
EPIC-04 — Distributor and Audit Operations

## scope included
- Audit request creation and status transitions
- Findings/document metadata capture
- Signature verification on submission
- Evidence hash/reference persistence

## scope excluded
- Automated third-party forensic audit analytics

## dependencies
- Evidence storage service
- Signature verification controls

## related docs
- `/docs/product/srs.md`
- `/docs/flows/process-flows.md`
- `/docs/api/openapi.yaml`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- Audit submissions require valid signature.
- Missing mandatory documents block completion.
- Audit records retain evidence references and status history.

## test expectations
- API tests for audit create/submit
- Negative tests for signature/doc failures
- Process tests for exception states

## risk level
Medium

## definition of done
- Audit lifecycle and evidence rules pass acceptance tests.
- Compliance and operations review complete.
