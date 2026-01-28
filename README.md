# my-npm-test

> test

An npm package with GitHub Actions for Cursor-powered automated changes and pull requests.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Scripts](#scripts)
- [Project Structure](#project-structure)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Installation

```bash
npm install
```

### Dependencies

- **extjs-gpl** (^6.2.0) – Ext JS GPL framework

## Usage

After installation, the package entry point is `index.js`. Use it according to your application’s requirements.

## Scripts

| Command | Description |
|--------|-------------|
| `npm test` | Run tests (placeholder; add tests as needed) |

## Project Structure

```
.
├── .github/
│   ├── shared-actions/     # Reusable org actions (e.g. cursor-agent-fix)
│   └── workflows/
│       └── cursor-open-pr.yml   # Apply changes and open PR via Cursor
├── package.json
├── package-lock.json
└── README.md
```

### GitHub Actions

- **Apply changes and open PR** (`workflow_dispatch`)  
  Runs the Cursor shared action with a prompt, then opens a PR on branch `cursor/auto-fixes` when there are changes.  
  Requires `port_context` (with `runId`), `PRIVATE_ACTION_TOKEN`, `CURSOR_API_KEY`, and `GITHUB_TOKEN`.

## Development

1. Clone the repo:  
   `git clone https://github.com/hq-secuity-test/my-npm-test.git`
2. Install dependencies:  
   `npm install`
3. Run tests:  
   `npm test`

## Contributing

1. Open or pick an [issue](https://github.com/hq-secuity-test/my-npm-test/issues).
2. Use the **“Apply changes and open PR”** workflow (if available) to generate Cursor-assisted changes, or work in a branch and open a PR manually.

## License

ISC – see [package.json](package.json) for details.

## Links

- **Repository:** [github.com/hq-secuity-test/my-npm-test](https://github.com/hq-secuity-test/my-npm-test)
- **Issues:** [github.com/hq-secuity-test/my-npm-test/issues](https://github.com/hq-secuity-test/my-npm-test/issues)
