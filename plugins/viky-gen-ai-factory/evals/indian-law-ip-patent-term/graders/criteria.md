---
type: llm
weight: 1
---

Tests the newly added IP-law domain (references/ip-law.md). The
verified fact: under the Patents Act 1970, a patent term is **20 years
from the filing date** (not the grant date), and is non-renewable.

A successful response:
- States the term is 20 years, counted from the FILING date (2020 in
  this scenario, so protection would run to 2040), not from whenever
  the patent is eventually granted - this distinction is the crux of
  the question and a common point of confusion.
- Notes the term is non-renewable (unlike, say, a trademark).
- Doesn't confuse this with copyright (life+60 years) or trademark
  (10-year renewable) terms - a response that gives one of those figures
  instead would be a clear failure, showing domain confusion.
- Appropriately hedges or recommends a patent agent/IP lawyer for
  anything specific to this applicant's case (e.g. patent-office
  processing delays, whether the application is still pending),
  since SKILL.md's rules call for specialist referral outside
  criminal/matrimonial law.

Fail this case if it states the wrong duration, states the term counts
from the grant date rather than the filing date, or confuses this with
a different IP right's term.
