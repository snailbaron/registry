### To download

`.bazelrc`:
```
common --registry=https://raw.githubusercontent.com/snailbaron/registry/main
common --registry=https://bcr.bazel.build
```

### To upload

> [!WARNING]
> This workflow will happily overwrite existing versions in the registry with new commits.

`.github/workflows/ci.yaml`:
```yaml
# yaml-language-server: $schema=https://json.schemastore.org/github-workflow.json
name: CI

on:
  push:
    branches:
      - main
  workflow_dispatch:

jobs:
  publish:
    uses: snailbaron/actions/.github/workflows/publish-to-registry.yaml@main
    secrets:
      token: ${{ secrets.TOKEN }}
```
