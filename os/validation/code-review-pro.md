---
argument-hint: [--project=<path>] [--scope=diff|staged|all|repo] [--profile=standard|strict] [--focus=correctness|security|performance|maintainability|tests] [--style=brief|full] [--fix]
description: Perform a structured code review with actionable feedback (and optional fixes), including full-repo and strict production-ready checks
---

Perform structured code review with actionable feedback and optional fixes.

## Core Principles

Review Philosophy:

- Correctness first - bugs and edge cases matter most
- Security always - validate authn/authz, input, secrets
- Production-ready under strict profile - no mocks, no placeholders
- Minimal, actionable feedback - specific fixes over vague complaints

## Command Options

- `--project=<path>`: Project root directory to review (default: auto-detect Git repo root)
- `--scope=diff|staged|all|repo`: Review scope (default: diff)
- `--profile=standard|strict`: Review depth (default: standard)
- `--focus=correctness|security|performance|maintainability|tests`: Priority area (default: correctness)
- `--style=brief|full`: Report detail level (default: full)
- `--fix`: Apply safe fixes directly (ask before large changes)

## What to Review

1. **Collect context**
   - Determine project root from `--project` or Git repo
   - Run `git status` and diff for the selected scope
   - Identify changed files and primary intent
   - Locate impacted entry points (APIs, CLI, UI routes, migrations)

2. **Review by priority**
   - Correctness: logic errors, edge cases, contracts, error handling
   - Security: validation, auth, secrets, dependency risks
   - Reliability: timeouts, retries, concurrency, resource cleanup
   - Maintainability: clarity, duplication, project patterns
   - Tests: coverage gaps, flaky tests, nondeterminism

3. **Full repo review (`--scope=repo`)**
   - Identify entry points and trace key flows
   - Validate configuration (paths, ports, env vars, endpoints)
   - Scan for high-risk patterns (TODO, mock, stub, placeholder)
   - Apply No Mock Data Policy under strict profile

## Strict Profile Requirements

When `--profile=strict` is enabled:

1. **Spatial Analysis (Architecture Integrity)**
   - Validate module dependency graph is consistent and acyclic
   - Verify imports resolve to real, accessible modules
   - Check layering boundaries (API/business/data)
   - Ensure cross-cutting concerns are consistent

2. **System Analysis (Vertical Integration)**
   - Trace end-to-end flows (UI/CLI -> API -> service -> data store)
   - Validate API endpoints: request validation, response schema, status codes
   - Validate database operations: CRUD, transactions, rollbacks
   - Validate third-party integrations: auth, timeouts, retries, observability

3. **Reverse-Engineering Analysis (Logic Verification)**
   - Infer intended behavior from contracts and verify implementation matches
   - Backtrack from user workflows for completeness
   - Verify exception handling covers realistic failure modes
   - Review security from attack-surface perspective

4. **No Mock Data Policy (Production Paths)**
   - Mock/stub/simulated data in production paths is a Blocker by default
   - Allowed: mocks in tests, docs examples, explicitly gated dev paths
   - Not allowed: mock data to real users, fake records to real DBs
   - Replace with real integration or fail fast with descriptive error

5. **Production Readiness Gate**
   - No placeholder/example-only code in production paths
   - No incomplete features behind silent defaults
   - No commented-out blocks or dead code in production
   - Error handling must be explicit with debugging context
   - Network calls must be bounded (timeouts)
   - Data mutations should be transactional when required

## Output Format

Save to `.agents/code-reviews/[appropriate-name].md`

**Stats:**

- Files Modified: 0
- Files Added: 0
- Files Deleted: 0
- New lines: 0
- Deleted lines: 0

**Top issues (ordered):**

```
severity: blocker|major|minor
file: path/to/file.py
symbol: function/class name
issue: [short description]
detail: [explanation and impact]
suggestion: [how to fix]
```

**Suggested patch:**

- Minimal diffs grouped by file

**Test guidance:**

- Which tests to run
- New tests to add

**Follow-ups:**

- Non-blocking improvements and refactors

## Review Checklist

- Correctness: edge cases handled, error paths logged, async flows cleaned
- Security: inputs validated, secrets excluded, external calls bounded
- Consistency: follows existing patterns, backward-compatible APIs
- Tests: new behavior covered, tests are deterministic

## Important

- Prefer small, reviewable changes over large rewrites
- Under strict profile: mocks/stubs/placeholders in production paths are Blockers
- Never silently swallow exceptions - fail fast with descriptive messages
- If repository has formatting/lint/type checks, respect them
