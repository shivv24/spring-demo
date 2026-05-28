# Migration TODO

This repository was migrated from Bitbucket Cloud to GitHub.

## CI / CD

`bitbucket-pipelines.yml` has been preserved as-is in this repo.
**It will not run on GitHub.** Bitbucket Pipelines and GitHub Actions use
incompatible formats (different runner model, step syntax, caching, secrets).

### Next steps

1. Read `bitbucket-pipelines.yml` to understand the existing CI steps.
2. Create `.github/workflows/ci.yml` (or equivalent) using GitHub Actions syntax.
3. Migrate any Bitbucket Pipeline variables/secrets to GitHub Actions secrets
   (Settings → Secrets and variables → Actions).
4. Once the GitHub Actions workflow is working, you can delete `bitbucket-pipelines.yml`.

Ref: https://docs.github.com/en/actions/migrating-to-github-actions/manually-migrating-to-github-actions/migrating-from-bitbucket-pipelines
