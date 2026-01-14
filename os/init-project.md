---
description: Set up and start the project locally
argument-hint: [project-path]
---

# Init Project: Set up and start the project locally

## Overview

Analyze the project structure and provide appropriate initialization commands for the specified project.

## Input

- **Project Path**: `$ARGUMENTS` (default: current directory)
- If empty, use current directory

## Process

### 1. Analyze Project Structure

Examine project directory to identify:

1. **Build system files:**
   - package.json, pyproject.toml, go.mod, Cargo.toml
   - Makefile, pom.xml, build.gradle
   - next.config.js, vite.config.ts, angular.json

2. **Package manager:**
   - npm/yarn/pnpm (Node.js)
   - uv/pip/poetry (Python)
   - go mod (Go)
   - cargo (Rust)

3. **Runtime environment:**
   - Node.js version requirements
   - Python version requirements
   - Go version requirements

4. **Framework:**
   - Next.js, Vite, React, Vue
   - FastAPI, Django, Flask
   - Gin, Echo

5. **Development tools:**
   - eslint, prettier
   - pytest, jest
   - mypy, ruff

### 2. Generate Initialization Steps

Based on detected project type, generate:

1. **Prerequisites** - Required runtimes and tools
2. **Dependencies** - Package installation commands
3. **Environment Setup** - .env configuration
4. **Start Commands** - Development server commands
5. **Common Commands** - Test, build, lint commands

### 3. Write Output File

Create comprehensive initialization guide with project-specific commands.

## Output File

**Filename**: `.agents/init/{kebab-case-project-name}.md`

- Replace `{kebab-case-project-name}` with short project name
- Examples: `check-ai-cli.md`, `habit-tracker.md`
- Create `.agents/init/` directory if it doesn't exist

**Execute Command (use relative path):**
```bash
# Create directory (use relative path, avoid Windows path format in bash)
mkdir -p .agents/init

# Write init guide
cat > .agents/init/project-name.md << 'EOF'
# Init: project-name
...
EOF
```

## Output Structure

```markdown
# Init: {project-name}

## Overview

{Project description and purpose}

## Prerequisites

### Required Runtimes
- Runtime versions and how to verify

### Required Tools
- Package managers and build tools

## Installation

### 1. Install Dependencies
{Project-specific install commands}

### 2. Configure Environment
{Environment setup commands}

### 3. Start Development Server
{Start commands}

## Common Commands

### Update Dependencies
{Update commands}

### Run Tests
{Test commands}

### Build for Production
{Build commands}

### Lint and Format
{Lint commands}

## Validation

Execute validation commands to confirm setup:

```bash
# Verify installation
{verify-command}

# Run tests
{test-command}
```

## Notes

- Project-specific notes and caveats
- Any additional configuration required
- Common issues and solutions
```

## Quality Criteria

- [ ] All runtime and tool requirements identified
- [ ] Commands are executable and non-interactive
- [ ] Platform-specific instructions included (Windows/Bash)
- [ ] Validation commands provided
- [ ] Common commands documented

## Report

After creating the initialization guide, provide:

- Summary of project structure detected
- Key technologies identified
- Full path to created initialization file
- Next steps for user to set up the project
