# PymtHouse documentation (Mintlify)

Public integrator documentation for PymtHouse. Production URL: **https://docs.pymthouse.com**.

This repository is the **Mintlify site root** (`docs.json` lives here). The main application and canonical contract markdown live in the **[pymthouse](https://github.com/pymthouse/pymthouse)** monorepo.

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

1. Create a Mintlify account and install the [Mintlify GitHub app](https://mintlify.com/docs/settings/github) on this repository.
2. In the [Mintlify dashboard](https://dashboard.mintlify.com), create a deployment that points at **this** repository. Set the **docs root** to the **repository root** (the directory that contains `docs.json`).
3. Under **Custom domain**, add `docs.pymthouse.com` and complete the DNS steps Mintlify provides (typically a `CNAME` to Mintlify’s target).
4. Push changes to your default branch; Mintlify deploys on merge.

## Keeping content in sync with the app repo

Canonical contract text for code review still lives in the pymthouse repo:

- `docs/builder-api.md`

When that file changes, update the matching pages under `integration/` and `api-reference/` in this repository in the same release cycle (same PR on each repo, or coordinated merges).

Machine-readable endpoints are also available on every deployment:

- `GET /api/v1/openapi.json`
- `GET /api/v1/docs` (Scalar UI)
