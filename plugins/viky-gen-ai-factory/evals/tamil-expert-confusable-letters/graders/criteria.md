---
type: llm
weight: 1
---

SKILL.md section 3 gives verified example pairs for this exact
confusion: ல/ள/ழ (வால் tail, வாள் sword, வாழ் live; கலை art, களை weed,
கழை bamboo), and section 3 also states native words don't begin with
ட, ற, ர, ல, ழ, ள, ண or ன (this response only needs the ழ/ள half of that,
per what was asked).

A successful response:
- Explains the three sounds are meaningfully distinct (not just
  spelling variants of "the same" letter).
- Gives correct example word pairs that actually differ in meaning by
  this letter alone - either the ones from SKILL.md above, or other
  genuinely correct minimal pairs. It should NOT invent a pair that
  doesn't actually work (e.g. two words that don't really differ only
  by ல/ள/ழ, or a meaning gloss that's wrong).
- States that native Tamil words don't begin with ழ or ள, and that a
  word appearing to start with one of these is either a name, a loanword
  that kept it, or (worth flagging) possibly a spelling mistake worth
  double-checking.
- Doesn't overclaim precision it doesn't have (e.g. doesn't claim there
  are zero exceptions) - some hedging on edge cases is fine and expected
  per the skill's own rules against overclaiming.

Fail this case if it gives a wrong example pair (words that don't
actually differ only by that letter, or an incorrect meaning), or
states the letters are interchangeable, or omits the word-beginning
rule entirely despite being asked about it directly.
