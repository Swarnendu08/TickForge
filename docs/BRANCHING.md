# Branching policy

TickForge uses branch names to distinguish long-lived integration branches from temporary contributor branches.

## Retained integration branches

Use:

```text
feature/<capability>
feature/<capability>/<subfeature>
```

Examples:

```text
feature/srv6
feature/srv6/isis
```

These branches may be based on `main` or another `feature/...` branch. They are retained after pull requests are merged.

## Temporary contributor branches

Use:

```text
contrib/<owner>/<topic>
```

Examples:

```text
contrib/swarnendu/timer-api
contrib/alex/expiry-tests
```

These branches may be based on `main` or any `feature/...` branch. After a pull request is merged, the automation deletes the branch automatically.

If a contributor branch must be retained, add the `keep-branch` label to the pull request before merging.

## Naming rules

- Use lowercase letters, numbers, and hyphens.
- Keep the owner and topic short and descriptive.
- Use `main` only as the stable default branch.
- Pull requests may target `main` or a retained `feature/...` branch.
- Do not use a temporary contributor branch name for work that needs to remain as an integration branch.
