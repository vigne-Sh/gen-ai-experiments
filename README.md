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
| [`viky-gen-ai-factory`](plugins/viky-gen-ai-factory) | A growing collection of skills: [`indian-law-factory`](plugins/viky-gen-ai-factory/skills/indian-law-factory) — a citizen-friendly Indian law guide for people with no lawyer: describe any scenario and it works out which law applies on those dates (BNS/BNSS/BSA vs IPC/CrPC, both numbers), the offences that could be made out and what each needs to be proved, lawful defence options, your rights on FIR/arrest/bail, and the free legal-aid route. Includes a BNS↔IPC table of ~70 common offences (not all 511/358 sections — it looks up the rest live), an A-to-Z key-laws map, 13 legal domains with landmark cases, and a live-research protocol. [`tamil-language-expert`](plugins/viky-gen-ai-factory/skills/tamil-language-expert) — careful Tamil writing, translating, proofreading, spelling/grammar checklists, and legal/formal Tamil documents. |

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

`plugins/viky-gen-ai-factory/evals/` has 11 behavioral test cases run via
`claude plugin eval` — each targets a specific failure mode (fabricating
a citation or contact detail, claiming false certainty, using the wrong
code for the date, missing the labour-code enacted-vs-in-force trap),
graded by an LLM judge.

Latest results (2026-10-05, Claude Code 2.1.283), reported without spin:
- 11 cases; 10 passed on the first full run. The one miss
  (`indian-law-ip-patent-term`) was the judge being inconsistent about an
  optional point in my own grading rubric — I clarified the rubric
  (required vs nice-to-have) and it then passed 3/3. `indian-law-no-fabrication`
  is flaky at about 2 of 3.
- **A with/without-plugin ablation scored identically on every case.**
  These probes are ones the base model already handles, so they show the
  skill does no harm and keeps answers hedged and plain — they do **not**
  prove the skill adds capability. In several runs the skill's reference
  files could not be read inside the eval sandbox at all. Proving uplift
  needs cases built around facts a base model tends to get wrong
  (post-cutoff changes, unusual section numbers); that is still to do.

Re-run it yourself from `plugins/viky-gen-ai-factory/`:
```bash
claude plugin eval . --trust-plugin --runs 1 --no-publish
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
