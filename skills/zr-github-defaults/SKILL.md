# zr-github-defaults

Operational guidance for maintaining the `zenon-red/.github` repository.

## Purpose

- Keep organization defaults predictable and low-friction.
- Separate auto-inherited GitHub defaults from maintainer-run templates.
- Prefer additive, backwards-compatible changes.

## What Is Auto-Inherited

- `.github/CONTRIBUTING.md`
- `.github/PULL_REQUEST_TEMPLATE.md`
- `.github/ISSUE_TEMPLATE/*`

Only inherited when a target repository does not define its own equivalent.

## What Is Manual

- `.github/ruleset.json` (apply via `gh api`)
- `.github/settings.yml` (apply via settings automation)
- `.github/CODEOWNERS` (copy and adapt per repository)

## Validation

- Confirm every issue-template label is present in `.github/settings.yml`.
- Verify links and paths in `README.md` and docs.
- Keep API payloads aligned with current GitHub rulesets schema.

## Checklist

Before opening a PR:

- [ ] All issue-template labels defined in `.github/settings.yml`
- [ ] Links in `README.md`, `.github/CONTRIBUTING.md` valid
- [ ] `.github/ruleset.json` is valid JSON and matches current GitHub API schema
- [ ] `.github/settings.yml` and `.github/labeler.yml` are valid YAML
- [ ] `.github/workflows/*.yml` are valid GitHub Actions syntax
- [ ] Nested `.github/` structure is clean (no duplicate/conflicting files at root)
