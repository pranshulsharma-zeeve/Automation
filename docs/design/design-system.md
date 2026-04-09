# GolDefi Design System

## Foundations
- 8px spacing grid.
- Desktop: 12-column layout; mobile: 4-column layout.
- Corner radius scale: 4 / 8 / 12.
- Elevation scale: 0-3.

## Typography Scale
- H1: 32px / 40
- H2: 24px / 32
- H3: 20px / 28
- Body L: 16px / 24
- Body M: 14px / 20
- Caption: 12px / 16
- Data/Hashes: 13px mono

## Core Components (MVP)
1. Buttons (primary, secondary, ghost, destructive)
2. Inputs (text, number, OTP, wallet address, amount)
3. Selects (single, searchable)
4. Status badges (draft, pending, approved, rejected, exception)
5. Alerts/Banners (info, success, warning, error)
6. Tables (sortable/filterable with status chips)
7. Stepper (onboarding, KYC, redemption)
8. Modal confirmations for destructive/high-value actions
9. Wallet connection and signature prompt module

## Component Style Rules
- Primary CTA uses Gold Primary on dark text where contrast passes.
- Destructive actions require explicit confirmation and warning copy.
- Disabled buttons include helper text when action is blocked by policy.
- Monetary figures use monospaced numeric style for readability.

## Interaction Rules
- Inline validation plus summary-level error display.
- Long-running operations must show deterministic status states.
- Critical flows require clear progress states (e.g., lock -> burn -> fulfill).
- Re-auth/MFA prompts required for sensitive profile or payout changes.

## Content Rules
- Always display final payable amount before order confirmation.
- Always display compliance reason codes for blocked actions where permitted.
- Avoid ambiguous labels like “Continue” for irreversible actions.

## Accessibility Rules
- Keyboard navigable components.
- Focus ring visible on all interactive controls.
- WCAG-compliant color contrast targets.
- Error messaging with actionable remediation.

## MVP vs Later Phase
### MVP
- Base tokens, layouts, and core transactional components.

### Later Phase
- Advanced charting components.
- Localized component variants and RTL support.

## Ambiguities Identified
- Formalized content/localization strategy timeline.
