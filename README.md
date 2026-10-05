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

`plugins/viky-gen-ai-factory/evals/` has 25 behavioral test cases run via
`claude plugin eval`, graded by an LLM judge. Latest full run
(2026-10-05, Claude Code 2.1.283): **25/25 passed**. What those numbers do
and do not show, reported without spin:

- **Factual accuracy: no measurable advantage over the base model.** On 19
  fact-and-behaviour cases (including obscure ones such as BNS 137 vs 139,
  BNSS 479's one-third rule, hit-and-run BNS 106(2), mob-lynching 103(2)),
  the plugin scored 19/19 and the plain model 18/19 — and that single
  difference is a case that flips between runs anyway. This model already
  knows these facts; the skill's references mainly make the answers
  checkable and consistent.
- **Procedure adherence: a clear, measured effect.** For the six-step citizen
  procedure (ask missing facts → law by date with old+new numbers → what
  must be proved → lawful options → what not to do → next step + free legal
  aid + not-legal-advice), the plain model passed **0 of 8** runs. The plugin
  passed 5 of 8 at first; I tightened step 1 and it passed 12 of 12 on those
  same four scenarios — so that figure is partly tuned to them. On two
  scenarios I had *not* tuned against, the plugin passed 5 of 5 runs and the
  plain model 0 of 5. The rubric is the skill's own spec, so this proves the
  skill changes behaviour as intended, not that the behaviour is the best
  possible.
- **Known limit — it needs an India cue to fire.** A prompt that says only
  "we live in Salem" (no state, rupees, FIR, or police-station cue) did not
  trigger the skill in either of two runs; the model assumed the US. With
  "Salem, Tamil Nadu" it fired every time. Users can always invoke it
  directly with `/viky-gen-ai-factory:indian-law-factory`.
- Two rubric clarifications were made after judge flakiness (required vs
  nice-to-have items); `indian-law-no-fabrication` still flips between runs
  (about 2 of 3).

Re-run it yourself from `plugins/viky-gen-ai-factory/`:
```bash
claude plugin eval . --trust-plugin --runs 1 --no-publish
claude plugin eval . --trust-plugin --runs 2 --ablation with-without   # shows the with/without gap
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
