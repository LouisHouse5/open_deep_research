# Contributing to Open Deep Research

Thank you for your interest in contributing to Open Deep Research!

## Syncing with Upstream Repository

This repository is a fork of [langchain-ai/open_deep_research](https://github.com/langchain-ai/open_deep_research). To keep your fork up-to-date with the latest changes from the upstream repository, you can use one of the following methods:

### Method 1: Automated Sync (Recommended)

We have a GitHub Actions workflow that automatically checks for updates from the upstream repository weekly and creates a pull request when updates are available.

**To manually trigger the sync:**

1. Go to the [Actions tab](../../actions/workflows/sync-upstream.yml) in this repository
2. Click on "Sync with Upstream" workflow
3. Click "Run workflow" button
4. Select the branch and click "Run workflow"

The workflow will:
- Fetch the latest changes from upstream
- Create a pull request if there are updates
- Notify you if there are merge conflicts that need manual resolution

### Method 2: Manual Sync via Command Line

If you prefer to sync manually or need more control over the process:

#### 1. Add the upstream remote (one-time setup)

```bash
git remote add upstream https://github.com/langchain-ai/open_deep_research.git
git remote -v
```

You should see:
```
origin    https://github.com/LouisHouse5/open_deep_research.git (fetch)
origin    https://github.com/LouisHouse5/open_deep_research.git (push)
upstream  https://github.com/langchain-ai/open_deep_research.git (fetch)
upstream  https://github.com/langchain-ai/open_deep_research.git (push)
```

#### 2. Fetch upstream changes

```bash
git fetch upstream
```

#### 3. Checkout your default branch

```bash
git checkout main  # or whatever your default branch is
```

#### 4. Merge upstream changes

```bash
git merge upstream/main
```

If there are merge conflicts, resolve them manually:
1. Open the conflicted files in your editor
2. Look for conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
3. Resolve the conflicts by choosing which changes to keep
4. Stage the resolved files: `git add <file>`
5. Complete the merge: `git commit`

#### 5. Push changes to your fork

```bash
git push origin main
```

### Method 3: Using GitHub Web Interface

1. Navigate to your repository on GitHub
2. You should see a message like "This branch is X commits behind langchain-ai:main"
3. Click on "Sync fork" button
4. Click "Update branch" to sync with upstream

**Note:** This method only works when there are no conflicts. For complex merges, use Method 1 or Method 2.

## Keeping Your Feature Branches Updated

If you're working on a feature branch and want to incorporate upstream changes:

```bash
# Update your local main branch first
git checkout main
git fetch upstream
git merge upstream/main
git push origin main

# Then rebase your feature branch
git checkout your-feature-branch
git rebase main
```

Alternatively, you can merge main into your feature branch:

```bash
git checkout your-feature-branch
git merge main
```

## Development Workflow

1. Create a new branch for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Make your changes and commit them:
   ```bash
   git add .
   git commit -m "Description of your changes"
   ```

3. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

4. Create a Pull Request on GitHub

## Code Style and Testing

Before submitting a pull request:

1. Run linting:
   ```bash
   ruff check
   ```

2. Run type checking:
   ```bash
   mypy
   ```

3. Test your changes:
   ```bash
   python tests/run_evaluate.py
   ```

## Questions?

If you have questions about contributing or syncing with upstream, please open an issue in this repository.
