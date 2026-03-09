# External Link Validation Policy

## Classification Rules
- Start with initial check for each external URL.
- If initial check fails, perform at least 3 retry attempts.
- Retry attempts MUST be separated by 30-120 seconds.
- Classify as `broken` only if all retries fail consistently.
- Classify as `inconclusive` if outcomes are unstable, blocked by anti-bot, or environment constraints prevent reliable verification.

## Required Log Fields
- URL
- attempt count
- per-attempt result
- final classification
- classification reason
