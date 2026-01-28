# my-npm-test

> NPM package and Cursor automation test repository.

A minimal npm package used for testing Cursor-based CI/CD workflows and shared GitHub Actions.

---

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [CI/CD & Automation](#cicd--automation)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

This repository serves as:

- An **npm package** (`my-npm-test`) with a basic `package.json` and dependency setup.
- A **testbed** for GitHub Actions workflows that use Cursor Agent for automated changes and PR creation.

---

## Prerequisites

- [Node.js](https://nodejs.org/) (LTS recommended)
- [npm](https://www.npmjs.com/) (included with Node.js)

---

## Installation

```bash
npm install
```

Or install as a dependency in another project:

```bash
npm install my-npm-test
```

---

## Usage

```bash
# Run the default test script (placeholder)
npm test
```

---

## Project Structure

```
.
├── .github/
│   ├── shared-actions/     # Checked-out private org-shared-actions repo
│   └── workflows/          # GitHub Actions workflow definitions
│       └── cursor-open-pr.yml
├── package.json
├── package-lock.json
└── README.md
```

---

## CI/CD & Automation

The repository includes a **workflow-dispatch** workflow that:

1. Checks out this repo and the private `org-shared-actions` repository.
2. Runs the **Cursor Agent Fix** action with a configurable prompt.
3. Opens a pull request (`cursor/auto-fixes`) if there are changes.

**Manual trigger:** _Actions → apply changes and open PR → Run workflow_

Required inputs and secrets:

- `port_context` (workflow input, JSON with `runId` etc.)
- `PRIVATE_ACTION_TOKEN` — access to the private shared-actions repo
- `CURSOR_API_KEY` — for the Cursor Agent

---

## Contributing

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/your-feature`).
3. Commit your changes (`git commit -m 'feat: add something'`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

---

## License

[ISC](LICENSE) — see [package.json](./package.json) for details.

---

## Links

- **Repository:** [hq-secuity-test/my-npm-test](https://github.com/hq-secuity-test/my-npm-test)
- **Issues:** [Open an issue](https://github.com/hq-secuity-test/my-npm-test/issues)
- **Homepage:** [README on GitHub](https://github.com/hq-secuity-test/my-npm-test#readme)
