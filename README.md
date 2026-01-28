# my-npm-test

> Test npm package with Cursor-powered GitHub Actions for automated documentation and fixes.

## Overview

This repository is an npm package that integrates with GitHub Actions to run Cursor Agent workflows. It uses shared actions from the organization to apply automated changes (e.g., documentation updates) and open pull requests.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [GitHub Actions](#github-actions)
- [Project Structure](#project-structure)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

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

```javascript
// Example usage when applicable
const pkg = require('my-npm-test');
```

## GitHub Actions

### Apply changes and open PR

The workflow **Apply changes and open PR** (`cursor-open-pr.yml`) can be run manually from the **Actions** tab. It:

1. Checks out this repo and the private shared-actions repository
2. Runs the **Cursor Agent Fix** action with a prompt you provide
3. Opens a pull request from branch `cursor/auto-fixes` if there are changes

**Required inputs:**

| Input          | Type   | Description                          |
|----------------|--------|--------------------------------------|
| `port_context` | string | JSON context including `runId`       |

**Required secrets:**

- `PRIVATE_ACTION_TOKEN` – token with access to the shared-actions repo
- `CURSOR_API_KEY` – API key for the Cursor agent
- `GITHUB_TOKEN` – provided by GitHub for the workflow

### Shared actions

Reusable actions are loaded from `org-shared-actions` into `.github/shared-actions/`. The **Cursor Agent Fix** action runs the Cursor CLI with a given prompt and model.

## Project Structure

```
.
├── .github/
│   ├── shared-actions/          # Reusable actions (from org-shared-actions)
│   │   └── .github/actions/
│   │       └── cursor-agent-fix/
│   └── workflows/
│       └── cursor-open-pr.yml   # Manual workflow: Cursor fix + PR
├── package.json
├── package-lock.json
└── README.md
```

## Development

### Scripts

| Command   | Description                    |
|----------|--------------------------------|
| `npm test` | Runs the test script (placeholder) |

### Local setup

1. Clone the repository.
2. Run `npm install`.
3. Use the **Apply changes and open PR** workflow from the Actions tab when you want to run Cursor-based updates.

## Contributing

1. Open an issue or discuss the change first if it’s large.
2. Fork the repo, create a branch, make your changes.
3. Ensure any new logic is covered by tests or scripts where applicable.
4. Open a pull request toward the default branch.

## License

ISC © [Repository maintainers](https://github.com/hq-secuity-test/my-npm-test)

---

**Links:** [Repository](https://github.com/hq-secuity-test/my-npm-test) · [Issues](https://github.com/hq-secuity-test/my-npm-test/issues)
