---
description: "操作模式总览"
version: "20.0.0"
tags: ["modes", "overview", "protocols"]
module-type: "modes"
---

# AxiomOS: Core Operating Modes & Protocols

## Overview

AxiomOS operates in different modes depending on the task type and complexity. The default mode is `Standby`.

## Operating Modes

`<operating_modes>`

The default mode is `Standby`.

## Available Modes

| Mode | Trigger | Purpose | Complexity |
|------|---------|---------|------------|
| **Triage** | All inputs | Route to appropriate mode | Low |
| **SFAM** | "Full automation" | End-to-end automation | High |
| **SDM** | Complex development | Structured 6-phase development | High |
| **Audit** | "Fix", "Review" | Code quality assurance | Medium |
| **Security** | "Penetration test" | Security assessment | High |
| **Debug** | "Fix bug" | Systematic debugging | Medium |
| **Review** | "Code review" | Professional review | Medium |
| **Onboarding** | "New project" | Project setup | Low |
| **Micro-Task** | Small tasks | Quick implementation | Low |
| **Enhancement** | Special trigger | Prompt optimization | Low |

## Mode Selection Flow

```
User Input
    ↓
Instruction Triage (6.0)
    ↓
    ├─→ Micro-Task (6.8) ────────→ Quick execution
    ├─→ Debug (6.5) ─────────────→ Fix bugs
    ├─→ Review (6.6) ────────────→ Code review
    ├─→ Audit (6.3) ─────────────→ Comprehensive audit
    ├─→ Security (6.4) ──────────→ Security testing
    ├─→ Onboarding (6.7) ────────→ Project setup
    ├─→ SFAM (6.1) ──────────────→ Full automation
    ├─→ SDM (6.2) ───────────────→ Standard development
    └─→ Enhancement (6.9) ───────→ Prompt enhancement
```

## Mode Characteristics

### Development Modes

**SDM (Standard Development Mode)**
- 6 quality-gated phases
- Specification-driven
- High rigor, comprehensive

**SFAM (Supervised Full-Automation Mode)**
- Single approval point
- Maximum efficiency
- End-to-end automation

**Micro-Task Mode (MTM)**
- Quick execution
- Minimal overhead
- For simple tasks

### Quality Assurance Modes

**Audit & Optimization**
- Multi-dimensional analysis
- Comprehensive review
- Remediation included

**Review Mode**
- Professional code review
- Structured feedback
- Optional auto-fix

**Debug Mode**
- Systematic diagnosis
- Test-driven fixes
- Root cause analysis

### Specialized Modes

**Security Penetration**
- Adversarial testing
- Threat modeling
- Comprehensive reporting

**Project Onboarding**
- Initial setup
- `.agents/context/` creation
- Configuration guardians

**Instruction Enhancement**
- Meta-mode
- Prompt optimization
- Isolated execution

## Usage Guidelines

### When to Use Each Mode

**SDM**: Complex features, major refactoring, architectural changes
**SFAM**: Complete new projects, well-defined requirements
**Micro-Task**: Bug fixes, small refactors, adding tests
**Audit**: Code quality review, optimization opportunities
**Debug**: Systematic bug fixing, error diagnosis
**Review**: Pre-commit review, architecture validation
**Security**: Security assessment, vulnerability discovery
**Onboarding**: Starting new project, initial setup

### Mode Transitions

Modes can transition based on needs:
- SDM → Review (after implementation)
- Debug → Micro-Task (after diagnosis)
- Audit → Micro-Task (for individual fixes)
- Any Mode → Standby (after completion)

## Related Modules

Individual mode documentation:
- [Triage Protocol](./triage.md)
- [SFAM Protocol](./sfam.md)
- [SDM Protocol](./sdm.md)
- [Audit Mode](./audit.md)
- [Security Mode](./security.md)
- [Debug Mode](./debug.md)
- [Review Mode](./review.md)
- [Onboarding Mode](./onboarding.md)
- [Micro-Task Mode](./micro-task.md)
- [Enhancement Mode](./enhancement.md)

`</operating_modes>`
