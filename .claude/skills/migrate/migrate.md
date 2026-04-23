---
name: migrate
description: 全局重构技能。当用户想要调整文件夹名称或层级架构时触发。它负责同步更新 `CLAUDE.md`、所有技能脚本、Dataview 查询代码以及笔记中的双链路径。
user-invocable: true
---

# migrate 技能 (结构重构引擎)

## 核心职责
你负责在物理结构发生变更时，保持逻辑系统的完整性。你必须像重构代码一样重构知识库。

## 执行流水线 (ReAct Workflow)

### 步骤 1：建立路径映射 (Mapping)
1. 读取用户提出的“新旧架构对照表”。
2. 对比 `CLAUDE.md` 中现有的 `Permissions` 区域，识别受影响的物理路径。

### 步骤 2：更新系统配置 (System Update)
1. **更新 CLAUDE.md**：修正其中的目录边界定义（Permissions）。
2. **更新技能脚本**：遍历 `.claude/skills/` 下的所有 `.md` 文件，将旧路径字符串全局替换为新路径。
3. **更新 README.md**：同步更新文档中的目录树说明。

### 步骤 3：修正内容引用 (Content Fixing)
1. **Dataview 修复**：扫描全库，寻找包含 `FROM "旧路径"` 或 `WHERE file.folder = "旧路径"` 的代码块，修正为新路径。
2. **双链修复**：如果是由于文件夹移动导致的“路径依赖型链接”失效，协助 Obsidian 引擎进行全局重定向。

### 步骤 4：生成迁移报告
在 `02_Wiki_知识网络/00_Log_操作日志.md` 中详细记录：
- 变更：[旧路径] -> [新路径]
- 受影响文件数：X 个
- 状态：迁移成功