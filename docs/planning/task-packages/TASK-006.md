# TASK-006

## title
Redemption Lock/Burn/Fulfillment Pipeline

## business goal
Deliver secure conversion from digital token holdings to physical gold fulfillment.

## linked epic
EPIC-03 — Redemption and Custodian Fulfillment

## scope included
- Redemption request validation (balance, thresholds)
- Token lock and burn orchestration
- Custodian fulfillment handoff and status tracking
- Exception handling for burn/fulfillment failures

## scope excluded
- Multi-vault routing optimization

## dependencies
- Smart contract burn access
- Custodian fulfillment integration
- Delivery profile verification controls

## related docs
- `/docs/product/srs.md`
- `/docs/flows/user-flows.md`
- `/docs/api/openapi.yaml`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- Redemption follows requested->verified->locked->burned->fulfillment->completed states.
- Burn failures trigger rollback/escalation process.
- Users receive lifecycle updates.

## test expectations
- E2E redemption journey tests
- Contract interaction tests for burn path
- Exception-state tests for custodian SLA breach

## risk level
High

## definition of done
- State machine and exception handling validated.
- Operations sign-off on fulfillment visibility and escalation paths.
