# tamil-language-expert

A Claude Code skill for careful Tamil (தமிழ்) writing, translation,
proofreading, and document work — distinct from
[`tamil-language-factory`](../tamil-language-factory) (translation,
script/grammar overview, and Tamil history). This one is focused on the
practical checklists a fluent-Tamil writer or editor actually runs:
spelling confusions, consonant-doubling at word boundaries, legal/formal
vocabulary, and file-level mechanics (fonts, Unicode, rendering).

Part of the [`viky-gen-ai-factory`](../..) plugin in the
[`gen-ai-experiments`](../../../..) marketplace.

## What it does

- Explains the Tamil letter system (uyir/mei/aaythu/uyirmei) and the
  spelling rules that follow from it.
- Gives checklists for common confusable letters (ல/ள/ழ, ன/ண/ந, ர/ற,
  short vs. long vowels) and consonant-doubling at word boundaries (வலி
  மிகுதல்) — explicit about which cases it is and isn't confident about.
- Gives templates and vocabulary for formal letters, petitions, and legal
  Tamil documents.
- Gives mechanical checks for Tamil files: fonts, Unicode, rendering,
  consistency between an English and a Tamil version of the same
  document.
- Points to where to verify anything uncertain (Tamil Virtual Academy,
  Tamil Nadu government glossaries, Tamil spellcheck in Google Docs/Word,
  a fluent human reader).

## What it does not do

This is a guide, not a certified Tamil grammar checker or dictionary — it
has no dictionary or grammar engine behind it. It is written to be honest
about its own limits: it tells the agent using it to never claim a
document is free of spelling or grammar mistakes, and to recommend a
fluent human reader for anything formal, legal, or public. See
`REFERENCES.md` for exactly which parts of `SKILL.md` are verified vs.
written from general knowledge.

## Install

```
/plugin marketplace add vigne-Sh/gen-ai-experiments
/plugin install viky-gen-ai-factory@gen-ai-experiments
```

Then invoke it with `/viky-gen-ai-factory:tamil-language-expert`, or just
ask — it triggers on Tamil writing, translation, proofreading, spelling,
grammar, name transliteration, or document-building requests.

## Files

- [`SKILL.md`](SKILL.md) — the skill definition Claude Code loads.
- [`REFERENCES.md`](REFERENCES.md) — what's independently checked vs.
  carried over from the skill author's own general knowledge, and where.

## License

MIT, under this repo's root [`LICENSE`](../../../../LICENSE) — the
original standalone version of this plugin shipped without one; folding
it into this marketplace applies the marketplace's license.
