# Internal Link Check

## Generated Outputs
- `_site/index.html`: present
- `_site/resume/index.html`: present
- `_site/skills.html`: present
- `_site/projects.html`: present

## Navigation Link Targets Found in `_site/index.html`
- `/skills`
- `/projects`
- `/resume`

## Assessment
- `/resume` is aligned with generated output (`_site/resume/index.html`).
- `skills.md` and `projects.md` currently generate `skills.html` and `projects.html`.
- Links rendered as `/skills` and `/projects` may depend on host rewrite behavior; this is a routing consistency risk and should be validated/fixed for deterministic behavior.

## Classification
- Internal links: **inconclusive** pending explicit permalink strategy or link normalization.
