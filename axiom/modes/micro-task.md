---
description: "微任务模式 - 快速执行小型任务"
version: "20.0.0"
tags: ["micro-task", "mtm", "quick"]
module-type: "mode"
---

# AxiomOS: Micro-Task Mode - MTM Protocol

## Overview

For independent, well-scoped, minor tasks (e.g., refactoring a function, writing unit tests). Optimized for speed with minimal overhead.

## Protocol

`<protocol name="Micro-Task Mode - MTM">`

**Scenarios:** For independent, well-scoped, minor tasks.

### Phase 1: Scope & Approve

1. **Briefly restate** the task objective and acceptance criteria for confirmation.
2. After a clear "yes" or "proceed," move to the next phase.

**Example:**
```
Task: Add unit test for validateEmail function
Acceptance: Test covers valid/invalid formats
Proceed? (yes/no)
```

### Phase 2: Automate

1. **Test-First Implementation** (If applicable):
   - Write failing tests
   - Write implementation code
   - Run tests until all pass

2. **Quality Standards:**
   Generated code **must** comply with **Production-Grade Deliverable Standards**.

### Phase 3: Deliver

1. Provide the complete code that passes all tests.
2. Briefly explain the logic and return to `Standby` state.

`</protocol>`

## Characteristics

- **Fast**: Minimal overhead
- **Focused**: Single concern
- **Complete**: Production-ready
- **Tested**: If applicable

## Examples

### Example 1: Add Unit Test

**Input:** "Add unit test for calculateTax function"

**Scope & Approve:**
```
Task: Write unit test for calculateTax
Coverage: Valid rates, edge cases, errors
Proceed? → Yes
```

**Automate:**
```python
def test_calculate_tax():
    assert calculate_tax(100, 0.1) == 10
    assert calculate_tax(100, 0) == 0
    # ... more tests
```

**Deliver:** Tests implemented, all passing.

### Example 2: Refactor Function

**Input:** "Refactor getUserById to use async/await"

**Scope & Approve:**
```
Task: Convert getUserById to async/await
Maintain: Same interface, error handling
Proceed? → Yes
```

**Automate:**
```javascript
async function getUserById(id) {
  try {
    return await db.users.findOne({ id });
  } catch (error) {
    throw new DatabaseError(error);
  }
}
```

**Deliver:** Function refactored, tests updated.

## When to Use

✅ **Use Micro-Task for:**
- Adding single unit test
- Refactoring one function
- Fixing typos/formatting
- Adding documentation
- Small config changes

❌ **Don't use for:**
- Multiple related changes
- Architectural modifications
- New features
- Breaking changes

## Related Modules

- [Triage Protocol](./triage.md) - Routing to Micro-Task
- [Deliverable Standards](../standards/deliverable.md) - Quality requirements
