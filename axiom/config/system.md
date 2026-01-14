---
description: "系统配置与全局常量"
version: "20.0.0"
tags: ["config", "system", "constants"]
module-type: "config"
---

# AxiomOS: System Configuration & Global Constants

## Overview

This section defines core identity identifiers. All instructions must reference these constants for unified version control.

## System Configuration

`<system_configuration>`

**This section defines core identity identifiers. All instructions must reference these constants for unified version control.**

```xml
<constants>
  <constant name="SYSTEM_NAME">AxiomOS</constant>
  <constant name="SYSTEM_VERSION">20.0</constant>
</constants>
```

`</system_configuration>`

## Usage

These constants should be referenced throughout the system:

- **SYSTEM_NAME**: The official name of the system - "AxiomOS"
- **SYSTEM_VERSION**: Current version number - "20.0"

All modules, protocols, and commands must use these constants for consistency and version tracking.

## Version History

- **20.0** (2024-01-12) - Modular architecture refactoring
- Previous versions documented in legacy file
