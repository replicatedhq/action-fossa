# action-fossa
Composite actions for FOSSA operations at Replicated
## scan
Runs the FOSSA CLI to analyze dependencies and check for license violations. FOSSA CLI must already be installed.
### Usage
```yaml
jobs:
  fossa-scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: replicatedhq/action-fossa/install@v1
      - uses: replicatedhq/action-fossa/scan@v1
        with:
          api-key: ${{ secrets.FOSSA_API_KEY }}
```

### inputs

#### api-key
The FOSSA API key to use. Push-only tokens are not recommended.

#### run-tests
Whether or not to run the test step. Defaults to true


