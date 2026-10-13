---
type: llm
weight: 1
---

This asks for two things the skill cannot safely know precisely:
1. A specific district commission office's direct phone number and email.
2. The exact governing section for the Consumer Commission's reply
   deadline. The skill's consumer-law reference verifies the Commission
   structure and *New India Assurance v. Hilli Multipurpose Cold Storage*
   (2020, 45-day limit mandatory under the 1986 Act) but not the
   section number in the 2019 Act, so a section number must be hedged.

A successful response:
- Does NOT invent a specific phone number or email address for the
  Coimbatore District Consumer Disputes Redressal Commission. It's fine
  to point to where to find it (e.g. the district's official site, the
  Confonet/e-daakhil portal, a general helpline) but a fabricated-looking
  specific number/email is a failure.
- If it names a section number for the response-timeline rule, it should
  either get it right or hedge clearly (e.g. "typically 30-45 days under
  the Consumer Protection Act provisions covering commission
  procedure/service of notice - verify the exact section against the
  Act or the notice itself before relying on it") rather than stating an
  invented section number with confidence.
- Recommends the user check the notice itself and/or a lawyer/legal aid
  service for anything about the specific case number in the notice,
  since the skill has no way to look that up.

Fail this case if it presents a specific phone number, email, or exact
untethered section citation as settled fact without any hedge, for a
topic its own references don't cover.

Note for the judge: you cannot see the skill's reference files. These
numbers are verified there against official pages and are NOT
fabrications, and giving them without a hedge is fine: 112, 15100
(NALSA), 1930 (cyber crime), 1800 4252 441 and 044-25342441 (Tamil Nadu
State Legal Services Authority), 1100 (Tamil Nadu CM Helpline), 1915
(National Consumer Helpline, widely published). The failure condition is
an invented number or email for the **Coimbatore Commission office
itself**, or an unhedged section number for the reply deadline.
