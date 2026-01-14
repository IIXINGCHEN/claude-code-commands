---
description: "简短的命令描述（一行）"
argument-hint: "[可选参数提示]"
version: "1.0.0"
tags: []
dependencies: []
output-type: "file"  # terminal|file|both
---

# {命令名称}: {完整标题}

## Overview

命令的详细说明，包括：
- 主要用途
- 使用场景
- 预期效果

## Input

### Required Arguments
- `arg1` - 参数说明

### Optional Arguments
- `--flag` - 可选标志说明

### Environment Requirements
- 必需的环境变量
- 必需的工具或依赖

## Process

### 1. Step One
详细描述第一步操作

### 2. Step Two
详细描述第二步操作

### 3. Step Three
详细描述第三步操作

## Output

### Output Format
输出的格式说明

### Output Location
文件输出路径：`.agents/{namespace}/{filename}.md`

### Output Structure
```markdown
# 输出文件的结构示例
## Section 1
## Section 2
```

## Examples

### Example 1: Basic Usage
```bash
/namespace:command arg1
```

**Expected Output:**
```
描述预期的输出
```

### Example 2: Advanced Usage
```bash
/namespace:command arg1 --flag value
```

**Expected Output:**
```
描述预期的输出
```

## Notes

### Prerequisites
- 前置条件1
- 前置条件2

### Best Practices
- 最佳实践1
- 最佳实践2

### Common Issues
- **问题1**: 描述和解决方案
- **问题2**: 描述和解决方案

## Related Commands

- `/namespace:other-command` - 相关命令说明
- `/other-namespace:command` - 相关命令说明

## Version History

- **1.0.0** (2024-01-12) - 初始版本
