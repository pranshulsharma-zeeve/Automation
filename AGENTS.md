# AGENTS.md

This document defines the mandatory operating model for Codex agents working in this repository.

## Mission
Deliver production-ready product increments through a documentation-first workflow, with explicit traceability from requirements to implementation and verification.

---

## Required Operating Model (Non-Negotiable)

1. **Never generate implementation issues directly from the raw SRS.**
2. **Before backlog generation, first create and refine these artifacts (in order, iterating as needed):**
   1. Product brief (`/docs/product/brief.md`)
   2. Priorities (`/docs/product/priorities.md`)
   3. Scope (`/docs/product/scope.md`)
   4. Architecture (`/docs/architecture/overview.md`, `/docs/architecture/decisions.md`)
   5. User flows (`/docs/flows/user-flows.md`)
   6. Process flows (`/docs/flows/process-flows.md`)
   7. Wireframes (`/docs/design/wireframes.md`)
   8. Branding (`/docs/design/branding.md`)
   9. Design system (`/docs/design/design-system.md`)
   10. API contracts (`/docs/api/openapi.yaml`)
   11. Acceptance matrix (`/docs/qa/acceptance-matrix.md`)
   12. Test strategy (`/docs/qa/test-strategy.md`)
3. **Only after the above artifacts are complete and internally consistent may backlog items be generated.**
4. **Every implementation task must be grounded in a task package under `/docs/planning/task-packages`.**
5. **Every PR must include an evidence summary with:**
   - Requirements covered
   - Tests run
   - Files changed and why
   - Unresolved items
   - Risk level
   - Confidence
6. **Prefer targeted clarification questions over assumptions when product detail is missing.**
7. **Always update `/.ai/sessions/<task-id>/status.md` during active work.**
8. **Always restate the task and the execution plan before coding.**
9. **Always run project validation commands before marking work complete.**
10. **Never auto-merge high-risk work (auth, billing, permissions, migrations, security-sensitive changes).**

---

## Repo Navigation
- Product requirements and framing: `/docs/product`
- System structure and decisions: `/docs/architecture`
- UX and operational behavior: `/docs/flows`
- UI and design language: `/docs/design`
- API contracts: `/docs/api/openapi.yaml`
- Quality definitions: `/docs/qa`
- Planning artifacts and task packages: `/docs/planning`
- Session logs and active task tracking: `/.ai/sessions`

When starting work, identify which of the above areas are impacted and update docs first when required by the operating model.

---

## Branching Rules
- Use short-lived feature branches.
- One branch should focus on one task package or tightly related set of changes.
- Keep commits logically grouped and message each commit clearly.
- Rebase or merge mainline frequently to reduce drift.
- Do not merge if evidence summary or validation output is incomplete.

---

## Coding Standards
- Match existing project conventions and naming.
- Prefer small, reviewable changes with clear intent.
- Avoid unrelated refactors in implementation PRs.
- Preserve backwards compatibility unless scope explicitly allows breaking changes.
- Add or update tests proportionate to risk and impact.
- For ambiguous requirements, pause and ask focused clarification questions.

---

## Validation Steps
Before marking any task complete, run validation commands appropriate to the tech stack (for example: lint, type-check, unit tests, integration tests, contract checks, build).

Minimum requirements:
1. Run all repository-standard validation commands.
2. Capture command outputs for PR evidence summary.
3. If a validation command cannot run, document why, impact, and mitigation.

---

## Documentation Rules
- Docs are the source of truth for planning and scope alignment.
- Keep `/docs/product`, `/docs/architecture`, `/docs/flows`, `/docs/design`, `/docs/api`, and `/docs/qa` internally consistent before generating backlog items.
- Every implementation change must trace to:
  1. An approved artifact set,
  2. A task package in `/docs/planning/task-packages`, and
  3. Acceptance and test criteria.
- Update docs in the same PR when implementation alters behavior, interfaces, or constraints.

---

## Session Logging Rules
For every active task:
1. Create/update `/.ai/sessions/<task-id>/status.md`.
2. Log: objective, current plan, progress, blockers, validations run, and next steps.
3. Update status at meaningful checkpoints (start, major change, validation, handoff).
4. Ensure session log matches final PR evidence summary.

---

## Risk Classification Rules
Classify each task and PR as:
- **Low:** isolated, reversible, minimal user impact.
- **Medium:** multi-file or behavior-affecting changes with bounded blast radius.
- **High:** auth, billing, permissions, migrations, security-sensitive logic, data integrity, or irreversible changes.

Rules:
- High-risk work requires stricter review, explicit rollback notes, and no auto-merge.
- Increase test depth with risk level.
- Explicitly document unresolved risks.

---

## Merge Gate Rules
A PR is merge-ready only when all conditions are met:
1. Task is grounded in `/docs/planning/task-packages/<task-id>.md` (or equivalent package file).
2. Required upstream artifacts are complete and consistent.
3. Validation commands have been run and results captured.
4. Evidence summary includes:
   - Requirements covered
   - Tests run
   - Files changed and why
   - Unresolved items
   - Risk level
   - Confidence
5. For high-risk changes, auto-merge is disabled and reviewer sign-off is explicit.

If any gate fails, do not mark work complete.
