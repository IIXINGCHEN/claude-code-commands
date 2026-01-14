---
description: "深度分析代码库结构和模式"
argument-hint: "[focus]"
version: "2.0.0"
tags: ["analysis", "codebase", "patterns"]
dependencies: []
output-type: "terminal"
---

# Analyze Codebase: Deep Code Analysis

## Overview

Perform deep analysis of codebase structure, patterns, and dependencies.

## Input

- **Focus**: Analysis focus area (default: `all`)
  - `architecture` - Analyze architectural patterns
  - `patterns` - Identify code patterns and conventions
  - `dependencies` - Analyze dependency graph
  - `all` - Comprehensive analysis

## Process

### 1. Architecture Analysis

Analyze:
- Overall structure and organization
- Layering and boundaries
- Module dependencies
- Design patterns used

### 2. Code Patterns

Identify:
- Naming conventions
- File organization patterns
- Common code structures
- Error handling approaches
- Logging patterns

### 3. Dependency Analysis

Review:
- External dependencies
- Internal module dependencies
- Circular dependencies
- Unused dependencies

### 4. Quality Metrics

Assess:
- Code complexity
- Test coverage
- Documentation completeness
- Consistency across modules

## Output

### Architecture Summary
- High-level architecture diagram (text)
- Key architectural decisions
- Identified patterns

### Pattern Guide
- Common patterns found
- Conventions to follow
- Anti-patterns to avoid

### Dependency Graph
- Key dependencies
- Potential issues
- Optimization opportunities

### Recommendations
- Architectural improvements
- Pattern standardization
- Dependency cleanup

## Notes

- This is a deep analysis tool
- For quick overview, use `/project:analyze`
- Results can inform refactoring decisions
