# erb-lint-problem-matchers-action

GitHub Action to setup [Problem Matchers](https://github.com/actions/toolkit/blob/1cc56db0ff126f4d65aeb83798852e02a2c180c3/docs/problem-matchers.md) for [ERB Lint](https://github.com/Shopify/erb-lint).

## Usage

Add this action as a step before running `erb-lint` step:

```yaml
name: lint

on:
  pull_request:
  push:
    branches:
      - master

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: ruby/setup-ruby@v1
        with:
          bundler-cache: true
          ruby-version: 2.7.2
      - uses: polydice/erb-lint-problem-matchers-action@v1
      - run: bundle exec erblint --format compact .
```

### Note

- `--format compact` is required.

### Screenshot

![screenshot](https://user-images.githubusercontent.com/14349/100225328-00fb5c00-2f59-11eb-928b-2c7378653881.png)