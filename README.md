# my-npm-test

[![npm version](https://img.shields.io/npm/v/my-npm-test.svg)](https://www.npmjs.com/package/my-npm-test)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

> test

A minimal npm package template with GitHub Actions for Cursor-based automation.

## Table of contents

- [Installation](#installation)
- [Usage](#usage)
- [Scripts](#scripts)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Installation

```bash
npm install my-npm-test
```

## Usage

<!-- Describe how to use the package. Example: -->

```javascript
// Add usage example here
const myNpmTest = require('my-npm-test');
```

## Scripts

| Script | Description |
|--------|-------------|
| `npm test` | Run tests (placeholder) |

## Development

This repository includes:

- **npm package** – Node project with `extjs-gpl` as a dependency.
- **GitHub Actions** – Workflow to apply changes via Cursor and open a PR:
  - **Workflow**: [`.github/workflows/cursor-open-pr.yml`](.github/workflows/cursor-open-pr.yml)  
    Triggered manually (`workflow_dispatch`) with a `port_context` input. It runs the Cursor agent and opens a PR on `cursor/auto-fixes` when there are changes.
  - **Shared actions** – Uses `hq-secuity-test/org-shared-actions` (e.g. `cursor-agent-fix`) from `.github/shared-actions/`.

Required secrets for the workflow:

- `PRIVATE_ACTION_TOKEN` – Access to the org-shared-actions repo.
- `CURSOR_API_KEY` – Cursor API key for the agent.
- `GITHUB_TOKEN` – Provided by GitHub for PR creation.

## Contributing

1. Open an [issue](https://github.com/hq-secuity-test/my-npm-test/issues) or fork the repo.
2. Create a branch, make changes, and run `npm test`.
3. Open a pull request.

## License

ISC © [Add author name or link](https://github.com/hq-secuity-test/my-npm-test)
