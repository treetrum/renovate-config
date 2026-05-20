# AGENTS

## Repo purpose

- This repo is a shared Renovate preset; the only functional config file is `default.json`.
- Consumer repos load this preset via `"extends": ["github>treetrum/renovate-config"]` (documented in `README.md`).

## Source of truth

- Treat `default.json` as the product; there are no app packages, build scripts, or test suites in this repo.
- Keep the schema line intact: `"$schema": "https://docs.renovatebot.com/renovate-schema.json"`.

## Current policy to preserve unless intentionally changing behavior

- Base extends: `config:recommended`, semantic commit type forced to `deps`, semantic commit scope disabled.
- Global defaults: semantic commits enabled, dependency PR label is `dependencies`, range strategy is `pin`.
- Package rules currently enforce:
  - patch updates automerge
  - `oxfmt`, `oxlint`, and `oxlint-tsgolint` automerge
  - minor/major updates request reviewer `@treetrum`

## Editing/verification workflow

- Make focused edits in `default.json`; avoid adding unrelated files or tooling unless explicitly requested.
- Before completing a task that changes Renovate config, run `npx --yes --package renovate -- renovate-config-validator default.json` and confirm it passes.
- If behavior changes, reflect it in `README.md` usage notes only when consumer-facing behavior changed.
