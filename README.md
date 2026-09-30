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
| [`viky-gen-ai-factory`](plugins/viky-gen-ai-factory) | A growing collection of skills: [`indian-law-factory`](plugins/viky-gen-ai-factory/skills/indian-law-factory) — multi-domain Indian law research (constitutional, criminal, family/matrimonial, consumer, cyber/IT, corporate, tax/GST, labour, property, IP, RTI), with a live-research protocol that requires checking a specific fact before stating it rather than answering from memory, how to read sections and case judgments, official legal sources, and Tamil Nadu grievance/legal-aid channels (CM Helpline, TNSLSA, 181). [`tamil-language-expert`](plugins/viky-gen-ai-factory/skills/tamil-language-expert) — careful Tamil writing, translating, proofreading, spelling/grammar checklists, and legal/formal Tamil documents. |

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

Beyond manifest/structural checks, `plugins/viky-gen-ai-factory/evals/`
has real behavioral test cases run via `claude plugin eval` — each one
targets a specific failure mode the skill needs to avoid (fabricating a
citation or contact detail, claiming false certainty on a legal/formal
document), not just "does it answer the question". Latest run
(2026-09-28, Claude Code 2.1.283): 4/4 cases passed, all graders
unanimous across their judge votes. Re-run it yourself from
`plugins/viky-gen-ai-factory/`:
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
