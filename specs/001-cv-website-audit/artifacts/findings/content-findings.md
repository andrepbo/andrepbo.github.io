# Content Findings

## F-001
- Category: outdated_content
- Severity: medium
- Page or Asset: `resume.md`, `skills.md`
- Description: Certification year mismatch for "AI - Assisted Certified Professional".
- Evidence: `resume.md` shows 2024 while `skills.md` shows 2025.
- Recommendation: Confirm the correct year with owner and normalize across pages.
- Requires Owner Approval: true
- Status: open

## F-002
- Category: outdated_content
- Severity: low
- Page or Asset: `_config.yml` vs English page content
- Description: Site language metadata uses `pt-BR` while content is predominantly English.
- Evidence: `_config.yml` has `lang: pt-BR` and `locale: pt_BR`; page content is English.
- Recommendation: Align `lang/locale` metadata with dominant content language.
- Requires Owner Approval: false
- Status: open
