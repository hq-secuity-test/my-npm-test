# my-npm-test

[![npm version](https://img.shields.io/npm/v/my-npm-test.svg)](https://www.npmjs.com/package/my-npm-test)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)

> Test npm package with ExtJS and GitHub Actions automation.

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Development](#development)
- [GitHub Actions](#github-actions)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository is an npm package used for testing and experimentation. It includes:

- An **ExtJS** dependency (`extjs-gpl`)
- **GitHub Actions** workflows that use [Cursor Agent](https://cursor.com) to review and suggest changes, then open pull requests automatically

## Prerequisites

- [Node.js](https://nodejs.org/) (v14 or later recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)

## Installation

```bash
npm install my-npm-test
```

Or add to your `package.json`:

```json
{
  "dependencies": {
    "my-npm-test": "^1.0.0"
  }
}
```

## Usage

<!-- Describe how to use this package in code or as a dependency. -->

```javascript
// Example usage (customize for your package)
// const myNpmTest = require('my-npm-test');
```

## Development

### Setup

```bash
git clone https://github.com/hq-secuity-test/my-npm-test.git
cd my-npm-test
npm install
```

### Scripts

| Script   | Description                    |
| -------- | ------------------------------ |
| `npm test` | Runs tests (currently placeholder) |

### GitHub Actions

The repo uses a **Cursor-driven workflow** that:

1. Runs on **workflow_dispatch** with a `port_context` input.
2. Checks out this repo and the private shared-actions repo.
3. Runs the **Cursor Agent Fix** shared action with a configurable prompt and model.
4. Creates a PR on the `cursor/auto-fixes` branch if there are changes.

**Required secrets:**

- `PRIVATE_ACTION_TOKEN` – access to the org-shared-actions repo
- `CURSOR_API_KEY` – Cursor API key for the agent
- `GITHUB_TOKEN` – provided by Actions for PR creation

To trigger: **Actions → "apply changes and open PR" → Run workflow**, and supply the required `port_context` (JSON with `runId`, etc.).

## Contributing

1. Open an [issue](https://github.com/hq-secuity-test/my-npm-test/issues) or reuse an existing one.
2. Create a branch, make changes, and open a pull request.
3. Automated Cursor-based PRs use the `cursor/auto-fixes` branch; manual contributions can use a different branch and base.

## License

ISC © [Authors](https://github.com/hq-secuity-test/my-npm-test)

---

**Repository:** [github.com/hq-secuity-test/my-npm-test](https://github.com/hq-secuity-test/my-npm-test) · **Issues:** [Report a bug](https://github.com/hq-secuity-test/my-npm-test/issues)
