# action-fossa
Composite actions for FOSSA operations at Replicated

## install
Installs the FOSSA CLI.

###
### Usage
```yaml
jobs:
  fossa-scan:
    runs-on: ubuntu-latest
    steps:
      - uses: replicatedhq/action-fossa/install@v1
```

### inputs
#### version
The version of the FOSSA CLI to install, e.g. '3.6.0'. Default is set to latest tested version

#### sha256sum
The SHA256 checksum for the archive file for the selected version. Used to verify the archive.

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


