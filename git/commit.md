---
description: "创建规范化的Git提交"
version: "2.0.0"
tags: ["git", "commit", "version-control"]
dependencies: []
output-type: "terminal"
---

# Git Commit: Create Atomic Commit

## Overview

Create a new commit for all uncommitted changes with a conventional commit message.

## Process

### 1. Check Current Status

Run git status to see what files are uncommitted:
```bash
git status && git diff HEAD && git status --porcelain
```

### 2. Add Files

Add the untracked and changed files to staging area.

### 3. Create Commit Message

Create an atomic commit message with appropriate prefix:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### 4. Add Co-Author

Append co-author tag:
```
Co-Authored-By: Claude Sonnet 4.5 (1M context) <noreply@anthropic.com>
```

## Notes

- Keep commit messages concise and descriptive
- Focus on "why" rather than "what"
- Follow conventional commit format
