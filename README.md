# my-npm-test

A Node.js package for testing and development workflows, integrated with Cursor-driven automation via GitHub Actions.

## Overview

This repository provides an npm package scaffold with ExtJS dependencies and GitHub Actions that use a shared Cursor agent to apply automated fixes and open pull requests.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Repository Structure](#repository-structure)
- [Development & Automation](#development--automation)
- [Contributing](#contributing)
- [License](#license)

## Installation

Install the package from the project directory:

```bash
npm install
```

Or add as a dependency in another project:

```bash
npm install <package-name-or-path>
```

## Usage

After installation, the package entry point is `index.js` (as defined in `package.json`). Ensure Node.js and npm are available in your environment.

```bash
node index.js
```

Run tests (when implemented):

```bash
npm test
```

## Repository Structure

```
.
├── .github/
│   ├── shared-actions/          # Checked-out org-shared-actions (CI only)
│   │   └── .github/actions/
│   │       └── cursor-agent-fix/
│   └── workflows/
│       └── cursor-open-pr.yml   # Manual workflow: Cursor fixes → PR
├── package.json
├── package-lock.json
└── README.md
```

## Development & Automation

### Cursor-driven PR workflow

The repository uses a **workflow_dispatch** workflow that:

1. Checks out this repository and the private shared-actions repo.
2. Runs the shared **Cursor Agent Fix** action with a configurable prompt.
3. Opens a pull request from branch `cursor/auto-fixes` if there are changes.

**To run it:**

1. Go to **Actions** → **apply changes and open PR** → **Run workflow**.
2. Provide the required `port_context` input (JSON including `runId` and any context your run needs).

**Required secrets:**

- `PRIVATE_ACTION_TOKEN` – access to the `org-shared-actions` repository.
- `CURSOR_API_KEY` – used by the Cursor agent action.
- `GITHUB_TOKEN` – provided by the runner for creating the PR.

### Local development

Clone the repo, install dependencies, and make changes locally. Use the Cursor workflow for automated documentation or code changes via prompts.

## Contributing

1. Open an issue or discussion for larger changes.
2. Use a feature branch and open a pull request against `main`.
3. Ensure `npm test` passes when tests are added.

## License

ISC. See `package.json` for details.

---

**Links**

- [Repository](https://github.com/hq-secuity-test/my-npm-test)
- [Issues](https://github.com/hq-secuity-test/my-npm-test/issues)
