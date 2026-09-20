# Memory

Standing preferences for Claude Code sessions working in this repository
(and, by extension, other repos owned by vigne-Sh where the same identity
question comes up):

- **Commit authorship**: always set the local git `user.name`/`user.email`
  to the user's own identity before committing, not the sandbox's default
  (`Claude <noreply@anthropic.com>`). Use the GitHub privacy alias that
  already appears on this repo's own commits:
  `Vignesh Srinivasan <34839394+vigne-Sh@users.noreply.github.com>`.
  This is set per-repo (`git config user.name`/`user.email`, no `--global`)
  since the sandbox's SessionStart hook resets the global git identity on
  every session start for commit-signing reasons.
- The `Co-Authored-By: Claude ...` / `Claude-Session: ...` trailers that
  Claude Code appends to commit messages stay — this records AI
  involvement in the commit's author identity, not the fact that Claude
  helped write it.
