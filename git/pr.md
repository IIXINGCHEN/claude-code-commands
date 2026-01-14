---
description: "创建GitHub Pull Request"
argument-hint: "[base-branch]"
version: "2.0.0"
tags: ["git", "github", "pr", "collaboration"]
dependencies: ["git:push"]
output-type: "terminal"
requires: ["gh"]
---

# Git PR: Create Pull Request

## Overview

Create a GitHub Pull Request for the current branch.

## Prerequisites

- GitHub CLI installed and authenticated (`gh auth status`)
- Current branch pushed to remote
- Working in a GitHub repository

## Input

- **Base Branch**: Target branch for PR (default: `main`)

## Process

### 1. Verify Branch Status

Check if current branch is pushed and up to date:
```bash
git status
git diff --stat origin/$(git branch --show-current)
```

### 2. Analyze Changes

Review all commits that will be included in the PR:
```bash
git log origin/<base-branch>...HEAD
git diff origin/<base-branch>...HEAD
```

### 3. Draft PR Summary

Create PR title and body based on:
- All commits in the branch (NOT just the latest!)
- Full scope of changes
- Test plan and validation

### 4. Create Pull Request

Use GitHub CLI to create PR:
```bash
gh pr create --title "PR Title" --body "$(cat <<'EOF'
## Summary
- Bullet point summary

## Test Plan
- Testing checklist

🤖 Generated with [Claude Code](https://claude.com/claude-code)
EOF
)"
```

## Output

- PR URL
- PR number
- Status

## Notes

### PR Best Practices

- Title should be concise and descriptive
- Include comprehensive test plan
- Reference related issues
- Add relevant labels

### Common Issues

- **No changes**: Ensure branch is different from base
- **Authentication**: Run `gh auth login` if needed
- **Branch not pushed**: Push branch first with `git push -u origin <branch>`
