# AGENTS.md

This file defines the mandatory operating model for Codex agents working in this repository.

## Mission
Deliver production-ready increments through a **documentation-first workflow** with explicit traceability from requirement framing to implementation and verification.

---

## Required Operating Model (Non-Negotiable)

1. **Never generate implementation issues directly from the raw SRS.**
2. **Before backlog generation, first generate and refine these artifacts (in this order, iterating as needed):**
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
3. **Only after the artifacts above are complete and internally consistent may backlog items be generated.**
4. **Every implementation task must be grounded in a task package under `/docs/planning/task-packages`.**
5. **Every PR must include an evidence summary containing:**
   - Requirements covered
   - Tests run
   - Files changed and why
   - Unresolved items
   - Risk level
   - Confidence
6. **Prefer targeted clarification questions instead of assumptions when product detail is missing.**
7. **Always update `/.ai/sessions/<task-id>/status.md` during active work.**
8. **Always restate the task and execution plan before coding.**
9. **Always run project validation commands before marking work complete.**
10. **Never auto-merge high-risk work (auth, billing, permissions, migrations, security-sensitive changes).**

---

## Repo Navigation

- Product requirements and planning context: `/docs/product`
- Architecture and technical decisions: `/docs/architecture`
- UX and operational flows: `/docs/flows`
- Design artifacts (wireframes, branding, system): `/docs/design`
- API contract source of truth: `/docs/api/openapi.yaml`
- QA acceptance and strategy: `/docs/qa`
- Planning and task packages: `/docs/planning`
- Active session traces: `/.ai/sessions`

**Start-of-task expectation:** identify impacted areas and update documentation first when required by the operating model.

---

## Branching Rules

- Use short-lived branches focused on a single task package or tightly related scope.
- Keep commits logically grouped and messages explicit.
- Rebase/merge from mainline frequently to reduce drift.
- Do not mark work complete if evidence summary or validation output is incomplete.

---

## Coding Standards

- Follow existing naming and style conventions.
- Prefer small, reviewable diffs with clear intent.
- Avoid unrelated refactors.
- Preserve backward compatibility unless scope explicitly permits breaking changes.
- Add/update tests proportional to risk and blast radius.
- Ask focused clarification questions when requirements are ambiguous.

---

## Validation Steps

Run validations appropriate to the stack before completion (e.g., lint, type-check, unit, integration, contract, build).

Minimum validation requirements:
1. Run all repository-standard validation commands.
2. Capture command outputs for PR evidence.
3. If a command cannot run, document:
   - why,
   - impact,
   - mitigation or follow-up action.

---

## Documentation Rules

- Documentation is the planning source of truth.
- Keep `/docs/product`, `/docs/architecture`, `/docs/flows`, `/docs/design`, `/docs/api`, and `/docs/qa` internally consistent before backlog generation.
- Every implementation change must trace to:
  1. approved upstream artifacts,
  2. a task package in `/docs/planning/task-packages`, and
  3. acceptance + test criteria.
- If behavior/interfaces/constraints change, update docs in the same PR.

---

## Session Logging Rules

For every active task:
1. Create/update `/.ai/sessions/<task-id>/status.md`.
2. Log objective, current plan, progress, blockers, validations run, and next steps.
3. Update at meaningful checkpoints: start, major edits, validation, handoff.
4. Keep session status consistent with final PR evidence summary.

---

## Risk Classification Rules

Classify each task/PR as:
- **Low:** isolated, reversible, minimal user impact.
- **Medium:** multi-file or behavior-impacting change with bounded blast radius.
- **High:** auth, billing, permissions, migrations, security-sensitive logic, data integrity, or irreversible change.

Risk handling rules:
- Increase test depth with risk level.
- Explicitly document unresolved risks.
- High-risk work requires rollback notes and explicit reviewer sign-off.
- High-risk work is never auto-merged.

---

## Merge Gate Rules

A PR is merge-ready only when all criteria are met:
1. Task is grounded in `/docs/planning/task-packages/<task-id>.md` (or equivalent).
2. Required upstream artifacts are complete and consistent.
3. Validation commands were run and outputs captured.
4. Evidence summary includes:
   - Requirements covered
   - Tests run
   - Files changed and why
   - Unresolved items
   - Risk level
   - Confidence
5. If risk is high, auto-merge is disabled and reviewer sign-off is explicit.

If any gate fails, do not mark work complete.

---

## PR Evidence Template (Required)

Use this structure in every PR description:

1. **Requirements covered**
2. **Tests run** (commands + outcomes)
3. **Files changed and why**
4. **Unresolved items**
5. **Risk level** (Low/Medium/High + rationale)
6. **Confidence** (Low/Medium/High + rationale)

---

## Backlog Generation Gate (Checklist)

Backlog/implementation issue generation is allowed **only if all are true**:

- [ ] Product brief complete
- [ ] Priorities complete
- [ ] Scope complete
- [ ] Architecture complete
- [ ] User flows complete
- [ ] Process flows complete
- [ ] Wireframes complete
- [ ] Branding complete
- [ ] Design system complete
- [ ] API contracts complete
- [ ] Acceptance matrix complete
- [ ] Test strategy complete
- [ ] Artifact set internally consistent

If any item is unchecked, continue artifact refinement and do not generate implementation issues.
