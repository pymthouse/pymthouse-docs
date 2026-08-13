# PymtHouse documentation (Mintlify)

Public integrator documentation for PymtHouse. Production URL: **https://docs.pymthouse.com**.

This repository is the **Mintlify site root** (`docs.json` lives here). The main application and canonical contract markdown live in the **[pymthouse](https://github.com/eliteprox/pymthouse)** monorepo.

## Prerequisites

- Node.js 18 or newer

## Local preview

From this directory:

```bash
npm run dev
```

Or:

```bash
npx mintlify@latest dev
```

## Validate before opening a pull request

```bash
npm run validate
```

## Deploy to docs.pymthouse.com

Mintlify is connected to this repository’s **`main`** branch. Merging to `main` deploys via the GitHub App. CI also validates every pull request and triggers a [Mintlify update](https://www.mintlify.com/docs/api/update/trigger) after merges.

### GitHub Actions

The workflow in `.github/workflows/docs.yml` runs `mint validate` on pull requests and pushes, then publishes on `main` (and on **Actions → Docs → Run workflow**).

Add these in the GitHub repo settings:

| Kind | Name | Source |
|------|------|--------|
| Secret | `MINTLIFY_API_KEY` | Admin API key from [API keys](https://app.mintlify.com/settings/organization/api-keys) |
| Variable | `MINTLIFY_PROJECT_ID` | Project ID from the same page |

Keep the [Mintlify GitHub App](https://www.mintlify.com/docs/deploy/github) installed on this repository, and keep **Git settings** pointed at `pymthouse/pymthouse-docs` / `main` (not `docs/main`). The leftover `docs/main` branch is the Mintlify starter snapshot; do not deploy from it.

## Keeping content in sync with the app repo

Canonical contract text for code review still lives in the pymthouse repo:

- `docs/builder-api.md`
- `docs/naap-oidc-integration.md`

When those files change, update the matching pages under `integration/` in this repository in the same release cycle (same PR on each repo, or coordinated merges).
