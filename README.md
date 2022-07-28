# instruqt-workflows

This repo contains shared Github Action Workflows for tracks hosted on the Instruqt platform.

## Calling a reusable workflow

### :sparkles: .github/workflows/instruqt-deploy-dev.yml

:key: Secret Requirements

* INSTRUQT_API_KEY

* INSTRUQT_ORG_SLUG

* INSTRUQT_TOKEN

:jigsaw: Job Configuration Example

```yaml
jobs:
  instruqt-deploy-dev:
    if: |
      github.event.pull_request.merged ||
      github.event.inputs.run-manually == 'true'
    uses: nsthompson/instruqt-workflows/.github/workflows/instruqt-deploy-dev.yml@main
    secrets:
      INSTRUQT_API_KEY: ${{ secrets.INSTRUQT_API_KEY }}
      INSTRUQT_ORG_SLUG: ${{ secrets.INSTRUQT_ORG_SLUG }}
      INSTRUQT_TOKEN: ${{ secrets.INSTRUQT_TOKEN }}
```

### :sparkles: .github/workflows/instruqt-deploy-prod.yml

:key: Secret Requirements

* INSTRUQT_API_KEY

* INSTRUQT_ORG_SLUG

* INSTRUQT_TOKEN

:jigsaw: Job Configuration Example

```yaml
jobs:
  instruqt-deploy-prod:
    if: |
      github.event.pull_request.merged ||
      github.event.inputs.run-manually == 'true'
    uses: nsthompson/instruqt-workflows/.github/workflows/instruqt-deploy-prod.yml@main
    secrets:
      INSTRUQT_API_KEY: ${{ secrets.INSTRUQT_API_KEY }}
      INSTRUQT_ORG_SLUG: ${{ secrets.INSTRUQT_ORG_SLUG }}
      INSTRUQT_TOKEN: ${{ secrets.INSTRUQT_TOKEN }}
```

### :sparkles: .github/workflows/instruqt-nightly-test.yml

:key: Secret Requirements

* INSTRUQT_API_KEY

* INSTRUQT_ORG_SLUG

* INSTRUQT_TOKEN

:jigsaw: Job Configuration Example

```yaml
jobs:
  instruqt-nightly-test:
    uses: nsthompson/instruqt-workflows/.github/workflows/instruqt-nightly-test.yml@main
    secrets:
      INSTRUQT_API_KEY: ${{ secrets.INSTRUQT_API_KEY }}
      INSTRUQT_ORG_SLUG: ${{ secrets.INSTRUQT_ORG_SLUG }}
      INSTRUQT_TOKEN: ${{ secrets.INSTRUQT_TOKEN }}
```

## Contributors

* Nick Thompson ([@nsthompson](https://github.com/nsthompson))
