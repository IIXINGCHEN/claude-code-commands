# Claude Code Commands 使用指南

## 概述

`.claude/commands` 目录包含预定义的命令模板，用于规范化 AI Agent 的工作流程。这些命令覆盖了从项目初始化、需求分析、代码规划到实现、验证、审查的完整开发周期。

## 命令分类索引

| 分类 | 命令 | 用途 |
|------|------|------|
| **规划与执行** | `/core_piv_loop:prime` | 加载项目上下文和代码库理解 |
| | `/core_piv_loop:plan-feature` | 通过代码库分析制定全面的实施计划 |
| | `/core_piv_loop:execute` | 逐步执行实施计划 |
| **验证** | `/validation:validate` | 进行全面验证：测试、lint、覆盖、前端构建 |
| | `/validation:code-review` | 对更改文件进行技术代码审查 |
| | `/validation:code-review-fix` | 修复代码审查中发现的问题 |
| | `/validation:execution-report` | 实现功能后生成报告 |
| | `/validation:system-review` | 分析流程改进的实施与计划 |
| **Bug 修复** | `/github_bug_fix:rca` | 为 GitHub 问题创建根因分析文档 |
| | `/github_bug_fix:implement-fix` | 基于 RCA 文档实施修复 |
| **其他** | `/commit` | 创建带有相应标签（feat、fix、docs 等）的原子提交 |
| | `/init-project` | 安装依赖，启动开发服务器 |
| | `/create-prd` | 从对话中生成产品需求文档 |

---

## 规划与执行

### /core_piv_loop:prime

**描述：** 加载项目上下文和代码库理解

**用途：** 首次接触项目时，快速理解项目结构、技术栈、架构模式

**输出：** 终端摘要报告

**执行示例：**
```bash
/core_piv_loop:prime
```

**报告内容：**
- 项目概述（目的、应用类型）
- 架构（结构、组织模式）
- 技术栈（语言、框架、库）
- 核心原则（代码风格、文档标准）
- 当前状态（分支、最近变更）

---

### /core_piv_loop:plan-feature [feature-name]

**描述：** 通过代码库分析制定全面的实施计划

**用途：** 为新功能创建详细、可执行的实施计划

**参数：**
- `feature-name`: 功能名称（短横线命名）

**输出：** `.agents/plans/{kebab-case-feature-name}.md`

**执行示例：**
```bash
/core_piv_loop:plan-feature add-user-authentication
/core_piv_loop:plan-feature implement-search-api
```

**计划内容：**
- 功能描述和用户故事
- 代码库上下文引用（文件:行号）
- 需要创建的新文件列表
- 遵循的代码模式
- 分阶段实现计划
- 原子化步骤任务
- 测试策略
- 验证命令
- 验收标准

**工作流程：**
```
/core_piv_loop:plan-feature <功能> → 生成计划
/core_piv_loop:execute <计划文件> → 执行实现
```

---

### /core_piv_loop:execute [path-to-plan]

**描述：** 逐步执行实施计划

**用途：** 按照计划文件逐步实现功能

**参数：**
- `path-to-plan`: 计划文件路径

**输出：** 终端执行摘要

**执行示例：**
```bash
/core_piv_loop:execute .agents/plans/add-user-authentication.md
```

**执行步骤：**
1. 阅读并理解计划
2. 按顺序执行任务
3. 实现测试策略
4. 运行验证命令
5. 最终确认

---

## 验证

### /validation:validate [project-path]

**描述：** 进行全面验证：测试、lint、覆盖、前端构建

**用途：** 执行项目健康检查，验证代码质量和功能

**参数：**
- `project-path`: 项目路径（默认当前目录）

**输出：** `.agents/validation/{kebab-case-project-name}.md`

**执行示例：**
```bash
/validation:validate
/validation:validate ./frontend
```

**验证项目：**
1. 语法和 linting
2. 类型检查
3. 单元测试
4. 集成测试
5. 构建验证
6. 安全检查

---

### /validation:code-review

**描述：** 对更改文件进行技术代码审查

**用途：** 在提交前进行技术审查，发现潜在问题

**输出：** `.agents/code-reviews/{name}.md`

**执行示例：**
```bash
/validation:code-review
```

**审查内容：**
- 逻辑错误
- 安全问题
- 性能问题
- 代码质量
- 符合代码库标准

**输出格式：**
```yaml
severity: critical|high|medium|low
file: path/to/file.py
line: 42
issue: 问题描述
detail: 详细解释
suggestion: 修复建议
```

---

### /validation:code-review-fix [code-review-file] [scope]

**描述：** 修复代码审查中发现的问题

**用途：** 逐个修复代码审查中发现的问题

**参数：**
- `code-review-file`: 审查结果文件
- `scope`: 修复范围（可选，如 critical-only）

**执行示例：**
```bash
/validation:code-review-fix .agents/code-reviews/review-001.md
/validation:code-review-fix .agents/code-reviews/review-001.md critical-only
```

**执行步骤：**
1. 阅读审查文件
2. 逐个修复问题
3. 创建并运行测试
4. 重新验证

---

### /validation:execution-report

**描述：** 实现功能后生成报告

**用途：** 记录实现过程中的经验教训

**输出：** `.agents/execution-reports/{feature-name}.md`

**执行示例：**
```bash
/validation:execution-report
```

**报告内容：**
- 元信息（文件变更统计）
- 验证结果
- 顺利之处
- 遇到的挑战
- 与计划的偏差
- 跳过的项目
- 改进建议

---

### /validation:system-review [plan-file] [execution-report-file]

**描述：** 分析流程改进的实施与计划

**用途：** 审查计划与执行的一致性，改进流程

**参数：**
- `plan-file`: 计划文件路径
- `execution-report-file`: 执行报告路径

**输出：** `.agents/system-reviews/{feature-name}-review.md`

**执行示例：**
```bash
/validation:system-review .agents/plans/feature.md .agents/execution-reports/feature.md
```

**审查重点：**
- 计划依从性
- 偏差分类（好/坏）
- 根因追溯
- 流程改进建议

---

## Bug 修复

### /github_bug_fix:rca [github-issue-id]

**描述：** 为 GitHub 问题创建根因分析文档

**用途：** 系统分析问题，找出根本原因，制定修复策略

**参数：**
- `github-issue-id`: GitHub 问题编号

**输出：** `docs/rca/issue-{issue-id}.md`

**执行示例：**
```bash
/github_bug_fix:rca 123
```

**RCA 文档内容：**
- 问题摘要
- 问题描述
- 复现步骤
- 根因分析
- 影响评估
- 修复方案
- 测试要求

---

### /github_bug_fix:implement-fix [github-issue-id]

**描述：** 基于 RCA 文档实施修复

**用途：** 根据根因分析实现 Bug 修复

**参数：**
- `github-issue-id`: GitHub 问题编号

**输出：** 终端摘要

**执行示例：**
```bash
/github_bug_fix:implement-fix 123
```

**执行步骤：**
1. 阅读 RCA 文档
2. 验证问题存在
3. 实现修复
4. 添加测试
5. 运行验证
6. 验证修复

---

## 其他

### /commit

**描述：** 创建带有相应标签（feat、fix、docs 等）的原子提交

**用途：** 创建规范化的 Git 提交

**执行示例：**
```bash
/commit
```

**执行步骤：**
1. 显示未提交变更
2. 添加所有变更
3. 创建提交信息
4. 添加合适的标签

---

### /init-project [project-path]

**描述：** 安装依赖，启动开发服务器

**用途：** 分析项目结构，生成初始化指南并设置开发环境

**参数：**
- `project-path`: 项目路径（默认当前目录）

**输出：** `.agents/init/{kebab-case-project-name}.md`

**执行示例：**
```bash
/init-project
/init-project ./my-project
```

**输出内容：**
- 项目技术栈识别
- 依赖安装命令
- 环境配置说明
- 启动开发服务器命令
- 常用命令（测试、构建、lint）

---

### /create-prd [output-filename]

**描述：** 从对话中生成产品需求文档

**用途：** 基于讨论内容生成规范的 PRD 文档

**参数：**
- `output-filename`: 输出文件名（默认 `PRD.md`）

**输出：** 指定文件名

**执行示例：**
```bash
/create-prd
/create-prd my-app-prd.md
```

**PRD 包含章节：**
1. 执行摘要
2. 使命
3. 目标用户
4. MVP 范围
5. 用户故事
6. 核心架构
7. 工具/功能
8. 技术栈
9. 安全与配置
10. API 规范
11. 成功标准
12. 实现阶段
13. 未来考虑
14. 风险与缓解
15. 附录

---

### /compress-context [output-filename]

**描述：** 生成对话摘要用于上下文压缩

**用途：** 为长对话创建详细的上下文摘要，便于后续继续工作

**参数：**
- `output-filename`: 输出文件名（默认 `context-summary.md`）

**输出：** `.agents/context-summaries/[output-filename]`

**执行示例：**
```bash
/compress-context
/compress-context session-20240111.md
```

**摘要内容：**
- 上下文（如何继续对话）
- 对话历史
- 当前工作状态
- 技术概念
- 相关文件
- 待完成任务

---

## 标准工作流程

### 新功能开发

```
1. /core_piv_loop:prime              → 理解项目
2. /core_piv_loop:plan-feature <名>  → 创建计划
3. /core_piv_loop:execute <计划>     → 实现功能
4. /validation:validate              → 验证结果
5. /validation:code-review           → 代码审查
6. /validation:execution-report      → 生成报告
7. /validation:system-review         → 流程改进
8. /commit                           → 提交代码
```

### Bug 修复

```
1. /github_bug_fix:rca <issue-id>    → 根因分析
2. /github_bug_fix:implement-fix <id> → 实现修复
3. /validation:validate               → 验证修复
4. /commit                            → 提交代码
```

### 新项目初始化

```
1. /init-project                      → 生成初始化指南
2. 按照指南设置项目
3. /validation:validate               → 验证设置
```

---

## 输出文件结构

| 目录 | 用途 | 生成命令 |
|------|------|----------|
| `.agents/init/` | 项目初始化指南 | `/init-project` |
| `.agents/plans/` | 功能实施计划 | `/core_piv_loop:plan-feature` |
| `.agents/validation/` | 验证报告 | `/validation:validate` |
| `.agents/code-reviews/` | 代码审查报告 | `/validation:code-review` |
| `.agents/execution-reports/` | 执行报告 | `/validation:execution-report` |
| `.agents/context-summaries/` | 对话摘要 | `/compress-context` |
| `.agents/system-reviews/` | 系统审查报告 | `/validation:system-review` |
| `docs/rca/` | 根因分析文档 | `/github_bug_fix:rca` |

---

## 注意事项

### 路径使用

在 bash 环境下使用**相对路径**，避免 Windows 路径格式：

- 错误：`mkdir -p E:\project\.agents\plans`
- 正确：`mkdir -p .agents/plans`

### 前置条件

- `/github_bug_fix:rca` 需要 GitHub CLI 安装和认证
- `/github_bug_fix:implement-fix` 需要先运行 `/rca` 生成 RCA 文档
- `/core_piv_loop:execute` 需要先运行 `/plan-feature` 生成计划

### 执行顺序

1. 先创建输出目录
2. 按依赖顺序执行命令
3. 验证通过后再提交
