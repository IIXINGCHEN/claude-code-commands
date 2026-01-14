---
description: Run comprehensive validation of the project
argument-hint: [project-path]
---

# Validate Project: Run comprehensive validation of the project

## Overview

Execute validation commands to verify project health, code quality, and functionality.

## Input

- **Project Path**: `$ARGUMENTS` (default: current directory)
- If empty, use current directory

## Process

### 1. Analyze Project Structure

Examine project directory to identify:

1. **Build system files:**
   - package.json, pyproject.toml, go.mod, Cargo.toml
   - Makefile, pom.xml, build.gradle

2. **Testing framework:**
   - jest, pytest, mocha
   - vitest, unittest
   - cypress, playwright

3. **Linting tools:**
   - eslint, ruff, pylint
   - prettier, black, gofmt

4. **Build tools:**
   - npm scripts, uv run
   - make, gradle

5. **Configuration files:**
   - .eslintrc, pyproject.toml
   - tsconfig.json, go.mod

### 2. Detect Validation Commands

Based on detected project type:

1. **Syntax/Linting**
2. **Type Checking**
3. **Unit Tests**
4. **Integration Tests**
5. **Build Validation**
6. **Security Checks**

### 3. Execute Validation

Run validation commands in order and collect results.

## Output File

**Filename**: `.agents/validation/{kebab-case-project-name}.md`

- Replace `{kebab-case-project-name}` with short project name
- Examples: `check-ai-cli.md`, `xxx-xxx.md`
- Create `.agents/validation/` directory if it doesn't exist

**Execute Command (use relative path):**
```bash
# Create directory (use relative path, avoid Windows path format in bash)
mkdir -p .agents/validation

# Write validation report
cat > .agents/validation/project-name.md << 'EOF'
# Validate: project-name
...
EOF
```

## Output Structure

```markdown
# Validate: {project-name}

## Validation Summary

- **Status**: PASS / PARTIAL / FAIL
- **Total Checks**: N
- **Passed**: N
- **Failed**: N
- **Execution Time**: {duration}

## Validation Results

### 1. Syntax & Linting

**Command:**
```bash
{command}
```

**Result:** PASS / FAIL

**Output:**
```bash
{output}
```

### 2. Type Checking

**Command:**
```bash
{command}
```

**Result:** PASS / FAIL

**Output:**
```bash
{output}
```

### 3. Unit Tests

**Command:**
```bash
{command}
```

**Result:** PASS / FAIL

**Output:**
```bash
{output}
```

### 4. Integration Tests

**Command:**
```bash
{command}
```

**Result:** PASS / FAIL

**Output:**
```bash
{output}
```

### 5. Build Validation

**Command:**
```bash
{command}
```

**Result:** PASS / FAIL

**Output:**
```bash
{output}
```

## Issues Found

### Critical

- [ ] Issue description with file:line

### High

- [ ] Issue description with file:line

### Medium

- [ ] Issue description with file:line

### Low

- [ ] Issue description with file:line

## Recommendations

- Priority fixes needed
- Optimization suggestions
- Best practices to follow

## Next Steps

1. Fix critical issues first
2. Re-run validation
3. Address remaining issues
4. Commit changes
```

## Quality Criteria

- [ ] All validation commands executed successfully
- [ ] Results clearly categorized (PASS/FAIL)
- [ ] Issues categorized by severity
- [ ] Error messages include file:line locations
- [ ] Recommendations provided for each failure

## Report

After validation, provide:

- Overall health assessment (PASS/PARTIAL/FAIL)
- Summary of each validation check
- Critical issues requiring immediate attention
- Suggested next steps to resolve issues
- Full path to validation report
