# Claude Code Commands

模块化的 Claude Code 命令系统，提供项目管理、工作流程、代码验证、Bug修复等完整开发工具链。

## 安装

命令系统需要安装到 Claude Code 可以识别的目录。Claude Code 会按以下顺序搜索命令文件:

1. 项目级目录: `<项目根目录>/.agents/commands/`
2. 全局配置目录: `~/.claude/commands/` (Windows: `%USERPROFILE%\.claude\commands\`)

### 全局安装（推荐）

全局安装后，所有项目都可以使用这些命令。

Windows:
```bash
# 克隆或下载本仓库后，在仓库目录执行
xcopy /E /I /Y . "%USERPROFILE%\.claude\commands"
```

macOS/Linux:
```bash
# 克隆或下载本仓库后，在仓库目录执行
mkdir -p ~/.claude/commands
cp -r . ~/.claude/commands/
```

### 项目级安装

项目级安装只在当前项目生效，适合项目特定的自定义命令。

```bash
# 在项目根目录执行
mkdir -p .agents/commands
cp -r /path/to/this/repo/* .agents/commands/
```

### 验证安装

安装完成后，在 Claude Code 中运行:
```bash
/COMMANDS
```

如果看到完整的命令列表，说明安装成功。

### 更新

更新到最新版本:

```bash
# 在本仓库目录执行 git pull 后
# Windows:
xcopy /E /I /Y . "%USERPROFILE%\.claude\commands"

# macOS/Linux:
cp -r . ~/.claude/commands/
```

### 卸载

删除命令文件:

Windows:
```bash
rmdir /S /Q "%USERPROFILE%\.claude\commands"
```

macOS/Linux:
```bash
rm -rf ~/.claude/commands
```

### 注意事项

- 安装目录必须包含完整的目录结构，不能只复制单个命令文件
- 项目级命令优先级高于全局命令，会覆盖同名全局命令
- 修改命令文件后，Claude Code 会自动重新加载，无需重启
- 建议定期更新到最新版本以获得新功能和修复

### 目录结构

安装后的目录结构:
```
~/.claude/commands/          # 或 .agents/commands/
├── axiom/                   # AxiomOS 架构认知引擎
├── bugfix/                  # Bug 修复流程
├── docs/                    # 文档生成
├── git/                     # Git 操作
├── project/                 # 项目管理
├── utils/                   # 工具集
├── validation/              # 代码验证
├── workflow/                # 工作流程
├── _meta/                   # 元数据和架构文档
├── COMMANDS.md             # 命令索引
└── README.md               # 本文档
```

### 故障排查

**问题: 运行 /COMMANDS 提示命令不存在**
- 检查安装路径是否正确
- 确认使用的是 `~/.claude/commands/` 或 `.agents/commands/`
- 验证目录结构完整，包含所有子目录

**问题: 命令列表不完整**
- 检查是否只复制了部分文件
- 重新执行完整的安装命令
- 确认没有权限问题（Windows 可能需要管理员权限）

**问题: 修改命令后不生效**
- Claude Code 应该自动重新加载
- 如果未生效，尝试重启 Claude Code
- 检查修改的文件路径是否正确

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
