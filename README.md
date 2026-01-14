# Claude Code Commands

模块化的 Claude Code 命令系统，提供项目管理、工作流程、代码验证、Bug修复等完整开发工具链。

## 快速开始

查看所有可用命令:
```bash
/COMMANDS
```

查看完整文档: [COMMANDS.md](COMMANDS.md)

## 核心命名空间

- `project` - 项目初始化和分析
- `workflow` - 开发工作流程(规划、执行、报告)
- `validation` - 代码验证和质量审查
- `bugfix` - Bug分析和修复流程
- `git` - Git版本控制操作
- `docs` - 文档自动生成
- `utils` - 实用工具集合
- `axiom` - AxiomOS高级架构认知引擎

## 使用方式

命令格式: `/namespace:command [arguments]`

示例:
```bash
/workflow:prime                 # 理解项目结构
/workflow:plan feature-name     # 规划功能实施
/validation:code-review         # 执行代码审查
/git:commit                     # 创建规范提交
```

## 标准开发流程

新功能开发:
```bash
/workflow:prime                    # 1. 理解项目
/workflow:plan feature-name        # 2. 创建计划
/workflow:execute plan-path        # 3. 实现功能
/validation:validate               # 4. 验证结果
/validation:code-review            # 5. 代码审查
/git:commit                        # 6. 提交代码
```

Bug修复:
```bash
/bugfix:rca issue-id               # 1. 根因分析
/bugfix:implement issue-id         # 2. 实现修复
/validation:validate               # 3. 验证修复
/git:commit                        # 4. 提交代码
```

## 项目统计

- 8个命名空间
- 24个命令
- 27个AxiomOS模块

## 文档

- [完整命令索引](COMMANDS.md) - 所有命令的详细说明
- [架构文档](_meta/README.md) - 系统架构和扩展指南
- [AxiomOS系统](axiom/README.md) - 高级领域架构认知引擎

## 许可证

MIT License
