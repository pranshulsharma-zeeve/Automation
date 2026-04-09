# AI Delivery Label Policy

This policy defines how GitHub labels are used to automate and track documentation-first delivery.

## Lifecycle Labels (AI Workflow)

| Label | Purpose | Typical Trigger | Exit Condition |
|---|---|---|---|
| `ai:intake` | Issue has entered AI-driven workflow. | New issue created via template. | Replaced/paired with next-state labels. |
| `ai:needs-clarification` | Issue needs focused clarification before progress. | Missing or ambiguous requirements. | Clarification answered and issue updated. |
| `ai:planning` | Planning artifact creation/refinement in progress. | Planning issue active. | Planning deliverable approved. |
| `ai:foundation-ready` | Prerequisite foundation artifacts exist for this issue. | Artifact set validated. | Promoted to backlog approval state. |
| `ai:approved-for-backlog` | Human-approved for backlog inclusion. | Product/compliance approval. | Task packaging complete. |
| `ai:task-packaged` | Task package exists and is linked. | `/docs/planning/task-packages/TASK-xxx.md` created. | Ready for implementation. |
| `ai:ready-for-implementation` | Work can start without missing prerequisites. | Dependencies and acceptance criteria confirmed. | Engineering starts work (`ai:implementing`). |
| `ai:implementing` | Active implementation in progress. | Branch/work begins. | Implementation complete and self-validated. |
| `ai:self-validating` | Agent is running required checks/tests. | Validation phase started. | Validation outputs captured. |
| `ai:ready-for-verification` | Ready for QA/human verification. | Self-validation passes. | Verification completed. |
| `ai:verified` | QA/reviewer verification passed. | Acceptance criteria validated. | PR prepared to merge. |
| `ai:ready-to-merge` | Merge gates satisfied, awaiting merge action. | Evidence summary complete + approvals. | Merged. |
| `ai:merged` | Work merged into target branch. | Merge complete. | Terminal state. |
| `ai:blocked` | Progress blocked by unresolved dependency/risk. | Hard blocker appears. | Blocker resolved. |
| `ai:needs-human-decision` | Requires business/legal/owner decision. | Non-derivable decision needed. | Decision recorded in issue/docs. |
| `ai:revision-requested` | Reviewer requested changes. | Review feedback issued. | Revisions submitted and accepted. |

## Risk Labels

| Label | Usage |
|---|---|
| `risk:low` | Isolated, reversible, low user/operational impact. |
| `risk:medium` | Multi-file behavior changes or moderate blast radius. |
| `risk:high` | Auth, billing, permissions, migrations, security-sensitive, or high-integrity workflows. |

Rules:
- Exactly one `risk:*` label should be present on active implementation issues.
- `risk:high` issues require stricter review and no auto-merge.

## Type Labels

| Label | Usage |
|---|---|
| `type:feature` | New functional capability. |
| `type:bug` | Defect fix. |
| `type:api` | API contract/interface work. |
| `type:design` | UX/UI/design-system work. |
| `type:architecture` | Structural/infra/ADR-level changes. |

Rules:
- At least one `type:*` label is required for planning and implementation issues.
- Multi-domain issues may carry multiple `type:*` labels.

## Automation Guidelines

1. New issues start with `ai:intake`.
2. Planning issues progress via `ai:planning` -> `ai:foundation-ready` -> `ai:approved-for-backlog`.
3. Implementation issues progress via `ai:task-packaged` -> `ai:ready-for-implementation` -> `ai:implementing` -> `ai:self-validating` -> `ai:ready-for-verification` -> `ai:verified` -> `ai:ready-to-merge` -> `ai:merged`.
4. Apply `ai:blocked` and optionally `ai:needs-human-decision` immediately when work cannot proceed.
5. Use `ai:revision-requested` whenever reviewer feedback requires rework.

## Recommended Label Combinations

- **Planning item:** `ai:intake`, `ai:planning`, one `type:*`, one `risk:*`
- **Backlog-approved task:** `ai:task-packaged`, `ai:ready-for-implementation`, one `type:*`, one `risk:*`
- **Clarification:** `ai:needs-clarification`, `ai:needs-human-decision`, relevant `type:*`, `risk:*`
- **Risk escalation:** `ai:blocked`, `ai:needs-human-decision`, `risk:high`, relevant `type:*`

## Governance Notes

- Labels do not replace required documentation gates in `AGENTS.md`.
- Label state should reflect reality; stale labels must be corrected during triage.
- Merge is allowed only when issue and PR states align with validation evidence.
