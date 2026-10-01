<!--
document: CONTRIBUTING
scope: contributors
status: active
version: 1.0
updated: 2026-10-01T20:00+02:00
-->

# Welcome

## Development setup

Before making your first commit, configure the repository to use the Git hooks provided in `.githooks/`:

```bash
git config core.hooksPath .githooks
```

> **Linux/macOS:** if necessary, make the hook executable:

```bash
chmod +x .githooks/pre-commit
```

The hooks are intentionally **not installed automatically**. Since they modify your local Git configuration, each contributor is expected to enable them explicitly.

The provided `pre-commit` hook prevents accidental commits directly to the `main` branch.

## Branches

Do not work directly on `main`.

Create a dedicated branch for each change. Branch names use a short category prefix followed by a descriptive name:

- `fix/<short-description>` — bug fixes
- `issue/<issue-number>` — work associated with a GitHub issue
- `docs/<short-description>` — documentation
- `feature/<short-description>` — new functionality
- `content/<short-description>` — site or editorial content
- `refactor/<short-description>` — structural changes without intended functional changes

Examples:

```text
fix/mobile-navigation
issue/42
docs/development-setup
feature/project-filtering
content/beaumont-page
refactor/project-layout
```

Use lowercase names and separate words with hyphens.

## Note

If you encounter any issue, ask a more experienced team member before spending time troubleshooting. There's no point repeating mistakes the team has already solved.