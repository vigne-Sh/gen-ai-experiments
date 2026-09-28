# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this repo is

A catch-all for gen-AI experiments — not limited to one packaging format
or one coding assistant. It also doubles as a **Claude Code plugin
marketplace**: `.claude-plugin/marketplace.json` at the repo root lists
every installable plugin under `plugins/`.

See [`AGENTS.md`](AGENTS.md) for the tool-agnostic version of this
guidance (Codex, Kiro, and other agents that read `AGENTS.md` instead of
`CLAUDE.md`). Keep the two in sync when either changes.

## Layout

```
.claude-plugin/marketplace.json   # marketplace manifest (lists all plugins below)
plugins/
  <plugin-name>/
    .claude-plugin/plugin.json    # plugin manifest
    skills/
      <skill-name>/SKILL.md       # one or more skills per plugin
```

A plugin can bundle more than one skill — `viky-gen-ai-factory` is
meant to grow this way rather than spinning up a new plugin per skill.
Only split out a new plugin when a skill needs its own version/release
cadence independent of the others.

## Adding a new skill

1. Decide whether it belongs inside `plugins/viky-gen-ai-factory/skills/`
   (the general growing collection) or warrants its own plugin directory.
2. Write `SKILL.md` with YAML frontmatter (`name`, `description` — the
   description is what triggers the skill, so make it specific about when
   to use it).
3. If it's a new plugin (not an addition to an existing one), add a
   `.claude-plugin/plugin.json` manifest and a new entry in the root
   `.claude-plugin/marketplace.json`.
4. Validate before committing:
   ```bash
   python3 -c "import json; json.load(open('.claude-plugin/marketplace.json'))"
   claude plugin marketplace add .   # validates the manifest against a local path
   ```
5. Add or extend eval cases under `plugins/viky-gen-ai-factory/evals/`
   (one directory per case: `prompt.md` + `graders/criteria.md` — see the
   existing cases for the format) covering the specific failure mode the
   skill needs to avoid (fabricating a citation/contact detail, claiming
   false certainty, etc. — not just "does it answer the question").
   Run it before committing:
   ```bash
   cd plugins/viky-gen-ai-factory
   claude plugin eval . --trust-plugin --runs 1 --no-publish
   ```
   A skill without at least one eval case testing its stated failure
   modes is unverified in practice, not just untested in principle —
   don't treat "it compiles and the manifest validates" as sufficient on
   its own.
6. Update the plugin table in `README.md` and `AGENTS.md`.

## Commit identity

Commit as the repo owner's identity, not the sandbox default
(`Claude <noreply@anthropic.com>`) — set per-repo, since a session-start
hook resets the global git identity every session:
```bash
git config user.name "Vignesh Srinivasan"
git config user.email "34839394+vigne-Sh@users.noreply.github.com"
```
See [`memory.md`](memory.md) for the standing note on this. The
`Co-Authored-By: Claude ...` trailer Claude Code appends to commit
messages stays regardless — it discloses AI involvement, which is
separate from author identity.

## Non-goals

Don't assume every experiment in this repo is or should become a Claude
Code plugin. Scripts, prompts, and notes that aren't packaged that way
are fine — they just won't show up in `marketplace.json` or the README's
plugin table.
