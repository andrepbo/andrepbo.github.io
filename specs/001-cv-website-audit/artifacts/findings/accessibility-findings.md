# Accessibility Findings

## F-003
- Category: accessibility
- Severity: high
- Page or Asset: `_layouts/default.html`
- Description: Icon-only social links lack accessible names.
- Evidence: Social anchor tags contain only `<i>` icons without `aria-label`.
- Recommendation: Add accessible names (`aria-label`) and keep decorative icons hidden if needed.
- Requires Owner Approval: false
- Status: open

## F-004
- Category: accessibility
- Severity: medium
- Page or Asset: `assets/css/style.scss`
- Description: No explicit focus-visible styling for keyboard navigation.
- Evidence: CSS defines hover states but no dedicated focus/focus-visible styles for nav/social links.
- Recommendation: Add visible `:focus-visible` styles for interactive elements.
- Requires Owner Approval: false
- Status: open
