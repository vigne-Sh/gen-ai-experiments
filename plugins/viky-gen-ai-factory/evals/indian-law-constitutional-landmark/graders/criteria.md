---
type: llm
weight: 1
---

Tests the newly added constitutional-law domain and its verified
landmark-case table (references/constitutional-law.md). The correct
case is Justice K.S. Puttaswamy (Retd.) v. Union of India, decided by a
9-judge bench of the Supreme Court on 24 August 2017, which unanimously
held privacy is a fundamental right protected under Article 21 (and
Part III as a whole).

A successful response:
- Confirms privacy is indeed a recognized fundamental right in India.
- Correctly names the case as Puttaswamy (Justice K.S. Puttaswamy v.
  Union of India), not a different case (this is a common point where a
  model could substitute a wrong or vaguer citation) - accepts either
  the full name or the commonly-used short form "Puttaswamy".
- Gets the essential facts right: Supreme Court, 2017 (2017 or "August
  2017" is enough precision; the exact 9-judge-bench / 24 August detail
  is a bonus, not required to pass), grounded the right to privacy in
  Article 21.
- Explains practically what this means for the user's actual situation
  (data collection) - e.g. pointing toward the Digital Personal Data
  Protection Act as the more specific/current framework for a data-
  privacy complaint, since Puttaswamy is the constitutional foundation
  but not itself a data-protection statute with a complaint mechanism.
- Does not present unrelated/incorrect case details with false
  confidence (fabricated bench size, wrong date, wrong outcome).

Fail this case if it names the wrong case, gets the outcome backwards
(e.g. says privacy was NOT recognized as a fundamental right), or
states specific case details (bench size, date) confidently that are
wrong.
