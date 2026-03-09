# Recommendation Items

## R-001
- Title: Normalize language metadata and page link targets
- Priority: p1
- Effort: small
- Expected Impact: Improves SEO clarity and reduces navigation/link ambiguity.
- Linked Findings: F-002, F-005, F-006, F-008
- Implementation Scope: `_config.yml`, `index.md`, `projects.md`, `_layouts/default.html`

## R-002
- Title: Improve accessibility semantics and keyboard focus visibility
- Priority: p1
- Effort: medium
- Expected Impact: Moves site toward WCAG 2.2 AA and improves keyboard/screen reader usability.
- Linked Findings: F-003, F-004
- Implementation Scope: `_layouts/default.html`, `assets/css/style.scss`

## R-003
- Title: Align resume and main-site visual consistency
- Priority: p2
- Effort: medium
- Expected Impact: Reduces layout drift and improves professional cohesion.
- Linked Findings: F-007
- Implementation Scope: `_layouts/resume.html`, `assets/css/style.scss`

## R-004
- Title: Resolve/verify inconclusive external links
- Priority: p2
- Effort: small
- Expected Impact: Improves trust and reduces outbound-link risk.
- Linked Findings: F-009, F-010
- Implementation Scope: `index.md`, `projects.md`, `specs/001-cv-website-audit/artifacts/links/external-link-check.md`

## R-005
- Title: Resolve factual certification year mismatch
- Priority: p1
- Effort: small
- Expected Impact: Prevents conflicting professional history data.
- Linked Findings: F-001
- Implementation Scope: `resume.md`, `skills.md`
- Owner Approval Required: yes
