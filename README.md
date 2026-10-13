# gen-ai-experiments

A home for gen-AI experiments: skills, agents, prompts, and small tools —
not tied to one coding assistant. Anything added here should work with
whichever of these you use:

- **[Claude Code](https://claude.ai/code)** — skills/plugins via
  `SKILL.md` + `.claude-plugin/plugin.json`, this repo doubling as a
  **plugin marketplace** (see Install below), and repo guidance in
  [`CLAUDE.md`](CLAUDE.md).
- **[Codex](https://developers.openai.com/codex)** and
  **[Kiro](https://kiro.dev)** — both read [`AGENTS.md`](AGENTS.md) for
  repo/agent guidance (the emerging cross-tool convention). Claude Code
  reads it too when there's no `CLAUDE.md`.

Not every experiment here will be a Claude Code plugin — some may just be
a script, a prompt, or notes. The marketplace section below only covers
the ones packaged as installable plugins.

## Plugins (Claude Code marketplace)

This repo is a Claude Code plugin marketplace
(`.claude-plugin/marketplace.json`). Anyone can install from it — you
don't need to clone the repo or have push access.

| Plugin | What it does |
|---|---|
| [`viky-gen-ai-factory`](plugins/viky-gen-ai-factory) | A growing collection of skills: [`indian-law-factory`](plugins/viky-gen-ai-factory/skills/indian-law-factory) — a citizen-friendly Indian law guide for people with no lawyer: describe any scenario and it works out which law applies on those dates (BNS/BNSS/BSA vs IPC/CrPC, both numbers), the offences that could be made out and what each needs to be proved, lawful defence options, your rights on FIR/arrest/bail, and the free legal-aid route. Includes the full text of all 358 BNS sections with notes, an IPC→BNS index for every IPC section (each mapping labelled official chart or wording match), a plain-words table of ~80 common offences, verified helplines, maintenance and alimony case law, an A-to-Z key-laws map, 13 legal domains with landmark cases, and a live-research protocol for everything else. [`tamil-language-expert`](plugins/viky-gen-ai-factory/skills/tamil-language-expert) — careful Tamil writing, translating, proofreading, spelling/grammar checklists, and legal/formal Tamil documents. |

### Install

In Claude Code or Cowork:

```
/plugin marketplace add vigne-Sh/gen-ai-experiments
/plugin install viky-gen-ai-factory@gen-ai-experiments
```

Then use a skill directly — `/viky-gen-ai-factory:indian-law-factory` or `/viky-gen-ai-factory:tamil-language-expert` — or just ask; both trigger automatically on the right kind of question.

Verified working end to end (Claude Code 2.1.278): adding the marketplace
from a fresh clone, installing the plugin from it, and confirming
`claude plugin list` shows it enabled with both skills in the
component inventory (`claude plugin details viky-gen-ai-factory`).

### Eval suite

`plugins/viky-gen-ai-factory/evals/` has 29 behavioural test cases run with
`claude plugin eval` and graded by an LLM judge. Results below are from
2026-10-13 (Claude Code 2.1.296), reported as measured — including what
failed and every change made to the tests themselves.

- **Full run, session default model: 26 of 29 passed.** The three failures
  were fixed in the skill and each re-run three times:
  - *no-fabrication* 3/3 — it now says where each helpline number was
    checked, so a correct number does not look invented;
  - *labour-code date trap* 3/3 — it now explains why articles online
    conflict (when a law was passed vs. when it came into force);
  - *scared first-time user* 2/3 — it now explains every legal word in
    brackets; one run in three still leaves a term unexplained.
- **Does the plugin make answers more accurate? Measured with and without
  it on a smaller model** (10 section-number cases, 2 runs each): **17/20
  with the plugin, 12/20 without.** The plain model gave wrong numbers for
  kidnapping (IPC 363) and false accusation, among others. One case
  exposed a rubric bug: the judge passed an answer that gave mob lynching
  (BNS 103(2)) a "seven years" punishment that is not in the enacted text.
  After fixing the rubric to check the punishment, that case scored **2/3
  with the plugin and 0/3 without** (all three plain answers had the
  wrong punishment; the skill now reads punishments from the Gazette text).
- **New in this release, all passed first time:** quoting BNS 304
  (snatching) word for word from the full text, a balanced maintenance
  answer that does not repeat the "qualified wives get nothing" claim,
  and two section-number cases from the official chart.
- **Changes to the tests, disclosed:** the privacy-case turn limit was
  raised from 6 to 8 (the model ran out of turns reading files); the
  judge is given the list of verified helpline numbers, since it cannot
  see the skill's files; the bounced-cheque case no longer requires
  naming the procedure code; the mob-lynching case now requires the
  correct punishment and treats "no IPC equivalent" as nice to have.
- **Known limit — it needs an India cue to fire.** A prompt that only says
  "we live in Salem" did not trigger it; "Salem, Tamil Nadu" did. You can
  always invoke it directly with `/viky-gen-ai-factory:indian-law-factory`.

Re-run it yourself from `plugins/viky-gen-ai-factory/`:
```bash
claude plugin eval . --trust-plugin --runs 1 --no-publish
claude plugin eval . --trust-plugin --runs 2 --ablation with-without --case "indian-law-uplift-*"
```

## Disclaimer

`indian-law-factory` provides general legal information, **not legal advice**. It is not a substitute for a licensed advocate. Laws, helpline numbers and contact details change; verify them on official sources before relying on them. Free legal aid is available through the Legal Services Authorities (NALSA 15100).

`tamil-language-expert` is a language-learning and reference aid, not an
academic source or a certified grammar/spell checker — its own
`REFERENCES.md` says plainly what's independently verified vs. carried
over from general knowledge, and it always recommends a fluent human
reader before relying on it for anything formal, legal, or public.

## License

MIT, see [LICENSE](LICENSE).
