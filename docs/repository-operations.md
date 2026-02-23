# Repository Operations

This repository mixes two categories of artifacts:

1. Default files inherited by org repositories.
2. Maintainer-run templates and helper assets.

## Inherited Defaults

- `.github/CONTRIBUTING.md`
- `.github/PULL_REQUEST_TEMPLATE.md`
- `.github/ISSUE_TEMPLATE/*`

These are used only when a target repository does not provide its own file.

## Maintainer-Run Templates

- `.github/settings.yml` for repository settings and labels (via settings automation).
- `.github/ruleset.json` for branch ruleset creation (via `gh api`).
- `.github/CODEOWNERS` as a source template to copy per repository when needed.
- `skills/zr-github-defaults/SKILL.md` for repo-specific agent behavior.

These are not applied automatically by GitHub.

## Release Checklist For This Repo

- `.github` repository visibility is public.
- Required assets referenced by docs exist (`.github/zr-gh.png`, `LICENSE`, linked docs).
- Issue template labels are defined in `.github/settings.yml`.
- `.github/ruleset.json` is valid against current REST API schema.
- `@zenon-red/zoe` exists and has intended repository access.
- Canonical agent guidance is at `skills/zr-github-defaults/SKILL.md`.
