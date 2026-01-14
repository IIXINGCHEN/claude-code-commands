---
description: "导出当前会话信息"
argument-hint: "[format]"
version: "2.0.0"
tags: ["export", "session", "backup"]
dependencies: []
output-type: "file"
---

# Export Session: Export Current Session

## Overview

Export current session information including commands run, files modified, and conversation summary.

## Input

- **Format**: Export format (default: `markdown`)
  - `markdown` - Human-readable markdown format
  - `json` - Machine-readable JSON format

## Process

### 1. Collect Session Information

Gather:
- Session start time
- Commands executed
- Files read/written/modified
- Git operations performed
- Key decisions made

### 2. Summarize Conversation

Create:
- Conversation summary
- Key topics discussed
- Problems solved
- Pending items

### 3. Generate Export

Format data according to selected format.

## Output

### Markdown Format

```markdown
# Session Export - {timestamp}

## Summary
{conversation summary}

## Commands Executed
- Command 1
- Command 2

## Files Modified
- file1.txt
- file2.py

## Git Operations
- commits made
- branches created

## Key Decisions
- Decision 1
- Decision 2

## Pending Items
- [ ] Task 1
- [ ] Task 2
```

### JSON Format

```json
{
  "timestamp": "2024-01-12T10:30:00Z",
  "summary": "...",
  "commands": [],
  "files_modified": [],
  "git_operations": [],
  "decisions": [],
  "pending": []
}
```

## Notes

- Useful for documentation and handoff
- Can be used for session recovery
- Helps track progress
