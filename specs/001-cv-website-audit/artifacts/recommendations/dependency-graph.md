# Recommendation Dependency Graph

- R-002 (Accessibility semantics/focus)
  - Depends on: none
- R-001 (Metadata/link normalization)
  - Depends on: none
- R-005 (Certification year mismatch)
  - Depends on: explicit owner approval entry in `factual-approval-log.md`
- R-003 (Resume/main visual consistency)
  - Depends on: R-002 (shared style adjustments should not regress accessibility)
- R-004 (Inconclusive external links follow-up)
  - Depends on: R-001 (link target normalization may affect final URL set)

## Suggested Execution Order
1. R-002 and R-001 in parallel where file overlap allows.
2. R-005 after owner approval.
3. R-003.
4. R-004 and final verification pass.
