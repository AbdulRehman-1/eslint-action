# ESLint Test

> This is a GitHub Action that use airbnb style guide to lint JavaScript and TypeScript projects in a pull request with inline error and warning annotations, By default it uses the airbnb and eslint recommended rules if your project doesn't have `.eslintrc` file.

![Lint](https://github.com/AbdulRehman-1/eslint-action/workflows/Lint/badge.svg)

![Annotation](assets/annotation.png)

## Usage

`.github/workflows/lint.yml`:

```yml
name: Lint

on:
  pull_request:
  push:
    branches:
      - main

jobs:
  eslint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-node@v3
        with:
          node-version: 16
      - name: ESLint Test
        uses: AbdulRehman-1/eslint-action@latest
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }} # Optional
          eslint-args: '--ignore-path=.gitignore'
          eslintrc: false # Set this to true if you want to use your own .eslintrc rules
          extensions: 'js,jsx,ts,tsx'
          auto-auto-fix-before-test: false # Set this to true if want to format and fix all the lint issue before testing
          annotations: true
```

## Common Issues

- Yarn 2+ is not supported

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## Infos

- Use `AbdulRehman-1/eslint-action@latest` to get the latest none development version of ESLint Test.

- Please report everything like bugs by creating an [issue](https://github.com/AbdulRehman-1/eslint-action/issues/new/choose).

## Author

**eslint-action** © [Abdul Rehman](https://github.com/AbdulRehman-1)  
Authored and maintained by Abdul Rehman.
