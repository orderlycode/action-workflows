# act.yml
input:
- registry: string # docker registry url

secrets:
- DOCKER_REGISTRY_USERNAME # registry username
- DOCKER_REGISTRY_PASSWORD # registry password
- K8S_STAGING # k8s config for staging
- K8S_PROD # k8s config for production

# Usage
```yaml
on:
  push:
    branches:
      - main
jobs:
  Act:
    permissions:
      contents: write
    uses: orderlycode/action-workflows/.github/workflows/act.yml@main
    secrets: inherit
    with:
      registry: hub.orderlycode.com
```
