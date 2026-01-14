---
description: "修复代码审查中发现的问题"
argument-hint: "[review-file] [scope]"
version: "2.0.0"
tags: ["code-review", "bugfix", "remediation"]
dependencies: ["validation:code-review"]
output-type: "terminal"
---

I ran/performed a code review and found these issues:

Code-review (file or description of issues): $1

Please fix these issues one by one. If the Code-review is a file read the entire file first to understand all of the issue(s) presented there.

Scope: $2

For each fix:
1. Explain what was wrong
2. Show the fix
3. Create and run relevant tests to verify

After all fixes, run the validate command (see commands/validate.md) to finalize your fixes.