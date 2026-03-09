# Consolidated Audit Findings

## F-001
- Category: outdated_content
- Severity: medium
- Page or Asset: `resume.md`, `skills.md`
- Description: Certification year mismatch for "AI - Assisted Certified Professional".
- Evidence: `resume.md` lists 2024; `skills.md` lists 2025.
- Recommendation: Confirm canonical year with owner and align both pages.
- Requires Owner Approval: true
- Status: deferred
- Verification Notes: Deferred pending explicit owner approval (logged in factual approval log).

## F-002
- Category: outdated_content
- Severity: low
- Page or Asset: `_config.yml`
- Description: Language metadata appeared inconsistent with current English-first content.
- Evidence: `_config.yml` previously used `lang: pt-BR` / `locale: pt_BR`.
- Recommendation: Align metadata language with dominant page content.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Updated to `lang: en-US` and `locale: en_US`.

## F-003
- Category: accessibility
- Severity: high
- Page or Asset: `_layouts/default.html`
- Description: Icon-only social links lacked accessible names.
- Evidence: Social links previously contained icon tags only.
- Recommendation: Add meaningful accessible labels and preserve decorative icon semantics.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Added `aria-label` and `rel="noopener noreferrer"` for external links.

## F-004
- Category: accessibility
- Severity: medium
- Page or Asset: `assets/css/style.scss`
- Description: Missing explicit keyboard focus-visible styles.
- Evidence: Hover styles existed without dedicated focus indicators.
- Recommendation: Add visible `:focus-visible` styles for links/buttons/navigation.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Added global `a:focus-visible` rule and skip-link styles.

## F-005
- Category: seo
- Severity: medium
- Page or Asset: `_config.yml`
- Description: Language/locale metadata was misaligned with English content pages.
- Evidence: Portuguese locale tags in a predominantly English site.
- Recommendation: Set site/page language metadata consistently.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Metadata normalized in config.

## F-006
- Category: seo
- Severity: low
- Page or Asset: `index.md`, `projects.md`
- Description: External markdown links used malformed target value syntax.
- Evidence: `{:target="\_blank"}` appeared in multiple links.
- Recommendation: Use valid target behavior and secure external link conventions.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Updated to `target="_blank"` with `rel="noopener noreferrer"`.

## F-007
- Category: layout_consistency
- Severity: medium
- Page or Asset: `_layouts/default.html`, `_layouts/resume.html`
- Description: Resume page visual system diverges from main site layout.
- Evidence: `resume.html` still uses dedicated inline style system.
- Recommendation: Harmonize shared typography/spacing or explicitly document print-first divergence.
- Requires Owner Approval: false
- Status: deferred
- Verification Notes: Kept deferred to avoid introducing broader print-layout regressions in this cycle.

## F-008
- Category: layout_consistency
- Severity: medium
- Page or Asset: Header navigation vs generated routes
- Description: Navigation used extensionless `/skills` and `/projects` while build output naming could diverge.
- Evidence: Earlier build generated `skills.html`/`projects.html` without permalink.
- Recommendation: Define permalink strategy and normalize links to deterministic routes.
- Requires Owner Approval: false
- Status: implemented
- Verification Notes: Added permalinks in page front matter and normalized nav links to `/skills/` and `/projects/`.

## F-009
- Category: broken_link
- Severity: medium
- Page or Asset: External link `https://www.linkedin.com/in/andrepbo`
- Description: Automated verification returned anti-bot responses.
- Evidence: Initial + 3 retries returned HTTP 999.
- Recommendation: Treat as inconclusive in automation; validate manually in browser during implementation phase.
- Requires Owner Approval: false
- Status: inconclusive
- Verification Notes: See `specs/001-cv-website-audit/artifacts/links/external-link-check.md`.

## F-010
- Category: broken_link
- Severity: medium
- Page or Asset: External link `https://www.vet4all.com.br/`
- Description: Automated checks failed with repeated resolution/network errors in execution environment.
- Evidence: Initial + 3 retries returned unresolved/failed code values.
- Recommendation: Treat as inconclusive in automation and validate from production-like network context.
- Requires Owner Approval: false
- Status: inconclusive
- Verification Notes: See `specs/001-cv-website-audit/artifacts/links/external-link-check.md`.
