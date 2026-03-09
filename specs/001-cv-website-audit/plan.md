# Implementation Plan: CV Website Audit and Improvement

**Branch**: `001-cv-website-audit` | **Date**: 2026-03-09 | **Spec**: [/workspaces/andrepbo.github.io/specs/001-cv-website-audit/spec.md](/workspaces/andrepbo.github.io/specs/001-cv-website-audit/spec.md)
**Input**: Feature specification from `/specs/001-cv-website-audit/spec.md`

## Summary

Execute a full CV website audit and targeted improvement cycle covering content freshness,
link health, accessibility, SEO, and layout consistency, then implement prioritized fixes
with strict GitHub Pages + Jekyll compatibility. The approach uses a traceable finding ->
recommendation -> improvement workflow, with explicit owner approval required for factual
content changes.

## Technical Context

**Language/Version**: Jekyll (GitHub Pages toolchain), Markdown, HTML, SCSS, YAML  
**Primary Dependencies**: `github-pages`, `jekyll-seo-tag`, `jekyll-feed`, theme `jekyll-theme-minimal`  
**Storage**: Repository files only (Markdown/content/layout/assets), no database  
**Testing**: `bundle exec jekyll build` + manual QA checklist (content/link/a11y/SEO/layout)  
**Target Platform**: GitHub Pages static hosting (desktop + mobile browsers)  
**Project Type**: Static CV/portfolio website  
**Performance Goals**: Core Web Vitals targets on primary pages: LCP <= 2.5s, CLS <= 0.1, INP <= 200ms  
**Constraints**: Must remain GitHub Pages/Jekyll compatible; WCAG 2.2 AA for primary pages/shared layouts; no backend runtime; analytics retained with privacy-safe disclosure; external links validated with >=3 retries before "broken" classification  
**Scale/Scope**: 4 primary pages (`index.md`, `resume.md`, `projects.md`, `skills.md`) plus shared `_layouts`, `assets/css`, and `_config.yml`

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

- `I. Representacao Profissional Fiel`: PASS
  - Plan enforces owner approval for factual profile changes before implementation.
- `II. Consistencia Entre Paginas`: PASS
  - Plan includes cross-page consistency checks with `resume.md` as canonical source.
- `III. Clareza e Leitura Escaneavel`: PASS
  - Audit criteria include readability and concise recruiter-focused presentation.
- `IV. Site Estatico, Acessivel e Rapido`: PASS
  - Static architecture preserved; WCAG 2.2 AA and Core Web Vitals targets included.
- `V. Disciplina de Mudanca e Revisao`: PASS
  - Build validation (`bundle exec jekyll build`) and post-change verification report required.

No constitution violations detected.

Post-design re-check (after Phase 1 artifacts): PASS.

## Project Structure

### Documentation (this feature)

```text
specs/001-cv-website-audit/
├── plan.md
├── research.md
├── data-model.md
├── quickstart.md
├── artifacts/
│   ├── findings/
│   ├── recommendations/
│   ├── links/
│   └── verification/
├── contracts/
│   └── audit-report-contract.md
└── tasks.md
```

### Source Code (repository root)

```text
_config.yml
index.md
resume.md
projects.md
skills.md

_layouts/
├── default.html
└── resume.html

assets/
├── css/
│   └── style.scss
└── img/
    └── andre.jpg
```

**Structure Decision**: Keep the existing single static-site structure. Implement changes
in content/layout/style/config files directly, and capture audit outcomes in
feature documentation artifacts.

## Complexity Tracking

No constitution exceptions expected; section intentionally empty.
