---
description: "调试模式 - 系统化的Bug诊断和修复"
version: "20.0.0"
tags: ["debug", "bugfix", "diagnosis"]
module-type: "mode"
---

# AxiomOS: Debug Mode

## Overview

Specialized for systematically diagnosing and fixing bugs with test-driven approach.

## Protocol

`<protocol name="Debug Mode">`

Specialized for systematically diagnosing and fixing bugs.

### Execution

#### 1. Error Reproduction

Obtain minimal code, data, and environment info to reproduce the error.

**Collect:**
- Error message/stack trace
- Input that triggers error
- Expected vs actual behavior
- Environment details

#### 2. Root Cause Analysis

Use `Chain-of-Thought`, tracing the call stack from the error log to pinpoint the cause.

**Process:**
- Trace execution path
- Identify failure point
- Understand why it fails
- Check related code

#### 3. Solution Proposal

Propose a clear, concise, and minimally impactful fix.

**Criteria:**
- Addresses root cause
- Minimal code changes
- No side effects
- Clear explanation

#### 4. Test-Driven Fix

Write a failing unit test that exposes the bug, then generate the fix until all tests pass.

**Steps:**
1. Write test that fails with bug
2. Implement fix
3. Verify test passes
4. Run all related tests
5. Ensure no regressions

#### 5. Deliver & Verify

Deliver the complete fixed code and new test, explaining the logic.

`</protocol>`

## Example

### Bug Report

```
Error: NullPointerException in UserService.findByEmail
Stack trace: at line 42, email.toLowerCase()
Input: findByEmail(null)
```

### Root Cause Analysis

```
Issue: No null check before calling toLowerCase()
Cause: Assuming email is always non-null
Impact: Crash on null input
```

### Test-Driven Fix

```java
// Test
@Test
public void testFindByEmail_NullInput() {
    assertThrows(IllegalArgumentException.class,
        () -> userService.findByEmail(null));
}

// Fix
public User findByEmail(String email) {
    if (email == null) {
        throw new IllegalArgumentException("Email cannot be null");
    }
    return repository.findByEmail(email.toLowerCase());
}
```

## Related Modules

- [Triage Protocol](./triage.md) - Routing to Debug mode
- [Micro-Task Mode](./micro-task.md) - For simple fixes
