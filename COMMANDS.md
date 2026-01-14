# Claude Code Commands 使用指南

> **版本 2.0** - 完全模块化的命名空间架构

## 概述

这是一个完全模块化的命令系统，所有命令按照功能领域组织到不同的命名空间中。每个命令都遵循统一的格式规范和文档标准。

### 命令调用格式

```bash
/namespace:command [arguments]
```

### 架构说明

详细的架构文档请参阅 [_meta/README.md](_meta/README.md)

---

## 🔄 命名空间索引

| 图标 | 命名空间 | 描述 | 命令数 |
|------|---------|------|--------|
| 🤖 | `axiom` | AxiomOS系统 - 高级领域架构认知引擎 | 4 |
| 🏗️ | `project` | 项目初始化、设置和分析 | 2 |
| 🔄 | `workflow` | 完整的开发工作流：规划、执行、报告 | 3 |
| ✅ | `validation` | 代码验证、审查和质量保证 | 6 |
| 🐛 | `bugfix` | 系统化的Bug分析和修复流程 | 2 |
| 📦 | `git` | Git版本控制和协作 | 3 |
| 📚 | `docs` | 自动生成各类项目文档 | 2 |
| 🔧 | `utils` | 各种辅助工具和实用功能 | 2 |

**总计**: 8个命名空间，24个命令

---

## 🤖 axiom - AxiomOS系统

> 高级领域架构认知引擎 - 完全模块化架构（27个模块，7大领域）

**AxiomOS v20.0** 已完全模块化，拆分为独立的功能模块。通过 `axiom` 命名空间可以访问整个系统。

### 🎯 快速访问

**查看系统概览:**
```bash
/axiom:view axiom/README.md    # 查看完整系统说明
```

**查看核心模块:**
```bash
/axiom:view config/system       # 系统配置与常量
/axiom:view foundation/principles  # 核心原则（8大原则）
/axiom:view modes/_overview     # 10种操作模式总览
/axiom:view modes/sdm           # 标准开发模式（6阶段）
/axiom:view cognitive/ultrathink   # 超级思考协议
```

### `/axiom:view [module-path]`
**查看特定模块的内容**

查看 AxiomOS 的任何模块。

- **参数**: `module-path` - 模块路径
- **输出**: 终端展示模块内容

**模块结构:**
- `config/` - 配置模块（3个：system, security, compliance）
- `foundation/` - 基础模块（3个：role, principles, context）
- `standards/` - 标准规范（2个：deliverable, artifact）
- `modes/` - 操作模式（11个：overview + 10种模式）
- `cognitive/` - 认知机制（2个：session, ultrathink）
- `protocols/` - 协议（2个：interaction, tools）

```bash
/axiom:view config/security
/axiom:view foundation/principles
/axiom:view modes/sdm
/axiom:view standards/deliverable
```

### `/axiom:activate [mode-name]`
**激活特定操作模式**

激活 AxiomOS 的10种操作模式之一。

- **参数**: `mode-name` - 模式名称
- **输出**: 终端确认

**可用模式:**
- `sdm` - 标准开发模式（6阶段质量门控）
- `sfam` - 监督全自动模式（单点审批）
- `micro-task` - 微任务模式（快速执行）
- `audit` - 审计优化模式（全面审查）
- `debug` - 调试模式（系统化修复）
- `review` - 代码审查模式
- `security` - 安全渗透模式
- `onboarding` - 项目启动模式

```bash
/axiom:activate sdm          # 激活标准开发模式
/axiom:activate debug        # 激活调试模式
/axiom:activate audit        # 激活审计模式
```

### `/axiom:status`
**查看系统状态**

显示 AxiomOS 当前状态和配置。

- **输出**: 系统状态报告（YAML格式）

```bash
/axiom:status
```

### `/axiom:load-all`
**加载完整系统**

加载完整的 AxiomOS v20.0 系统，包括所有27个模块。

- **输出**: 加载确认和状态

```bash
/axiom:load-all
```

### 📚 详细文档

完整的 AxiomOS 文档参见：
- **系统入口**: [axiom/README.md](axiom/README.md)
- **原始文件**: [v20.0-legacy.md](v20.0-legacy.md) （完整原文备份）

---

## 🏗️ project - 项目管理

> 项目初始化、设置和分析

### `/project:init [project-path]`
**安装依赖，启动开发服务器**

分析项目结构并生成初始化指南。

- **参数**: `project-path` - 项目路径（默认当前目录）
- **输出**: `.agents/init/{project-name}.md`

```bash
/project:init
/project:init ./my-project
```

### `/project:analyze [project-path]`
**分析项目结构和技术栈**

提供项目的高层次结构分析和技术栈识别。

- **参数**: `project-path` - 项目路径（默认当前目录）
- **输出**: 终端报告

```bash
/project:analyze
```

---

## 🔄 workflow - 工作流程

> 完整的开发工作流：规划、执行、报告

### `/workflow:prime`
**加载项目上下文和代码库理解**

首次接触项目时，快速理解项目结构、技术栈、架构模式。

- **输出**: 终端摘要报告

```bash
/workflow:prime
```

### `/workflow:plan [feature-name]`
**制定功能实施计划**

通过代码库分析制定全面的实施计划。

- **参数**: `feature-name` - 功能名称（kebab-case格式）
- **输出**: `.agents/plans/{feature-name}.md`

```bash
/workflow:plan add-user-authentication
/workflow:plan implement-search-api
```

### `/workflow:execute [plan-path]`
**执行实施计划**

按照计划文件逐步实现功能。

- **参数**: `plan-path` - 计划文件路径
- **输出**: 终端执行摘要

```bash
/workflow:execute .agents/plans/add-user-authentication.md
```

---

## ✅ validation - 验证审查

> 代码验证、审查和质量保证

### `/validation:validate [project-path]`
**进行全面验证：测试、lint、覆盖、前端构建**

执行项目健康检查，验证代码质量和功能。

- **参数**: `project-path` - 项目路径（默认当前目录）
- **输出**: `.agents/validation/{project-name}.md`

```bash
/validation:validate
/validation:validate ./frontend
```

### `/validation:code-review`
**对更改文件进行技术代码审查**

在提交前进行技术审查，发现潜在问题。

- **输出**: `.agents/code-reviews/{timestamp}.md`

```bash
/validation:code-review
```

### `/validation:code-review-pro`
**执行结构化代码审查（可选自动修复）**

包含全仓库和严格生产就绪检查的结构化审查。

- **输出**: `.agents/code-reviews/{timestamp}-pro.md`

```bash
/validation:code-review-pro --profile=strict
/validation:code-review-pro --scope=all --fix
```

### `/validation:code-review-fix [review-file] [scope]`
**修复代码审查中发现的问题**

逐个修复代码审查中发现的问题。

- **参数**:
  - `review-file` - 审查结果文件路径
  - `scope` - 修复范围（可选，如 critical-only）
- **输出**: 终端

```bash
/validation:code-review-fix .agents/code-reviews/review-001.md
/validation:code-review-fix .agents/code-reviews/review-001.md critical-only
```

### `/validation:execution-report`
**实现功能后生成报告**

记录实现过程中的经验教训。

- **输出**: `.agents/execution-reports/{feature-name}.md`

```bash
/validation:execution-report
```

### `/validation:system-review [plan-file] [execution-report-file]`
**分析流程改进的实施与计划**

审查计划与执行的一致性，改进流程。

- **参数**:
  - `plan-file` - 计划文件路径
  - `execution-report-file` - 执行报告路径
- **输出**: `.agents/system-reviews/{feature-name}-review.md`

```bash
/validation:system-review .agents/plans/feature.md .agents/execution-reports/feature.md
```

---

## 🐛 bugfix - Bug修复

> 系统化的Bug分析和修复流程

### `/bugfix:rca [github-issue-id]`
**为GitHub问题创建根因分析文档**

系统分析问题，找出根本原因，制定修复策略。

- **参数**: `github-issue-id` - GitHub问题编号
- **输出**: `docs/rca/issue-{issue-id}.md`
- **依赖**: GitHub CLI (`gh`)

```bash
/bugfix:rca 123
```

### `/bugfix:implement [github-issue-id]`
**基于RCA文档实施修复**

根据根因分析实现Bug修复。

- **参数**: `github-issue-id` - GitHub问题编号
- **输出**: 终端摘要
- **依赖**: `bugfix:rca`, GitHub CLI (`gh`)

```bash
/bugfix:implement 123
```

---

## 📦 git - Git操作

> Git版本控制和协作

### `/git:commit`
**创建规范化的Git提交**

创建带有相应标签（feat、fix、docs等）的原子提交。

- **输出**: 终端

```bash
/git:commit
```

### `/git:push [remote] [branch]`
**推送提交到远程仓库**

推送本地提交到远程仓库。

- **参数**:
  - `remote` - 远程仓库名称（默认 origin）
  - `branch` - 分支名称（默认当前分支）
- **输出**: 终端

```bash
/git:push
/git:push origin feature-branch
```

### `/git:pr [base-branch]`
**创建GitHub Pull Request**

为当前分支创建Pull Request。

- **参数**: `base-branch` - 目标分支（默认 main）
- **输出**: 终端（包含PR URL）
- **依赖**: GitHub CLI (`gh`)

```bash
/git:pr
/git:pr develop
```

---

## 📚 docs - 文档生成

> 自动生成各类项目文档

### `/docs:create-prd [output-filename]`
**从对话中生成产品需求文档**

基于讨论内容生成规范的PRD文档。

- **参数**: `output-filename` - 输出文件名（默认 PRD.md）
- **输出**: 指定文件名

```bash
/docs:create-prd
/docs:create-prd my-app-prd.md
```

### `/docs:compress-context [output-filename]`
**生成对话摘要用于上下文压缩**

为长对话创建详细的上下文摘要，便于后续继续工作。

- **参数**: `output-filename` - 输出文件名（默认 context-summary.md）
- **输出**: `.agents/context-summaries/{filename}`

```bash
/docs:compress-context
/docs:compress-context session-20240112.md
```

---

## 🔧 utils - 实用工具

> 各种辅助工具和实用功能

### `/utils:analyze-codebase [focus]`
**深度分析代码库结构和模式**

执行深度代码库分析，识别模式和依赖。

- **参数**: `focus` - 分析焦点（architecture|patterns|dependencies|all，默认 all）
- **输出**: 终端报告

```bash
/utils:analyze-codebase
/utils:analyze-codebase patterns
```

### `/utils:export-session [format]`
**导出当前会话信息**

导出会话信息用于文档和备份。

- **参数**: `format` - 导出格式（markdown|json，默认 markdown）
- **输出**: `.agents/utils/session-{timestamp}.{format}`

```bash
/utils:export-session
/utils:export-session json
```

---

## 📋 标准工作流程

### 新功能开发

```bash
1. /workflow:prime                    # 理解项目
2. /workflow:plan feature-name        # 创建计划
3. /workflow:execute plan-path        # 实现功能
4. /validation:validate               # 验证结果
5. /validation:code-review            # 代码审查
6. /validation:execution-report       # 生成报告
7. /validation:system-review          # 流程改进
8. /git:commit                        # 提交代码
9. /git:pr                            # 创建PR
```

### Bug修复流程

```bash
1. /bugfix:rca issue-id               # 根因分析
2. /bugfix:implement issue-id         # 实现修复
3. /validation:validate               # 验证修复
4. /git:commit                        # 提交代码
```

### 新项目初始化

```bash
1. /project:init                      # 生成初始化指南
2. 按照指南设置项目
3. /workflow:prime                    # 理解项目结构
4. /validation:validate               # 验证设置
```

---

## 📁 输出文件结构

```
.agents/
├── init/                    # 项目初始化指南 (/project:init)
├── plans/                   # 功能实施计划 (/workflow:plan)
├── validation/              # 验证报告 (/validation:validate)
├── code-reviews/            # 代码审查报告 (/validation:code-review*)
├── execution-reports/       # 执行报告 (/validation:execution-report)
├── system-reviews/          # 系统审查报告 (/validation:system-review)
├── context-summaries/       # 对话摘要 (/docs:compress-context)
└── utils/                   # 工具输出 (/utils:*)

docs/
└── rca/                     # 根因分析文档 (/bugfix:rca)
```

---

## ⚙️ 配置和扩展

### 添加新命令

1. 选择合适的命名空间或创建新的
2. 使用模板创建命令文件：`_meta/templates/command-template.md`
3. 在命名空间配置中注册命令
4. 更新此索引文档

### 创建新命名空间

1. 创建命名空间目录
2. 添加 `_namespace.yaml` 配置文件
3. 在 `_meta/namespaces.yaml` 中注册
4. 添加命令文件

详细说明请参阅 [_meta/README.md](_meta/README.md)

---

## 📚 相关资源

- [架构说明](_meta/README.md) - 详细的架构文档
- [命令规范](_meta/command-schema.yaml) - 命令格式规范
- [命令模板](_meta/templates/command-template.md) - 新命令模板
- [AxiomOS核心指令](v20.0.md) - 高级领域架构认知引擎

---

## 📝 版本历史

- **v2.0.0** (2024-01-12) - 完全模块化重组，统一命名空间架构
- **v1.0.0** - 初始版本

---

**注意事项**

- 在 bash 环境下使用**相对路径**
- 某些命令需要 GitHub CLI (`gh`) 工具
- 命令之间可能存在依赖关系，请按推荐顺序执行
