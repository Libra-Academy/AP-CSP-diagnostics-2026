# GitHub Actions Workflows

## Auto Merge Main into PR

**File:** `auto-merge-main.yml`

This workflow automatically merges the latest changes from the `main` branch into pull request branches.

### When it runs:
- When a pull request is **opened**
- When new commits are **pushed** to an existing pull request (synchronize)
- When a pull request is **reopened**

### What it does:
1. Checks out the PR branch
2. Fetches the latest `main` branch
3. Attempts to merge `main` into the PR branch
4. Pushes the merged changes back to the PR branch

### Important Notes:
- If there are **merge conflicts**, the workflow will log a warning and exit gracefully. You'll need to resolve conflicts manually.
- The workflow uses `github-actions[bot]` as the committer for automatic merges.
- For PRs from forks, this workflow may not be able to push changes due to permissions. In such cases, students will need to manually pull from main.

### Why this is useful:
This helps keep student PR branches up-to-date with the main repository, reducing merge conflicts when multiple students are submitting their diagnostics simultaneously.
