# Quickstart: CV Website Audit and Improvement

## Prerequisites
- Ruby/Bundler environment available for this repository.
- Feature branch checked out: `001-cv-website-audit`.
- Owner availability for factual content approval decisions.

## 1. Review Scope and Constraints
1. Read the feature spec:
   - `/workspaces/andrepbo.github.io/specs/001-cv-website-audit/spec.md`
2. Confirm non-negotiable constraints:
   - GitHub Pages + Jekyll compatibility
   - WCAG 2.2 AA target
   - Core Web Vitals targets
   - External link retry policy (`>=3` retries, 30-120s separation)
   - Explicit owner approval for factual changes

## 2. Execute Audit Pass
1. Audit all primary pages and shared assets in scope.
2. Record findings using the `AuditFinding` model.
3. For external links:
   - Retry failed links at least 3 times with 30-120 second separation.
   - Classify as `broken` only with consistent failure and conclusive evidence.
   - Use `inconclusive` for anti-bot/network-limited validations.

## 3. Build Recommendation Set
1. Convert findings into prioritized `RecommendationItem` entries.
2. Ensure each recommendation links to one or more findings.
3. Mark recommendations requiring owner approval for factual profile edits.

## 4. Approve and Implement
1. Request/record explicit owner approval for factual content changes.
2. Implement selected improvements in scoped files.
3. Track each change as an `ImprovementItem` linked to recommendation IDs.
4. For navigation consistency, keep permalink strategy aligned with header routes.

## 5. Validate and Verify
1. Run build validation:
```bash
bundle exec jekyll build
```
2. Perform verification checks:
   - Accessibility (WCAG 2.2 AA criteria on primary pages/shared layouts)
   - SEO metadata and semantic structure
   - Layout consistency (desktop/mobile)
   - Core Web Vitals target compliance
   - Navigation route integrity (`/`, `/skills/`, `/projects/`, `/resume/`)

## 6. Final Report
1. Produce final summary listing:
   - Findings resolved
   - Findings deferred
   - Findings inconclusive
2. Include changed files, compatibility status, and any follow-up items.
3. Explicitly list deferred factual items pending owner approval.
