---

description: "Task list for CV website audit and improvement implementation"
---

# Tasks: CV Website Audit and Improvement

**Input**: Design documents from `/specs/001-cv-website-audit/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md, contracts/

**Tests**: Automated tests are not explicitly required in the spec. Validation tasks use build checks and manual verification criteria (WCAG 2.2 AA, Core Web Vitals thresholds, link retry policy).

**Organization**: Tasks are grouped by user story to enable independent implementation and validation of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- Repository root content: `_config.yml`, `index.md`, `resume.md`, `projects.md`, `skills.md`
- Shared layouts: `_layouts/default.html`, `_layouts/resume.html`
- Styling/assets: `assets/css/style.scss`, `assets/img/`
- Feature artifacts: `specs/001-cv-website-audit/`

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Prepare reproducible audit/improvement workspace and artifact skeleton.

- [X] T001 Create audit artifact directory structure under `specs/001-cv-website-audit/artifacts/` (`findings/`, `recommendations/`, `verification/`, `links/`)
- [X] T002 Create findings schema template in `specs/001-cv-website-audit/artifacts/findings/findings-template.md` aligned with `specs/001-cv-website-audit/data-model.md`
- [X] T003 [P] Create link-check log template in `specs/001-cv-website-audit/artifacts/links/link-check-log.md` with retry tracking fields from `specs/001-cv-website-audit/contracts/audit-report-contract.md`
- [X] T004 [P] Create recommendation matrix template in `specs/001-cv-website-audit/artifacts/recommendations/recommendation-matrix.md`
- [X] T005 [P] Create implementation verification template in `specs/001-cv-website-audit/artifacts/verification/improvement-verification.md`

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Establish baseline inventory, constraints guardrails, and compatibility checks required before any user-story execution.

**⚠️ CRITICAL**: No user story work can begin until this phase is complete.

- [X] T006 Build page/layout/style inventory in `specs/001-cv-website-audit/artifacts/findings/scope-inventory.md` covering `_config.yml`, pages, `_layouts/`, and `assets/css/style.scss`
- [X] T007 Define factual-change approval gate process in `specs/001-cv-website-audit/artifacts/verification/factual-approval-log.md` (owner approval required before factual edits)
- [X] T008 Define external link multi-pass policy checklist in `specs/001-cv-website-audit/artifacts/links/external-link-policy.md` (minimum 3 separated retries before broken classification)
- [X] T009 Define WCAG 2.2 AA verification checklist in `specs/001-cv-website-audit/artifacts/verification/wcag-aa-checklist.md` for primary pages/shared layouts
- [X] T010 Define Core Web Vitals verification checklist in `specs/001-cv-website-audit/artifacts/verification/core-web-vitals-checklist.md` with LCP/CLS/INP thresholds
- [X] T011 Establish compatibility guardrails in `specs/001-cv-website-audit/artifacts/verification/github-pages-jekyll-guardrails.md` (supported plugins/config only)
- [X] T012 Run baseline build and capture output in `specs/001-cv-website-audit/artifacts/verification/baseline-build.txt` using `bundle exec jekyll build`

**Checkpoint**: Foundation ready - user story implementation can now begin.

---

## Phase 3: User Story 1 - Complete Audit Baseline (Priority: P1) 🎯 MVP

**Goal**: Produce a complete, structured audit baseline across all required domains.

**Independent Test**: `specs/001-cv-website-audit/artifacts/findings/audit-findings.md` exists and includes findings for content, links, accessibility, SEO, and layout consistency, each with severity/evidence/recommendation.

### Implementation for User Story 1

- [X] T013 [US1] Audit content freshness/consistency across `index.md`, `resume.md`, `projects.md`, and `skills.md`; document findings in `specs/001-cv-website-audit/artifacts/findings/content-findings.md`
- [X] T014 [US1] Audit accessibility issues in `_layouts/default.html`, `_layouts/resume.html`, and `assets/css/style.scss`; document findings in `specs/001-cv-website-audit/artifacts/findings/accessibility-findings.md`
- [X] T015 [US1] Audit SEO quality in `_config.yml`, `_layouts/default.html`, and page front matter; document findings in `specs/001-cv-website-audit/artifacts/findings/seo-findings.md`
- [X] T016 [US1] Audit layout consistency across desktop/mobile behaviors using `index.md`, `resume.md`, `projects.md`, `skills.md`, and `assets/css/style.scss`; document findings in `specs/001-cv-website-audit/artifacts/findings/layout-findings.md`
- [X] T017 [US1] Execute internal link check across generated site paths and record results in `specs/001-cv-website-audit/artifacts/links/internal-link-check.md`
- [X] T018 [US1] Execute external link checks with >=3 retries separated by 30-120 seconds; record per-attempt evidence in `specs/001-cv-website-audit/artifacts/links/external-link-check.md`
- [X] T019 [US1] Consolidate all category outputs into normalized finding records in `specs/001-cv-website-audit/artifacts/findings/audit-findings.md` following contract and data-model fields

**Checkpoint**: User Story 1 delivers a complete audit baseline and is independently reviewable.

---

## Phase 4: User Story 2 - Prioritized Recommendation Plan (Priority: P2)

**Goal**: Convert audit findings into an actionable prioritized recommendation set.

**Independent Test**: `specs/001-cv-website-audit/artifacts/recommendations/recommendation-plan.md` maps each recommendation to findings, includes priority/effort/impact, and defines execution sequence.

### Implementation for User Story 2

- [X] T020 [US2] Map findings to `RecommendationItem` records in `specs/001-cv-website-audit/artifacts/recommendations/recommendation-items.md`
- [X] T021 [US2] Tag recommendations requiring factual approval and log in `specs/001-cv-website-audit/artifacts/verification/factual-approval-log.md`
- [X] T022 [P] [US2] Define quick wins and strategic tracks in `specs/001-cv-website-audit/artifacts/recommendations/prioritization-rationale.md`
- [X] T023 [P] [US2] Build recommendation dependency graph in `specs/001-cv-website-audit/artifacts/recommendations/dependency-graph.md`
- [X] T024 [US2] Produce final recommendation plan in `specs/001-cv-website-audit/artifacts/recommendations/recommendation-plan.md`

**Checkpoint**: User Story 2 produces a clear implementation-ready recommendation plan.

---

## Phase 5: User Story 3 - Implement Compatible Improvements (Priority: P3)

**Goal**: Apply approved high-priority improvements while preserving GitHub Pages/Jekyll compatibility and all clarified quality constraints.

**Independent Test**: Approved improvements are implemented, build succeeds, and verification artifacts confirm WCAG/Core Web Vitals/link-policy/analytics-disclosure outcomes.

### Implementation for User Story 3

- [X] T025 [US3] Apply approved content consistency/freshness updates to `index.md`, `resume.md`, `projects.md`, and `skills.md` (only approved factual changes)
- [X] T026 [US3] Apply approved accessibility and semantic updates to `_layouts/default.html` and `_layouts/resume.html`
- [X] T027 [US3] Apply approved visual consistency and readability updates to `assets/css/style.scss`
- [X] T028 [US3] Apply approved SEO/metadata updates to `_config.yml` and page front matter in `index.md`, `projects.md`, `skills.md`, `resume.md`
- [X] T029 [US3] Add/update analytics privacy disclosure content in `index.md` (or designated visible page section), including IP anonymization and no direct personal identifier collection
- [X] T030 [US3] Revalidate external links using retry policy (>=3 retries separated by 30-120 seconds) and update `specs/001-cv-website-audit/artifacts/links/external-link-check.md`
- [X] T031 [US3] Run compatibility build check (`bundle exec jekyll build`) and record output in `specs/001-cv-website-audit/artifacts/verification/post-change-build.txt`
- [X] T032 [US3] Execute post-change verification (WCAG 2.2 AA, Core Web Vitals, SEO, layout consistency) and record in `specs/001-cv-website-audit/artifacts/verification/improvement-verification.md`
- [X] T033 [US3] Verify core navigation and resume access on desktop/mobile (`/`, `/skills`, `/projects`, `/resume`) and log results in `specs/001-cv-website-audit/artifacts/verification/navigation-access-check.md`

**Checkpoint**: User Story 3 implements selected improvements and validates compatibility/quality.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Final reconciliation and delivery-quality reporting across stories.

- [X] T034 [P] Update `specs/001-cv-website-audit/quickstart.md` if execution flow changed during implementation
- [X] T035 Reconcile final status (`resolved`, `deferred`, `inconclusive`) for all findings in `specs/001-cv-website-audit/artifacts/findings/audit-findings.md`
- [X] T036 Produce final outcome summary in `specs/001-cv-website-audit/artifacts/verification/final-summary.md` with changed files, constraints compliance, and follow-ups
- [X] T037 Execute final sanity build (`bundle exec jekyll build`) and append result to `specs/001-cv-website-audit/artifacts/verification/post-change-build.txt`

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies - starts immediately.
- **Foundational (Phase 2)**: Depends on Setup completion - blocks all user stories.
- **User Story 1 (Phase 3)**: Depends on Foundational completion.
- **User Story 2 (Phase 4)**: Depends on User Story 1 outputs.
- **User Story 3 (Phase 5)**: Depends on User Story 2 plan and owner approvals.
- **Polish (Phase 6)**: Depends on completion of selected User Story 3 tasks.

### User Story Dependencies

- **US1 (P1)**: No dependency on other user stories; delivers MVP audit baseline.
- **US2 (P2)**: Depends on US1 finding artifacts.
- **US3 (P3)**: Depends on US2 recommendations and required factual-approval decisions.

### Within Each User Story

- US1: Category audits -> link checks -> consolidated findings.
- US2: Mapping and prioritization -> dependency graph -> final recommendation plan.
- US3: Approved changes -> link/build checks -> final verification artifacts.

### Parallel Opportunities

- Phase 1: T003, T004, T005 can run in parallel.
- Phase 4: T022 and T023 can run in parallel.
- Phase 6: T034 can run in parallel with status reconciliation before T036.

---

## Parallel Example: User Story 1

```bash
# Run category-specific audit documentation in parallel:
Task: "T013 [US1] Audit content findings in specs/001-cv-website-audit/artifacts/findings/content-findings.md"
Task: "T014 [US1] Audit accessibility findings in specs/001-cv-website-audit/artifacts/findings/accessibility-findings.md"
Task: "T015 [US1] Audit SEO findings in specs/001-cv-website-audit/artifacts/findings/seo-findings.md"
Task: "T016 [US1] Audit layout findings in specs/001-cv-website-audit/artifacts/findings/layout-findings.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1 and Phase 2.
2. Complete Phase 3 (US1) to deliver full baseline audit.
3. Validate audit completeness against independent test criteria.
4. Stop for review before recommendations/implementation.

### Incremental Delivery

1. Setup + Foundational -> stable audit framework.
2. US1 -> complete findings baseline.
3. US2 -> prioritized recommendation plan.
4. US3 -> apply approved improvements with verification.
5. Polish -> finalize status and delivery summary.

### Parallel Team Strategy

With multiple contributors:

1. One owner finalizes foundational guardrails (T006-T012).
2. Split US1 category audits across team members (T013-T016).
3. Split US2 prioritization and dependency analysis (T022-T023).
4. Split US3 by concern areas (content/layout/SEO) while one owner validates build + verification.

---

## Notes

- [P] tasks denote parallelizable work with low coupling.
- Every user-story task contains explicit file paths for direct execution.
- Factual profile edits require explicit owner approval before implementation.
- External links must follow 3+ retry classification policy before `broken` status.
- GitHub Pages/Jekyll compatibility is a hard gate for completion.
