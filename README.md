# Helm Validator

GitHub action for linting and validating charts

# Usage

Add a step to any existing GitHub Action, setting the `chartPath` variable to the specific sub directory relative to the repositories root where the chart you want to validate resides, e.g.

```yaml
name: CI

on: push

jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - id: validate
        uses: elifesciences/helm-validator-action@master
        with:
          chartPath: 'helm/basex-validator'
```

If you want to validate a chart against a specific kubernetes version, set `kubernetesVersion` to the desired version, e.g.

```yaml
  with:
    kubernetesVersion: '1.22.0'
```
If you want to use a specific version of helm, set `helmVersion` to the desirect version, e.g.

```yaml
  with:
    helmVersion: '2.13.1'
```

# License

Licensed under [MIT](https://choosealicense.com/licenses/mit/)
