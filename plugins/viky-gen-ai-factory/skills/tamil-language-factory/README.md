# tamil-language-factory

A Claude Code skill for Tamil language help: translation, reading and
working with Tamil documents, the Tamil script, Tamil grammar, and Tamil
history.

Part of the [`viky-gen-ai-factory`](../..) plugin in the
[`gen-ai-experiments`](../../../..) marketplace.

## What it does

- **Translation** (English↔Tamil and other pairs): Tamil script, a
  transliteration (states which scheme), and a natural translation - not
  just a literal word-for-word gloss. Flags idioms and honorifics that
  don't carry over directly.
- **Document work**: reads a shared document in full before answering; if
  a scanned/OCR'd document has an ambiguous character, says so instead of
  silently guessing.
- **Script**: explains the uyir/mei/uyirmei letter system (247 letters
  total) and how Tamil is romanized.
- **Grammar**: case system, agglutination, sandhi, word order - and the
  real gap between spoken and literary Tamil grammar.
- **History**: Dravidian language family, the Tolkāppiyam, Sangam
  literature, script evolution, and Tamil's 2004 classical-language
  status - flagging genuinely disputed dates as disputed rather than
  picking one.

## What it does not do

- It does not invent Tamil quotations, proverbs, or verses and attribute
  them to a real source - it says when something isn't verified, or
  offers to look it up live.
- It does not treat one register (spoken vs. literary) or one regional
  variety (Tamil Nadu vs. Sri Lankan vs. Malaysian/Singapore Tamil) as
  the unmarked default without saying so.

## Install

```
/plugin marketplace add vigne-Sh/gen-ai-experiments
/plugin install viky-gen-ai-factory@gen-ai-experiments
```

Then invoke it with `/viky-gen-ai-factory:tamil-language-factory`, or
just ask a Tamil translation/script/grammar/history question, or share a
Tamil document.

## Files

- [`SKILL.md`](SKILL.md) — the skill definition Claude Code loads.
- [`REFERENCES.md`](REFERENCES.md) — the specific historical and script
  facts the skill relies on, each checked against a live source rather
  than taken from model memory, with the date checked.
