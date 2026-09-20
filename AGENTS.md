# AGENTS.md

Guidance for coding agents (Codex, Kiro, Claude Code, and others that
read this file) working in this repository.

## What this repo is

A catch-all for gen-AI experiments — not limited to one coding assistant
or one packaging format. One part of it is also a **Claude Code plugin
marketplace**: `.claude-plugin/marketplace.json` at the repo root lists
every installable plugin under `plugins/`. That part is Claude
Code-specific by necessity (plugins/skills are a Claude Code concept);
everything else in the repo should stay tool-agnostic where possible.

Claude Code reads the equivalent [`CLAUDE.md`](CLAUDE.md) instead of this
file when both are present. Keep the two in sync when either changes —
`CLAUDE.md` additionally documents the plugin/marketplace mechanics in
Claude Code's own vocabulary (skills, `/plugin` commands).

## Layout

```
.claude-plugin/marketplace.json   # Claude Code marketplace manifest
plugins/
  <plugin-name>/
    .claude-plugin/plugin.json    # Claude Code plugin manifest
    skills/
      <skill-name>/SKILL.md       # one or more skills per plugin
```

## Working in this repo

- Prefer small, self-contained additions (a script, a prompt file, a
  skill) over shared infrastructure — this is an experiments repo, not a
  framework.
- If what you're adding is a Claude Code skill, see `CLAUDE.md` for the
  plugin/marketplace-specific steps (manifest updates, validation
  commands). Skills aren't a Codex/Kiro concept, so there's nothing
  equivalent to scaffold there — just make sure whatever you add doesn't
  assume a Claude Code-only runtime unless it's explicitly under
  `plugins/`.
- Don't rewrite or delete another experiment's files to "clean up" the
  repo structure without being asked — different experiments here are
  independent and can be inconsistent with each other on purpose.

## Commit identity

Commit as the repo owner's real identity, not an assistant's default
bot identity:
```bash
git config user.name "Vignesh Srinivasan"
git config user.email "34839394+vigne-Sh@users.noreply.github.com"
```
Set this per-repo (not `--global`) since some sandboxes reset the global
git identity between sessions. See [`memory.md`](memory.md).
