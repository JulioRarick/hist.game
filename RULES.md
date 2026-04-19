# Repository Rules Configuration Guide

This guide explains how to set up branch protection rules and rulesets for the `hist.game` repository.

## Overview

This project uses GitHub's protection mechanisms to ensure code quality and security on the `main` branch.

## Available Options

### Option 1: Rulesets (GitHub Team/Enterprise Plans) ⭐ Recommended

**Rulesets** are the modern approach with more granular control and rule layering capabilities.

**Requirements:**
- GitHub Team or GitHub Enterprise plan
- Repository owner or organization admin access

#### Recommended Ruleset Configuration for `main`

**1. Create a new ruleset:**
- Go to: Settings → Rules → Rulesets → New ruleset
- **Ruleset name:** `protect-main-branch`
- **Enforcement status:** Active

**2. Target branches:**
- Pattern: `main`

**3. Required rules:**

| Rule | Setting | Reason |
|------|---------|--------|
| Require signed commits | Enabled | Track who made changes and ensure authenticity |
| Require a pull request before merging | Enabled | All changes reviewed before merge |
| Require code reviews | 1 approval | At least one reviewer must approve |
| Dismiss stale pull request approvals | Enabled | Reviews must be re-approved after new commits |
| Require status checks to pass | Enabled | CI/CD pipelines must pass before merge |
| Require branches to be up to date before merging | Enabled | Branch must be synced with main |
| Require a linear history | Enabled | Prevents rewriting history with force push |
| Require commit message format | Pattern: `^(feat|fix|docs|style|refactor|perf|test|chore|ci)(\([a-z0-9\-]+\))?!?: .+` | Enforce Conventional Commits |

**4. Block rules:**

| Rule | Setting |
|------|---------|
| Block force pushes | Enabled |
| Block deletions | Enabled |

**5. Bypass permissions:**
- ✅ Repository Administrators (only)

#### Required Status Checks

In the ruleset, under "Require status checks to pass", add:
- `build` - Next.js production build must succeed
- `lint` - ESLint checks must pass
- `test` - Any test suite must pass (if added)

### Option 2: Branch Protection Rules (Free Plans)

**Branch Protection Rules** provide basic protection and work with all GitHub plans.

**Requirements:**
- Repository owner or admin access
- Works on Free, Pro, and Team plans

#### Recommended Configuration for `main`

**1. Go to:** Settings → Branches → Add rule

**2. Branch pattern:** `main`

**3. Enable the following:**

- ✅ **Require a pull request before merging**
  - Require approvals: **1**
  - Dismiss stale pull request approvals: **Yes**
  - Require review from code owners: **No** (unless CODEOWNERS file exists)

- ✅ **Require status checks to pass before merging**
  - Require branches to be up to date before merging: **Yes**

- ✅ **Require signed commits**

- ✅ **Require linear history**

- ✅ **Include administrators**
  - Allow force pushes: **No**
  - Allow deletions: **No**

#### Status Checks to Configure

Add these status checks (configured in GitHub Actions):
- `build` - Production build success
- `lint` - Code linting pass

## GitHub Actions Setup (Status Checks)

To make status checks work, you need GitHub Actions workflows:

### Build Workflow

Create `.github/workflows/build.yml`:

```yaml
name: Build

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '18'
      - run: npm ci
      - run: npm run build
```

### Lint Workflow

Create `.github/workflows/lint.yml`:

```yaml
name: Lint

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main, develop]

jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '18'
      - run: npm ci
      - run: npm run lint
```

## Implementation Steps

### For Rulesets Users (Team/Enterprise)

1. Navigate to Settings → Rules → Rulesets
2. Click "New ruleset" or "New repository ruleset"
3. Name it `protect-main-branch`
4. Set enforcement status to **Active**
5. Configure target to `main` branch
6. Enable all recommended rules above
7. Set bypass permissions to "Repository Administrators"
8. Click "Create"

### For Branch Protection Users (Free Plans)

1. Navigate to Settings → Branches
2. Under "Branch protection rules", click "Add rule"
3. Enter `main` as the branch pattern
4. Enable all recommended settings above
5. Configure required status checks
6. Click "Create"

## Commit Signing Setup

To enable signed commits requirement, you need to set up GPG or SSH signing:

### For GPG Signing (Recommended for Teams)

```bash
# Generate GPG key
gpg --full-generate-key

# List your GPG key ID
gpg --list-secret-keys --keyid-format=long

# Configure Git
git config --global user.signingkey YOUR_KEY_ID
git config --global commit.gpgsign true

# Sign commits
git commit -S -m "your message"
```

### For SSH Signing (Recommended for Solo)

```bash
# Use your existing SSH key

# Configure Git
git config --global user.signingkey ~/.ssh/id_ed25519.pub
git config --global gpg.format ssh
git config --global commit.gpgsign true

# Sign commits
git commit -S -m "your message"
```

### For GitHub Web Editor

When creating commits via GitHub's web interface, they are automatically signed with GitHub's signature.

## Recommended Branch Strategy

Protect `main` and create additional branches for development:

```
main (protected)
  ├── develop (recommended development branch)
  │   ├── feature/new-quiz-format
  │   ├── fix/button-alignment
  │   └── docs/api-documentation
  └── release/v1.0.0
```

## Troubleshooting

### Merging fails due to unsigned commits

**Solution:** Sign your local commits:
```bash
git commit -S -m "your message"
# or
git config --global commit.gpgsign true  # for all future commits
```

### Merging fails due to out-of-date branch

**Solution:** Update your branch:
```bash
git pull origin main
# or
git fetch origin && git rebase origin/main
```

### PR can't be merged - status checks haven't run

**Solution:** 
1. Push new commit (even if empty) to trigger workflows
2. Or wait for workflows to complete
3. Check Actions tab to see workflow status

## Best Practices

1. **Keep it simple** - Don't over-complicate rules
2. **Communicate** - Ensure team understands the rules
3. **Review regularly** - Update rules as team processes evolve
4. **Enable gradually** - Add rules incrementally if introducing to existing workflow
5. **Test with admins** - Verify admins can still bypass if needed
6. **Document** - Add rules in CONTRIBUTING.md (✅ Done in this repo)

## References

- [GitHub Rulesets Documentation](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets)
- [Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [GitHub Actions](https://docs.github.com/en/actions)

## Questions?

Refer to CONTRIBUTING.md for more guidelines or check GitHub documentation.
