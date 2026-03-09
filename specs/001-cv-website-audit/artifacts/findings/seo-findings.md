# SEO Findings

## F-005
- Category: seo
- Severity: medium
- Page or Asset: `_config.yml`
- Description: Language metadata likely misaligned with actual content language.
- Evidence: `lang`/`locale` configured as Portuguese while content is in English.
- Recommendation: Set language metadata consistently to improve crawl/index interpretation.
- Requires Owner Approval: false
- Status: open

## F-006
- Category: seo
- Severity: low
- Page or Asset: `index.md`, `projects.md`
- Description: Markdown links use malformed target attribute syntax (`target="\_blank"`).
- Evidence: Links include escaped underscore target value which renders nonstandard target names.
- Recommendation: Replace with valid `_blank` behavior and include secure external link handling.
- Requires Owner Approval: false
- Status: open
