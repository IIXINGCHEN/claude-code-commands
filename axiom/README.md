# AxiomOS v20.0 - Superior Domain Architecture Cognitive Engine

> **完全模块化架构** | **26个独立模块** | **7大功能领域**

## 系统概述

AxiomOS 是一个高级领域架构认知引擎，为复杂的软件开发任务提供结构化、规范化的工作流程和质量保证。通过模块化设计，每个功能域都可以独立访问和使用。

---

## 📋 核心组件

### 🔧 配置模块 (`config/`)

系统核心配置和安全协议。

| 模块 | 说明 |
|------|------|
| **system.md** | 系统配置与全局常量（SYSTEM_NAME, SYSTEM_VERSION） |
| **security.md** | 安全内核与边界保护（最高优先级协议） |
| **compliance.md** | 合规与安全协议（版权尊重、有害内容避免） |

**查看配置:**
```bash
/axiom:view config/system
/axiom:view config/security
/axiom:view config/compliance
```

---

### 🏛️ 基础模块 (`foundation/`)

系统身份、原则和上下文管理。

| 模块 | 说明 |
|------|------|
| **role.md** | 系统角色与使命定义（高级架构专家） |
| **principles.md** | 8大核心原则 + 4种思维模型 |
| **context.md** | 全局上下文核心 (`.agents/context/` 协议) |

**核心原则:**
1. 领域驱动优先
2. 规范驱动开发
3. 战略对齐
4. 主动守护
5. 全程可追溯
6. 零信任安全
7. 质量优先思维
8. 平台无关性

**查看基础:**
```bash
/axiom:view foundation/principles
/axiom:view foundation/context
```

---

### 📏 标准规范 (`standards/`)

生产级交付标准和制品协议。

| 模块 | 说明 |
|------|------|
| **deliverable.md** | 11项生产级交付标准（A-K） |
| **artifact.md** | 基于交付物的协议（代码、文档、视觉） |

**11项标准:**
- A. 领域对齐 | B. 零信任安全 | C. 可靠性与韧性
- D. 可观测性 | E. 可测试性 (>95%) | F. 性能与效率
- G. 可维护性 | H. 精确性与完整性 | I. 遵循现有模式
- J. 保持简单和范围 | K. 跨平台兼容性

**查看标准:**
```bash
/axiom:view standards/deliverable
```

---

### 🎮 操作模式 (`modes/`)

10种专业化工作模式。

| 模式 | 文件 | 触发器 | 用途 |
|------|------|---------|------|
| **分流** | triage.md | 所有输入 | 路由到合适模式 |
| **全自动** | sfam.md | "全自动化" | 端到端自动化 |
| **标准开发** | sdm.md | 复杂开发 | 6阶段质量门控 |
| **审计** | audit.md | "审计", "优化" | 代码质量保证 |
| **安全** | security.md | "渗透测试" | 安全评估 |
| **调试** | debug.md | "修复bug" | 系统化调试 |
| **审查** | review.md | "代码审查" | 专业审查 |
| **启动** | onboarding.md | "新项目" | 项目设置 |
| **微任务** | micro-task.md | 小任务 | 快速执行 |
| **增强** | enhancement.md | 特殊触发 | 提示优化 |

**SDM 6阶段流程:**
```
Scope → Architect → Atomize → Approve → Automate → Assess
```

**激活模式:**
```bash
/axiom:activate sdm        # 标准开发模式
/axiom:activate audit      # 审计模式
/axiom:activate debug      # 调试模式
```

**查看模式:**
```bash
/axiom:view modes/_overview    # 模式总览
/axiom:view modes/sdm         # 查看SDM详情
```

---

### 🧠 认知机制 (`cognitive/`)

高级认知和思考协议。

| 模块 | 说明 |
|------|------|
| **session.md** | 会话状态管理协议（序列化/反序列化） |
| **ultrathink.md** | 超级思考协议（4阶段深度分析） |

**Ultrathink 4阶段:**
1. 系统思维 - 全局影响分析
2. 辩证与创新 - 多方案对比
3. 批判思维 - 压力测试
4. 决策制定 - 最终选择

**查看认知:**
```bash
/axiom:view cognitive/ultrathink
```

---

### 📡 协议模块 (`protocols/`)

交互和工具集成协议。

| 模块 | 说明 |
|------|------|
| **interaction.md** | 交互与自诊断协议（Self-Diagnostic Report） |
| **tools.md** | 工具集成与外部数据协议 |

**自诊断报告包含:**
- Report ID 与时间戳
- 当前操作模式和阶段
- 任务状态与分解
- 上下文同步状态
- 合规检查

**查看协议:**
```bash
/axiom:view protocols/interaction
```

---

## 🚀 快速开始

### 查看特定模块

```bash
/axiom:view config/system          # 查看系统配置
/axiom:view foundation/principles  # 查看核心原则
/axiom:view modes/sdm              # 查看标准开发模式
/axiom:view cognitive/ultrathink   # 查看超级思考协议
```

### 激活操作模式

```bash
/axiom:activate sdm              # 激活标准开发模式
/axiom:activate audit            # 激活审计模式
/axiom:activate debug            # 激活调试模式
/axiom:activate micro-task       # 激活微任务模式
```

### 系统管理

```bash
/axiom:status                    # 查看系统状态
/axiom:load-all                  # 加载完整系统
```

---

## 📁 完整模块树

```
axiom/
├── README.md                          # 本文件 - 系统入口
├── _namespace.yaml                    # 命名空间配置
│
├── config/                            # 🔧 配置模块（3个文件）
│   ├── system.md
│   ├── security.md
│   └── compliance.md
│
├── foundation/                        # 🏛️ 基础模块（3个文件）
│   ├── role.md
│   ├── principles.md
│   └── context.md
│
├── standards/                         # 📏 标准规范（2个文件）
│   ├── deliverable.md
│   └── artifact.md
│
├── modes/                             # 🎮 操作模式（11个文件）
│   ├── _overview.md
│   ├── triage.md
│   ├── sfam.md
│   ├── sdm.md
│   ├── audit.md
│   ├── security.md
│   ├── debug.md
│   ├── review.md
│   ├── onboarding.md
│   ├── micro-task.md
│   └── enhancement.md
│
├── cognitive/                         # 🧠 认知机制（2个文件）
│   ├── session.md
│   └── ultrathink.md
│
├── protocols/                         # 📡 协议模块（2个文件）
│   ├── interaction.md
│   └── tools.md
│
└── commands/                          # 🚀 命令接口（4个文件）
    ├── view.md
    ├── activate.md
    ├── status.md
    └── load-all.md
```

**总计:** 27个文件，7大功能领域

---

## 🔄 标准工作流程

### 复杂功能开发（使用SDM）

```bash
1. /axiom:activate sdm                        # 激活标准开发模式
2. [Phase 1: Scope] 明确需求和边界
3. [Phase 2: Architect] 设计技术方案
4. [Phase 3: Atomize] 分解原子任务
5. [Phase 4: Approve] ⚠️ 获取批准（质量门）
6. [Phase 5: Automate] 测试驱动实现
7. [Phase 6: Assess] 验证与知识沉淀
```

### 快速任务（使用Micro-Task）

```bash
1. /axiom:activate micro-task                 # 激活微任务模式
2. [Scope & Approve] 确认任务
3. [Automate] 快速实现
4. [Deliver] 交付成果
```

### Bug修复（使用Debug）

```bash
1. /axiom:activate debug                      # 激活调试模式
2. 错误重现
3. 根因分析
4. 解决方案提议
5. 测试驱动修复
6. 交付与验证
```

---

## 📊 模块依赖关系

```
config (基础配置)
  ↓
foundation (核心原则)
  ↓
standards (交付标准)
  ↓
modes (操作模式) ←→ cognitive (认知机制)
  ↓
protocols (交互协议)
```

---

## 🎯 使用建议

### 首次使用

1. 阅读 `foundation/principles.md` 了解核心理念
2. 查看 `modes/_overview.md` 理解各种模式
3. 根据任务类型选择合适模式

### 日常开发

- **简单任务**: 使用 Micro-Task 模式
- **复杂功能**: 使用 SDM 模式
- **代码质量**: 使用 Audit 或 Review 模式
- **问题修复**: 使用 Debug 模式

### 特殊场景

- **新项目**: 使用 Onboarding 模式
- **安全审计**: 使用 Security 模式
- **完整项目**: 使用 SFAM 模式
- **深度思考**: 触发 Ultrathink 协议

---

## 📝 版本信息

- **系统名称**: AxiomOS
- **版本**: 20.0
- **架构**: 模块化命名空间
- **模块数**: 27个
- **拆分日期**: 2024-01-12
- **原文件**: v20.0-legacy.md

---

## 🔗 相关文档

- [命令系统总览](../COMMANDS.md) - 所有命令索引
- [命名空间架构](../_meta/README.md) - 架构说明
- [原始v20.0文件](../v20.0-legacy.md) - 完整原文（备份）

---

## 💡 核心理念

> "Quality is not an act, it is a habit." - Aristotle

AxiomOS 致力于通过系统化的流程和严格的质量标准，将软件开发提升到艺术的高度。每个模块都是这个理念的具体体现。

**核心价值观:**
- 🎯 **质量优先** - 永不妥协的质量标准
- 🔒 **安全第一** - 零信任架构设计
- 📊 **可追溯性** - 完整的决策链条
- 🌍 **平台无关** - 真正的跨平台支持
- 🧠 **深度思考** - 系统化的思维模型

---

**AxiomOS v20.0** - Transforming Intent into Excellence
