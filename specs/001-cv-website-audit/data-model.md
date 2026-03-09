# Data Model: CV Website Audit and Improvement

## Entity: AuditFinding
- Purpose: Represent a single detected issue in the website audit.
- Fields:
  - `id` (string, required, unique): Stable identifier (`F-001`, etc.).
  - `category` (enum, required): `outdated_content | broken_link | accessibility | seo | layout_consistency`.
  - `severity` (enum, required): `critical | high | medium | low`.
  - `page_or_asset` (string, required): Affected path or asset reference.
  - `description` (string, required): Issue summary.
  - `evidence` (string, required): Proof or observation supporting the finding.
  - `recommendation` (string, required): Proposed corrective action.
  - `requires_owner_approval` (boolean, required): True when factual profile data changes are involved.
  - `status` (enum, required): `open | approved | implemented | deferred | inconclusive`.
  - `verification_notes` (string, optional): Post-change validation details.

## Entity: LinkCheckRecord
- Purpose: Capture retry-based validation details for links.
- Fields:
  - `url` (string, required): Checked URL.
  - `link_type` (enum, required): `internal | external`.
  - `attempts` (integer, required): Number of attempts executed.
  - `attempt_results` (array<string>, required): Result per attempt (`ok`, `timeout`, `dns_error`, `blocked`, etc.).
  - `final_classification` (enum, required): `valid | broken | inconclusive`.
  - `classification_reason` (string, required): Why final status was assigned.

## Entity: RecommendationItem
- Purpose: Prioritized action item linked to one or more findings.
- Fields:
  - `id` (string, required, unique): Stable identifier (`R-001`, etc.).
  - `title` (string, required): Recommendation label.
  - `priority` (enum, required): `p1 | p2 | p3`.
  - `effort` (enum, required): `small | medium | large`.
  - `expected_impact` (string, required): User/business impact summary.
  - `linked_findings` (array<string>, required): List of `AuditFinding.id`.
  - `implementation_scope` (string, required): Files/areas expected to change.

## Entity: ImprovementItem
- Purpose: Track implementation and verification of an approved recommendation.
- Fields:
  - `id` (string, required, unique): Stable identifier (`I-001`, etc.).
  - `recommendation_id` (string, required): Link to `RecommendationItem.id`.
  - `changed_files` (array<string>, required): Files modified.
  - `build_validation` (enum, required): `pass | fail`.
  - `a11y_validation` (enum, required): `pass | fail | partial`.
  - `seo_validation` (enum, required): `pass | fail | partial`.
  - `performance_validation` (enum, required): `pass | fail | partial`.
  - `final_status` (enum, required): `done | deferred | blocked`.

## Relationships
- `RecommendationItem.linked_findings` references one or many `AuditFinding` records.
- `ImprovementItem.recommendation_id` references exactly one `RecommendationItem`.
- `LinkCheckRecord` may be linked to `AuditFinding` when category is `broken_link`.

## Validation Rules
- Every `AuditFinding` MUST include severity, evidence, and recommendation.
- Findings impacting factual CV data MUST set `requires_owner_approval = true`.
- External link findings MUST include a `LinkCheckRecord` with `attempts >= 3` before `broken` classification.
- Every `ImprovementItem` MUST reference an existing recommendation and include build validation result.

## State Transitions

### AuditFinding.status
- `open -> approved` when owner confirms recommendation path.
- `open -> deferred` when not selected for current implementation cycle.
- `open -> inconclusive` when validation cannot confirm issue conclusively.
- `approved -> implemented` when corresponding change is completed and validated.

### ImprovementItem.final_status
- `blocked -> done` when dependencies or approvals are resolved.
- `blocked -> deferred` when postponed.
- `done` is terminal for the current cycle.
