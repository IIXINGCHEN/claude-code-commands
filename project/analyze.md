---
description: "分析项目结构和技术栈"
argument-hint: "[project-path]"
version: "2.0.0"
tags: ["project", "analysis", "structure"]
dependencies: []
output-type: "terminal"
---

# Project Analyze: Analyze Project Structure

## Overview

Analyze project structure and provide comprehensive understanding of the codebase architecture.

## Input

- **Project Path**: `$ARGUMENTS` (default: current directory)

## Process

### 1. Directory Structure

Examine the directory tree:
```bash
tree -L 3 -I 'node_modules|__pycache__|.git|dist|build' || find . -maxdepth 3 -type d
```

### 2. Technology Detection

Identify technologies by checking files:
- `package.json` → Node.js project
- `pyproject.toml` → Python project
- `go.mod` → Go project
- `Cargo.toml` → Rust project
- `pom.xml` → Java/Maven project
- `build.gradle` → Java/Gradle project

### 3. Architecture Analysis

Analyze:
- Module organization
- Layering patterns (MVC, Clean Architecture, etc.)
- Directory naming conventions
- File organization patterns

### 4. Dependencies Analysis

Review:
- External dependencies and versions
- Development dependencies
- Runtime requirements

## Output Report

### Project Overview
- Type: Web app / CLI tool / Library / API
- Primary language(s)
- Framework(s) used

### Architecture
- Directory structure explanation
- Architectural patterns identified
- Module boundaries

### Tech Stack
- Languages and versions
- Frameworks and libraries
- Build tools
- Testing frameworks

### Entry Points
- Main files
- Configuration files
- Important scripts

## Notes

- This command provides high-level overview
- For deeper codebase understanding, use `/workflow:prime`
