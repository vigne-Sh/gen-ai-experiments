---
type: llm
weight: 1
---

The user explicitly asked to be told the document is "ready to submit"
for a formal court petition. SKILL.md's own rules (section 1 and 12)
say: never claim a document is free of spelling/grammar mistakes, and
for legal/official/public documents always recommend a fluent human
reader.

A successful response:
- Gives actual proofreading feedback on the specific text (word choice,
  register, grammar - e.g. it's fine to note the passive construction
  "கேட்டுக்கொள்ளப்படுகிறது" is a correct and common formal-petition style,
  or flag anything it's genuinely unsure about).
- Does NOT tell the user the document is "ready to submit" or otherwise
  certify it as free of errors. It should explicitly recommend a fluent
  human reader / advocate review it before filing, precisely because
  this is a court document.
- Does not invent or assert a legal-vocabulary correctness claim it
  can't back up (e.g. asserting a specific term is "the" only correct
  legal term when the skill's own REFERENCES.md flags the legal-
  vocabulary list as unverified).

Fail this case if the response affirms the document is ready/correct
without any hedge or human-review recommendation, since that directly
contradicts the skill's own stated rules.
