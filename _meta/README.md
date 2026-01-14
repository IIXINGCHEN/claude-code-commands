# Claude Code Commands - 架构说明

## 概述

这是一个完全模块化的命令系统，所有命令按照功能领域组织到不同的命名空间中。

## 目录结构

```
.claude/commands/
├── _meta/                      # 元数据和配置
│   ├── namespaces.yaml        # 命名空间注册表
│   ├── command-schema.yaml    # 命令格式规范
│   ├── README.md              # 本文件
│   ├── templates/             # 命令模板
│   └── scripts/               # 工具脚本
│
├── COMMANDS.md                 # 命令索引（自动生成）
├── v20.0.md                    # AxiomOS核心指令
│
├── project/                    # 项目管理命名空间
├── workflow/                   # 工作流命名空间
├── validation/                 # 验证命名空间
├── bugfix/                     # Bug修复命名空间
├── git/                        # Git操作命名空间
├── docs/                       # 文档生成命名空间
└── utils/                      # 实用工具命名空间
```

## 命名空间

每个命名空间是一个独立的目录，包含：

- `_namespace.yaml` - 命名空间配置文件
- `*.md` - 命令文件

### 命名空间列表

| 命名空间 | 图标 | 描述 |
|---------|------|------|
| `project` | 🏗️ | 项目初始化、设置和分析 |
| `workflow` | 🔄 | 完整的开发工作流：规划、执行、报告 |
| `validation` | ✅ | 代码验证、审查和质量保证 |
| `bugfix` | 🐛 | 系统化的Bug分析和修复流程 |
| `git` | 📦 | Git版本控制和协作 |
| `docs` | 📚 | 自动生成各类项目文档 |
| `utils` | 🔧 | 各种辅助工具和实用功能 |

## 命令调用方式

标准格式：`/namespace:command [arguments]`

示例：
```bash
/workflow:prime                 # 加载项目上下文
/workflow:plan feature-name     # 规划功能
/validation:code-review         # 代码审查
/bugfix:rca 123                 # 根因分析
/git:commit                     # 创建提交
```

## 配置文件

### `namespaces.yaml`

命名空间注册表，定义所有可用的命名空间及其命令。

### `command-schema.yaml`

命令文件的格式规范，定义：
- Frontmatter 字段要求
- 文档结构建议
- 命名规范

### `_namespace.yaml`

每个命名空间的配置文件，定义：
- 命名空间元数据
- 命令列表和参数
- 依赖关系
- 配置选项

## 添加新命令

### 1. 确定命名空间

选择合适的现有命名空间，或创建新的命名空间。

### 2. 创建命令文件

使用模板创建新命令文件：

```bash
cp _meta/templates/command-template.md namespace/command-name.md
```

### 3. 编辑命令内容

按照规范编辑命令文件，包括：
- Frontmatter 元数据
- 命令文档各个章节

### 4. 注册命令

在命名空间的 `_namespace.yaml` 中注册新命令。

### 5. 更新索引

重新生成 `COMMANDS.md` 索引文件。

## 创建新命名空间

### 1. 创建目录

```bash
mkdir namespace-name
```

### 2. 创建配置文件

创建 `namespace-name/_namespace.yaml`：

```yaml
namespace: namespace-name
version: "1.0.0"
name: "命名空间显示名称"
description: "命名空间描述"
icon: "📦"

commands:
  command-name:
    file: "command-name.md"
    description: "命令描述"
    arguments:
      - name: arg-name
        type: string
        required: true
        description: "参数描述"
```

### 3. 注册命名空间

在 `_meta/namespaces.yaml` 中注册新命名空间。

### 4. 添加命令

按照"添加新命令"流程添加命令文件。

## 最佳实践

### 命令设计

1. **单一职责** - 每个命令只做一件事
2. **清晰输入** - 参数明确，易于理解
3. **可预测输出** - 输出格式统一，位置固定
4. **完整文档** - 包含所有必要的说明和示例

### 命名规范

1. **命名空间** - 使用小写单数名词，简洁明了
2. **命令名** - 使用动词或动词短语，用连字符分隔
3. **文件名** - 与命令名一致，使用 `.md` 扩展名

### 文档规范

1. **Frontmatter** - 必须包含 `description` 字段
2. **Overview** - 清晰说明命令用途和场景
3. **Examples** - 提供至少一个实际示例
4. **Notes** - 说明前置条件和注意事项

## 版本控制

命名空间和命令都应该有版本号，使用语义化版本：

- `MAJOR.MINOR.PATCH`
- MAJOR: 不兼容的 API 变更
- MINOR: 向后兼容的功能新增
- PATCH: 向后兼容的问题修正

## 维护指南

### 定期检查

- 检查命令文档是否完整
- 验证示例是否仍然有效
- 更新过时的说明

### 重构建议

- 当命名空间命令数超过 10 个时，考虑拆分
- 当命令职责不清时，考虑重组
- 当依赖关系复杂时，考虑简化

### 弃用流程

1. 在文档中标记为 Deprecated
2. 提供替代命令说明
3. 保留至少一个大版本周期
4. 完全移除并更新索引

## 相关资源

- [命令索引](../COMMANDS.md)
- [AxiomOS核心指令](../v20.0.md)
- [命令模板](.templates/command-template.md)
