# Layout Consistency Findings

## F-007
- Category: layout_consistency
- Severity: medium
- Page or Asset: `_layouts/default.html`, `_layouts/resume.html`
- Description: Resume page uses a distinct inline style system and visual language from the main site layout.
- Evidence: `resume.html` has inline CSS with Arial and separate spacing rules; main layout relies on shared stylesheet/theme.
- Recommendation: Reduce visual drift by sharing key typography/spacing tokens or documenting intentional print-specific divergence.
- Requires Owner Approval: false
- Status: open

## F-008
- Category: layout_consistency
- Severity: medium
- Page or Asset: Navigation targets vs generated outputs
- Description: Header links point to `/skills` and `/projects` while build output currently generates `skills.html` and `projects.html`.
- Evidence: `_site/index.html` links use extensionless paths; generated artifacts are file-based.
- Recommendation: Define explicit permalink strategy or normalize links to deterministic routes.
- Requires Owner Approval: false
- Status: open
