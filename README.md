# treetrum Renovate config

This repository stores the shared Renovate preset used by multiple repositories.

## Usage

In each consumer repository, set the Renovate config to:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>treetrum/renovate-config"]
}
```

Renovate loads `default.json` from this repository automatically.

## Notable defaults

- npm dependencies are pinned by default.
- Updates have a one-day minimum release age. Docker updates without release timestamps are allowed through instead of remaining pending indefinitely.
- Baseline policy for all updates: no automerge and request `@treetrum` as reviewer.
- Exceptions:
  - All patch updates, including Docker and npm dependencies, are set to automerge after required status checks pass, with reviewer assignment skipped.
  - npm `devDependencies` minor updates are set to automerge after required status checks pass, with reviewer assignment skipped.
  - pnpm package-manager updates are set to automerge after required status checks pass, with reviewer assignment skipped.
