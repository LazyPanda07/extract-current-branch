# Extract-Current-Branch

Extract current branch and set to CURRENT_BRANCH env variable  
Uses PowerShell for extracting variable

# Usage
See [action.yml](https://github.com/LazyPanda07/extract-current-branch/blob/master/action.yml)

# Example
```yml
name: Test

on:
  push:
    branches: [dev, distribute]

jobs:
  test:
    runs-on: windows-latest

    steps:
    - uses: actions/checkout@v3

    - uses: LazyPanda07/extract-current-branch@v1.0.0

    - name: Print branch
      run: echo ${{ env.CURRENT_BRANCH }} # print dev or distribute

    - uses: LazyPanda07/extract-current-branch@v1.0.0
      with:
        variable-name: custom-branch # override default variable name to custom-branch

    - name: Print custom branch
      run: echo ${{ env.custom-branch }} # print dev or distribute
```
