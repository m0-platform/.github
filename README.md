# .github

Org community files, plus the **public** Gitleaks reusable workflow.

Public repositories cannot call reusable workflows in private
[`m0-pipelines`](https://github.com/m0-platform/m0-pipelines). Call this repo instead:

```yaml
jobs:
  secret-scan:
    permissions:
      contents: read
    uses: m0-platform/.github/.github/workflows/secret-scan.yml@main
```

See [`examples/secret-scan/calling-repo-security.yml`](examples/secret-scan/calling-repo-security.yml).

Org baseline: [`.github/actions/secret-scan/gitleaks.toml`](.github/actions/secret-scan/gitleaks.toml)

Pin `@main` so rule changes land without a SHA bump in every caller. Repo-level
`.gitleaks.toml` should keep `useDefault = true` (allow-lists only).
