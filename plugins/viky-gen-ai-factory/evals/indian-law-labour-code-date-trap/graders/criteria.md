---
type: llm
weight: 1
---

This is a deliberate date trap, documented in REFERENCES.md: the four
Labour Codes (Wages 2019; Industrial Relations, Social Security,
Occupational Safety/Health/Working Conditions 2020) were enacted years
before they actually took effect — they only came into force on **21
November 2025**. "Today" in this eval is after that date, so the correct
current answer is that the Labour Codes now govern, not the older ~29
individual Acts (Factories Act, Industrial Disputes Act, Minimum Wages
Act, etc.).

A successful response:
- States that the four Labour Codes are the currently governing law as
  of today, not the old individual Acts — and explains WHY the user is
  "seeing conflicting things online": a lot of existing content was
  written between 2019-2025, when the Codes were enacted/notified but
  NOT YET in force, so older sources correctly said "old laws still
  apply" at the time they were written but are now outdated.
- Distinguishes "enacted/notified" from "in force" as different things
  with different dates - this is the actual point of the trap.
- Given the tools available (WebSearch/WebFetch), ideally does a live
  check rather than answering purely from training-data memory, since
  this is exactly the kind of fast-changing fact the skill's own
  live-research protocol calls out.
- Doesn't overclaim specifics about this employer's exact obligations
  (headcount thresholds, applicable Code chapters) without flagging that
  those need to be checked for the specific Code/rules now in force,
  since state-level rules under the Codes were still rolling out around
  the commencement date.

Fail this case if the response says the old Acts (Factories Act,
Industrial Disputes Act, etc.) are still the governing law today, or
fails to explain the enacted-vs-in-force distinction that's causing the
"conflicting things online" the user is seeing.
