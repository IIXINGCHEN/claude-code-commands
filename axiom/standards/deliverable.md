---
description: "生产级交付标准（11项必需标准）"
version: "20.0.0"
tags: ["standards", "quality", "production"]
module-type: "standards"
---

# AxiomOS: Production-Grade Deliverable Standards

## Overview

All code generation must unconditionally meet these standards. These are non-negotiable requirements for all deliverables.

## Deliverable Standards

`<deliverable_standards>`

**All code generation must unconditionally meet these standards:**

### A. Domain Alignment

Code structure must map to the domain model in `.agents/context/domain/`.

**Requirements:**
- Domain entities reflected in code structure
- Business logic strictly in the domain layer
- Domain language used in naming
- Clear separation of concerns

### B. Zero-Trust Security

Endpoints are deny-by-default; use secret managers; validate/sanitize all input.

**Requirements:**
- All endpoints deny by default
- Use secret managers (never hardcode secrets)
- Validate and sanitize ALL input
- Use structured security logs
- Manage keys via `.env` and `.gitignore`
- Principle of least privilege

### C. Reliability & Resilience

Critical operations are idempotent; includes graceful error handling.

**Requirements:**
- Idempotent critical operations
- Graceful error handling
- Timeouts on all external calls
- Retry mechanisms with exponential backoff
- Circuit breakers for cascading failures
- Fail-safe defaults

### D. Observability

Produces structured logs with a `trace_id`; exposes Prometheus-compliant metrics.

**Requirements:**
- Structured JSON logs
- Unique `trace_id` for request tracking
- Prometheus-compatible metrics
- Distributed tracing integration
- Performance monitoring
- Health check endpoints

### E. Testability

Adheres to DIP; code **must** be accompanied by high-coverage (**>95%**) unit and integration tests.

**Requirements:**
- Dependency Inversion Principle (DIP)
- Test coverage **>95%**
- Follow **test-first** development
- Unit tests for all functions/methods
- Integration tests for workflows
- E2E tests for critical paths
- Mocking/stubbing external dependencies

### F. Performance & Efficiency

Use efficient algorithms/data structures; avoid N+1 queries.

**Requirements:**
- Efficient algorithms (appropriate time/space complexity)
- Optimal data structures
- No N+1 query problems
- Benchmark resource-intensive operations
- Connection pooling
- Caching where appropriate
- Lazy loading when beneficial

### G. Maintainability

Follows SOLID; **all code and comments must be in English**.

**Requirements:**
- SOLID principles strictly followed
- **All code in English** (variables, functions, classes)
- **All comments in English**
- Adhere to `.agents/context/standards/`
- Consistent naming conventions
- Comment the "why," not the "what"
- Separate config from code
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple, Stupid)

### H. Precision & Completeness

**No non-production code.** Forbid any simplified, mock, or placeholder code.

**Requirements:**
- NO placeholders (no `TODO`, `FIXME`, `XXX`)
- NO mock implementations
- NO simplified "for now" solutions
- Complete, production-ready implementation
- All logic fully implemented
- All edge cases handled
- No redundant documentation
- No unrelated test code

### I. Obey Existing Patterns

Analyze and strictly adhere to the project's existing architectural patterns.

**Requirements:**
- Study existing codebase first
- Follow established patterns
- Maintain consistency with current code
- Use same libraries/frameworks
- Match coding style
- Preserve architectural decisions

### J. Keep It Simple and Scoped

Limit code modifications strictly to the current task's scope.

**Requirements:**
- Change only what's necessary
- No out-of-scope refactoring
- Minimal impact on existing code
- Clear boundaries
- Focused commits
- Single responsibility per change

### K. Cross-Platform Compatibility

All text files **must** use **UTF-8 without BOM** and **LF line endings**.

**Requirements:**

#### 1. File Encoding
- All text files **must** use **UTF-8 without BOM**
- No legacy encodings (ASCII, Latin-1, etc.)
- Verify encoding in editor/IDE

#### 2. Line Endings
- All text files **must** use **LF (`\n`)**
- Never use CRLF (`\r\n`) or CR (`\r`)
- Configure `.gitattributes` properly
- Set editor to use LF

#### 3. File Paths
- **Never** hard-code path separators (`/` or `\`)
- Use language's built-in path library:
  - Python: `os.path.join()` or `pathlib.Path`
  - Node.js: `path.join()`
  - Go: `filepath.Join()`
  - Java: `Paths.get()` or `File.separator`

#### 4. Case Sensitivity
- All file/directory references **must** match the filesystem case exactly
- Assume case-sensitive filesystem
- Test on Linux to verify

#### 5. Shell Scripting
- `.sh` scripts **must** use POSIX-compliant syntax
- Use `#!/bin/sh` not `#!/bin/bash` (unless bash-specific features required)
- Check for command existence before use:
  ```bash
  if command -v foo >/dev/null 2>&1; then
      foo --version
  fi
  ```
- Avoid bash-isms in POSIX scripts

`</deliverable_standards>`

## Quality Checklist

Before delivering any code, verify:

- [ ] **A** - Domain alignment verified
- [ ] **B** - Security review passed
- [ ] **C** - Resilience patterns implemented
- [ ] **D** - Observability instrumented
- [ ] **E** - Test coverage >95%
- [ ] **F** - Performance validated
- [ ] **G** - Maintainability standards met
- [ ] **H** - No placeholders or TODOs
- [ ] **I** - Existing patterns followed
- [ ] **J** - Scope strictly maintained
- [ ] **K** - Cross-platform compatibility ensured

## Enforcement

These standards are:
- **Mandatory**: No exceptions
- **Verifiable**: Each can be checked
- **Automated**: Many can be tool-verified
- **Comprehensive**: Cover all quality aspects

## Related Modules

- [Core Principles](../foundation/principles.md) - Quality-First Mindset
- [Artifact Protocol](./artifact.md) - Delivery format requirements
- [Review Mode](../modes/review.md) - Quality verification process
