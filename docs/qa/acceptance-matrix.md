# Acceptance Matrix

| Feature | MVP/Later | Acceptance Criteria | Evidence Required |
|---|---|---|---|
| Foundation artifact creation | MVP | All required artifact files exist and contain non-placeholder structured content. | Document review checklist |
| Artifact consistency check | MVP | Cross-references (scope, architecture, API, QA) show no unresolved contradictions. | Review sign-off + issue log |
| Open questions tracking | MVP | Unresolved assumptions are documented with owner and status. | `docs/product/open-questions.md` completeness |
| MVP vs later separation | MVP | Each artifact distinguishes MVP and post-MVP items. | Reviewer validation notes |
| API contract quality | MVP | OpenAPI includes paths, schemas, and error model examples. | Contract lint + peer review |
| Acceptance-to-test alignment | MVP | Each MVP feature has matching test strategy coverage. | Traceability table review |
| Readiness gate for backlog generation | MVP | Backlog generation is blocked when required artifacts/criteria are incomplete. | Gate checklist output |
| Automated consistency linting | Later | Semantic checks detect conflicts automatically. | Lint report |
| Integration connectors | Later | External tool sync works for configured systems. | Integration test report |

## Ambiguities Identified
- No target thresholds for “consistency quality” were defined.
- No explicit owner for final acceptance sign-off is defined.
