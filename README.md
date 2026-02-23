<div align="center">
<img width="128px" alt="zenon-red logo" src="./.github/zr-gh.png">

# GitHub

<p align="center">
Shared GitHub configuration for the ZENON Red organization.<br/>
Issue templates, PR templates, and repository automation.<br/>
Built by Aliens.
</p>

</div>

## Why

This repository centralizes shared GitHub standards for the zenon-red organization. It combines default files (which GitHub can inherit automatically) with operational templates used by @zenon-red/zoe when bootstrapping new repositories.

Important: for organization-wide default templates to work, the `.github` repository must be public.

<p align="center">
  <a href="./.github/CONTRIBUTING.md">Contributing</a> ·
  <a href="./.github/PULL_REQUEST_TEMPLATE.md">PR Template</a> ·
  <a href="./.github/ISSUE_TEMPLATE">Issue Templates</a> ·
  <a href="./docs/repository-operations.md">Operations</a>
</p>

## Usage

### What This Repository Provides

| File/Directory | Purpose | Applied automatically by GitHub |
|----------------|---------|----------------------------------|
| `.github/CODEOWNERS` | Repo ownership map + copy template | No |
| `.github/CONTRIBUTING.md` | Default contribution guide | Yes (fallback) |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default PR template | Yes (fallback) |
| `.github/ISSUE_TEMPLATE/` | Default issue forms | Yes (fallback) |
| `.github/workflows/` | Local workflow examples | No |
| `.github/settings.yml` | Repo settings/labels template | No |
| `.github/ruleset.json` | Branch ruleset payload template | No |
| `docs/` | Ops and publishing docs | No |
| `skills/` | Agent instructions | No |

### Applying Repository Rules

Use the ruleset template to protect the default branch in a target repository:

```bash
gh api repos/zenon-red/<repo>/rulesets -X POST --input .github/ruleset.json
```

Replace `<repo>` with the target repository name.

### Available Issue Templates

- **Bug Report** - Structured template for reporting bugs
- **Feature Request** - Template for proposing new features  
- **Task** - Template for development tasks
- **Documentation** - Template for documentation improvements

## Contributing

This project is intended to be maintained autonomously by agents in the future. Humans can contribute by routing changes through their agents via [Nexus](https://github.com/zenon-red/nexus). See [CONTRIBUTING.md](./.github/CONTRIBUTING.md) for details.

## License

[MIT](./LICENSE)
