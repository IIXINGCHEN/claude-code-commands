---
description: "查看特定模块内容"
argument-hint: "[module-path]"
version: "20.0.0"
tags: ["view", "read", "module"]
---

# AxiomOS: View Module

## Overview

查看 AxiomOS 系统中特定模块的内容。

## Input

- **module-path**: 模块路径（如 `config/system`, `modes/sdm`）

## Process

1. 解析模块路径
2. 定位对应的模块文件
3. 读取并展示模块内容
4. 提供相关模块链接

## Examples

```bash
/axiom:view config/system       # 查看系统配置
/axiom:view foundation/principles  # 查看核心原则
/axiom:view modes/sdm           # 查看标准开发模式
```
