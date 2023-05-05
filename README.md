# swagger-validate-container
This repository creates a container image `swagger-validate` that has the swagget validator in-built.

## Usage
This is to be used in CI runners to validate the openapi spec yaml files or json files for the specified directory.

## GitHub Example
To use in GitHub Actions,
```yaml
name: swagger-validate
on:
  push:
    branches: [ master ]
jobs:
  build:
    container: jaymlaws/swagger-validate:latest
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: validate
      run: validate .
```

## Credits
This container image uses the [swagger-cli](https://www.npmjs.com/package/@apidevtools/swagger-cli) to validate the yaml files.