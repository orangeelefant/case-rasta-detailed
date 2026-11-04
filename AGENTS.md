# AGENTS.md

Instructions for automation agents (Claude Code, Codex and similar) working in this repository.

## Repository

- **Location:** `orangeelefant/case-rasta-detailed`
- **Status:** archived. The maintained copy is `orangeelefant/case-studies`, folder `rasta-detailed/`.
- **Contents:** Webraketen case study for Rastahunden (detailed write-up), Markdown only
- **Live site:** https://rastahunden.com

## Rules

- Markdown only. There is no build, no test suite and no dependencies.
- Keep every outbound link to a client or partner site, with the same URL and the same anchor text.
- Push directly to `main`. One logical change per commit.
- Add a line under `## [Unreleased]` in `CHANGELOG.md` for every content change.
- No credentials, private contact details or internal file paths.
- `README.md` ends with the shared Webraketen footer. Keep it as the last block.
