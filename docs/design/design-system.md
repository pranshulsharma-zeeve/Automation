# Design System

## Typography
- **Primary Font:** Inter, sans-serif.
- **Heading Scale:** 32 / 24 / 20 / 16.
- **Body:** 14 (default), 16 (long-form reading).
- **Code/Data:** JetBrains Mono, 13.

## Spacing & Layout
- 8px spacing grid.
- Container max-width: 1200px.
- Card padding: 16px (compact), 24px (standard).

## Core Components
1. **Buttons:** primary, secondary, ghost, danger.
2. **Inputs:** text, textarea, select, tag picker.
3. **Status Chips:** draft, in-review, approved, blocked.
4. **Tables:** sortable, filterable, sticky header.
5. **Panels:** right-side context drawer for dependencies.
6. **Alerts:** info, warning, error, success.

## Component Style Rules
- Border radius: 8px standard.
- Button height: 36px default.
- Inputs must show helper text and validation messages.
- Disabled states require reduced contrast + tooltip rationale.

## Interaction Rules
- Unsaved change warning on navigation.
- Inline validation for required sections.
- Keyboard shortcuts for save/comment/submit-for-review.
