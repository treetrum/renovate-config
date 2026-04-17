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
