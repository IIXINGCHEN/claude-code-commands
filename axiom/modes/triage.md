---
description: "指令分流协议"
version: "20.0.0"
tags: ["triage", "routing", "intent-analysis"]
module-type: "mode"
priority: "entry-point"
---

# AxiomOS: Instruction Triage Protocol

## Overview

The first entry point for all user instructions, routing intent to the appropriate mode to balance speed and rigor.

## Protocol

`<protocol name="Instruction Triage Protocol">`

**Description:** The first entry point for all user instructions, routing intent to the appropriate mode to balance speed and rigor.

### Execution

#### 1. Intent Analysis

Scan input for:
- **Keywords**: "fix," "design," "review," "optimize," "new project," etc.
- **Complexity Quantifiers**: "simple," "complex," "quick," "comprehensive"
- **Scope Indicators**: File paths, number of changes, impact area
- **Urgency Markers**: "urgent," "asap," "when you have time"

#### 2. Routing Decision

Based on analysis, route to appropriate mode:

**Micro-Task (6.8)**
- **Triggers**: "fix typo," "add test," "refactor function"
- **Characteristics**: Atomic operations, well-scoped, independent
- **Example**: "Add unit test for calculateTotal function"

**Debug (6.5)**
- **Triggers**: "fix bug," "error in," "not working"
- **Characteristics**: Error-fixing intent, specific problem
- **Example**: "Fix the null pointer exception in UserService"

**Review (6.6)**
- **Triggers**: "review," "check," "validate"
- **Characteristics**: Code review, quality check
- **Example**: "Review the authentication implementation"

**Audit (6.3)**
- **Triggers**: "audit," "optimize," "improve"
- **Characteristics**: Comprehensive analysis, optimization
- **Example**: "Audit and optimize the entire payment module"

**Security (6.4)**
- **Triggers**: "security test," "penetration test," "vulnerability"
- **Characteristics**: Security assessment, adversarial testing
- **Example**: "Perform security audit on the API"

**Onboarding (6.7)**
- **Triggers**: "new project," "start project," "initialize"
- **Characteristics**: Project setup, initial configuration
- **Example**: "Help me start a new e-commerce project"

**SFAM (6.1)**
- **Triggers**: "build," "create app," "automate everything"
- **Characteristics**: End-to-end automation, single approval
- **Example**: "Build a complete user management system"

**SDM (6.2)** - Complex Development
- **Triggers**: "implement feature," "add major functionality"
- **Characteristics**: New features, major refactoring, architectural changes
- **Example**: "Implement real-time notification system"

**Enhancement (6.9)**
- **Triggers**: Exact match: "Generate an enhanced version of this prompt..."
- **Characteristics**: Meta-mode, prompt optimization
- **Example**: Special trigger format only

**Default**
- If unclassified, default to the `Scope` phase of **SDM (6.2)** for clarification

`</protocol>`

## Decision Matrix

### Complexity Assessment

| Factor | Low | Medium | High |
|--------|-----|--------|------|
| **Scope** | Single function | Single module | Multiple modules |
| **Files** | 1-2 files | 3-5 files | 6+ files |
| **Dependencies** | None | Few | Many |
| **Risk** | Low impact | Moderate impact | High impact |
| **Time** | <30 min | 30min-2hrs | 2hrs+ |

### Mode Mapping

| Complexity | Risk | Mode |
|------------|------|------|
| Low | Low | **Micro-Task** |
| Low | Medium | **Debug/Review** |
| Medium | Low | **Review** |
| Medium | Medium | **Audit** |
| Medium | High | **SDM** |
| High | Medium | **SDM** |
| High | High | **SDM + Security** |
| Any | Security | **Security** |

## Examples

### Example 1: Micro-Task

**Input:** "Add a unit test for the validateEmail function"

**Analysis:**
- Keyword: "add," "unit test"
- Scope: Single function
- Complexity: Low

**Routing:** → **Micro-Task Mode (6.8)**

### Example 2: Debug

**Input:** "Fix the bug where users can't log in with special characters in password"

**Analysis:**
- Keyword: "fix," "bug"
- Scope: Authentication module
- Complexity: Medium

**Routing:** → **Debug Mode (6.5)**

### Example 3: Complex Development

**Input:** "Implement a caching layer with Redis for all API endpoints"

**Analysis:**
- Keyword: "implement"
- Scope: Multiple modules, infrastructure
- Complexity: High

**Routing:** → **SDM (6.2)**

### Example 4: Security

**Input:** "Perform a security audit on the payment processing system"

**Analysis:**
- Keyword: "security audit"
- Scope: Critical system
- Risk: High

**Routing:** → **Security Mode (6.4)**

## Triage Output

After routing decision, output should include:

```yaml
Triage Result:
  Intent: [Brief description]
  Selected Mode: [Mode name]
  Reasoning: [Why this mode]
  Next Steps: [What will happen next]
```

## Related Modules

- [Mode Overview](./_overview.md) - All available modes
- [Micro-Task Mode](./micro-task.md) - Simple task execution
- [SDM Protocol](./sdm.md) - Complex development
- [Debug Mode](./debug.md) - Bug fixing
