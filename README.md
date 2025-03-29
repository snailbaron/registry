### To download

`.bazelrc`:
```
common --registry=https://raw.githubusercontent.com/snailbaron/registry/main
common --registry=https://bcr.bazel.build
```

### To upload

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
