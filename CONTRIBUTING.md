# Contributing to veeam-cli

Thank you for your interest in contributing to veeam-cli! This document provides guidelines and information for contributors.

## Getting Started

1. Fork the repository
2. Clone your fork:
   ```bash
   git clone https://github.com/<your-username>/veeam-cli.git
   cd veeam-cli
   ```
3. Install dependencies:
   ```bash
   npm install
   ```
4. Build the project:
   ```bash
   npm run build
   ```

## Development Workflow

1. Create a feature branch from `main`:
   ```bash
   git checkout -b feat/my-feature
   ```
2. Make your changes in `src/`
3. Build and test:
   ```bash
   npm run build
   npm test
   ```
4. Commit with a clear message following [Conventional Commits](https://www.conventionalcommits.org/):
   ```bash
   git commit -m "feat: add support for new VBR endpoint"
   ```
5. Push and open a pull request

## Code Style

- TypeScript with strict mode enabled
- ESM modules (`.js` extension in imports)
- Prefer `node:` prefixed built-in imports
- Keep functions small and focused

## Adding a New Command

1. Create a new file under `src/commands/<product>/`
2. Export a `register*Command(parent: Command)` function
3. Wire it into the product's `index.ts`
4. Update the CHANGELOG and README

## Reporting Issues

Please include:
- Node.js version (`node --version`)
- Operating system
- Steps to reproduce
- Expected vs actual behavior

## License

By contributing, you agree that your contributions will be licensed under the MIT License.
