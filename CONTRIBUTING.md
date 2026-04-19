# Contributing to Hist.Game

Thank you for your interest in contributing to Hist.Game! This document provides guidelines and instructions for contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Branch Protection Rules](#branch-protection-rules)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)
- [Code Style](#code-style)
- [Reporting Issues](#reporting-issues)

## Code of Conduct

Be respectful, inclusive, and professional in all interactions. We are committed to providing a welcoming and inspiring community for all.

## Getting Started

1. Fork the repository
2. Clone your fork: `git clone https://github.com/YOUR_USERNAME/hist.game.git`
3. Add upstream remote: `git remote add upstream https://github.com/JulioRarick/hist.game.git`
4. Create a feature branch: `git checkout -b feature/your-feature-name`

## Development Setup

### Prerequisites

- Node.js 18+ or higher
- pnpm (recommended) or npm

### Installation

```bash
# Install dependencies
pnpm install

# Start development server
pnpm dev

# Run linter
pnpm lint

# Create production build
pnpm build
```

## Branch Protection Rules

The `main` branch is protected with the following rules:

### For Rulesets (Team/Enterprise Plans)

When creating a ruleset for the `main` branch, apply these settings:

#### Required Rules
- ✅ **Require commits to be signed** - All commits must be signed with GPG or SSH
- ✅ **Require a pull request before merging** - All changes must go through PR review
- ✅ **Require code reviews** - Minimum 1 approved review required
- ✅ **Dismiss stale pull request approvals** - Reviews must be re-approved after new commits
- ✅ **Require status checks to pass** - CI/CD pipelines must pass
- ✅ **Require branches to be up to date** - Branch must be up to date with `main` before merging
- ✅ **Require linear history** - Force push is blocked to maintain clean history
- ✅ **Require commit message pattern** - Follow Conventional Commits format

#### Restricted Rules
- 🚫 **Block force pushes** - Prevent rewriting history
- 🚫 **Block deletions** - Prevent accidental deletion

#### Bypass Permissions
- Repository Administrators only

### For Standard Branch Protection (Free Plans)

If using standard branch protection rules:

```bash
# Settings → Branches → Add rule
# Pattern: main

- ✅ Require a pull request before merging
- ✅ Require approvals
- ✅ Dismiss stale pull request approvals
- ✅ Require status checks to pass before merging
- ✅ Require branches to be up to date before merging
- ✅ Include administrators
- ✅ Require signed commits
- ✅ Require linear history
```

## Commit Guidelines

This project uses **Conventional Commits** format for clear, semantic commit messages.

### Commit Message Format

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

### Type

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation changes
- **style**: Changes that don't affect code meaning (formatting, missing semicolons)
- **refactor**: Code refactoring without feature or fix
- **perf**: Performance improvements
- **test**: Adding or updating tests
- **chore**: Build, dependencies, tooling changes
- **ci**: CI/CD pipeline changes

### Scope

The scope specifies what part of the project is affected:
- `quiz` - Quiz functionality
- `ui` - User interface components
- `data` - Data files or quiz content
- `build` - Build configuration
- `docs` - Documentation

### Subject

- Use imperative mood ("add" not "added" or "adds")
- Don't capitalize first letter
- No period (.) at the end
- Maximum 50 characters

### Body

- Use imperative mood
- Include motivation for the change
- Contrast with previous behavior
- Line length: maximum 72 characters

### Footer

Include any breaking changes or issue references:

```
BREAKING CHANGE: description of breaking change

Fixes #123
Closes #456
```

### Examples

Good commit messages:

```
feat(quiz): add support for multiple choice questions

Add support for multiple choice questions in addition to 
true/false questions. This allows for more complex quiz 
scenarios and better assessment of knowledge.

Closes #42
```

```
fix(ui): prevent button overflow on mobile devices

Remove fixed width constraint and use max-width instead
to allow buttons to fit properly on small screens.

Fixes #89
```

```
docs: update installation instructions

Add Node.js version requirement and alternative installation
methods using npm and yarn.
```

## Pull Request Process

1. **Create a feature branch** from latest `main`:
   ```bash
   git fetch upstream
   git checkout -b feature/your-feature-name upstream/main
   ```

2. **Make your changes** and commit with proper message format

3. **Keep branch up to date**:
   ```bash
   git fetch upstream
   git rebase upstream/main
   ```

4. **Push your branch**:
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request**:
   - Use a clear, descriptive title
   - Reference any related issues (#123)
   - Describe what changes were made and why
   - Include screenshots if UI changes were made

6. **Respond to review feedback**:
   - Make requested changes
   - Commit with `git commit --amend` if minor changes
   - Push updates
   - Resolve conversations

7. **Ensure all checks pass**:
   - CI/CD pipelines
   - Code coverage
   - Linting
   - Build succeeds

## Code Style

This project uses automated tools to enforce code style:

### ESLint

TypeScript/JavaScript linting:
```bash
pnpm lint
```

Configuration: `.eslintrc.json` (via `@juliorarickorg/eslint-config`)

### Prettier

Code formatting:
```bash
# Check formatting
prettier --check .

# Format code
prettier --write .
```

Configuration: `prettier.config.cjs`

### TypeScript

Strict type checking:
```bash
npx tsc --noEmit
```

Configuration: `tsconfig.json`

### Pre-commit Hooks (Recommended)

Install Husky for automatic checks before commits:

```bash
pnpm add -D husky
npx husky install
npx husky add .husky/pre-commit "pnpm lint && pnpm format"
```

## Code Review Guidelines

### For Reviewers

- Be respectful and constructive
- Focus on the code, not the person
- Approve once you're satisfied with the changes
- Request changes if improvements are needed
- Comment on the PR if you need clarification

### For Authors

- Respond to feedback promptly
- Ask questions if you don't understand feedback
- Keep PRs focused and reasonably sized (< 400 lines if possible)
- Rebase before merge if history is messy

## Reporting Issues

Before creating an issue, check if it already exists. When reporting bugs:

### Bug Report Template

```markdown
## Description
Brief description of the bug

## Steps to Reproduce
1. Step 1
2. Step 2
3. ...

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Screenshots
If applicable, add screenshots

## Environment
- OS: [e.g., macOS, Windows, Linux]
- Node version: [e.g., 18.0.0]
- pnpm/npm version: [e.g., 8.0.0]
- Browser: [if applicable]

## Additional Context
Any other relevant information
```

### Feature Request Template

```markdown
## Description
Clear description of the feature

## Motivation
Why is this feature needed?

## Proposed Solution
How should it work?

## Alternatives
Other solutions considered

## Additional Context
Any other relevant information
```

## Questions or Need Help?

- Check existing [issues](https://github.com/JulioRarick/hist.game/issues)
- Review the [README](README.md) for project overview
- Check the [documentation](docs/) if available

## License

By contributing to Hist.Game, you agree that your contributions will be licensed under the MIT License.

---

Happy contributing! 🚀
