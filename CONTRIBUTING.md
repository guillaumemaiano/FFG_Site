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

## Note

If you encounter any issue, ask a more experienced team member before spending time troubleshooting. There's no point repeating mistakes the team has already solved.