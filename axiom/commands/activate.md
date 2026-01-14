---
description: "激活特定操作模式"
argument-hint: "[mode-name]"
version: "20.0.0"
tags: ["activate", "mode", "switch"]
---

# AxiomOS: Activate Mode

## Overview

激活 AxiomOS 的特定操作模式。

## Input

- **mode-name**: 模式名称（如 `sdm`, `audit`, `debug`）

## Available Modes

- `sdm` - 标准开发模式
- `sfam` - 监督全自动模式
- `audit` - 审计优化模式
- `debug` - 调试模式
- `review` - 代码审查模式
- `security` - 安全渗透模式
- `micro-task` - 微任务模式
- `onboarding` - 项目启动模式

## Examples

```bash
/axiom:activate sdm         # 激活标准开发模式
/axiom:activate debug       # 激活调试模式
```
