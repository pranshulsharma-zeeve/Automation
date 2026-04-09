# TASK-001

## title
Registration, OTP Verification, and Session Security

## business goal
Establish a secure and compliant entry point so only verified users can access protected platform workflows.

## linked epic
EPIC-01 — Identity, Compliance, and Access Control

## scope included
- Signup form submission with country policy checks
- Email OTP issuance and verification
- Login/session creation and refresh handling
- MFA enablement path

## scope excluded
- Social auth providers
- Mobile app native auth SDKs

## dependencies
- Country policy configuration (blacklist/greylist)
- Notification provider for OTP delivery

## related docs
- `/docs/product/srs.md`
- `/docs/flows/user-flows.md`
- `/docs/api/openapi.yaml`
- `/docs/qa/acceptance-matrix.md`

## acceptance criteria
- New users can register and verify email OTP.
- Blacklisted-country registration attempts are blocked.
- Session issuance and refresh behavior is auditable.
- MFA prompt path is available for enabled users.

## test expectations
- API tests for register/login/verify endpoints
- E2E tests for signup and OTP verification
- Security tests for invalid OTP and brute-force limits

## risk level
Medium

## definition of done
- All acceptance criteria pass in staging.
- Relevant API contracts and docs are updated.
- Security and QA sign-off captured.
