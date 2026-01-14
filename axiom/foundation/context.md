---
description: "全局上下文核心 (.agents/context/) 协议"
version: "20.1.0"
tags: ["context", "agents", "source-of-truth"]
module-type: "foundation"
---

# AxiomOS: Global Context Core - The Single Source of Truth (`.agents/context/`)

## Overview

This is an inviolable mechanism for achieving "Global Context". The `.agents/context/` directory serves as the single source of truth for all persistent project context.

## Source of Truth Protocol

`<source_of_truth_protocol>`

**This is an inviolable mechanism for achieving "Global Context".**

### Single Source of Truth

The `.agents/context/` directory is the **sole** source for all persistent project context:
- Domain model
- Architecture Decision Records (ADRs)
- Coding standards
- API specifications
- Design patterns
- Project conventions

### Context Synchronization

Before any task requiring background knowledge, my first action is to determine if `.agents/context/` info is needed.

#### If Context is Needed

I **must** pause and output a structured `CONTEXT_REQUEST` XML block. Proceeding with assumptions is **forbidden**.

**Example:**
```xml
<CONTEXT_REQUEST reason="Fetching latest domain model, API specs, and relevant ADRs for feature design and architectural consistency.">
  <file path=".agents/context/domain/user_management.md" />
  <file path=".agents/context/api/auth_v2.yaml" />
  <directory path=".agents/context/architecture/adr/" />
</CONTEXT_REQUEST>
```

#### Status Reporting

Explicitly report sync status in the `Context Sync Status` field of every `Self-Diagnostic Report`:
- "Awaiting context" - Waiting for context provision
- "Sync Success: .agents/context/ commit <hash>" - Successfully synced
- "N/A" - Context not needed for current task

`</source_of_truth_protocol>`

## `.agents/context/` Directory Structure

### Recommended Organization

```
.agents/
├── context/                   # Global project context (source of truth)
│   ├── domain/               # Domain entities and concepts
│   │   ├── entities.md
│   │   ├── relationships.md
│   │   └── business-rules.md
│   ├── architecture/         # Architectural decisions
│   │   ├── adr/             # Architecture Decision Records
│   │   │   ├── 001-api-design.md
│   │   │   ├── 002-database-choice.md
│   │   │   └── ...
│   │   └── patterns.md      # Common patterns
│   ├── api/                 # API specifications
│   │   ├── rest_api_v1.yaml
│   │   └── specifications.md
│   ├── standards/           # Coding standards and conventions
│   │   ├── style-guide.md
│   │   ├── naming-conventions.md
│   │   └── review-checklist.md
│   ├── security/            # Security policies
│   │   ├── authentication.md
│   │   └── authorization.md
│   ├── config/              # Project configuration
│   │   ├── tech-stack.md
│   │   └── dependencies.md
│   └── README.md            # Context directory guide
│
├── plans/                   # AI-generated feature plans
├── code-reviews/            # Code review reports
├── validation/              # Validation reports
├── execution-reports/       # Execution reports
├── context-summaries/       # Conversation summaries
└── init/                    # Project initialization guides
```

### Content Guidelines

#### Domain Model
- Define business entities
- Describe relationships
- Specify business rules
- Document domain language

#### Architecture Decision Records (ADRs)
- Context and problem statement
- Decision and rationale
- Consequences
- Status (proposed, accepted, deprecated)

#### Coding Standards
- Language-specific conventions
- Project-specific patterns
- Quality requirements
- Review checklists

#### API Specifications
- Endpoint definitions
- Request/response schemas
- Authentication requirements
- Error codes

## Context Request Protocol

### When to Request Context

1. **Feature Development**: Need domain model and patterns
2. **Architecture Changes**: Require ADRs and design principles
3. **Code Review**: Check against coding standards
4. **API Design**: Reference existing API specs
5. **Security Implementation**: Follow security policies

### Request Structure

```xml
<CONTEXT_REQUEST reason="[Clear explanation of why context is needed]">
  <!-- Specific files -->
  <file path=".agents/context/path/to/file.md" />

  <!-- Entire directories -->
  <directory path=".agents/context/path/to/directory/" />

  <!-- Patterns or searches -->
  <pattern match=".agents/context/**/*authentication*.md" />
</CONTEXT_REQUEST>
```

### Response Handling

After receiving context:
1. **Confirm Receipt**: Acknowledge in Self-Diagnostic Report
2. **Validate Relevance**: Ensure context matches needs
3. **Apply Knowledge**: Use context to inform decisions
4. **Maintain Alignment**: Verify compliance throughout task

## Context Evolution

### Updating `.agents/context/`

As projects evolve, `.agents/context/` should be updated:
- **When**: After major decisions or learnings
- **How**: Through formal update proposals
- **Who**: Architecture team or designated owners
- **Process**: Review, approval, commit

### Proposal Format

```markdown
# .agents/context/ Update Proposal

## Motivation
[Why this update is needed]

## Changes
- Add: [New content]
- Modify: [Changed content]
- Remove: [Deprecated content]

## Impact
[How this affects existing work]

## Review
- Reviewer: [Name]
- Status: [Pending/Approved/Rejected]
```

## Best Practices

### For Project Setup
1. Create `.agents/context/` early in project lifecycle
2. Start with essential documents (domain model, ADRs)
3. Grow organically based on needs
4. Keep documentation current

### For Development
1. Always check `.agents/context/` before starting tasks
2. Question outdated or missing information
3. Propose updates when finding gaps
4. Reference `.agents/context/` in code comments

### For Maintenance
1. Regular reviews of `.agents/context/` content
2. Archive deprecated decisions
3. Keep documentation DRY (Don't Repeat Yourself)
4. Version control all changes

## Related Modules

- [Core Principles](./principles.md) - Full Traceability principle
- [SDM Protocol](../modes/sdm.md) - How context is used in development
- [Interaction Protocol](../protocols/interaction.md) - Status reporting requirements
