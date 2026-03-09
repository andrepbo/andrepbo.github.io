# GitHub Pages / Jekyll Compatibility Guardrails

## Mandatory Constraints
- Keep static-site architecture; no backend runtime dependencies.
- Use GitHub Pages compatible Jekyll configuration and plugins.
- Avoid unsupported plugin additions and incompatible build tooling changes.
- Preserve essential routes: `/`, `/skills`, `/projects`, `/resume`.

## Verification Checks
- `bundle exec jekyll build` succeeds.
- `_config.yml` remains compatible with GitHub Pages context.
- No new runtime service dependency introduced.
- Navigation and resume access remain functional.
