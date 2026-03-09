# Research: CV Website Audit and Improvement

## Decision 1: Accessibility standard
- Decision: Adopt WCAG 2.2 AA for all primary pages and shared layouts/components.
- Rationale: Matches clarified spec target and provides measurable acceptance criteria.
- Alternatives considered:
  - WCAG 2.1 AA (lower bar, less future-oriented)
  - Best-effort accessibility without formal target (harder to validate)

## Decision 2: Performance validation model
- Decision: Use Core Web Vitals thresholds for primary pages (LCP <= 2.5s, CLS <= 0.1, INP <= 200ms).
- Rationale: User-centric, measurable, and aligned with SEO and UX expectations.
- Alternatives considered:
  - Generic page-load-only metric (less complete)
  - No explicit threshold (weak acceptance testing)

## Decision 3: External link reliability policy
- Decision: Classify failed external links via multi-pass checks with at least three separated retries.
- Rationale: Reduces false positives from anti-bot blocks, transient DNS, and temporary outages.
- Alternatives considered:
  - Single-pass check (too noisy)
  - Manual-only checking (low repeatability)

## Decision 4: Factual content governance
- Decision: Require explicit owner approval for factual CV/profile changes.
- Rationale: Protects professional accuracy and aligns with constitution principle I.
- Alternatives considered:
  - Auto-apply factual corrections from audit confidence
  - Approval required only for major changes

## Decision 5: Analytics and privacy handling
- Decision: Retain analytics with privacy-safe configuration and visible disclosure.
- Rationale: Preserves measurement while improving transparency and trust.
- Alternatives considered:
  - Remove analytics (lose insights)
  - Keep analytics unchanged (missed privacy improvement)

## Decision 6: SEO modernization boundaries
- Decision: Focus SEO improvements on metadata quality, canonical consistency, semantic headings, and crawlable structure without adding unsupported plugins.
- Rationale: High-impact changes that remain compatible with GitHub Pages constraints.
- Alternatives considered:
  - Introduce additional SEO plugins beyond GitHub Pages support
  - Restrict SEO only to title/description edits

## Decision 7: Audit output structure
- Decision: Use a normalized finding schema with severity, evidence, recommendation, owner-approval flag, and resolution status.
- Rationale: Enables traceability from issue detection through implementation verification.
- Alternatives considered:
  - Free-form narrative report (lower traceability)
  - Tool-specific format only (less portable)
