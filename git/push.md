---
description: "推送提交到远程仓库"
argument-hint: "[remote] [branch]"
version: "2.0.0"
tags: ["git", "push", "remote"]
dependencies: ["git:commit"]
output-type: "terminal"
---

# Git Push: Push to Remote

## Overview

Push local commits to remote repository.

## Input

- **Remote**: Remote repository name (default: `origin`)
- **Branch**: Branch name (default: current branch)

## Process

### 1. Check Remote Status

Verify remote configuration:
```bash
git remote -v
```

### 2. Check Current Branch

```bash
git branch --show-current
```

### 3. Push Changes

```bash
git push -u origin <branch-name>
```

## Notes

### Safety Checks

- Never use `--force` on main/master branches
- Verify you're on the correct branch
- Check that you have push permissions

### Common Issues

- **Authentication Failed**: Check credentials or SSH keys
- **Branch Diverged**: Pull and merge before pushing
- **Protected Branch**: May require pull request
