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
- npm `devDependencies` patch/minor updates are set to automerge after required status checks pass.
- Non-npm dependencies keep Renovate's manager defaults for range behavior.
